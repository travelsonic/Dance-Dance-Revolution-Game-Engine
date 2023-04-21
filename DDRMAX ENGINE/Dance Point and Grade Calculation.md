# Dance Point and Grade Calculation
## Dance Point Calculations:
During a song, the game keeps track of how many steps of each judgment quality (Perfect, Great, Good, Boo, Miss, O.K, etc) you get.

Associated with each of these timing judgments is a multiplier value.

```
                     
Judgment:     Multiplier Value (Hexadecimal/Decimal):
Marvelous*    0x00000002 / 2
Perfect       0x00000002 / 2
Great         0x00000001 / 1
Good          0x00000000 / 0
Boo           0xFFFFFFF4 /-4
Miss          0xFFFFFFF8 /-8
O.K.          0x00000006 / 6
N.G.          Not Tracked?

* DanceDanceRevolution EXTREME and onward
```

To calculate the amount of earned D.P, the game takes the number of steps that fall into a particular judgment quality, multiply it by the associated multipliers, then takes that product, and adds it to a sum.

```
Let:
P = Perfect Count, PM = Perfect Multiplier,
G = Great Count, GM = Great Multiplier,
Go = Good Count, GoM = Good Multiplier,
B = Boo Count, BM = Boo Multiplier,
M = Miss Count, MM = Miss Multiplier,
O = O.K Count, and OM = O.K Multiplier.

Total Earned DP = (P * PM) + (G * GM) + (Go * GoM) + (B * BM) + (M * MM) + (O * OM)
```

Boos and Misses, as you can see, take away earned D.P - the algorithm uses negative values because this allows the algorithm to take away D.P through the addition of said negative values, which keeps the algorithm simple, and consistent.

## Grade Calculations:
After the game has calculated the amount of D.P you've earned, it divides that number by the maximum number of D.P that one can earn for a given song/chart difficulty.

To get the maximum amount of earnable DP in a song:
```
Let: 
TS = Total Step, TSM = Total Step Multiplier
TF = Total Freez, TFM = Total Freez Multiplier
WHERE
Total Step  = a stepchart's total number of non-freeze steps
Total Freez = a stepchart's total number of freeze steps 
```
Maximum Earnable DP = (TS * TSM) + (TF * TFM)

Earned DP percentage = (Total Earned DP * 100) / Maximum Earnable DP

The result of this DIV instruction puts the quotient (earned D.P / max D.P) in $LO, the remainder (earned DP % max DP) in $HI, $LO and $HI being special registers used to access the results of a division operation on a system using a MIPS architecture.

The game then puts the quotient, stored in $LO, into the register that previously held the maximum earnable D.P.

From there, it does a series of comparisons with the quotient against hard coded values, using the results to determine your letter grade.
```
Value:                                     Grade Earned:*
0x64 (100%)                               AAA if the quotient is equal to this value
0x5D ( 93%)                                AA if the quotient is greater than this value
0x50 ( 80%)                                 A if the quotient is greater than this value
0x41 ( 65%)                                 B if the quotient is greater than this value
0x20 ( 45%)                                 C if the quotient is greater than this value
Less than or equal to 0x20 (45%)            D

Health gauge depleted                       E
(irrespective of DP quotient value)
```
\* The non-E grades can only be earned if the player is able to keep their health gauge from becoming completely empty.  Once the health gauge runs out, the game sets a flag, "dead," to true - which forces the game to give you a grade of E, even if, for instance, the player managed to earn enough D.P to earn an A after the health gauge depleted.

### Checking for a Full Great + Perfect Combo:
In several mixes (though not universal to every mix in the DDRMAX-EXTREME era), such as Dancing Stage Megamix, and the US release of DDRMAX2, there is an additional step.

After the dance_level is calculated, the game will check to see if the value is greater than 2, and less than 6, that is, if the player earned an "A," "B," or "C."

If the player did earn either an "A," "B," or "C," the game will check to see if the number of PERFECT steps, and GREAT steps, add up to the total number of non-freeze steps (total_step).

If it does add up to this value, then the player's dance_level is changed to a value of 2, or a AA, overriding the "A," "B," or "C" that they would have otherwise earned.

### Checking that the Dance Level is Within a Valid Range:
The game will wrap up the dance_level calculation function by checking to see if the dance_level is within a valid range of 1 to 6 - specifically, to see if the value is greater than 6 (or a grade of "D"), or not.

If it is, for whatever reason, greater than 6, the game will set your dance_level to 6, or a grade of "D."
