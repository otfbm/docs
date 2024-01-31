# Fog of war

Fog of war allows you to only reveal certain parts of the map, or more map over time. Using `-fow` will activate fog of war on your map. From there you designate the top left square and the bottom right of the area you want to reveal, separated by a colon as in`-fow b2:d2`. Multiple areas can be revealed in this way by separating each set of coordinates with a comma `-fow b2:d2,d4:e8`.

**Note** - Fog of war will only be active if there is a background image loaded.

## Examples

### Adding fog of war

```
!map -fow b2:d4,f2:h4,b6:d8,f6:h8
```
![](https://otfbm.io/@d/*fb2d4/*ff2h4/*fb6d8/*ff6h8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)

### Removing fog of war
```
!map -addfow b2:d4,b6:d8
```
![](https://otfbm.io/@d/*fb2d4/*fb6d8/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)

### Make the whole map visible
```
!map -fow none
```
![](https://otfbm.io/@d/10x10/?load=https://cdn.discordapp.com/attachments/740988703689801850/763079108636049459/DeathHousev3.json)
