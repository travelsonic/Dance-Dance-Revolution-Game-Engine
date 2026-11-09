Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information physically within 
the game's flash memory, and the logical address will refer to where the information resides from the perspective of the 
Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

In this game, the difference between the physical, and logical addresses, is 0x80000000.

<pre>
Physical Address(es):       Logical Address(es):        Description:                         Size (in bytes):
0x000E0F08 -                0x800E0F08 -                Global g_game_w Structure  
             0x000E0F08                  0x800E0F08     g_game_w.state                       2 bytes
             0x000E0F0A                  0x800E0F0A     g_game_w.genre                       2 bytes
             0x000E0F0C                  0x800E0F0C     g_game_w.mip                         4 bytes
             0x000E0F0D                  0x800E0F0D     g_game_w.start_chip                  1 byte
             0x000E0F0E                  0x800E0F0E     g_game_w.extra_chip                  1 byte
             0x000E0F0F                  0x800E0F0F     g_game_w.use_chip                    1 byte
             0x000E0F10                  0x800E0F10     g_game_w.lost_chip                   1 byte
</pre>
