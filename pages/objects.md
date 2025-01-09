# Objects

You can place an assortment of objects on any grid square. They are icons that represent things such as traps, chests, stairs, chairs, and tables. As with structures, there is nothing to prevent a token from passing through or on top of objects.

---

## Adding Objects

A simple example is adding a trap. There are also trip wires, pits, and other more precise objects, but a generic trap works for this purpose.

_*Example*_

A trap object in B3

<!-- tabs:start -->

#### **Discord**

```
!map -mapsize 5x5 -object B3:trap
```

#### **Url**

```
https://otfbm.io/5x5/b3$tr
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/b3$tr)

---

## Scaling Objects

Objects can be scaled to cover multiple squares. You can draw a pit trap that not even Mario can jump over.

_*Example*_

A pit scaled from A1 to D3

<!-- tabs:start -->

#### **Discord**

```
!map -mapsize 5x5 -object A1D3:open
```

#### **Url**

```
https://otfbm.io/a1d3$po
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/a1d3$po)

---

## Rotating Objects

Objects can even be rotated. Not actually rotated like overlays, but you can specify the direction from top left square to bottom right square, and it will be drawn appropriately.

_*Example*_

A table rotated from C4 to D3

<!-- tabs:start -->

#### **Discord**

```
!map -mapsize 5x5 -object C4D3:table
```

#### **Url**

```
https://otfbm.io/5x5/c4d3$ta
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/c4d3$ta)

---

## Coloring Objects

You can add colors to objects as well which is especially helpful if you're placing chests in a dark cave. Adding a color requires using either a predefined color code or a valid hexadecimal value prefixed with a tilde `~`.This is entered after the object code, prefixed by a comma `,`. To change color, retype the command with the desired color instead.

_*Example*_

A purple chest, orange fire, and golden puddle

<!-- tabs:start -->

#### **Discord**

```
!map -object A1:es,p
!map -object B2:fi,o
!map -object C3:pu,~FFD700
```

#### **Url**

```
https://otfbm.io/5x5/a1p$es/b2o$fi/c3~f97$pu/c3~f93$pu/c3~ffd700$pu
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/a1p$es/b2o$fi/c3~f97$pu/c3~f93$pu/c3~ffd700$pu)

---

## Deleting Objects

To remove an object, use `-deleteobject <coord>:<object>`. Please note that to remove objects that are scaled, rotated, or have a color applied, you MUST include each value as well, as it was entered when it was added, or Avrae will DM you an error like `ValueError: list.remove(x): x not in list`.

_*Example*_

Gary the wizard casts a portal spell. We have an object for that.

<!-- tabs:start -->

#### **Discord**

```
!map -object C3:mp,b
```

#### **Url**

```
https://otfbm.io/5x5/c3b$mp/b3g-Gary
```

<!-- tabs:end -->

