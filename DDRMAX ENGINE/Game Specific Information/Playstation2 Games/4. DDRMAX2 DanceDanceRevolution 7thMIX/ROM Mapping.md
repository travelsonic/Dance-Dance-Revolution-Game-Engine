Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, or a Playstation2 emulator.

In this game, the difference between the physical, and logical addresses, is 0xFFF80

```
Physical Address(es):       Logical Address(es):        Description:  
0x00160AC0 - 0x00163540     0x00260A40 - 0x002634C0     Song Metadata Structures
             0x00160AC0                  0x00260A40     Metadata Structure For Long Train Runnin'
             0x00160B48                  0x00260AC8     Metadata Structure For Maximum Overdrive
             0x00160BD0                  0x00260B50     Metadata Structure For Waka Laka
             0x00160C58                  0x00260BD8     Metadata Structure For Baby Love Me
             0x00160CE0                  0x00260C60     Metadata Structure For D2R
             0x00160D68                  0x00260CE8     Metadata Structure For Destiny
             0x00160DF0                  0x00260D70     Metadata Structure For Living In America
             0x00160E78                  0x00260DF8     Metadata Structure For Sweet Sweet ♥ Magic
             0x00160F00                  0x00260E80     Metadata Structure For Ever Snow
             0x00160E88                  0x00260E08     Metadata Structure For AM-3P (303 BASS MIX)
             0x00161010                  0x00260F90     Metadata Structure For The Reflex
             0x00161098                  0x00261018     Metadata Structure For So Fabulous So Fierce (Freak Out!)
             0x00161120                  0x002610A0     Metadata Structure For Drifting Away
             0x001611A8                  0x00261128     Metadata Structure For Stay
             0x00161230                  0x002611B0     Metadata Structure For Secret Rendez-vous
             0x001612B8                  0x00261238     Metadata Structure For Little Boy (Boy Oh Boy Mix)
             0x00161340                  0x002612C0     Metadata Structure For Rain of Sorrow
             0x001613C8                  0x00261348     Metadata Structure For Maxx Unlimited
             0x00161450                  0x002613D0     Metadata Structure For Dive To The Night
             0x001614D8                  0x00261458     Metadata Structure For Tsugaru
             0x00161560                  0x002614E0     Metadata Structure For BRE∀K DOWN!
             0x001615E8                  0x00261568     Metadata Structure For Burning Heat! (3 Option Mix)
             0x00161670                  0x002615F0     Metadata Structure For Nothing Gonna Stop
             0x001616F8                  0x00261678     Metadata Structure For Fantasy
             0x00161780                  0x00261700     Metadata Structure For i feel ...
             0x00161808                  0x00261788     Metadata Structure For CANDY ♥ 
             0x00161890                  0x00261810     Metadata Structure For Spin the Disc
             0x00161918                  0x00261898     Metadata Structure For Trance De Janeiro
             0x001619A0                  0x00261920     Metadata Structure For Look At Us
             0x00161A28                  0x002619A8     Metadata Structure For The Whistle Song (Blow My Whistle Bitch)
             0x00161AB0                  0x00261A30     Metadata Structure For 革命 (Kakumei)
             0x00161B38                  0x00261AB8     Metadata Structure For AFRONOVA (From Nonstop Megamix)
             0x00161BC0                  0x00261B40     Metadata Structure For AM-3P (AM EAST MIX)
             0x00161C48                  0x00261BC8     Metadata Structure For Brillant 2U (K.O.G G3 Mix)
             0x00161CD0                  0x00261C50     Metadata Structure For B4U (B4 ZA BEAT MIX)
             0x00161D58                  0x00261CD8     Metadata Structure For DROP OUT (From Nonstop Megamix)
             0x00161DE0                  0x00261D60     Metadata Structure For Dynamite Rave (B4 ZA BEAT MIX)
             0x00161E68                  0x00261DE8     Metadata Structure For Hysteria 2001
             0x00161EF0                  0x00261E70     Metadata Structure For 祭 JAPAN (From Nonstop Megamix)
             0x00161F78                  0x00261EF8     Metadata Structure For SEXY PLANET (From Nonstop Megamix)
             0x00162000                  0x00261F80     Metadata Structure For Super Star (From Nonstop Megamix)
             0x00162088                  0x00262008     Metadata Structure For Still In My Heart (MOMO MIX)
             0x00162110                  0x00262090     Metadata Structure For Wild Rush (From Nonstop Megamix)
             0x00162198                  0x00262118     Metadata Structure For Burnin' The Floor (BLUE Fire mix)
             0x00162220                  0x002621A0     Metadata Structure For Tsugaru (Apple Mix)
             0x001622A8                  0x00262228     Metadata Structure For Ecstacy (Mifnight Blue Mix)
             0x00162330                  0x002622B0     Metadata Structure For Silent Hill (3rd Christmas Mix)
             0x001623B8                  0x00262338     Metadata Structure For Celebrate Nite (Euro Trance Style)
             0x00162440                  0x002623C0     Metadata Structure For Higher (Next Morning Mix)
             0x001624C8                  0x00262448     Metadata Structure For My Summer Love (Tommy's Smile Mix)
             0x00162550                  0x002624D0     Metadata Structure For Look to the Sky (True Color Mix)
             0x001625D8                  0x00262558     Metadata Structure For Cutie Chaser (Morning Mix)
             0x00162660                  0x002625E0     Metadata Structure For Do It Right (Harmonized 25step Mix)
             0x001626E8                  0x00262668     Metadata Structure For Drop the Bomb -System S.F Mix-
             0x00162770                  0x002626F0     Metadata Structure For Dynamite Rave (Down Bird SOTA Mix)
             0x001627F8                  0x00262778     Metadata Structure For I'm For Real
             0x00162880                  0x00262800     Metadata Structure For Jam & Marmalade
             0x00162908                  0x00262888     Metadata Structure For Kind Lady
             0x00162990                  0x00262910     Metadata Structure For Logical Dash
             0x00162A18                  0x00262998     Metadata Structure For Overblast!!
             0x00162AA0                  0x00262A20     Metadata Structure For Peace-Out
             0x00162B28                  0x00262AA8     Metadata Structure For So In Love
             0x00162BB0                  0x00262B30     Metadata Structure For The Shining Polaris
             0x00162C38                  0x00262BB8     Metadata Structure For Look To The Sky (Trance Mix)
             0x00162CC0                  0x00262C40     Metadata Structure For Do It Right (80s Electro Mix)
             0x00162D48                  0x00262CC8     Metadata Structure For Kind Lady (Interlude)
             0x00162DD0                  0x00262D50     Metadata Structure For B4U
             0x00162E58                  0x00262DD8     Metadata Structure For Crash!
             0x00162EE0                  0x00262E60     Metadata Structure For Dead End
             0x00162F68                  0x00262EE8     Metadata Structure For Drop Out
             0x00162FF0                  0x00262F70     Metadata Structure For Dynamite Rave
             0x00163078                  0x00262FF8     Metadata Structure For LOVE ♥ SHINE
             0x00163100                  0x00263080     Metadata Structure For PARANOiA Survivor
             0x00163188                  0x00263108     Metadata Structure For PARANOiA Rebirth
             0x00163210                  0x00263190     Empty Metadata Structure With Name "inst" 
             0x00163298                  0x00263218     Empty Metadata Structure With Name "name"
             0x00163320                  0x002632A0     Empty Metadata Structure With Name "scal"
             0x001633A8                  0x00263328     Empty Metadata Structure With Name "sele"
             0x00163430                  0x002633B0     Empty Metadata Structure With Name "stae"
             0x001634B8                  0x00263438     Empty Metadata Structure With Name "staf"
0x00163650 - 000x16377C     0x002635D0 - 0x002636FC     Sound Index Array
0x0016D6F0 - 0x0016D710     0x0026D670 - 0x0026D690     Dance Point Multipliers    
             0x0016D6F0                  0x0026D670     D.P Multiplier For Perfects
             0x0016D6F4                  0x0026D674     D.P Multiplier For Greats
             0x0016D6F8                  0x0026D678     D.P Multiplier For Goods
             0x0016D6FC                  0x0026D67C     D.P Multiplier For Boos
             0x0016D700                  0x0026D680     D.P Multiplier For Misses
             0x0016D710                  0x0026D690     D.P Multiplier For OKs
```
