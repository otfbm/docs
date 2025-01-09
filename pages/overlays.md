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

An arrow: `*a` followed by `<color><start_point><end _point>`

```
https://otfbm.io/*aRa1g4/g4r/
```

<!-- tabs:end -->

![](https://otfbm.io/*aRa1g4/g4r/)

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

![](https://otfbm.io/*c20rd5)

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

![](https://otfbm.io/*ct10yf2)

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

![](https://otfbm.io/10x10/G8Lr-OG1/*co25gh9)

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

![](https://otfbm.io/*t30ba5e5/A5b-DR1)

## Lines

Lines are used for lightning bolts or other similar spell effects. They are defined by `<length>`, `<width>`, `<color>`, `<topleft>`, and `<direction>`. Length indicates how long the line is, width is how wide it is, color is what color it should render as, topleft is where the line originates, and direction tells it which direction to go.

<!-- tabs:start -->

#### **Discord**

```
!i add "Wizard" 0
!map -t Wiz -move A1
!map -over line,30,5,g,a1,b2
```

#### **Url**

`*l` line `30` length `,5` width `g` color `a1` start coordinate `b2` direction coordinate

```
https://otfbm.io/*l30,5ga1b2/A1g-Wiz
```

<!-- tabs:end -->

![](https://otfbm.io/*l30,5ga1b2/A1g-Wiz)

## Squares

```
https://otfbm.io/*s30ca1b2
```

![](https://otfbm.io/*s30ca1b2)

`*s` square `30` size `c` _colour_ `a1` start co-ordinate `b2` direction co-ordinate

Alternatively use `*st` to anchor the square at the top left. (Or don't specify the direction co-ordinate.)

```
https://otfbm.io/*a10pD3E5
```

![](https://otfbm.io/*a10pD3E5)

`*a` arrow `10` size `p` _colour_ `d3` start co-ordinate `e5` direction co-ordinate

## Putting Overlays under the Token layer (Underlays)

In some cases you may have a need to put an overlay under tokens. Use `u` after the `*` to signify placing the item under the token layer. (an example would be the Grease spell.)

**_Example_**

A red 20 ft radius circle overlay example.

```
https://otfbm.io/*c20rd5/d5-Bard
```

![](https://otfbm.io/*c20rd5/d5-Bard)


A red 20 ft radius circle overlay example with `u` designation.

```
https://otfbm.io/*uc20rd5/d5-Bard
```

![](https://otfbm.io/*uc20rd5/d5-Bard)