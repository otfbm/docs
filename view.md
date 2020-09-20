# Setting Up The Grid

**Specifying Width and Height**

You can specify how much of a battle map you are looking at at any given time by specifying the number of cells wide and number of cells high you'd like to be looking at. (**Default 10x10**)

_Example_
```
https://otfbm.io/5x2/
```

![](https://otfbm.io/5x2/)

**Panning the map** 

You can also move what part of the map you are looking at around by prefixing the width and height values with a map cell the defines the top left corner of the view.

_Example_

The following will display a 5 cell wide by 2 cell high view starting at `m3`

```
https://otfbm.io/m3:5x2/
```

![](https://otfbm.io/m3:5x2/)

**Alternate syntax**

Another, simpler syntax makes it possible to display a viewport by a given top left cell and bottom right cell.

_Example_

The following will display a 5x2 grid starting in the cell `c3`

```
https://otfbm.io/c3:g4/
```

![](https://otfbm.io/c3:g4/)