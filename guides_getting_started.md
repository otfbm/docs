# Getting Started

If you're running the `!map` alias for the first time this is where you should start. 

> **Disclaimer**
This guide assumes you know the basic `!init` functions of Avrae: how to start an encounter, add monsters, add combatants, and generally run a combat. If you don't you can head over to [Avrae's documentation](https://avrae.readthedocs.io/en/latest/) to find out how.

## 1. Starting inintiative and setting up the map

First up, we start the initiative by typing the command:

```
!init begin
```

Once that is done, we need to add a character to the initiative order to whom we're going to attach the map. We recommend adding a dedicated character for this, instead of a player or a monster, to prevent the map from vanishing when a player exits combat or a monster is killed.

So our character is going to be called `DM`, but it can be called anything you want, `Map`, `Lair`, `Whatever`. And we’re going to set its initiative at 20 so it can also be used for Lair Actions, if needed:

```
!i add 0 DM -p 20
```

Next, we're going to attach the map itself to our `DM` character, to bring it up:

```
!map -mapattach DM
```

Without attaching a map to a character, every time you run the `!map` command the previous changes or settings are lost and the map reverts to its default. This way everything is saved.

## 2. Customizing the map

Now that you have a map going you're probably thinking that the default 10x10 grid isn't big enough. And you're right, we need to go bigger! So let's try making it a 26x14 grid instead:

```
!map -mapsize 26x14
```

Great, but it’s still a bland white background. Let's spice things up by adding a background image:

```
!map -mapbg https://i.imgur.com/WnTUKcJ.jpg 
```

Looking better. You can add any background you like provided you adhere to some requirements. The image needs to:
- line up with a 40px by 40px grid or things will be cropped;
- **be smaller than 1MB**.

Sweet. So now we have the map anchored to a character, set to a good size, and with a custom background. That’s a lot of commands to run separately. Luckily, you can use all those arguments on the same command instead:

```
!map -mapattach DM -mapsize 26x14 -mapbg https://i.imgur.com/WnTUKcJ.jpg
```

## 3. Adding combatants to the map

In the final step we're going to be adding some Goblins to the map. First you need to add them to initiative order:

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

Tada! The token should have moved to the new location, with an arrow showing where it came from.

Like monsters you can add your players to the map. Have them `!i join` the initiative order and place them on the map.

Congratulations, you now know the basics of how to run an encounter using the `!map` alias!
