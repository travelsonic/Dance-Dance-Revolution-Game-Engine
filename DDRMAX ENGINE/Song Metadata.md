# Song Metadata:
Dance Dance Revolution games utilizing the DDRMAX Engine keep specific metadata about each song, which is primarily used on the music selection screen.  This information is kept in the game's executable, and the metadata for each song is stored in a structure called music\_info.  

The size of this structure varies from game to game.
(List is currently incomplete)
**music\_info struct sizes:**
**Bemani System573 (Arcade) Mixes:**
```
Game Name                                   Region:        Struct Size (in bytes):
 DDRMAX -DanceDanceRevolution 6thMIX-        Japan                  80
DDRMAX2 -DanceDanceRevolution 7thMIX-        Japan                 108
Dancing Stage EuroMIX 2                     Europe                 108
Dance Dance Revolution EXTREME               Japan                 128
```
**Playstation2 Mixes:**
```
Game Name                                   Region:        Struct Size (in bytes):
DDRMAX2 -DanceDanceRevolution 7thMIX-        Japan                 136
DDRMAX2 -DanceDanceRevolution-           North America             152
Dance Dance Revolution EXTREME               Japan                 152
```

## Composition of the music\_info Struct:
**Note:** This information builds upon the work of Aaron in Japan user Taren, who has figured out a great deal of information about this, and other aspects of the DDRMAX era games. [You can see a good deal of his work here.](http://aaronin.jp/boards/viewtopic.php?t=10509&highlight=iso)

This work is mainly to take what has been already figured out, and complete that work.

```
Field Name:  Size (in bytes):  Description:
base_name

```
