# Structures

** This page is out of date, and will be updated soon.**

You can draw walls and doors directly onto a battlemap using coordinates. To draw a wall, use the `_` character followed by coordinates.

## Walls

**Example**

```
https://otfbm.io/_B3J3
```

![](https://otfbm.io/_B3J3)

This will draw a line from B3 to J3

## Multiple Walls

You can finish a line and start a new one with the `_` character

**Example**

```
https://otfbm.io/_B3J3_B6J6
```

![](https://otfbm.io/_B3J3_B6J6)

## Doors

You can add doors with following codes:

`-o` open door,
`-d` closed door,
`-b` double door,
`-s` secret door

Here is a complex example:

**Example**

```
https://otfbm.io/_B2G2G4H4-dH6G6G8-sF9E10-bC10B10B2_B6-oG6
```

![](https://otfbm.io/_B2G2G4H4-dH6G6G8-sF9E10-bC10B10B2_B6-oG6)

**Colors**
Color support has been added to walls and doors. The same colors can be used as per tokens. The character -c is used to specify the color. This must be defined at the start of each wall segment. Eg. for the wall section _a2g2, you can change its color to blue like so _-cba2g2


*Example Without Color*
```
https://otfbm.io/_a2g2
```
![](https://otfbm.io/_a2g2)

*Example With Color*
```
https://otfbm.io/_-cba2g2
```
![](https://otfbm.io/_-cba2g2)