# Tokens

**Defining tokens**
Tokens are optional and you can define as many as you need separating each with the `/` character. Tokens are defined with a letter and a number. The letter represents the X axis and the number, the Y axis so `C7` in X,Y would be `3,7` ie. 3 grid squares in from the left, 7 down from the top.

**Token colors**
You can color tokens a limited number of colors using a letter indicator. Use any of the following letters with the token definition to change its color.

`w` for `white`  
`bk` or `k` for `black`  
`gy` or `e` or `a` for `grey`  
`r` for `red`  
`g` for `green`  
`b` for `blue`  
`y` for `yellow`  
`p` for `purple`  
`c` for `cyan`  
`bn` or `n` for `brown`  
`o` for `orange`  
`pk` for `pink`

So to make a token at `F3` gold colored, just add `y` eg. `F3y`

Colour can also be specifed with `~` and a 3 or 6 digit hex code. E.g. `~f80` or `~f98010`.

_**Example**_
```
http://otfbm.io/D3p/A1r/G4y
```

![](http://otfbm.io/D3p/A1r/G4y)


**Token sizes**
You can change the token sizes to any of D&Ds monster sizes by adding a letter indicator. Use any of the following letters to indicate size:

`T` for `tiny`  
`S` for `small`  
`M` for `medium`  
`L` for `large`  
`H` for `huge`  
`G` for `gargantuan`  

So to make a token at `G5` large sized, just add `L` eg. `G5L`

_**Example**_
```
http://otfbm.io/D3L/A1M/G4S
```

![](http://otfbm.io/D3L/A1M/G4S)

**Token Labels**
You can add text labels to tokens. When doing so be careful not to use too much text or it will run outside the edge of the token. Labels are added using a `-` character and then the label. Eg. `-Goblin`

_**Example**_
```
http://otfbm.io/D3-Goblin/A1-Goblin/G4-Fighter
```

![](http://otfbm.io/D3-Goblin/A1-Goblin/G4-Fighter)

*Note* 
Labels have been added to tokens with images and numbered sequences. If the token is large enough, the full token label will be displayed. If the token is too small for this only the number will show.

**Token Sequence**
Adding tokens is not case sensitive.  Tokens are however sequence sensitive. Use the following sequence when defining a token within the url as shown below. As well as an example of creating a gargantuan, red token at D4 in the grid.  

 `column` `row` `size` `color` `-label`

_**Example**_
```
http://otfbm.io/D4GR-Warlock
```

![](http://otfbm.io/D4GR-Warlock)

**Note** - *When defining a gargantuan token, you need to include a color. `D4G` would place a green token on the grid, `D4GBK` would place a gargantuan black token on the grid (black being the default color).*

**Token Images**
Adding images to tokens is currently supported by preloading images at the following URL.  
```
https://token.otfbm.io/meta/<base64 of full URL>
```  
  
**NOTE** - *to convert a full URL to base64, see a site like ```http://www.base64url.com/```*  
  
once you generate the token code, insert it into the map URL for the desired token.  
```
https://otfbm.io/d3h-Urzer~<shortcode>
```  

![](https://otfbm.io/d3h-Urzer~6yts4)

**Facial Recognition on tokens**  
Token facial recognition can now be intentionally turned off on a case by case basis
Defining a token segment with a trailing ~ character will force the original token to be displayed rather than the one that was created using facial recognition.

Example. 
* with facial recognition /a2-satyr~wcqj3/
* without facial recognition /a2-satyr~wcqj3~/

```
https://otfbm.io/2x1/@c60/a1-satyr~wcqj3/b1-satyr~wcqj3~/
```

![](https://otfbm.io/2x1/@c60/a1-satyr~wcqj3/b1-satyr~wcqj3~/)
