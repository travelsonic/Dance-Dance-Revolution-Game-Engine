# Note:
This is more or less gonna be a brainfart filled thing full of observations from trying to look 
at SSQ files myself, and information derived from a (author unknown) SSQ guide that was linked 
to on DDR Freak a long time ago.

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
### Beat / Measure Entries:
Only the measures, and beats, where arrows actually appear are stored
in a song's stepdata chunk(s). This dramatically cuts down on how much 
data needs to be stored, and read by the game in comparison to if the
stepchart file stored values for every single measure and beat in a song.

Here is an example of what beat/measure data looks like in a hex editor.
This exerpt comes from Burning Heat! (3 Option Mix)'s single light chart.
```
81 00 00 00            // Number of beat entries
00 50 00 00 
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


### Step Values
Following the array of beat entries, is an array of bytes.  These are
individual step values, with one byte corresponding to each beat entry.

Individual arrow values are powers of 2, where:
```
 Left = 1 
 Down = 2
   Up = 4
Right = 8
```
In order to get values representing combinations of arrows, all you have to do
is add arrow values together.  For example, to get a left + right jump, you simply 
add 1 + 8 together to get a value of 9.