![](https://otfbm.io/5x5/c3b$mp/b3g-Gary)

He steps through the portal, disappearing as the portal closes behind him.

<!-- tabs:start -->

#### **Discord**

```
!map -t Gary -move C3
!map -deleteobject C3:mp,b
!i remove Gary
```

#### **Url**

```
https://otfbm.io/5x5
```

<!-- tabs:end -->

![](https://otfbm.io/5x5)

---

## Complete List

All of the available objects along with their codes. You can also use the shorthand value listed for the Url method in the alias method. You can pull up this list in your channel.

<!-- tabs:start -->

#### **Discord**

```
!map objectlist
```

<!-- tabs:end -->

| Icon                          | Name                                 | Discord                         | Url   |
|-------------------------------|--------------------------------------|--------------------------------|-------|
|![](https://otfbm.io/1x1/a1$bw)| Brick Wall                           |`-object A1:brick-wall`         |`a1$bw`|
|![](https://otfbm.io/1x1/a1$es)| Chest                                |`-object A1:chest`              |`a1$es`|
|![](https://otfbm.io/1x1/a1$ch)| Chair                                |`-object A1:chair`              |`a1$ch`|
|![](https://otfbm.io/1x1/a1$co)| Column                               |`-object A1:column`             |`a1$co`|
|![](https://otfbm.io/1x1/a1$pc)| Covered Pit                          |`-object A1:covered-pit`        |`a1$pc`|
|![](https://otfbm.io/1x1/a1$ow)| Crowd                                |`-object A1:crowd`              |`a1$ow`|
|![](https://otfbm.io/1x1/a1$cr)| Crystals                             |`-object A1:crystals`           |`a1$cr`|
|![](https://otfbm.io/1x1/a1$ex)| Explosion                            |`-object A1:explosion`          |`a1$ex`|
|![](https://otfbm.io/1x1/a1$fi)| Fire                                 |`-object A1:fire`               |`a1$fi`|
|![](https://otfbm.io/1x1/a1$gs)| Gargoyle Statue                      |`-object A1:gargoyle-statue`    |`a1$gs`|
|![](https://otfbm.io/1x1/a1$la)| Ladder                               |`-object A1:ladder`             |`a1$la`|
|![](https://otfbm.io/1x1/a1$li)| Lightning                            |`-object A1:lightning`          |`a1$li`|
|![](https://otfbm.io/1x1/a1$mp)| Magic Portal                         |`-object A1:magic-portal`       |`a1$mp`|
|![](https://otfbm.io/1x1/a1$ne)| Net                                  |`-object A1:net`                |`a1$ne` |
|![](https://otfbm.io/1x1/a1$po)| Open Pit                             |`-object A1:open`               |`a1$po` |
|![](https://otfbm.io/1x1/a1$pa)| Palisade                             |`-object A1:palisade`           |`a1$pa` |
|![](https://otfbm.io/1x1/a1$pe)| Person                               |`-object A1:person`             |`a1$pe` |
|![](https://otfbm.io/1x1/a1$pr)| Pillar Round                           |`-object A1:pillar-round`       |`a1$pr` |
|![](https://otfbm.io/1x1/a1$ps)| Pillar Square                          |`-object A1:pillar-square`      |`a1$ps` |
|![](https://otfbm.io/1x1/a1$pu)| Puddle                               |`-object A1:puddle`             |`a1$pu`|
|![](https://otfbm.io/1x1/a1$sd)| Secret Door                          |`-object A1:secret-door`        |`a1$sd`|
|![](https://otfbm.io/1x1/a1$sp)| Spiked Pit                           |`-object A1:spiked-pit`         |`a1$sp`|
|![](https://otfbm.io/1x1/a1$un)| Spiked Trunk                         |`-object A1:spiked-trunk`       |`a1$un`|
|![](https://otfbm.io/1x1/a1$st)| Stairs                               |`-object A1:stairs`             |`a1$st`|
|![](https://otfbm.io/1x1/a1$ss)| Statue Star                          |`-object A1:statue-star`        |`a1$ss`|
|![](https://otfbm.io/1x1/a1$th)| Stone Throne                         |`-object A1:stone-throne`       |`a1$th`|
|![](https://otfbm.io/1x1/a1$ta)| Table                                |`-object A1:table`              |`a1$ta`|
|![](https://otfbm.io/1x1/a1$or)| Thorns                               |`-object A1:thorns`             |`a1$or`|
|![](https://otfbm.io/1x1/a1$tr)| Trap                                 |`-object A1:trap`               |`a1$tr`|
|![](https://otfbm.io/1x1/a1$tw)| Trip Wire                            |`-object A1:trip-wire`          |`a1$tw`|
|![](https://otfbm.io/1x1/a1$we)| Web                                  |`-object A1:web`                |`a1$we`|
|![](https://otfbm.io/1x1/a1$wn)| Wind                                 |`-object A1:wind`               |`a1$wn`|

You can help us add more by contributing!
