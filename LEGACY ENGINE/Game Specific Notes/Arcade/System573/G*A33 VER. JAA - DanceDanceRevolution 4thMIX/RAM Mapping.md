Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information physically within 
the game's flash memory, and the logical address will refer to where the information resides from the perspective of the 
Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

In this game, the difference between the physical, and logical addresses, is 0x80000000.

<pre>
Physical Address(es):      Logical Address(es):     Description:                                        Size:
0x0016C978 - 0x0016E260    0x8016C978 - 0x8016E260  minfo_tab (music_info minfo_tab[45])                6,380 bytes
0x000E1038 -               0x800E1038 -             Global g_game_w Structure (g_game_w g_game_w)  
             0x000E1038                 0x800E1038  g_game_w.state                                      2 bytes
             0x000E103A                 0x800E103A  g_game_w.genre                                      2 bytes
             0x000E103C                 0x800E103C  g_game_w.mip                                        4 bytes
             0x000E103D                 0x800E103D  g_game_w.start_chip                                 1 byte
             0x000E103E                 0x800E103E  g_game_w.extra_chip                                 1 byte
             0x000E103F                 0x800E103F  g_game_w.use_chip                                   1 byte
             0x000E1040                 0x800E1040  g_game_w.lost_chip                                  1 byte
             0x800E1060                 0x800E1060
             0x800E1068                 0x800E1068
             0x000E1088                 0x800E1088  g_game_w.player[0].stage_evaluation.value_ct[0]     4 bytes
             0x000E108C                 0x800E108C  g_game_w.player[0].stage_evaluation.value_ct[1]     4 bytes
             0x000E1090                 0x800E1090  g_game_w.player[0].stage_evaluation.value_ct[2]     4 bytes
             0x000E1094                 0x800E1094  g_game_w.player[0].stage_evaluation.value_ct[3]     4 bytes
             0x000E1098                 0x800E1098  g_game_w.player[0].stage_evaluation.value_ct[4]     4 bytes
             0x000E109C                 0x800E109C   
             0x000E10A0                 0x800E10A0  
             0x000E10A4                 0x800E10A4  g_game_w.player[0].stage_evaluation.max_combo_ct    4 bytes   
             0x000E10A8                 0x800E10A8  g_game_w.player[0].stage_evaluation.dance_level     4 bytes
             0x000E227C                 0x800E227C  Total steps in the step sequence                    4 bytes
             0x000EB1AC                 0x800EB1AC  Total steps in the step sequence (repeat)           4 bytes
             0x00290050                 0x80290050  Total steps in the step sequence (repeat)           4 bytes
</pre>
