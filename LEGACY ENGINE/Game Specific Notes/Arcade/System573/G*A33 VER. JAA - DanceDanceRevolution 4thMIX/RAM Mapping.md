Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information physically within 
the game's flash memory, and the logical address will refer to where the information resides from the perspective of the 
Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

In this game, the difference between the physical, and logical addresses, is 0x80000000.

<pre>
Physical Address(es):       Logical Address(es):        Description:                         Size (in bytes):
0x000E1038 -                0x800E1038 -                Global g_game_w Structure  
             0x000E1038                  0x800E1038     g_game_w.state                       2 bytes
             0x000E103A                  0x800E103A     g_game_w.genre                       2 bytes
             0x000E103C                  0x800E103C     g_game_w.mip                         4 bytes
             0x000E103D                  0x800E103D     g_game_w.start_chip                  1 byte
             0x000E103E                  0x800E103E     g_game_w.extra_chip                  1 byte
             0x000E103F                  0x800E103F     g_game_w.use_chip                    1 byte
             0x000E1040                  0x800E1040     g_game_w.lost_chip                   1 byte
</pre>
