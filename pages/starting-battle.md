# Starting Battle

## !init

Before we can begin doing anything with the map, we have to start a battle. Battle maps only function within the context of an encounter, and while you don't actually have to engage in battle (maybe the party is exploring a cave or castle), the absolute first thing we have to run is `!init begin`.

_*Example*_

Initiating an encounter

<!-- tabs:start -->

#### **Discord**

```
!init begin
```

or

```
!i begin
```

<!-- tabs:end -->

```
Everyone roll for initiative!
If you have a character set up with SheetManager: !init join
If it's a 5e monster: !init madd <monster name>
Otherwise: !init add <modifier> <name>
```

---

## Adding the Map

A map must be attached to a participant in battle. In order to avoid the map vanishing when a player or monster are removed, it is important to attach the map to a pseudo-participant named either `DM`, `Map`, or `Lair`. It is also useful to set this participant's initiative to 20 and use it for Lair Actions, if those are available.

_*Example*_

Adding a combatant named `DM` to the battle

<!-- tabs:start -->

#### **Discord**

```
!i add 0 DM -p 20
```

<!-- tabs:end -->

```
Current initiative: 0 (round 0)
===============================
  20: DM (map)
```

---

## Adding Combatants

A battle map is pretty lonely without tokens, which represent combatants. Players should type `!i join` to automatically roll initiative and join the battle, and the DM should run `!i madd <monster_name>` to add monsters. You can move tokens to starting positions with `!map -t <token_name> -move <coord>`. Players can use `!move <coord>` to initially place their token.

_*Example*_

Adding three goblins to the map

<!-- tabs:start -->

#### **Discord**

```
!i madd Goblin -n 3
!map -t GO1 -move d4
!map -t GO2 -move e7
!map -t GO3 -move a1
```

#### **Url**

```
https://otfbm.io/E7Mr-GO2/D4Mr-GO1/A1Mr-GO3
```

<!-- tabs:end -->

![](https://otfbm.io/E7Mr-GO2/D4Mr-GO1/A1Mr-GO3)

---

## Removing Combatants

Things are gonna die in battle, obviously. You can remove dead or retreated combatants from the map with `I remove <token_name>`. Technically this is an `!init` command, but most folks don't want to go all the way [over here](https://avrae.readthedocs.io/en/latest/cheatsheets/dm_combat.html#removing-from-combat) so we're including it here for completeness. You should really check out the [Avrae docs](https://avrae.readthedocs.io/en/latest/index.html) too though if you haven't already.

_*Example*_

Goblin1 and Goblin3 suddenly died seemingly out of nowhere. Goblin2 is scared and confused.

<!-- tabs:start -->

#### **Discord**

```
!i remove GO1
!i remove GO3
```

#### **Url**

```
https://otfbm.io/E7Mr-GO2
```

<!-- tabs:end -->

![](https://otfbm.io/E7Mr-GO2)
