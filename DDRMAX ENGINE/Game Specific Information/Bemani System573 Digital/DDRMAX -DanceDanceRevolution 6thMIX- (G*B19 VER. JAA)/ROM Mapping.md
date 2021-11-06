Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and  
the logical address will refer to where the information resides from the perspective of the Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

The game's executable is located in GAME.DAT.  The offset for the game's executable within GAME.DAT is 0x1A80.

In this game, the difference between the physical, and logical addresses, is 0x8000F800.

<pre>
Physical Address(es):       Logical Address(es):        Description:   
0x00005D88 - 0x00005DAC     0x80015588 - 0x800155AC     DP Multipliers
             0x00005D88                  0x80015588     D.P Multiplier For Perfects                | A value of 2
             0x00005D8C                  0x8001558C     D.P Multiplier For Greats                  | A value of 1
             0x00005D90                  0x80015590     D.P Multiplier For Goods                   | A value of 0
             0x00005D94                  0x80015594     D.P Multiplier For Boos                    | A value of -4
             0x00005D98                  0x80015598     D.P Multiplier For Misses                  | A value of -8
             0x00005D9C                  0x8001559C     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x00005DA0                  0x800155A0     D.P Multiplier for the TOTAL_STEPS count   | A value of 2 
             0x00005DA4                  0x800155A4     D.P Multiplier for the TOTAL_FREEZ count   | A value of 6
             0x00005DA8                  0x800155A8     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x00005DAC                  0x800155AC     D.P Multiplier For OKs                     | A value of 6
0x00006520 - 0x00006590     0x80015D20 - 0x80015D90     Text strings for the censored words list
             0x00006520                  0x80015D20     "AIDS" 
             0x00006528                  0x80015D28     "ANAL" 
             0x00006530                  0x80015D30     "BUSU" 
             0x00006538                  0x80015D38     "CHON" 
             0x00006540                  0x80015D40     "COCK"
             0x00006548                  0x80015D48     "ETTA"
             0x00006550                  0x80015D50     "EATA"
             0x00006558                  0x80015D58     "FUCK"
             0x00006560                  0x80015D60     "OSHI"
             0x00006568                  0x80015D68     "ROUA"
             0x00006570                  0x80015D70     "TYON"
             0x00006578                  0x80015D78     "YOTU"
             0x00006580                  0x80015D80     "    "
             0x00006588                  0x80015D88     "FERA"
             0x00006590                  0x80015D90     "CUNT"
             
             
</pre>
