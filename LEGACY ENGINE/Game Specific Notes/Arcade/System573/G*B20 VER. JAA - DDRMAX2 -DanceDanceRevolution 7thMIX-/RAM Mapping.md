Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information physically within 
the game's flash memory, and the logical address will refer to where the information resides from the perspective of the 
Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

In this game, the difference between the physical, and logical addresses, is 0x80000000.

<pre>
Physical Address(es):      Logical Address(es):       Description:                                                Size:
0x000E68D8 -               0x800E68D8 -               Global g_game_w Structure (g_game_w g_game_w)  
             0x000E68D8                 0x800E68D8    g_game_w.state                                              2 bytes
0x001A3B28 - 0x001A7778    0x801A3B28 - 0x801A7778    minfo_tab - song metadata table (music_info minfo_tab[143]) 15,444 bytes
</pre>

