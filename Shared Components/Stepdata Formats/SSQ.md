# Data Structures
There are several data structures that are used to hold / process SSQ data:

### struct sq_header
```
struct sq_header{
    unsigned int size;
    unsigned short kind;
    unsigned short division;
};
```

### struct sq_standard
```
struct sq_standard{
    sq_header header;
    unsigned int num;
    signed int body[1];
};
```

### struct sq_indicator
```
struct sq_indicator{
    unsigned char class;
    unsigned char icode;
};
```

### sq_footstep_header
```
struct sq_footstep_header{
    struct{
        unsigned int panel:4;
        unsigned int player:4;
    };
    unsigned char seq_kind;
};
```

# Note:
This section is more or less gonna be a brainfart filled thing full of observations from trying to look 
at SSQ files myself, and information derived from a (author unknown) SSQ guide that was linked 
to on DDR Freak a long time ago.  Perhaps I will upload it if nobody has an issue with my doing 
so, so that it is preserved.

### Stepdata Chunks:
```
Chunk Data Members:
Size (in bytes):                           Discription: 
4 bytes/32 bits                            Size of the chunk in bytes
2 bytes/16 bits                            Chunk type
2 bytes/16 bits                            Stepchart Type?
4 bytes/32 bits                            Number of beat entries
(Number of beat entries * 4) bytes         Beat / Measure Entries
(Number of beat entries) bytes             Step values
```
### Song Start / Stop Data
The second chunk in a song's SSQ file contains data pertaining to the
beginning, and end of of the song playback.

Based off of the game_w structure, and how it stores the data from this
chunk of the stepfile, at least so far, I've mapped the data values out
as follows:
<pre>
Name/Discription:                Data Size:   Notes:
Chunk Size                       4 bytes
Chunk Type                       2 bytes      
UNKNOWN                          2 bytes      TODO: Find out what this does
Number of Entries(?)             4 bytes      TODO: Verify purpose of data
begin_beat_count                 4 bytes      TODO: Verify if these values ae in the correct order, or if the value labeled 
back_trans_start_music_count?    4 bytes            back_trans_start_music_count is really just a repeat of begin_beat_count
go_beat_counter                  4 bytes      When cur_p_counter == go_beat_counter, start reading the steps?
finish_beat_count                4 bytes
end_beat_count                   4 bytes
UNKNOWN                          UNSURE?      Looks like 6 2-byte values, TODO: see where this is loaded into memory
</pre>

### Beat / Measure Entries:
Only the measures, and beats, where arrows actually appear are stored
in a song's stepdata chunk(s). This dramatically cuts down on how much 
data needs to be stored, and read by the game in comparison to if the
stepchart file stored values for every single measure and beat in a song.

Here is an example of what beat/measure data looks like in a hex editor.
This exerpt comes from Burning Heat! (3 Option Mix)'s single light chart.
```
81 00 00 00            // Number of beat entries
00 50 00 00            // A step at measure 5 beat 0
00 58 00 00          
00 60 00 00 
00 68 00 00 
00 6C 00 00 
00 70 00 00 
00 78 00 00 
00 80 00 00 
00 88 00 00 
00 8C 00 00 
00 94 00 00 
00 A0 00 00 
00 A4 00 00 
00 AC 00 00 
00 B4 00 00 
00 C0 00 00 
00 C4 00 00 
00 CC 00 00 
00 D4 00 00 
00 DC 00 00 
00 E4 00 00 
00 EC 00 00 
00 F4 00 00 
00 F8 00 00 
00 00 01 00 
00 04 01 00 
00 08 01 00 
00 10 01 00 
00 14 01 00 
00 1C 01 00 
00 20 01 00 
00 24 01 00
```
As you can see, the measure number is followed by the beat number.  

The beat takes up only one nibble of space, having a value range of
0 <= X <= 15 (0x00 <= X <= 0x0F).

The measure number takes up anywhere from a nibble (when the measure 
number is < 16), to a full byte's worth of space (when the measure 
number is >= 16).

Due to the endianess of the data, though, when you look for the measure
and beat information, say for measure 18 beat 4 for instance, the data
will appear not as "01 24," but as 24 01.

At least one, perhaps both, of the bytes sandwiching the measure/beat 
values are used for flags, or other information on how to interpret the 
step data at that beat / measure.  For example, it APPEARS as if arrows 
that are not quantized as 4th (red), 8th (blue), or 16th (yellow) notes, 
will have a value of 170 (0xAA) preceding the measure / beat value for a 
particular entry.

I am not ENTIRELY sure about why the measure & beat information are 
stores in the middle 2 bytes of each dword though, as opposed to that
data being stored in the first or last 2 bytes of each dword.  MAYBE 
I am missing something - it DOES look like there could be a byte of
padding between the number of entries, and the start of the actual
entry data, which would (in combination with the endianess of the
data) explain a bit.  Definitely gonna keep investigating this.

It also appears that the game engine does have a lot of flexibility with 
regards to the beat/measure data, and how close you can place one arrow to
another.  I do not mean with regards to allowing more than just 1/4, 1/8, and
1/16 notes, but more so how far outside those bounds, and how close to another 
arrow you can go before things get odd.

### Step Values
Following the array of beat entries, is an array of bytes.  These are
individual step values, with one byte corresponding to each beat entry.

Individual arrow values are powers of 2:
```
Left  = 1   (0x01)
Down  = 2   (0x02)
Up    = 4   (0x04)
Right = 8   (0x08)
```
In order to get values representing combinations of arrows, all you have to do
is add arrow values together.  For example, to get a left + right jump, you simply 
add 1 + 8 together to get a value of 9. 

Interestingly, if you hex edit values while in Edit Mode, the values for each
arrow direction differ slightly.
```
Up    = 1   (0x01)
Down  = 4   (0x04)
Right = 8   (0x08)
Left  = 2   (0x02)
```

For each byte value, the leftmost nibble is used for steps that appear
on the player 2 side, while the rightmost nibble is used for steps that
appear on the player 1 side.  This holds true regardless of if you are
looking at official step data, or looking at edit data.
