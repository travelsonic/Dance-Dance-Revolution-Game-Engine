# Dance Point and Grade Calculation
## Dance Point Calculations:
During a song, the game keeps track of how many steps of each judgment quality (Perfect, Great, Good, Boo, Miss, O.K, etc) you get.

Associated with each of these timing judgments is a multiplier value.

To calculate the amount of earned DP, the game takes the number of steps that fall into a particular judgment quality, multiply it by the associated multipliers, then takes that product, and adds it to a sum.

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

## Grade Calculations:
