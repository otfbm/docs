# Overlays

This guide will show you how to draw overlays on top of your map. They can be used for a number of different reasons: to highlight something, to draw a structure or, mainly, to visually represent a spell's area of effect.

> **Disclaimer**
This guide assumes you know the basic functions of the `!map` alias. If you don't, you can head over to our [Getting Started Guide](http://docs.otfbm.com/#/guides_getting_started) to learn them.

## 1. The basics

First, a side note: we'll use some shorthand to signify \<Required Information\> and \[Optional Information\].

Alright, let's dive in. The basic command structure for adding an overlay is:

```
!map -over <shape>,<size>,<color>,<location> [additional arguments]
```

This command will be slightly different depending on the shape.  Let’s break this apart, shall we?
- `<shape>` - is what the overlay will look like on the map. You have circles, cones, lines (which are basically rectangles), arrows, and squares.
- `<size>` - will vary depending on the shape. Circles will ask for a radius, cones reach, lines length and width, and squares side length. All sizes are in feet (ft).
- `<color>` - a table with valid colors can be seen in the [Tokens' page](http://docs.otfbm.com/#/tokens).
- `<location>` - also depends on the shape and can be: where the shape's center is; where it's starting and end coordinates are (arrows); where the shape's aiming at; or where it's targeting at, attaching the overlay to a combatant, for instance `Paladin auras` or a combatant's `Body odor`. Some shapes/ spells can even have both a target and an aim. For example, `Dragon's Breath` where the combatant targets a willing creature (1st location) that aims at an area (2nd location). Two locations. One spell.

Here are all the possible combinations of the previous arguments:

Shape | Command | Explanation
:--- | :--- | :---
Circle | `circle,<radius>,<color>,<center>` | Draws a circle centered on a coordinate.
Circle | `circletop,<radius>,<color>,<topleft>` | Draws a circle with its top-left on a coordinate.
Circle | `circlecorner,<radius>,<color>,<topleft>` | Draws a circle centered on the top-left corner of a coordinate.
Cone | `cone,<size>,<color>,<start>,<aim>` | Draws a cone with start and aim coordinates.
Line | `line,<length>,<width>,<color>,<start>,<end>` | Draws a line with start and end coordinates.
Arrow | `arrow,<color>,<start>,<end>` | Draws an arrow with start and end coordinates.
Square | `square,<size>,<color>,<center>[,<aim>]` | Draws a square with its top-left on a coordinate. Optional: aim to cast it towards a coordinate, using its side as a pivot point.
Square | `squaretop,<size>,<color>,<center>[,<aim>]` | Draws a square with its top-left on a coordinate. Optional: aim to cast it towards a coordinate, using its corner as a pivot point.

### Your overlay keeps disappearing?

If the overlay has no `-aim`, just add `-t <combatant>` to your `-over` command:

```
!map -over circle,15,R,H5 -t GO1
```

Without a `-t`, an overlay defaults to showing only once. This means that the next time you run `!map` it won't be there. Target a combatant to stick an overlay to it and it'll remain visible until removed. It will also follow the target wherever he moves on the map.

If the overlay has both a `-t` and an `-aim` we have to force it to `|stick` to the `-aim`:

```
!map -over square,5,G,D8 -t GO2 -aim D8|stick
```

## 2. Overlays as spells

Overlays excel at showing spell effects on the battlefield. There is a list of ready-made spell overlays you can check by running:

````
!map -spellbook
````

This list contains most, if not all, official D&D area of effect spells. Next to each spell is an indication of whether you need to specify a `-t` or `-aim` location.

### Practical example

Now, let's get physical. Let's say you're the DM and, on its turn, you want your Druid enemy `DR1` to cast `Entangle` on an unsuspecting player named `Prixaris` located on `E3`. First we're going to look up that specific spell:

```
!map -spellbook -search Entangle
```

The spellbook should say it requires a `-t` and an `-aim`. Let's break that down:
- `-t` should be the targeted player, but it could be more than one. In this particular example it's just Prixaris. What this does is look in `!init` if the effect exists and attach the overlay to it. That way, when the effect is gone, the next time you run a `!map` command, the overlay goes too;
- `-aim` is the area where we're aiming the spell at. That'll be around `Prixaris`.

With that being said, we first need to cast the spell in `!init`:

```
!init cast Entangle -t Prixaris
```

Let's assume `Prixaris` fails the saving throw and gets entangled, gaining `restrained` as an effect. We'll then draw the overlay spell on the map as well. The overlay will remain visible until the effect is removed or the Druid is killed:

```
!map -spell Entangle -t Prixaris -aim E3
```

## 3. Custom spell overlays

Using the spellbook is all fine and dandy, but what if your spell isn't there? Don't you worry because you can save your own spell overlays on your spellbook, for quick access. Let's create our very own special spell, Red Goat's Dimensional Trap Door. A 20 ft, red, square shaped spell overlay that requires aim:

```
!map -saveoverlay “Red Goat's Dimensional Trap Door”:square,20,R,{aim}
```

You can also remove any custom spell overlays from your spellbook:

```
!map -deleteoverlay "Red Goat's Dimensional Trap Door”
```

Congratulations, you are now a overlay wizard. Check out our other guides to up your `!map` game.
