# Viewing The Grid

## Grid Size

The first thing you want to do is set your grid size. This can be achieved with `-mapsize <width>x<height>` where width is the horizontal scale of the grid in cells, and height is the vertical scale of the grid in cells. `!map -mapsize 5x7` will output a blank grid 5 cells wide by 7 cells tall, or 25 feet by 35 feet. In D&D and many other TTRPGs, a square is 5 feet, and some aliases like `!go` assume increments of 5 feet, so it helps to consider that when sizing your grid so your goblins aren't as large as houses.

By default, the grid is 10x10.

_*Example*_

A 5x7 map

<!-- tabs:start -->

#### **Discord**

```
!map -mapsize 5x7
```

#### **Url**

```
https://otfbm.io/5x7
```

<!-- tabs:end -->

![](https://otfbm.io/5x7)

## Grid Pan

You can also `!view` different parts of the map, which sets the top left corner to whatever grid location is specified. To define the size of the view, you can either specify the bottom right coordinate or provide a grid range.

_*Example*_

A 5x2 map view starting at **M3**

<!-- tabs:start -->

#### **Discord**

```
!view M3:Q6
```
or
```
!view M3:5x4
```

#### **Url**

```
https://otfbm.io/m3:q6/
```
or
```
https://otfbm.io/m3:5x4/
```

<!-- tabs:end -->

![](https://otfbm.io/m3:q6/)

## Grid Pan

This `!view` can be moved and resized in any direction you like by using the commands `shift`, `expand`, and `reduce`. These commands use a special directional syntax of **distance**__direction__ where distance is the number of feet (in 5ft increments) to shift, expand or reduce, and direction is the letter of the direction to move in, which can be `n`, `ne`, `e`, `se`, `s`, `sw`, `w`, `nw`. You can chain as many directions as you like, i.e. `5n15ne20n` translates to 5ft (1 cell) north, 15ft (3 cells) northeast, then 20ft (4 cells) north again.

Note that there is no special tool if you're manipulating the map directly from the url, you just have to calculate it out.

_*Example*_

The previous 5x4 view being shifted 15ft to the east and 20ft to the south.

<!-- tabs:start -->

#### **Discord**

```
!view 15e20s shift
```

#### **Url**

```
https://otfbm.io/P7:T10
```

<!-- tabs:end -->

![](https://otfbm.io/P7:T10)

Next let's expand it 25ft to the north and 10ft to the east

<!-- tabs:start -->

#### **Discord**

```
!view 25n10e expand
```

#### **Url**

```
https://otfbm.io/P2:V10
```

<!-- tabs:end -->

![](https://otfbm.io/P2:V10)

Finally we'll shrink the view 30ft south and 10ft west

<!-- tabs:start -->

#### **Discord**

```
!view 30s10w reduce
```

#### **Url**

```
https://otfbm.io/P8:T10
```

<!-- tabs:end -->

![](https://otfbm.io/P8:T10)

## Dark Mode

There is also dark mode, if you prefer, with `-options d`

[Options](/pages/options.md) can give you further control over how the map looks.

_*Example*_

A 20x20 map with dark mode

<!-- tabs:start -->

#### **Discord**

```
!map -mapsize 20x20 -options d
```

#### **Url**

```
https://otfbm.io/@d/20x20
```

<!-- tabs:end -->
![](https://otfbm.io/@d/20x20)

The emptiness may leave a lot to be desired unless your battle is on the Positive (or Negative) Energy Plane, so you may want to add a [Background](/pages/backgrounds.md) next.

If you prefer a more grid paper and pencils feel, you can also create a map using [Objects](/pages/objects.md) and [Structures](/pages/structures.md).