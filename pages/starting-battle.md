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

Adding a combatant named `Map` to the battle

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

## Moving Combatants

There are multiple ways to move tokens, including player tokens on a player's initiative. `!move` is used for direct movement, while `!go` is used for directional movement. To move multiple tokens at once you can invoke `!map -t <token> -move <coord>` for each token.

_*Example*_

Moving Goblin3 20 feet to D1 during their initiative

<!-- tabs:start -->

#### **Discord**

```
!move D1
```

#### **Url**

```
https://otfbm.io/E7Mr-GO2/D4Mr-GO1/D1Mr-GO3/E1Mg-Fighty
```

<!-- tabs:end -->

![](https://otfbm.io/E7Mr-GO2/D4Mr-GO1/D1Mr-GO3/E1Mg-Fighty)

Unfortunately, Fighty had readied a shove action just in case Goblin3 did just that. Goblin3 gets thrown 5 feet backward. The DM can use the following to move any token with `!map -t <token_name> -move <coord>`. We'll throw an explosion in just for fun.

<!-- tabs:start -->

#### **Discord**

```
!map -t GO3 -move C1
!map -object D1:ex
```

#### **Url**

```
https://otfbm.io/d1$ex/E7Mr-GO2/D4Mr-GO1/C1Mr-GO3/E1Mg-Fighty
```

<!-- tabs:end -->

![](https://otfbm.io/d1$ex/E7Mr-GO2/D4Mr-GO1/C1Mr-GO3/E1Mg-Fighty)

Goblin1 wants to heal Goblin3, but definitely doesn't want that smoke. They use `!go` to tactically maneuver towards Goblin3

<!-- tabs:start -->

#### **Discord**

```
!go 10nw5n
```

#### **Url**

```
https://otfbm.io/E7Mr-GO2/B1Mr-GO1/C1Mr-GO3/E1Mg-Fighty
```

<!-- tabs:end -->

![](https://otfbm.io/E7Mr-GO2/B1Mr-GO1/C1Mr-GO3/E1Mg-Fighty)