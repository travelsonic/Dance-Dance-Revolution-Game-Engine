Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, Ghidra, and PS2DIS.

The difference between physical and logical addresses is 0xFFF80

<pre>
Physical Address(es):       Logical Address(es):        Description: 
0x000C0260 - 0x000C03A8     0x001C01E0 - 0x001C0328     Function: 
                                                        LZ77 Decompression Routine
</pre>
