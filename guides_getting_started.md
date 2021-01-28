# Getting Started

If you're running the `!map` alias for the first time look no further. This guide will teach you how to set up a map, customize it, place characters as tokens, and move them. Check out our other guides if you've already got a handle on the `!map` alias.

> **Disclaimer**
This guide assumes you know the basic `!init` functions of Avrae: how to start an encounter, add monsters, add combatants, and generally run a combat. If you don't you can head over to [Avrae's documentation](https://avrae.readthedocs.io/en/latest/) to find out how.

## 1. Starting initiative and adding our map as a combatant

First up, we enter initiative by typing the command:

```
!init begin
```

Once that is done, we need to add a combatant to the initiative order onto whom the map is going to be automatically attached. Attaching a map allows every change that's made to it to be saved. We recommend adding a dedicated combatant for this, instead of a player or a monster, to prevent the map from vanishing when a player exits combat, or a monster is killed.

So our combatant is going to be called `DM`, but it can also be `Map` or `Lair`. Either name triggers the automatic attachment of the map. And we’re going to set its initiative at 20 so it can also be used for Lair Actions, if needed:

```
!i add 0 DM -p 20
```

## 2. Launching the map and customizing it

Next, we're going to bring up the map:

```
!map
```

Now that you have a map going, you're probably thinking that the default 10x10 grid isn't big enough. And you're right, we need to go bigger! So, let's try making it a 26x14 grid instead:

```
!map -mapsize 26x14
```

Great, but it’s still a bland white background. Let's spice things up by adding a background image:

```
!map -bg https://i.imgur.com/WnTUKcJ.jpg 
```

Looking better. You can add any background you like with the following caveats:
- images larger than 1MB may be resized or lose resolution unit they're reduced to that file size;
- since the default grid size is 40px by 40px the background image might not line up. If that's the case, check out our [Advanced Guides]() to find out how to change the grid size or offset the background image.

Sweet. So now we have the map anchored to the initiative order through a specific combatant, set to a good size, and with a custom background. That’s a lot of commands to run separately. Luckily, you can use all those arguments on the same command instead:

```
!map -mapsize 26x14 -bg https://i.imgur.com/WnTUKcJ.jpg
```

## 3. Adding combatants to the map

Finally, we're going to be adding some monsters to the map. Three Goblins, to make it more interesting. But first we need to add them to the initiative order:

```
!init madd Goblin -n 3
```

Now we're going to add our trio to the map, each in its own specific location. By default, their generated names should be GO1, GO2, and GO3:

```
!map -t GO1 -move d4
!map -t GO2 -move e7
!map -t GO3 -move a1
```

Three colourful tokens should have appeared. Notice that the `-move` argument, as its name implies, is used both for placing characters on the map and also for moving them. So, if you'd like GO2 to move from E7 to G3:

```
!map -t GO2 -move g3
```

Tada! The token is now in its new location, with an arrow showing where it came from to boot.

Like monsters you can add your players to the map. Have them `!init join` the initiative order and place them on the map using their names, just like we did with the Goblins.

Congratulations, you now know the basics of how to run an encounter using the `!map` alias! But this is just the beginning. Check out our other guides to up your `!map` game.
