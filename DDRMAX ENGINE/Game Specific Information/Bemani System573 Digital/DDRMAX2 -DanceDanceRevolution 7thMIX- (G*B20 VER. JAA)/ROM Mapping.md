Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and  
the logical address will refer to where the information resides from the perspective of the Bemani System573, an emulator that supports the Bemani System573, and many reverse engineering tools like IDA Pro, and GHidra.

The game's executatble is located in GAME.DAT.  The offset for the game's executable within GAME.DAT is 0x1AE0.

In this game, the difference between the physical, and logical addresses, is 0x8000F800.

<pre>
Physical Address(es):       Logical Address(es):        Description:   
0x00005EC8 - 0x00005EF0     0x800156C8 - 0x800156F0     DP Multipliers
             0x00005EC8                  0x800156C8     D.P Multiplier For Perfects                | A value of 2
             0x00005ECC                  0x800156CC     D.P Multiplier For Greats                  | A value of 1
             0x00005ED0                  0x800156D0     D.P Multiplier For Goods                   | A value of 0
             0x00005ED4                  0x800156D4     D.P Multiplier For Boos                    | A value of -4
             0x00005ED8                  0x800156D8     D.P Multiplier For Misses                  | A value of -8
             0x00005EDC                  0x800156DC     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x00005EE0                  0x800156E0     D.P Multiplier for the TOTAL_STEPS count   | A value of 2 
             0x00005EE4                  0x800156E4     D.P Multiplier for the TOTAL_FREEZ count   | A value of 6
             0x00005EE8                  0x800156E8     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x00005EEC                  0x800156EC     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x00005EF0                  0x800156F0     D.P Multiplier For OKs                     | A value of 6
</pre>
