# Dance Point and Grade Calculation
## Dance Point Calculations:
During a song, the game keeps track of how many steps of each judgment quality (Perfect, Great, Good, Boo, Miss, O.K, etc) you get.

Associated with each of these timing judgments is a multiplier value.

```
Judgment:       Multiplier Value:
Perfect                 2
Great                   1
Good                    0
Boo                    -4
Miss                   -8
O.K.                    6
N.G.               Not Tracked
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

DP = (P * PM) + (G*GM) + (Go * GoM) + (B * BM) + (M * MM) + (O * OM)
```

Boos and Misses, as you can see, take away earned D.P - the algorithm uses negative values because this allows the algorithm to take away D.P through the addition of negative values, which keeps the algorithm simple, and consistent.

## Grade Calculations:
After the game has calculated the amount of D.P you've earned, it divides that number by the maximum number of D.P that one can earn for a given song/chart difficulty.  This max D.P value is loaded into memory when you select the song from the song wheel.

The result of this DIV instruction puts the quotient (earned D.P / max D.P) in $LO, the remainder (earned DP % max DP) in $HI, $LO and $HI being special registers used to access the results of a division operation on a system using a MIPS architecture.

The game then puts the quotient, stored in $LO, into the register that previously held the maximum earnable D.P.

From there, it does a series of comparisons with the quotient against hard coded values, using the results to determine your letter grade.
```
Value                         Grade Earned:*
0x64 (100%)                   AAA if the quotient is equal to this value
0x5D ( 93%)                    AA if the quotient is greater than this value
0x50 ( 80%)                     A if the quotient is greater than this value
0x41 ( 65%)                     B if the quotient is greater than this value
0x20 ( 45%)                     C if the quotient is greater than this value
Less than 0x20 (45%)            D

Health gauge depleted
(irrespective of                E
quotient value)
```
* The non-E grades can only be earned if the player is able to keep their health gauge from becoming completely empty.  Once the health gauge runs out, the game defaults to assigning a grade of E, even if, for instance, the player anaged to earn enough D.P to earn an A after the health gauge depleted.
