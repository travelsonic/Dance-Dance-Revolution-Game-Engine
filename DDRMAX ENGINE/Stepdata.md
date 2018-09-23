# Stepdata
### Storage in Filedata.bin
In Playstation2 mixes, the game's stepdata is stored in one giant chunk.

At the very beginning of this chunk is an array of offsets.  The offset values are relative to the start
of the file.  For example, if the first SSQ file was 314 bytes into the file, the first offset in the 
array would be 0000013A (viewed as 3A010000 due to endiness, of course).

The overall length of this array is equal to 4 * the number of songs in the game.  For example, in
DDRMAX2 -DanceDanceRevolution 7thMIX- for the Playstation2, there are 74 songs.  Ergo, the array of
offsets would be (4 * 74), or 296 bytes, long.  The first offset in the array, as a result, will have
a value equal to the array length.


```
```
