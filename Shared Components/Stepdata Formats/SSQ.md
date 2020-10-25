# Note:
This is more or less gonna be a brainfart filled thing full of observations from trying to look 
at SSQ files myself, and information derived from a (author unknown) SSQ guide that was linked 
to on DDR Freak a long time ago.

### Stepdata Chunks
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
### Beat / Measure Entries
