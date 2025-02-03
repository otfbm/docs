**[Check here for updated lists of working image hosts](/pages/image-hosts)**

# Background Images

You can add custom background images to your map by providing the `-bg` option.

_*Example*_

A 25x20 map with the provided Forest background

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg
```

#### **Url**

```
https://otfbm.io/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg
```

<!-- tabs:end -->

![](https://otfbm.io/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg)

It is very important to remember that the url must have an extension, and that extension must be jpg, jpeg, gif, or png. OTFBM does not support webp as of yet. A list of working and non-working image hosting sites is available [here](/pages/image-hosts).

It is a rare but joyous occasion when you add a background and it fits perfectly. For all those other times, there are ways to fix it.

## Background Offset

If your map background does not start at the top left corner of the image, you can offset it with `!map -options -o<x_offset>:<y_offset>` where x_offset shifts the background to the right and y_offset will shift it down. It is currently not possible to use negative numbers to go left and up.

_*Example*_

The Forest map offset 30px right and 20px down

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg -options o30:20`
```

#### **Url**

```
https://otfbm.io/@o30:20/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg
```

<!-- tabs:end -->

![](https://otfbm.io/@o30:20/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg)

## Cell Size

Sometimes the grid doesn't fully fit your background, especially if it already has a grid. You can adjust the cell size by using `-options c<size>` where size is the cell size in pixels. By default it is 40, but can be set as small as 20 or as large as 100. A good rule of thumb is to resize your image using an image editor to be a nice round number divisible by 10 in both width and height, then calculate the cell size you need based on the grid size. TODO: Fill in details here later when I can find them in Discord.

_*Example*_

The Forest map with 60px cells

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg -options c60
```

#### **Url**

```
https://otfbm.io/@c60/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg
```

<!-- tabs:end -->

![](https://otfbm.io/@c60/25x20?bg=https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg)

## Ready to Use Maps

Some maps are included with the alias if you want to try out a preconfigured map before diving into a custom one. To see the list, use `!map maplist`. You can also save maps for later using `!map -savemap <name>` to tuck it away, and `!map -loadmap <name>` to load it back in, and when the DM TPK's your entire group, take revenge by using `!map -deletemap <name>` to wipe the painful memory from your Discord server forever.

Note that a map saved via `!map -savemap` will only be available on the same server it was saved on. To share it with another server, and learn a bit more about how the sausage is made, see [Advanced Usage](/pages/advanced.md).

### Background Maps from DynamicDungeons

A super cool artist has allowed us to use some of his maps. please check out their [Patreon](https://www.patreon.com/dynamicdungeons) at the link below.

The following can be used as a background, just paste the url after `!map -bg `.

Note this is the same list that is generated when running `!map maplist`.

**Forest** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest.jpeg`

**Desert** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/desert.jpeg`

**Ship Foredeck** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/ship-fd.jpeg`

**Ship Maindeck** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/ship-md.jpeg`

**Ship Upperdeck** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/ship-ud.jpeg`

**Winter Forest** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/forest-win.jpeg`

**Market Square** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/market.jpeg`

**Basic Dungeon Floor** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/tiles.jpeg`

**Graveyard** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/graveyard.jpeg`

**Haunted Cemetary** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/haunted.jpeg`

**Haunted Cathedral** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/cathedral.jpeg`

**Grassy Field** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/field.jpeg`

**Dragons Lair** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/lair.jpeg`

**Rocky Path** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/mountains.jpeg`

**Cellar** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/cellar.jpeg`

**Main Floor Inn** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/inn.jpeg`

**City Jail** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/jail.jpeg`

**Boat** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/boat.jpeg`

**Underground Fight Pit** - `https://raw.githubusercontent.com/otfbm/img/refs/heads/main/pit.jpeg`
