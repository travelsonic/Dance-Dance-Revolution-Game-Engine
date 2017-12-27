# Memory Addresses

Here is a (currently far from complete) list of memory addresses used in DDRMAX2 -DanceDanceRevolution 7thMIX-.  
To modify these addresses, you will need to use a cheat device, if playing the game on a console, or - if playing
the game in an emulator, need to use either the emulator's cheat support, OR the emulator's debugger if available.

The information here is sorted by function/use.

## Music Select Screen
```
**0x005674A8** The number of song wheel slots. When selecting a course in Oni mode; this is also the number of slots that are available for courses. The increment of this value past the number of songs/courses there are in the game will create blank slots. If you use Roulette, and land on a blank slot, the game will crash from attempting to access data at an invalid address.

**0x005674A4** - The current songwheel slot index the player has highlighted.

**0x005674B4** - Array of song wheel slot values, each value dictating which song appears in each slot. Each value is 4 bytes long. You can repeat values without any sort of conflict. If you extended the number of song wheel slots at 0x005674A8, and then append the list, the song wheel slots you added will show up without issue. The values that represent each song are, essentially, the indexd/order of the song data definitions, so a value of 0001 would be Long Train Runnin', 0002 would be Maximum Overdrive, 0003 Waka Laka, etc. It is worth noting that a value of 00C7 is the Roulette option, and a value of 00FF marks a "COMING SOON" dummy slot. (TODO: put up a full list of values?)

**0x0056F4C4** - The address of the song wheel data definition belonging to the song at the current position
on the wheel.

**0x0056F4D8** - The song wheel sort Label
0x01 = Normal sort / no graphic
0x02 = ABC sort
0x03 = BPM sort
0x04 = Best sort

A value of 0x00, or a value greater than 0x04 (0x05, 0x07, etc) results in nothing being shown.

```
- In a Game Stage -
Player's Scoring and Stepping Quality:
- General Note -: For some reason, these values are signed - as in, they can be either a positive, or a negative
value. Note that setting these values to negative will cause your score display to wildly
spin out of control, or become a garbled mess. Fortunately, this will not crash your game,
it just looks hilarious.

0x0056F508 - Player 1's displayed score. Editing this fails, as it is automatically replaced with the score
value stored at 0x0056F510 (see below).

0x0056F510 - Player 1's actual score. Completely editable, value range -2,147,483,648 <= X <= 2,147,483,647.
Note that the display you see in game is only 9 digits wide, so if you exceed 999,999,999, the score
counter will not show that 10th digit. Also note that if you enter a negative value, or enter a
value so great that the score becomes negative due to arithmetic overflow, the score counter will
become a garbled mess.

0x0056F5AC - Player 1's perfect count.
0x0056F5B0 - Player 1's great count.
0x0056F5B4 - Player 1's good count.
0x0056F5B8 - Player 1's boo count.
0x0056F5BC - Player 1's miss count.
0x0056F5C4 - Player 1's miss count repeated.
0x0056F5C8 - Player 1's O.K count.
0x0056F608 - Player 1's score on the score screen
0x0056F60C - Player 1's max combo
