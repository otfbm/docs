# Tokens

Tokens represent controllable creatures on a battle map. They are a major component of making your battle map interactive. When players join a battle using `!i join` they will automatically be added to the player group (default color blue). DMs can add generic monsters to the monster group (default color red) using `!i madd <monster_name>` where *monster_name* is one from the default list or any bestiaries your server is subscribed to. Token options are applied to tokens using the `-t` (target) option of the `!map` command using the format `-t <target>|<location>|<size>|<color>|<token_name>|<height>`, and each one will be explained below. There is also a shorthand version of each option listed in detail below.

## Token Moving

You can move tokens using `!map -t <target>|<location>` or `!map -t <target> -move <location>`. The `-move` method also draws a handy little arrow from the start to end position of the token. `!move <location>` will also move the token, and is equivalent to `!map -t <active> -move <location>`. `!move` allows you to target another token with `!move <location> -t <someone_else>`.

_*Example*_

Let's set up a simple battle first, three goblins and two generic player characters.

<!-- tabs:start -->

#### **Discord**

```
!map -t GO1|a1
!map -t GO2|a2
!map -t GO3|a3
!map -t Rogue|e4
!map -t Barb|e3
```

These `-t` options can be combined into a single `!map` call, just keep adding `-t <data>` like so.

```
!map -t GO1|a1 -t GO2|a2 -t GO3|a3 -t Rogue|e4 -t Barb|e3
```

#### **Url**

