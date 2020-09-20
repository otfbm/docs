# Predefined Maps and Tokens

It is possible to define map setups in JSON format, upload them to publically accessible URL somewhere (eg. Discord) and then load them in later. This makes it possible to easily share map setups with others as well as maintain groups of token images that you can take with you from battle to battle.

Any values placed into the URL directly will be merged with and take precedence over predefined values. This makes it easy to load in predefined setups to use as a starting point and then configure them as needed for a specific battle.

## Loading in an existing map setup

The following map setup in JSON format:

```json
{
    "options": "@c72dh20",
    "board": "30x20",
    "background": "https://cdn.discordapp.com/attachments/742395958104686635/742396921485721640/3ddsh2jkmor41.jpg"
}
```

has been uploaded to

```
https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json
```

and so it can be loaded using the `load` query parameter (in a similar way to loading background images)

```
https://otfbm.io/b10b-Urzer?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json
```

![](https://otfbm.io/b10b-Urzer?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json)

## Defining Token Images

It's possible to define token images in a similar way. Whenever a token is used that has a label that matches a predefined token image, that image will automatically be used. It would in theory be possible to define and share a file with others that contained whole beastiaries worth of tokens.

To add token images, use the `tokenImages` property

```json
{
    "tokenImages": {
        "goblin": "https://media-waterdeep.cursecdn.com/avatars/thumbnails/0/351/1000/1000/636252777818652432.jpeg"
    }
}
```

Then, after loading the monster tokens in from the URL, goblin tokens automatically get the goblin token image applied. 

```
https://otfbm.io/a:15x5/a1r-goblin/b2r-goblin/c3r-goblin/?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757305182878171246/monsters.json
```

![](https://otfbm.io/a1:3x3/a1r-goblin/b2r-goblin/c3r-goblin/?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757305182878171246/monsters.json)

**N.B.** Several setups have been loaded in via multiple uses of the `load` query parameter. This makes it possible to compose setups together in ways that make sense. You may wish to maintain a setup for each map, a setup for your characters tokens and a setup for all the monster tokens you have collected.

## Token image pattern matching

Some limited pattern matching is possible for tokens so that its possible to match token sequences. The `#` character is used to match any number.
The following token images definition will match all of the following `goblin`, `goblin1`, `gob`, `gob1`, `go`, `go1`, etc.

```json
{
    "tokenImages": {
        "goblin#": "https://media-waterdeep.cursecdn.com/avatars/thumbnails/0/351/1000/1000/636252777818652432.jpeg",
        "gob#": "https://media-waterdeep.cursecdn.com/avatars/thumbnails/0/351/1000/1000/636252777818652432.jpeg",
        "go#": "https://media-waterdeep.cursecdn.com/avatars/thumbnails/0/351/1000/1000/636252777818652432.jpeg"
    }
}
```

The following example uses 3 setup files, all loaded in but the tokens themselves are all defined in the URL. Notice that the goblin labels are `go1`, `go2`, `go3` and `go4`. The setup defined in the previous example above matched all of these and so the goblin token image was used in all cases.

```
https://otfbm.io/a7:12x8/b10b-Urzer/b11b-Nissa/a10-Brie/a11-Oiman/j9r-go1/j10r-go2/j11r-go3/j12r-go4?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757303919012610168/characters.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757305182878171246/monsters.json
```

![](https://otfbm.io/a7:12x8/b10b-Urzer/b11b-Nissa/a10-Brie/a11-Oiman/j9r-go1/j10r-go2/j11r-go3/j12r-go4?load=https://cdn.discordapp.com/attachments/746474041577308301/757301430020341760/patreon-seafootgames.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757303919012610168/characters.json&load=https://cdn.discordapp.com/attachments/746474041577308301/757305182878171246/monsters.json)