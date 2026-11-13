Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information physically within 
the game's flash memory, and the logical address will refer to where the information resides from the perspective of the 
Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

In this game, the difference between the physical, and logical addresses, is 0x80000000.

<pre>
Physical Address(es):      Logical Address(es):       Description:                                                          Size:
0x000DAC98 -               0x800DAC98 -               g_game_w - global game work structure (g_game_w g_game_w)  
             0x000DAC98                 0x800DAC98    g_game_w.state                                                            2 bytes
	           0x000DAC9A                 0x800DAC9A    g_game_w.genre                                                            2 bytes
	           0x000DAC9C                 0x800DAC9C    g_game_w.mip                                                              4 bytes
	           0x000DACA0                 0x800DACA0    g_game_w.start_chip                                                       1 byte
	           0x000DACA1                 0x800DACA1    g_game_w.extra_chip                                                       1 byte
	           0x000DACA2                 0x800DACA2    g_game_w.use_chip                                                         1 byte
	           0x000DACA3                 0x800DACA3    g_game_w.lost_chip                                                        1 byte
	           0x000DACA4                 0x800DACA4    g_game_w.stage                                                            2 bytes
	           0x000DACA6                 0x800DACA6    g_game_w.next_stage                                                       2 bytes
	           0x000DACA8                 0x800DACA8    g_game_w.failed                                                           2 bytes
	           0x000DACAA                 0x800DACAA    g_game_w.level                                                            2 bytes
0x00197BE8 - 0x00199C60    0x80197BE8 - 0x80199C60    minfo_tab - global song metadata table (music_info minfo_tab[77])     8,316 bytes 
             0x00197BE8                  0x80197BE    minfo_tab entry for "20, November"                                      108 bytes
</pre>

