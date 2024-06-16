**Imgur.com is not a reliable host anymore. A solution is being worked on, and workarounds are availble on Discord**

# Background Images

You can add custom background images to your map by providing the `-bg` option.

_*Example*_

A 25x20 map with the provided Forest background

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://i.imgur.com/9aG2VlY.jpg
```

#### **Url**

```
https://otfbm.io/25x20?bg=https://i.imgur.com/9aG2VlY.jpg
```

<!-- tabs:end -->

![](https://otfbm.io/25x20?bg=https://i.imgur.com/9aG2VlY.jpg)

It is very important to remember that the url must have an extension, and that extension must be jpg, jpeg, gif, or png. OTFBM does not support webp as of yet. Ironically enough, Imgur is a host notorious for removing extensions in their links, ~~so the recommended method is typically to upload the map as an attachment in Discord and then using the resulting CDN link for the alias.~~ currently we recommend using imgbb.com as they provide clean urls for OTFBM.

It is a rare but joyous occasion when you add a background and it fits perfectly. For all those other times, there are ways to fix it.

## Background Offset

If your map background does not start at the top left corner of the image, you can offset it with `!map -options -o<x_offset>:<y_offset>` where x_offset shifts the background to the right and y_offset will shift it down. It is currently not possible to use negative numbers to go left and up.

_*Example*_

The Forest map offset 30px right and 20px down

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://i.imgur.com/9aG2VlY.jpg -options o30:20`
```

#### **Url**

```
https://otfbm.io/@o30:20/25x20?bg=https://i.imgur.com/9aG2VlY.jpg
```

<!-- tabs:end -->

![](https://otfbm.io/@o30:20/25x20?bg=https://i.imgur.com/9aG2VlY.jpg)

## Cell Size

Sometimes the grid doesn't fully fit your background, especially if it already has a grid. You can adjust the cell size by using `-options c<size>` where size is the cell size in pixels. By default it is 40, but can be set as small as 20 or as large as 100. A good rule of thumb is to resize your image using an image editor to be a nice round number divisible by 10 in both width and height, then calculate the cell size you need based on the grid size. TODO: Fill in details here later when I can find them in Discord.

_*Example*_

The Forest map with 60px cells

<!-- tabs:start -->

#### **Discord**

```
!map -bg https://i.imgur.com/9aG2VlY.jpg -options c60
```

#### **Url**

```
https://otfbm.io/@c60/25x20?bg=https://i.imgur.com/9aG2VlY.jpg
```

<!-- tabs:end -->

![](https://otfbm.io/@c60/25x20?bg=https://i.imgur.com/9aG2VlY.jpg)

## Ready to Use Maps

Some maps are included with the alias if you want to try out a preconfigured map before diving into a custom one. To see the list, use `!map maplist`. You can also save maps for later using `!map -savemap <name>` to tuck it away, and `!map -loadmap <name>` to load it back in, and when the DM TPK's your entire group, take revenge by using `!map -deletemap <name>` to wipe the painful memory from your Discord server forever.

Note that a map saved via `!map -savemap` will only be available on the same server it was saved on. To share it with another server, and learn a bit more about how the sausage is made, see [Advanced Usage](/pages/advanced.md).

### Background Maps from DynamicDungeons

A super cool artist has allowed us to use some of his maps. please check out their [Patreon](https://www.patreon.com/dynamicdungeons) at the link below.

The following can be used as a background, just paste the url after `!map -bg `.

Note this is the same list that is generated when running `!map maplist`.

**Forest** - `https://i.imgur.com/9aG2VlY.jpg`

**Desert** - `https://i.imgur.com/65k1rE4.jpg`

**Ship Foredeck** - `https://i.imgur.com/5ODcwpV.jpg`

**Ship Maindeck** - `https://i.imgur.com/YlPvZzZ.jpg`

**Ship Upperdeck** - `https://i.imgur.com/NM5qPmS.jpg`

**Winter Forest** - `https://i.imgur.com/Kiasj9W.jpg`

**Market Square** - `https://i.imgur.com/FJd0Iv0.jpg`

**Basic Dungeon Floor** - `https://i.imgur.com/mxbQmxY.jpg`

**Graveyard** - `https://i.imgur.com/z3vLqEQ.jpg`

**Haunted Cemetary** - `https://i.imgur.com/HQl9k5o.jpg`

**Haunted Cathedral** - `https://i.imgur.com/5faalf2.jpg`

**Grassy Field** - `https://i.imgur.com/Zx2jHDC.jpg`

**Dragons Lair** - `https://i.imgur.com/PplwMVB.jpg`

**Rocky Path** - `https://i.imgur.com/O2tMCFC.jpg`

**Cellar** - `https://i.imgur.com/BhA8JQs.jpg`

**Main Floor Inn** - `https://i.imgur.com/jIpAjkT.jpg`

**City Jail** - `https://i.imgur.com/Eh3IEQb.jpg`

**Boat** - `https://i.imgur.com/9aYJJ3u.jpg`

**Underground Fight Pit** - `https://i.imgur.com/WgZSt8g.jpg`
