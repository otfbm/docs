# Overlays

Overlays (and underlays) are used to draw shapes on the map, such as the visual effect of a spell or a dragon's breath attack. They can represent a whole lot of things though, and we'll provide some examples.

## Arrows

Arrows support a color, a start coordinate, and an end coordinate. The most common use case for arrows is to show movement for a token, but with some creativity and the right token image you can literally make a guard take an arrow in the knee.

_*Example*_

A red arrow starting at A1 and ending at G4 where a red token is.

<!-- tabs:start -->

#### **Discord**

```
!map -over arrow,r,a1,g4
```

#### **Url**

An arrow: `*a` followed by `<color><start_point><end_point>`

```
https://otfbm.io/*aRa1g4/g4r/
```

<!-- tabs:end -->

![A red arrow drawn from A1 to G4](https://otfbm.io/*aRa1g4/g4r/)

## Circles

Circles are used for fireballs, explosions, yo mama jokes, anything with a larger circular radius. They can be drawn in three ways:

 - `circle`: the center of a grid coordinate that occupies one square.
 - `circletop`: the top left corner (drawing the circle to the right and down from the grid coordinate).
 - `circlecorner`: the top left grid coordinate of a center point that lies directly on the grid, such as large creatures who occupy four squares.

No matter which you use, you set the radius (half of the diameter), the color, and the target coordinate.

_*Example*_

A red circle centered on D5

<!-- tabs:start -->

#### **Discord**

```
!map -over circle,20,r,d5
```

#### **Url**

A centered circle: `*c` circle `20` diameter `r` color `d5` center coordinate

```
https://otfbm.io/*c20rd5
```

<!-- tabs:end -->

![A red circle centered on D5](https://otfbm.io/*c20rd5)

A yellow circle drawn down and to the right with F2 at the top left corner

<!-- tabs:start -->

#### **Discord**

```
!map -over circletop,10,y,f2
```

#### **Url**

A top left centered circle: `*ct` circletop `10` diameter `y` color `f2` center coordinate

```
https://otfbm.io/*ct10yf2
```

<!-- tabs:end -->

![A yellow circle centered on the top left corner of it's total space](https://otfbm.io/*ct10yf2)

A green 25ft circle centered on the top left grid intersection of H9 with a large Ogre, maybe it's an aura of stench

<!-- tabs:start -->

#### **Discord**

```
!i madd "Ogre" 0
!map -t OG1 -move G8 -size L
!map -over circlecorner,25,g,h9
```

#### **Url**

A bottom right of center circle: `*co` circlecorner `25` diameter `g` color `h9` center coordinate for the ogre token

```
https://otfbm.io/10x10/G8Lr-OG1/*co25gh9
```

<!-- tabs:end -->

![An ogre with an aura](https://otfbm.io/10x10/G8Lr-OG1/*co25gh9)

## Cones

Cones are used for cone shaped attacks or effects, like a Cone of Cold. You must define the `<size>`, `<color>`, `<start>` and `<direction>`. Size is how long the cone is, color is the color it will render as, start is the coordinate it should start at (generally where the casting creature is if the cone starts at the caster), and direction is the direction it will be drawn in.

_*Example*_

A 30 ft cone emanating from a small dragon on A5, pointed at E5. Note that the end coordinate only determines direction, it will always be drawn at the size provided.

<!-- tabs:start -->

#### **Discord**

```
!i madd "Dragon" 0
!map -t DR1 -move A5
!map -over cone,30,b,a5,e5
```

#### **Url**

`*t` cone `30` length `b` color `a5` start coordinate `e5` direction coordinate

```
https://otfbm.io/*t30ba5e5/A5b-DR1
```

<!-- tabs:end -->

![A dragon using it's breath weapon](https://otfbm.io/*t30ba5e5/A5b-DR1)

## Lines

Lines are used for lightning bolts or other similar spell effects. They are defined by `<length>`, `<width>`, `<color>`, `<topleft>`, and `<direction>`. Length indicates how long the line is, width is how wide it is, color is what color it should render as, topleft is where the line originates, and direction tells it which direction to go.

_*Example*_

A wizard casting a lightning bolt, or any other spell that draws a line, targetting b2 to draw it directly diagonally.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 "Wizard"
!map -t Wiz -move A1
!map -over line,30,5,g,a1,b2
```

#### **Url**

`*l` line `30` length `5` width `g` color `a1` start coordinate `b2` direction coordinate

```
https://otfbm.io/*l30,5ga1b2/A1g-Wiz
```

<!-- tabs:end -->

![A wizard standing at A1 casting a lightning bolt targetting B2](https://otfbm.io/*l30,5ga1b2/A1g-Wiz)

# Rectangles

Rectangles can also be drawn with `line`, just remember that they start from the target coordinate and expand outward in 5 ft increments from the _center_ of the coordinate. Note that the width is set to 25ft in this example to cover the five squares, as 20 ft would half cover the top and bottom cells the rectangle overlaps:

_*Example*_

A wizard standing in an arbitrarily drawn rectangle.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 "Wizard"
!map -t Wiz -move A1
!map -over line,45,25,y,a4,j4
```

#### **Url**

`*l` line `45` length `25` width `y` color `a4` start coordinate `j4` direction coordinate

```
https://otfbm.io/*l45,25ya4j4/E5g-Wiz
```

<!-- tabs:end -->

![A wizard standing in an arbitrarily drawn rectangle](https://otfbm.io/*l45,25ya4j4/E5g-Wiz)

## Squares

Squares can be drawn by size or by starting and end points. They are defined by `<size>`, `<color>`, `<top_left>`, and an optional `<aim>`. Size is how many square feet it is, color determines color, top left determines where it is drawn from, and aim will rotate the square's rightmost face towards the target cell or token.

_*Example*_

A wizard standing in a square overlay centered on the token.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 "Wizard"
!map -t Wiz -move E5
!map -over square,25,b,c3
```

#### **Url**

`*s` square `25` color `b` start co-ordinate `c3`.

Alternatively use `*st` to anchor the square at the top left. (Or don't specify the direction co-ordinate.)

```
https://otfbm.io/10x10/E5g-Wiz/*s25bC3
```

<!-- tabs:end -->

![A blue square centered on a wizard](https://otfbm.io/10x10/E5g-Wiz/*s25bC3)

To rotate the square into a diamond, target a direct diagonal cell from the starting cell. You can arbitrarily rotate the square by targetting any cell, but a diamond is achieved this way.

_*Example*_

A yellow square rotated into a diamond by targetting a direct diagonal cell from it's origin.

<!-- tabs:start -->

#### **Discord**

```
!map -over square,25,b,c3,h8
```

#### **Url**

`*s` square `25` color `b` start co-ordinate `c3` direction co-ordinate `h8`

Alternatively use `*st` to anchor the square at the top left. (Or don't specify the direction co-ordinate.)

```
https://otfbm.io/10x10/E5gWiz/*s25bC3h8
```

<!-- tabs:end -->

![A yellow square rotated into a diamond](https://otfbm.io/10x10/E5g-Wiz/*s25bC3h8)

## Underlays

You may notice all the overlays sit on top of the token, which may not make sense for something like Grease or Entangle that would logically be under the tokens.  For that we have underlays.  Any shape works, you just use `-under` instead of `-over`

_*Example*_

A paladin's aura barely reaching a bard ally. Your DM may decide that doesn't count as in range, or they may because the bard is touched by it.  Now you can visualize it while arguing about it.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 Bard
!i add 0 Paladin
!map -t Bard -move e5 -t Paladin -move g6
!map -under circle,10,b,g6
```

#### **Url**

`*c` = circle, `10` = diameter, `b` = color, `g6` center coordinate

```
http://otfbm.io/10x10/E5Mr-Bard/G6Mr-Paladin/*uc10bg6
```

<!-- tabs:end -->

![A paladin's aura barely reaching a bard ally](http://otfbm.io/10x10/E5Mr-Bard/G6Mr-Paladin/*uc10bg6)

## Targetting

These quick overlays only last for one map draw. The next time the map is updated, it will disappear. To make your overlay persist, add a target.

Use `{aim}` in your `-over` command to set the target. You can target both cells (A3) and tokens (GO1, GaryGoblin). `-t` will stick the overlay to a token so it persists as long as the token does in combat. For most persistent spells you'll want to stick the overlay to the spell's caster so the effect ends when they do.

_*Example*_

A druid casts Moonbeam, targetting a group of zombies with ZO1 being the direct target. To move it, on their next turn the druid can just use `!map -over circle,5,y,{aim} -aim <coordinate>` and reroll damage.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 Druid
!i madd "Zombie" -n 3
!map -t Druid -move d2 -color b
!map -t ZO1 -move f4
!map -t ZO2 -move e5
!map -t ZO3 -move g5
!cast "Moonbeam" -t ZO1
!map -over circle,5,y,{aim} -aim f5 -t Druid
```

#### **Url**

Note that when directly editing the url, there is no way to save the overlay as there is with the Discord alias. To move the moonbeam, you must manually change the center coordinate to the desired location.

`*c` = circle, `5` = diameter, `y` = color, `f5` center coordinate

```
https://otfbm.io/10x10/F4Mr-ZO1/D2Mb-Druid/E5Mr-ZO2/G5Mr-ZO3/*c5yf5
```

<!-- tabs:end -->

![A druid casts Moonbeam on three zombies](https://otfbm.io/10x10/F4Mr-ZO1/D2Mb-Druid/E5Mr-ZO2/G5Mr-ZO3/*c5yf5)

## Removing

To remove a persisting overlay, use `!map -over none -t <name>`

_*Example*_

The druid has cancelled the Moonbeam spell.

<!-- tabs:start -->

#### **Discord**

```
!i add 0 Druid
!i madd "Zombie" -n 3
!map -t Druid -move d2 -color b
!map -t ZO1 -move f4
!map -t ZO2 -move e5
!map -t ZO3 -move g5
!cast "Moonbeam" -t ZO1
!map -over circle,5,y,{aim} -aim f5 -t Druid
!map -over none -t Druid
```

#### **Url**

Just remove the `*c5yf5` component from the url.

```
https://otfbm.io/10x10/F4Mr-ZO1/D2Mb-Druid/E5Mr-ZO2/G5Mr-ZO3
```

<!-- tabs:end -->

![A druid casts Moonbeam on three zombies](https://otfbm.io/10x10/F4Mr-ZO1/D2Mb-Druid/E5Mr-ZO2/G5Mr-ZO3)