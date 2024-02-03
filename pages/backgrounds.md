# Background Images

You can add custom background images to your map by providing the `-bg` option.

```
!map -bg https://i.imgur.com/9aG2VlY.jpg
```
![](https://otfbm.io/25x20?bg=https://i.imgur.com/9aG2VlY.jpg)

It is VERY important to remember that the url must have an extension, and that extension must be jpg, jpeg, gif, or png. OTFBM does not support webp as of yet. Ironically enough, Imgur is a host notorious for removing extensions in their links, so the recommended method is typically to upload the map as an attachment in Discord and then using the resulting CDN link for the alias.

## Adjusting Grids to Maps

### Background Offset

It is a rare but joyous occasion when you add a background and it fits perfectly. For all those other times, there are ways to fix it.

If your map background does not start at the top left corner of the image, you can offset it with `!map -options -o<x_offset>:<y_offset>` where x_offset shifts the background to the right if positive, and to the left if negative; y_offset does the same except it shifts up if positive and down if negative.

To move the background image by 30px to the left and 20px up, use

```
!map -bg https://i.imgur.com/9aG2VlY.jpg -options o30:20`
```
![](https://otfbm.io/@o30:20/50x50?bg=https://i.imgur.com/9aG2VlY.jpg)

### Grid Size

Sometimes the grid doesn't fully fit your background. You can adjust the grid size by using `-options c<size>` where size is the cell size in pixels. By default it is 40, but can be set as small as 20 or as large as 100. A good rule of thumb is to resize your image using an image editor to be a nice round number divisible by 10 in both width and height, then calculate the cell size you need based on the grid size. TODO: Fill in details here later when I can find them in Discord.

#### Example


## Default Options

* The maps grid defaults to a grid scale of 40px
* Maps assume that the grid of an image starts in the very top left corner
* Zoom level `-z` starts at 1

### Adjusting the gridsize

Adjust the gridsize of the map (in pixels) using the map option `c`. (for cell)

#### Example

To set a gridsize of `50px` use the option `@c50`

```
http://otfbm.io/@c50
```
![](http://otfbm.io/@c50)

## Prepackaged Maps

Some maps are included with the alias if you want to try out a preconfigured map before diving into a custom one. To see the list, use `!map maplist`, and then `!map -loadmap <name>` to load the one you want to use. You can also save custom maps, use `!map -savemap <name>` to tuck it away for later, and when the DM TPK's your entire group, take revenge by using `!map -deletemap <name>` to wipe the painful memory from your Discord server forever.

## Background Maps from DynamicDungeons

A super cool artist has allowed us to use some of his maps. please check out their Patreon at the link below.
```
https://www.patreon.com/dynamicdungeons
```

_Example_

```
https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/9aG2VlY.jpg
```

![](https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/9aG2VlY.jpg)

The following can be used as a background as shown below

**Forest** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/9aG2VlY.jpg`

**Desert** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/65k1rE4.jpg`

**Ship Foredeck** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/5ODcwpV.jpg`

**Ship Maindeck** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/YlPvZzZ.jpg`

**Ship Upperdeck** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/NM5qPmS.jpg`

**Winter Forest** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/Kiasj9W.jpg`

**Market Square** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/FJd0Iv0.jpg`

**Basic Dungeon Floor** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/mxbQmxY.jpg`

**Graveyard** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/z3vLqEQ.jpg`

**Haunted Cemetary** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/HQl9k5o.jpg`

**Haunted Cathedral** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/5faalf2.jpg`

**Grassy Field** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/Zx2jHDC.jpg`

**Dragons Lair** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/PplwMVB.jpg`

**Rocky Path** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/O2tMCFC.jpg`

**Cellar** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/BhA8JQs.jpg`

**Main Floor Inn** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/jIpAjkT.jpg`

**City Jail** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/Eh3IEQb.jpg`

**Boat** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/9aYJJ3u.jpg`

**Underground Fight Pit** - `https://otfbm.io/26x14/@dc60/e5-Fighter?bg=https://i.imgur.com/WgZSt8g.jpg`
