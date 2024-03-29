# The SSQ Format
This document will attempt to document the SSQ format, which is, and has remained, the dominant
(though not the only?) way Konami's Dance Dance Revolution stepdata is stored.

SOME of the information here is derived from an old DDR Ultramix oriented SSQ hacking guide that was 
linked to on DDR Freak a long time ago.  Perhaps I will upload it if nobody has an issue with my doing 
so, so that it is preserved.  

## Basics:
SSQ files are a sequence of chunks, each utilizing a variety of data structures to store information
about a song's step data, as well as the actual step information for specific step charts.

Based on data structure names found in leftover debugging data, and observing other sequences in game file data, 
I'm tempted to say that the "SSQ" format is really specialized form of a more general sequence format meant to handle 
many kinds of sequences in the DDR game series.  At this point, however, this is speculation; I won't say anything definitive 
without doing more research first, as a lot is needed before such things are "proven" IMO.

## Data Structures:
The following data structures are used for organizing the data within a SSQ file.
### struct sq_header
#### Definition:
```
struct sq_header{
    unsigned int size;
    unsigned short kind;
    unsigned short division;
};
```
#### What Is It:
The sq_header data structure, as the name implies, serve as a basic chunk header.  Every 
chunk in a SSQ file has one of these headers.
#### Data Members: 
```
NAME:            SIZE:      WHAT:
size:            4 bytes    The size of the chunk in bytes.  
kind:            2 bytes    A byte identifying the kind of chunk, or what data resides within the chunk.
division:        2 bytes    Not entirely sure what this data member is for. MORE RESEARCH IS NEEDED.
```
### struct sq_standard
#### Definition:
```
struct sq_standard{
    sq_header header;
    unsigned int num;
    signed int body[1];
};
```
#### What Is It:
The sq_standard data structure represents an entire SSQ file chunk.
#### Data Members: 
```
NAME:            SIZE:      WHAT:
header           8 bytes    The SSQ chunk's header.
num              4 bytes    NOT ENTIRE SURE, most likely the number of elements in 
                            an array that follows this data member.
body             4 bytes    The main body of data that the chunk is meant to hold - whether it be timing data, step information,
                            or whatnot.
                            A single element array is used to provide support for variable-length data members. Prior to the C99 
                            version of the C standard, this "struct hack" was a necessity if you wanted a variable-length data 
                            member due to the lack (at the time) of flexible data member support. In later versions of the format, 
                            this was probably replaced with a proper flexible data members, however, more research is needed to
                            know for sure.       
```
Use of the aforementioned struct hack what allows (allowed?) each SSQ chunk to have the same general layout, but also hold completely different pieces of data in their respective body data members.

The following data structures I've not yet documented - I will do this documentation when able.
### struct sq_indicator
#### Definition:
```
struct sq_indicator{
    unsigned char class;
    unsigned char icode;
};
```
### sq_footstep_header
#### Definition:
```
struct sq_footstep_header{
    struct{
        unsigned int panel:4;
        unsigned int player:4;
    };
    unsigned char seq_kind;
};
```

# Example of a SSQ File's Data Layout:  
## Burning Heat! (3 Option Mix), DDRMAX2 -DanceDanceRevolution 7thMIX- CS:
### CHUNK 1:
```
Offset(s):                   Data Member:                    Value (hex (dec)):                Notes:
0x0000 - 0x0043              sq_standard             
         0x0000              sq_standard.header.size         0x00000044 (68 decimal)
         0x0004              sq_standard.header.kind         0x0001     (1 decimal)
         0x0006              sq_standard.header.division     0x0096     (150 decimal)
         0x0008              sq_standard.num                 0x00000007 (7 decimal)
         0x000C - 0x0043     sq_standard.body                At this point, struct hack applied
                                                             0x00000000 (0 decimal)
                             herewe_count                    0x00001000 (4,096 decimal)
                                                             0x00009000 (36,864 decimal)
                                                             0x00009000 (36,864 decimal)
                                                             0x0003DC00 (252,928 decimal)
                                                             0x0003DC00 (252,928 decimal)
                             check_timing_data[0]            0x00000001 (1 decimal)
                             check_timing_data[1]            0x000000D9 (217 decimal)
                             check_timing_data[2]            0x000007A1 (1,953 decimal)
                             check_timing_data[3]            0x000007D7 (2,007 decimal)
                             check_timing_data[4]            0x00003487 (13,447 decimal)
                             check_timing_data[5]            0x000034BD (13,501 decimal)
                             check_timing_data[6]            0x0000377B (14,203 decimal)
```
### CHUNK 2:
```
0x0044 - 0x0029              sq_standard             
         0x0000              sq_standard.header.size         0x00000030 (48 decimal)
         0x0004              sq_standard.header.kind         0x0002     (2 decimal)
         0x0006              sq_standard.header.division     0x001      (1 decimal)
         0x0008              sq_standard.num                 0x00000006 (6 decimal)
         0x000C - 0x0029     sq_standard.body                At this point, struct hack applied
                  0x000C     beat_counts[0]                  0x00000000 (0 decimal)
                  0x0010     beat_counts[1]                  0x00001000 (4,096 decimal)
                  0x0014     beat_counts[2]                  0x00009000 (36,864 decimal)
                  0x0018     beat_counts[3]                  0x00009000 (36,864 decimal)
                  0x001C     beat_counts[4]                  0x0003DC00 (252,928 decimal)
                  0x0020     beat_counts[5]                  0x0003DC00 (252,928 decimal)
                  0x0024     beat_counts[6]                  0x00041C00 (269,312 decimal)
                  0x0028     music_counts[0]                 0x00000002 (2 decimal)
                  0x002C     music_counts[1]                 0x000000DA (218 decimal)
                  0x0030     music_counts[2]                 0x000007A2 (1,954 decimal)
                  0x0034     music_counts[3]                 0x000007D8 (2,008 decimal)
                  0x0038     music_counts[4]                 0x00003488 (13,448 decimal)
                  0x003C     music_counts[5]                 0x000034BE (13,502 decimal)
                  0x0040     music_counts[6]                 0x00003820 (14,368 decimal)
         
```













------------------------------------------------------------------------------------------------------------------
# OLD UNSORTED INFORMATION (to be truncated)
# Note:
This section is more or less a brainfart filled thing full of observations from trying to look 
at SSQ files myself, and information derived from a (author unknown) SSQ guide that was linked 
to on DDR Freak a long time ago.  Perhaps I will upload it if nobody has an issue with my doing 
so, so that it is preserved.  

Hopefully I will get this stuff organized sooner, rather than later.
# Data Structures:
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
