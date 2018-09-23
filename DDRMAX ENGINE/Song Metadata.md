# Song Metadata:
Dance Dance Revolution games utilizing the DDRMAX Engine keep specific metadata about each song, which is primarily used on the music selection screen.  This information is kept in the game's executable, and the metadata for each song is stored in a structure called music\_info.  

The size of this structure went up as the series of games utilizing the MAX engine increased, and more data per song needed to be tracked.

## music\_info struct sizes:
### Bemani System573 (Arcade) Mixes:
```
Game Name                                     Game Region:        Struct Size (in bytes):
DDRMAX -DanceDanceRevolution 6thMIX-             Japan                     80
DDRMAX2 -DanceDanceRevolution 7thMIX-            Japan                    108
Dancing Stage EuroMIX 2                         Europe                    108
Dance Dance Revolution EXTREME                   Japan                    128
Dancing Stage Fusion                            Europe                    160
```
### Playstation2 Mixes:
```
Game Name                                     Game Region:        Struct Size (in bytes):
DDRMAX -DanceDanceRevolution 6thMIX-             Japan                    100
DDRMAX -DanceDanceRevolution-                North America                120
DDRMAX2 -DanceDanceRevolution 7thMIX-            Japan                    136
DDRMAX2 -DanceDanceRevolution- DEMO DISK     North America                152
DDRMAX2 -DanceDanceRevolution-               North America                152
Dancing Stage Megamix                           Europe                    152
Dance Dance Revolution Party Collection          Japan                    152
Dancing Stage Fever                             Europe                    152
Dance Dance Revolution EXTREME                   Japan                    152
Dance Dance Revolution EXTREME               North America                160
Dance Dance Revolution EXTREME 2             North America                160
Dancing Stage Fusion                            Europe                    160
```

## Composition of the music\_info Struct:
**Note:** This information builds upon the work of Aaron in Japan user Taren, who has figured out a great deal of information about this, and other aspects of the DDRMAX era games. [You can see a good deal of his work preserved here.](http://aaronin.jp/boards/viewtopic.php?t=10509&highlight=iso)

This work is mainly to take what has been already figured out, and complete that work.

```
Field Name:     Size (in bytes):     Description:
base_name             7              Song abbreviated name
album                 1              Determines the CD icon that spins at the 
                                     upper right corner of the song banner
bpm_min               2              Minimum song BPM
bpm_max               2              Minimum song BPM
difficulty            8              Song foot ratings
```

### album:
The album is the CD icon that spins at the upper right corner of the song banner on the music selection screen.  This value is one byte in size.  The specific values will vary from game to game, but there will usually be icons for Konami originals, Dancemania titles where applicable, Licenses where applicable, and game crossovers when applicable.

### bpm\_min and bpm\_max:

### difficulty:
The song's foot rating data is stored with the single mode foot ratings first, followed by the doubles mode foot ratings.

Each foot rating takes one nibble of data, and that value is treated as an unsigned value.  This means that the maximum value for a song step chart's foot rating is 15.  The foot ratings are stored in the order: Standard, Light, Oni, Heavy.  If a song does not have a foot rating for a particular difficulty, that foot rating will be 0x00.  IF you change that value to any number from 1 to 15, that difficulty will be selectable, even if the song does not actually have a stepchart for that difficulty.  

Note that the game will not crash if an empty stepchart is loaded.  You will just have to wait until the song finished playing.
