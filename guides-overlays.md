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
" | `circletop,<radius>,<color>,<center>` | Draws a circle centered on the top left corner of a coordinate.
Cone | `cone,<size>,<color>,<start>,<aim>` | Draws a cone with start and aim coordinates.
Line | `line,<length>,<width>,<color>,<start>,<end>` | Draws a line with start and end coordinates.
Arrow | `arrow,<color>,<start>,<end>` | Draws an arrow with start and end coordinates.
Square | `square,<size>,<color>,<center>[,<aim>]` | Draws a square centered on a coordinate. Optional: aiming at a coordinate rotates the square.
" | `squaretop,<size>,<color>,<center>[,<aim>]` | Draws a square centered on the top left corner of a coordinate. Optional: aiming at a coordinate rotates the square.
