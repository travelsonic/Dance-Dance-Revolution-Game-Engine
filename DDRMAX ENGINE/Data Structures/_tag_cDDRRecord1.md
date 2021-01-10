# _tag_cDDRRecord1 Data Structure

## Definition:
```
struct _tag_cDDRRecord1 {
    unsigned int Score[8];
    unsigned int Bonus[8];
    unsigned int nPlayed;
    unsigned short LinkNum;
    unsigned short Combo[8];
    unsigned short ComboMax[8];
    unsigned char Level[8];
    char pad[2];
};
```

## Other Notes:
### Naming Conventions:
Each game gives this structure a unique name, with a number or combination of characters between the 
_tag_cDDR" part of the structure name, and the "Record1" part of the structure name.

|Name:             |Used In:       |
| -----------------|---------------|
|_tag_cDDR6Record1 |DDRMAX -DanceDanceRevolution 6thMIX- C/S, DDRMAX -Dance Dance Revolution- C/S|
|_tag_cDDR7Record1 |DDRMAX2 -DanceDanceRevolution 7thMIX- C/S, DDRMAX2 -Dance Dance Revolution- C/S (Demo Disc & Retail Release), Dancing Stage MexaMix (C/S)
|_tag_cDDR8Record1 |Dance Dance Revolution EXTREME C/S (J.P, U.S E3 DEMO, U.S), Dance Dance Revolution Festival (C/S)|
|_tag_cDDRB2Record1|Dance Dance Revolution Party Collection|
