# Viewing The Grid

## Grid Size

The first thing you want to do is set your grid size. This can be achieved with `-mapsize <width>x<height>` where width is the horizontal scale of the grid in cells, and height is the vertical scale of the grid in cells. `!map -mapsize 5x7` will output a blank grid 5 cells wide by 7 cells tall, or 25 feet by 35 feet. In D&D and many other TTRPGs, a square is 5 feet, and some aliases like `!go` assume increments of 5 feet, so it helps to consider that when sizing your grid so your goblins aren't as large as houses.

By default, the grid is 10x10.

_*Example*_

A 5x7 map
```
!map -mapsize 5x7
```
![](https://otfbm.io/5x7)

## Grid Pan

You can also `!view` different parts of the map by panning, which sets the top left corner to whatever grid location is specified.

_*Example*_

A 5x2 map view starting at **M3**

```
!view M3:Q6
```
or
```
!view M3:5x4
```

![](https://otfbm.io/m3:q6/)

## Dark Mode

There is also dark mode, if you prefer `-options d`

[Options](/pages/options.md) can give you further control over how the map looks.

_*Example*_

A 20x20 map with dark mode
```
!map -mapsize 20x20 -options d
```
![](https://otfbm.io/@d/20x20)

The emptiness may leave a lot to be desired unless your battle is on the Positive (or Negative) Energy Plane, so you may want to add a [Background](/pages/backgrounds.md) next.

If you prefer a more grid paper and pencils feel, you can also create a map using [Objects](/pages/objects.md) and [Structures](/pages/structures.md).