```
https://otfbm.io/5x5/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/A2Mr-GO2/E3Mb-Barb
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/A2Mr-GO2/E3Mb-Barb)

Barb the barbarian goes first, readying an action to attack any hostile that enters a threatened square, and stands guard. GO2 goes next and the DM moves them to D2 to attack Barb the barbarian like a dummy.

<!-- tabs:start -->

#### **Discord**

Note that the default [arrow overlay](/pages/overlays.md) `!move` creates is white, we've manually changed it to black in the example for visibility without a [background image](/pages/backgrounds.md).

```
!move d3 -t GO2
```

#### **Url**

Without using the alias, you have to add the arrow manually. If you're comfortable enough to manually parse and hand edit a url this long, you probably don't mind.

```
https://otfbm.io/5x5/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/D3Mr-GO2/E3Mb-Barb/*a15kA2D3
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/D3Mr-GO2/E3Mb-Barb/*a15kA2D3)

Barb uses her readied action and just happened to score a critical hit and has the Crushing Blow feat, so Goblin2 is knocked back 5 ft. We add an explosion to accentuate just how hard this goblin got smacked.

<!-- tabs:start -->

#### **Discord**

```
!map -t GO2 -move c3 -object d3:ex
```

#### **Url**

```
https://otfbm.io/5x5/d3$ex/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/C3Mr-GO2/E3Mb-Barb
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/d3$ex/A3Mr-GO3/E4Mb-Rogue/A1Mr-GO1/C3Mr-GO2/E3Mb-Barb)

Rogue goes next, and he steps in to finish off the hurt goblin.

<!-- tabs:start -->

#### **Discord**

Remember to remove the explosion from last time.

```
!map -deleteobject d3:ex
!move d4
```

#### **Url**

```
https://otfbm.io/5x5/A3Mr-GO3/D4Mb-Rogue/A1Mr-GO1/C3Mr-GO2/E3Mb-Barb/*a5bE4D4
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/A3Mr-GO3/D4Mb-Rogue/A1Mr-GO1/C3Mr-GO2/E3Mb-Barb/*a5bE4D4)

After dispatching Goblin2, Rogue continues moving tactically towards the remaining opponents.

<!-- tabs:start -->

#### **Discord**

The `!go` command uses a specific directional syntax. `<distance><direction>` can be chained for as long as you like to dance about the map.

```
!i remove GO2
!go 5sw10w5n
```
That's 5 ft southwest, then 10 ft west, then 5 ft north.

#### **Url**

```
https://otfbm.io/5x5/A3Mr-GO3/A4Mb-Rogue/A1Mr-GO1/E3Mb-Barb/*a7bD4C5/*a10bC5A5/*a5bA5A4
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/A3Mr-GO3/A4Mb-Rogue/A1Mr-GO1/E3Mb-Barb/*a7bD4C5/*a10bC5A5/*a5bA5A4)

By now these goblins don't want any more smoke, and they're panicking. The DM can make them scramble about using `!go`

<!-- tabs:start -->

#### **Discord**

```
!go 5se5ne10s5nw -t GO1
!go n10e10 -t GO3
```

or

```
!go -t GO1|5se5ne10s5nw -t GO3|n10e10
```

#### **Url**

```
https://otfbm.io/5x5/C1Mr-GO3/A4Mb-Rogue/B2Mr-GO1/E3Mb-Barb/*a10~62c1bfA3A1/*a10~62c1bfA1C1/*a7rA1B2/*a7rB2C1/*a10rC1C3/*a7rC3B2
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/C1Mr-GO3/A4Mb-Rogue/B2Mr-GO1/E3Mb-Barb/*a10~62c1bfA3A1/*a10~62c1bfA1C1/*a7rA1B2/*a7rB2C1/*a10rC1C3/*a7rC3B2)

---

## Token Size

You can set the size of a token with `!map -t <target> -size <size>` or `!map -t <target>||<size>`. You can exclude the location if you don't want to change it, but the pipe characters `|` are important.

You can change the token sizes to any of D&Ds monster sizes by adding a letter indicator. Use any of the following letters to indicate size:

| Token                                                        | Size      | Code | Description                                                        |
|--------------------------------------------------------------|-----------|------|--------------------------------------------------------------------|
|![](https://otfbm.io/5x5/B2Tr-T1/B2Tg-T2/B2Tb-T3)             |Tiny       |`T`   |Up to 4 Tiny creatures can fit in a 5 ft square.                    |
|![](https://otfbm.io/5x5/C3Sy-Small)                          |Small      |`S`   |Occupies a 5 ft square.                                             |
|![](https://otfbm.io/5x5/C3Mo-Mid)                            |Medium     |`M`   |Occupies a 5 ft square. Default size.                               |
|![](https://otfbm.io/5x5/C3Le-Large)                          |Large      |`L`   |Occupies a 10x10 ft square, location at C3                          |
|![](https://otfbm.io/5x5/B2Hw-Huge)                           |Huge       |`H`   |Occupies a 15x15 ft square, location at B2                          |
|![](https://otfbm.io/5x5/A1Gr-Chonk)                          |Gargantuan |`G`   |Occupies a 20x20 ft square, location at A1                          |

_*Example*_

Setting several tokens of each size on the same grid.

<!-- tabs:start -->

#### **Discord**

```
!map -t T1|B2|T|r
!map -t T2|B2|T|g
!map -t T3|B2|T|b
!map -t Small|C3|S|y
!map -t Mid|D4||o
!map -t Large|E5|L|e
!map -t Huge|G7|H|w
!map -t Chonk|A7|G|r
```

or

```
!map -t T1|B2|T|r -t T2|B2|T|g -t T3|B2|T|b -t Small|C3|S|y -t Mid|D4||o -t Large|E5|L|e -t Huge|G7|H|w -t Chonk|A7|G|r
```

#### **Url**

```
https://otfbm.io/B2Tr-T1/B2Tg-T2/B2Tb-T3/C3Sy-Small/D4Mo-Mid/E5Le-Large/G7Hw-Huge/A7Gr-Chonk
```

<!-- tabs:end -->

![](https://otfbm.io/B2Tr-T1/B2Tg-T2/B2Tb-T3/C3Sy-Small/D4Mo-Mid/E5Le-Large/G7Hw-Huge/A7Gr-Chonk)

## Token Colors

You can change the color of a token with `!map -t <target> -color <color>` or `!map -t <target>|||<color>`. __color__ can be a valid [color code](pages/predefined?id=color-codes) or a hexadecimal value either 6 or 3 digits in length prefixed with a tilde `~` like `~dadb0d` or `~d20`.

_*Example*_

We'll make some technicolor goblins.

<!-- tabs:start -->

#### **Discord**

```
!map -t G01 -color dadb0d
!map -t GO2 -color d20
!map -t G03 -color c
```

or

```
!map -t G01|||dadb0d -t GO2|||d20 -t G03|||c
```

#### **Url**

Hexadecimal values must be prefixed by a tilde `~`.

```
https://otfbm.io/5x5/C1Mc-GO3/B2M~DADB0D-GO1/A1M~D20-GO2
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/C1Mc-GO3/B2M~DADB0D-GO1/A1M~D20-GO2)

## Token Labels

When you add a creature to a map, the name you provide is automatically set as the label for the token. For example, `!i madd "Goblin" -n 3` will generate three tokens named GO1, GO2, and GO3.

You can customize the names when you're adding creatures. Using `!i madd "Goblin Boss" -n 5 -name "El Jefe#"` will generate five goblin bosses named El Jefe1, El Jefe2, El Jefe3, El Jefe4, and El Jefe5, which is a little nicer.

The double quotes tell Avrae to see more than one word as the monster's name, so it will choose a Goblin Boss instead of a goblin. If you partial match a monster's name, `!i madd Gobl`, Avrae will PM you to ask which monster with `gobl` in their name you meant..

Some liberties are taken for autonaming, particularly to keep labels fitting in the token. Tiny tokens only display two characters, taken from the first character and last character, meaning a character named Pixie2 will be labelled P2 on the token. Small and Medium tokens accept up to four characters, so Goblin3 will just be Gobl, making Gob# a generally better choice if there is more than one. Large token labels can be up to 9 characters long, Huge token labels can be up to 14 characters long, and Gargantuan token labels can be up to 18 characters long.

_*Example*_

<!-- tabs:start -->

#### **Discord**

```
!i madd "Goblin" -n 3 -name Gob#
!map -t Gob1 -move A1
!map -t Gob2 -move C4
!map -t Gob3 -move D3
```

#### **Url**

Labels are added by prefixing a `-` and adding a label to a token in the url as shown.

```
https://otfbm.io/5x5/A1Sr-Gob1/C4Mr-Gob2/D3Mr-Gob3
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/A1Sr-Gob1/C4Mr-Gob2/D3Mr-Gob3)

*Note*
Labels have been added to tokens with images and numbered sequences. If the token is large enough, the full token label will be displayed. If the token is too small for this only the number will show.

**Token Sequence**
Adding tokens is not case sensitive.  Tokens are however sequence sensitive. Use the following sequence when defining a token within the url as shown below. As well as an example of creating a gargantuan, red token at D4 in the grid.

 `column` `row` `size` `color` `-label`

_**Example**_
```
http://otfbm.io/D4GR-Warlock
```

![](http://otfbm.io/D4GR-Warlock)

**Note** - *When defining a gargantuan token, you need to include a color. `D4G` would place a green token on the grid, `D4GBK` would place a gargantuan black token on the grid (black being the default color).*

## Custom Tokens

You can add custom images to any token, and they stick around. Very helpful for PCs and special NPCs or BBEGs. You can also use the [SRD token list](/pages/predefined?id=tokens) to customize every token if you like.

_*Example*_

A player adding their character and setting initial position

<!-- tabs:start -->

#### **Discord**

```
!move D1
```

#### **Url**

```
https://otfbm.io/E7Mr-GO2/D4Mr-GO1/D1Mr-GO3/E1Mg-Fighty
```

<!-- tabs:end -->

**Below here is outdated information that needs replaced with information on `-tokenimport`**

**Token Images**
Adding images to tokens is currently supported by preloading images at the following URL.
```
https://token.otfbm.io/meta/<base64 of full URL>
```

**NOTE** - *to convert a full URL to base64, see a site like ```http://www.base64url.com/```*

once you generate the token code, insert it into the map URL for the desired token.
```
https://otfbm.io/d3h-Urzer~<shortcode>
```

![](https://otfbm.io/d3h-Urzer~6yts4)

**Facial Recognition on tokens**
Token facial recognition can now be intentionally turned off on a case by case basis
Defining a token segment with a trailing ~ character will force the original token to be displayed rather than the one that was created using facial recognition.

Example.
* with facial recognition `/b1-satyr~wcqj3/`
* without facial recognition `/b1-satyr~wcqj3~/`

```
https://otfbm.io/2x1/@c60/a1-satyr~wcqj3/b1-satyr~wcqj3~/
```

![](https://otfbm.io/2x1/@c60/a1-satyr~wcqj3/b1-satyr~wcqj3~/)
