# Filedata Table
**Note:** The information about how this data is structured was discovered by Zenius-I-Vanisher & Gamehacking.org member root760. 

The game engine needs a way to locate chunks in the filedata.bin containing music, graphics, stepdata, and background videos.  This is accomplished through a table stored in the game executable.

Each entry in this table is a structure that takes up 8 bytes, and contains 3 fields:
```
Field:            Size (in bytes):   Description:
file_position         2              The index of the entry in the filedata table.
address               3              The address within filedata.bin where the data is located.
                                     The address is packed to fit into 3 bytes.  To get the full,
                                     uncompressed address, multiply the value here by 0x800, or
                                     2048 in decimal.
size                  3              The size of the data chunk.
                                     The size is packed to fit into 3 bytes.  To get the full,
                                     uncompressed file size, multiply the value here by 0x800, or
                                     2048 in decimal.
```
For some reason, Dancing Stage Fusion's table is separated in a few places by indistinguishable chunks of data.
