Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, and PS2DIS.

In this game, the difference between the physical, and logical addresses, is 0xFFF80

```
Physical Address(es):       Logical Address(es):        Description:  
             0x001564D0                  0x00256450     Challenge-Only Song Grouping - Red Channel Value
             0x001564D4                  0x00256464     Challenge-Only Song Grouping - Red Channel Value
             0x001564D8                  0x00256468     Challenge-Only Song Grouping - Red Channel Value
             0x001564DC                  0x0025645C     Challenge-Only Song Grouping - Green Channel Value
             0x001564E0                  0x00256460     Challenge-Only Song Grouping - Green Channel Value
             0x001564E4                  0x00256464     Challenge-Only Song Grouping - Green Channel Value
             0x001564E8                  0x00256468     Challenge-Only Song Grouping - Blue Channel Value
             0x001564EC                  0x0025646C     Challenge-Only Song Grouping - Blue Channel Value
             0x001564F0                  0x00256470     Challenge-Only Song Grouping - Blue Channel Value
             0x001564F4                  0x00256474     Boss Song Grouping - Red Channel Value
             0x001564F8                  0x00256478     Boss Song Grouping - Red Channel Value
             0x001564FC                  0x0025647C     Boss Song Grouping - Red Channel Value
             0x00156500                  0x00256480     Boss Song Grouping - Green Channel Value
             0x00156504                  0x00256484     Boss Song Grouping - Green Channel Value
             0x00156508                  0x00256488     Boss Song Grouping - Green Channel Value
             0x0015650C                  0x0025648C     Boss Song Grouping - Blue Channel Value
             0x00156510                  0x00256490     Boss Song Grouping - Blue Channel Value
             0x00156514                  0x00256484     Boss Song Grouping - Blue Channel Value
0x001566E0 - 0x0015670C     0x00256660 - 0x0025668C     Foot Rating Foot Color RGB Values
             0x001566E0                  0x00256660     Light Difficulty Foot Color - Red Channel Value
             0x001566E4                  0x00256664     Light Difficulty Foot Color - Green Channel Value
             0x001566E8                  0x00256668     Light Difficulty Foot Color - Blue Channel Value
             0x001566EC                  0x0025666C     Standard Difficulty Foot Color - Red Channel Value
             0x001566F0                  0x00256670     Standard Difficulty Foot Color - Green Channel Value
             0x001566F4                  0x00256674     Standard Difficulty Foot Color - Blue Channel Value
             0x001566F8                  0x00256678     Heavy Difficulty Foot Color - Red Channel Value
             0x001566FC                  0x0025667C     Heavy Difficulty Foot Color - Green Channel Value
             0x00156700                  0x00256680     Heavy Difficulty Foot Color - Blue Channel Value
             0x00156704                  0x00256684     Oni Difficulty Foot Color - Red Channel Value
             0x00156708                  0x00256688     Oni Difficulty Foot Color - Green Channel Value
             0x0015670C                  0x0025668C     Oni Difficulty Foot Color - Blue Channel Value
0x001566B0 - 0x001566D4     0x00256630 - 0x00256654     Groove Radar Label Positions
             0x001566B0                  0x00256630     Groove Radar Label - Stream - X Position
             0x001566B4                  0x00256634     Groove Radar Label - Stream - Y Position
             0x001566B8                  0x00256638     Groove Radar Label - Voltage - X Position
             0x001566BC                  0x0025663C     Groove Radar Label - Voltage - Y Position
             0x001566C0                  0x00256640     Groove Radar Label - Air - X Position
             0x001566C4                  0x00256644     Groove Radar Label - Air - Y Position
             0x001566C8                  0x00256648     Groove Radar Label - Freeze - X Position
             0x001566CC                  0x0025664C     Groove Radar Label - Freeze - Y Position
             0x001566D0                  0x002566D0     Groove Radar Label - Chaos - X Position
             0x001566D4                  0x002566D4     Groove Radar Label - Chaos - Y Position   
0x00156D60 - 0x00156D7C     0x00256CE0 - 0x00256CFC     Difficulty Selection Cursor Positions
             0x00156D60                  0x00256CE0     Light Mode - X Position
             0x00156D64                  0x00256CE4     Light Mode - Y Position
             0x00156D68                  0x00256CE8     Standard Mode - X Position
             0x00156D6C                  0x00256CEC     Standard Mode - Y Position
             0x00156D70                  0x00256CF0     Heavy Mode - X Position
             0x00156D74                  0x00256CF4     Heavy Mode - Y Position
             0x00156D78                  0x00256CF8     Nonstop Challenge - X Position
             0x00156D7C                  0x00256CFC     Nonstop Challenge - Y Position
0x00157600 - 0x0015760C     0x00257580 - 0x0025758C     Main Menu Graphics Indexes
             0x00157600                  0x00257580     Index For Main Menu Option Text Graphic
             0x00157604                  0x00257584     Index For Main Menu Background Graphic
             0x00157608                  0x00257588     Index For Main Menu "NEW!" Icon Graphic
             0x0015760C                  0x0025758C     Index For Main Menu Information Footer Graphic
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
0x001635C8 - 0x0016364C     0x00263548 - 0x002635CC     UNUSED SPACE - 132 BYTES
0x00163650 - 0x0016377C     0x002635D0 - 0x002636FC     Preview Sound Index Array
             0x00163650                  0x002635D0     Preview Sound Index Value For Long Train Runnin'
             0x00163654                  0x002635D4     Preview Sound Index Value For Maximum Overdrive
             0x00163658                  0x002635D8     Preview Sound Index Value For Waka Laka
             0x0016365C                  0x002635DC     Preview Sound Index Value For Baby Love Me
             0x00163660                  0x002635E0     Preview Sound Index Value For D2R
             0x00163664                  0x002635E4     Preview Sound Index Value For Destiny
             0x00163668                  0x002635E8     Preview Sound Index Value For Living In America
             0x0016366C                  0x002635EC     Preview Sound Index Value For Sweet Sweet ♥ Magic
             0x00163670                  0x002635F0     Preview Sound Index Value For Ever Snow
             0x00163674                  0x002635F4     Preview Sound Index Value For AM-3P (303 BASS MIX)
             0x00163678                  0x002635F8     Preview Sound Index Value For The Reflex
             0x0016367C                  0x002635FC     Preview Sound Index Value For So Fabulous So Fierce (Freak Out!)
             0x00163680                  0x00263600     Preview Sound Index Value For Drifting Away
             0x00163684                  0x00263604     Preview Sound Index Value For Stay
             0x00163688                  0x00263608     Preview Sound Index Value For Secret Rendez-vous
             0x0016368C                  0x0026360C     Preview Sound Index Value For Little Boy (Boy Oh Boy Mix)
             0x00163690                  0x00263610     Preview Sound Index Value For Rain of Sorrow
             0x00163694                  0x00263614     Preview Sound Index Value For Maxx Unlimited
             0x00163698                  0x00263618     Preview Sound Index Value For Dive To The Night
             0x0016369C                  0x0026361C     Preview Sound Index Value For Tsugaru
             0x001636A0                  0x00263620     Preview Sound Index Value For BRE∀K DOWN!
             0x001636A4                  0x00263624     Preview Sound Index Value For Burning Heat! (3 Option Mix)
             0x001636A8                  0x00263628     Preview Sound Index Value For Nothing Gonna Stop
             0x001636AC                  0x0026362C     Preview Sound Index Value For Fantasy
             0x001636B0                  0x00263630     Preview Sound Index Value For i feel ...
             0x001636B4                  0x00263634     Preview Sound Index Value For CANDY ♥ 
             0x001636B8                  0x00263638     Preview Sound Index Value For Spin the Disc
             0x001636BC                  0x0026363C     Preview Sound Index Value For Trance De Janeiro
             0x001636C0                  0x00263640     Preview Sound Index Value For Look At Us
             0x001636C4                  0x00263644     Preview Sound Index Value For The Whistle Song (Blow My Whistle Bitch)
             0x001636C8                  0x00263648     Preview Sound Index Value For 革命 (Kakumei)
             0x001636CC                  0x0026364C     Preview Sound Index Value For AFRONOVA (From Nonstop Megamix)
             0x001636D0                  0x00263650     Preview Sound Index Value For AM-3P (AM EAST MIX)
             0x001636D4                  0x00263654     Preview Sound Index Value For Brillant 2U (K.O.G G3 Mix)
             0x001636D8                  0x00263658     Preview Sound Index Value For B4U (B4 ZA BEAT MIX)
             0x001636DC                  0x0026365C     Preview Sound Index Value For DROP OUT (From Nonstop Megamix)
             0x001636E0                  0x00263660     Preview Sound Index Value For Dynamite Rave (B4 ZA BEAT MIX)
             0x001636E4                  0x00263664     Preview Sound Index Value For Hysteria 2001
             0x001636E8                  0x00263668     Preview Sound Index Value For 祭 JAPAN (From Nonstop Megamix)
             0x001636EC                  0x0026366C     Preview Sound Index Value For SEXY PLANET (From Nonstop Megamix)
             0x001636F0                  0x00263670     Preview Sound Index Value For Super Star (From Nonstop Megamix)
             0x001636F4                  0x00263674     Preview Sound Index Value For Still In My Heart (MOMO MIX)
             0x001636F8                  0x00263678     Preview Sound Index Value For Wild Rush (From Nonstop Megamix)
             0x001636FC                  0x0026367C     Preview Sound Index Value For Burnin' The Floor (BLUE Fire mix)
             0x00163700                  0x00263680     Preview Sound Index Value For Tsugaru (Apple Mix)
             0x00163704                  0x00263684     Preview Sound Index Value For Ecstacy (Mifnight Blue Mix)
             0x00163708                  0x00263688     Preview Sound Index Value For Silent Hill (3rd Christmas Mix)
             0x0016370C                  0x0026368C     Preview Sound Index Value For Celebrate Nite (Euro Trance Style)
             0x00163710                  0x00263690     Preview Sound Index Value For Higher (Next Morning Mix)
             0x00163714                  0x00263694     Preview Sound Index Value For My Summer Love (Tommy's Smile Mix)
             0x00163718                  0x00263698     Preview Sound Index Value For Look to the Sky (True Color Mix)
             0x0016371C                  0x0026369C     Preview Sound Index Value For Cutie Chaser (Morning Mix)
             0x00163720                  0x002636A0     Preview Sound Index Value For Do It Right (Harmonized 25step Mix)
             0x00163724                  0x002636A4     Preview Sound Index Value For Drop the Bomb -System S.F Mix-
             0x00163728                  0x002636A8     Preview Sound Index Value For Dynamite Rave (Down Bird SOTA Mix)
             0x0016372C                  0x002636AC     Preview Sound Index Value For I'm For Real
             0x00163730                  0x002636B0     Preview Sound Index Value For Jam & Marmalade
             0x00163734                  0x002636B4     Preview Sound Index Value For Kind Lady
             0x00163738                  0x002636B8     Preview Sound Index Value For Logical Dash
             0x0016373C                  0x002636BC     Preview Sound Index Value For Overblast!!
             0x00163740                  0x002636C0     Preview Sound Index Value For Peace-Out
             0x00163744                  0x002636C4     Preview Sound Index Value For So In Love
             0x00163748                  0x002636C8     Preview Sound Index Value For The Shining Polaris
             0x0016374C                  0x002636CC     Preview Sound Index Value For Look To The Sky (Trance Mix)
             0x00163750                  0x002636D0     Preview Sound Index Value For Do It Right (80s Electro Mix)
             0x00163754                  0x002636D4     Preview Sound Index Value For Kind Lady (Interlude)
             0x00163758                  0x002636D8     Preview Sound Index Value For B4U
             0x0016375C                  0x002636DC     Preview Sound Index Value For Crash!
             0x00163760                  0x002636E0     Preview Sound Index Value For Dead End
             0x00163764                  0x002636E4     Preview Sound Index Value For Drop Out
             0x00163768                  0x002636E8     Preview Sound Index Value For Dynamite Rave
             0x0016376C                  0x002636EC     Preview Sound Index Value For LOVE ♥ SHINE
             0x00163770                  0x002636F0     Preview Sound Index Value For PARANOiA Survivor
             0x00163774                  0x002636F4     Preview Sound Index Value For PARANOiA Rebirth
             0x00163778                  0x002636F8     Empty Preview Sound Index Array Element
             0x0016377C                  0x002636FC     Empty Preview Sound Index Array Element
0x0016D6F0 - 0x0016D710     0x0026D670 - 0x0026D690     Dance Point Multipliers    
             0x0016D6F0                  0x0026D670     D.P Multiplier For Perfects
             0x0016D6F4                  0x0026D674     D.P Multiplier For Greats
             0x0016D6F8                  0x0026D678     D.P Multiplier For Goods
             0x0016D6FC                  0x0026D67C     D.P Multiplier For Boos
             0x0016D700                  0x0026D680     D.P Multiplier For Misses
             0x0016D710                  0x0026D690     D.P Multiplier For OKs
0x0016E290 - 0x0016E2B4     0x0026E210 - 0x0026E234     Jump Table - Title Screen Menu Navigation Options
             0x0016E290                  0x0026E210     Menu Choice For Game Mode
             0x0016E294                  0x0026E214     Menu Choice For Diet Mode
             0x0016E298                  0x0026E218     Menu Choice Default Case?  Brings you back to the main menu
             0x0016E29C                  0x0026E21C     Menu Choice For Training Mode
             0x0016E2A0                  0x0026E220     Menu Choice For Edit Mode
             0x0016E2A4                  0x0026E224     Menu Choice For Options  
             0x0016E2A8                  0x0026E228     Menu Choice For Records
             0x0016E2AC                  0x0026E22C     Menu Choice For Information   
             0x0016E2B0                  0x0026E230     Menu Choice For Endless Mode
             0x0016E2B4                  0x0026E234     EMPTY/UNUSED
0x0017DDE8 - 0x0017F2F8     0x0027DD68 - 0x0027F278     Filedata Entry Table
0x0017F602 - 0x001DAC88      NO LOGICAL ADDRESSES       Leftover Debugging Data - Not Recognized By IDA, PS2DIS, Etc.  
```
