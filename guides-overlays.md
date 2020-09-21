# Overlays

This guide will show you how to draw overlays on top of your map. They can be used for a number of different reasons: to highlight something, to draw a structure or, mainly, to visually represent a spell's area of effect.

> **Disclaimer**
This guide assumes you know the basic functions of the `!map` alias. If you don't you can head over to our [Getting Started Guide](http://docs.otfbm.com/#/guides_getting_started) to learn them.

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
Circle | `circletop,<radius>,<color>,<center>` | Draws a circle from the top left coordinate.
Circle | `circlecorner,<radius>,<color>,<topleftcorner>` | Draws a circle centered on the top left corner of a coordinate.
Cone | `cone,<size>,<color>,<start>,<aim>` | Draws a cone with start and aim coordinates.
Line | `line,<length>,<width>,<color>,<start>,<end>` | Draws a line with start and end coordinates.
Arrow | `arrow,<color>,<start>,<end>` | Draws an arrow with start and end coordinates.
Square | `square,<size>,<color>,<center>[,<aim>]` | Draws a square with its top-left on a coordinate. Optional: aim to cast it towards a coordinate, using its side as a pivot point.
Square | `squaretop,<size>,<color>,<center>[,<aim>]` | Draws a square with its top-left on a coordinate. Optional: aim to cast it towards a coordinate, using its corner as a pivot point.

One of the additional arguments you can add to `-over` is `-t <combatant>`. An `-over` command without `-t` defaults to showing only for one run of `!map`. By targeting a combatant, that overlay sticks to it and remains visible until it's removed.

## 2. Overlays as spells

Overlays excel at showing spell effects on the battlefield. There is a list of ready-made spell overlays you can check:

````
!map -spellbook
````

This list contains most, if not all, official D&D area of effect spells. So, if you want to look up a specific spell:

```
!map -spellbook -search <Spell Name>
```

Now, let's get physical...
