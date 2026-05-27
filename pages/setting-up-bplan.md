# Setting up battles using `!bplan` and `!map`

Now that you know the basics of how to use `!map`, you can take advantage of another alias that helps make setting up an encounter much faster.  The `!bplan` alias allows you to set up an encounter and all of its combatants in advance.  By combining this time saver with the `!map` alias, we can get an encounter up and running during your session by running only two or three commands.  We’ll go through three different ways to work with both of these aliases.

Keep in mind that throughout this guide we will use brackets to signify `<required items>` and `[optional items]`.

## Beginner Level
 - All examples can be run in discord if running into issues

#### 1.) First with !bplan we will create

- Run the command: `!bplan new "<bplan name>"` Ex: `!bplan new test`. This creates the bplan itself to modify. Note the quotation marks.  These are not required, but will help prevent potential mismatches down the line.

- Next add/modify the monsters 

`!bplan add test !i madd Ogre -n 2`

- If you want to add more monsters: `!bplan add “<bplan name>” !i madd “<monster name>” [args]`

`!bplan add test !i madd "Orc Mauler" !i madd "Orc Mauler" !i madd "Orc Mauler" !i madd "Orc Mauler"`

- If you need to remove monsters you previously added you will need to know what command line the monster is on and use that number: `!bplan remove “<bplan name>” <line #>`

`!bplan remove test 3`

- When you're done adding monsters you can start your bplan with: `!bplan begin <bplan name>`

`!bplan begin test`


#### 2.) Next with !map

- Setup you map bg, options, size, etc. for your encounter. 

- Run the command: `!bplan map "<bplan name>" set <map cofigurations>` This saves the map to this bplan. Running a saved map will override the  original map.

`!bplan map test set -mapsize 10x10 -options dc75`

- After you have gotten your map background, options, size, etc. setup now setup your monsters locations, size, token image, overlays, etc.

- After you have set up your encounter, run the command `!bplan begin <bplan name>` to see if our bplan functions correctly 

`!bplan begin test`

- Then have your players join combat and have fun

## Moderate Level

You can add additional arguments in `!bplan` to spend less time setting things up in `!map`

- When adding monsters you can add notes which will allow you to place them in your map, set their size, and color right when you run `!bplan begin`

`!bplan add test !i madd "Orc Mauler" -note "Location: A5 | Size: S"`

**More help to come**

> Note that you can find the full list of valid size and color abbreviations by running `!map help`