# Fog of War

Fog of war allows you to only reveal certain parts of the map, or more map over time. Using `-fow` will activate fog of war on your map. From there you designate the top left square and the bottom right of the area you want to reveal, separated by a colon as in`-fow b2:d2`. Multiple areas can be revealed in this way by separating each set of coordinates with a comma `-fow b2:d2,d4:e8`.

**Note** - Fog of war will only be active if there is a background image loaded.

## Clearing Fog of War

Clearing the fog of war can be done as granularly as you wish to bother with. You can simulate each individual's vision range in dim areas and clear the fog of war as they explore if you're masochistic, or just expand rooms as doors are opened and torches are lit for a cool effect that won't take two years to type in.

_*Example*_

<!-- tabs:start -->

##### Discord

```
!map -fow b2:d4,f2:h4,b6:d8,f6:h8
```

##### Url

```
https://otfbm.io/@d/*fb2d4/*ff2h4/*fb6d8/*ff6h8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json
```

<!-- tabs:end -->

![](https://otfbm.io/@d/*fb2d4/*ff2h4/*fb6d8/*ff6h8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)

## Replacing Fog of War

You can add it back to an explored area as well, perhaps if the group has all left a room or a darkness spell is cast.

_*Example*_

<!-- tabs:start -->

##### Discord

```
!map -addfow b2:d4,b6:d8
```

##### Url

```
https://otfbm.io/@d/*fb2d4/*fb6d8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json
```

<!-- tabs:end -->

![](https://otfbm.io/@d/*fb2d4/*fb6d8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)

## Removing Fog of War

You can make the whole map visible again easily.

_*Example*_

<!-- tabs:start -->

##### Discord

```
!map -fow none
```

##### Url

```
https://otfbm.io/@d/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json
```

<!-- tabs:end -->

![](https://otfbm.io/@d/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)
