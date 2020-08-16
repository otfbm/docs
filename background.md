# Background Images


## The basics

You can add custom background images to your map by providing a link to an external image with the query parameter `bg`

### Example

```
http://otfbm.io?bg=https://i.imgur.com/k99s0ch.jpg
```

## Maps defaults:

* The maps grid defaults to a grid scale of `40px`
* Maps assume that the grid of an image starts in the very top left corner

## Setting up OTFBM backgrounds

When the defaults do not apply to the background image you are using, you can adjust the position and grid scale to line things up.

### Adjusting the gridsize

Adjust the gridsize of the map (in pixels) using the map option `c`. (for cell)

#### Example 

To set a gridsize of `50px` use the option `@c50`

```
http://otfbm.io/@c50
```

### Adjusting the background image position

When the grid does not start in the top left corner of the background image, you can push the background image around so that it does. This is specified as an x,y coordinate offset in pixels using the map option `o` (for offset)

#### Example

To move the background image by `30px` to the left and `20px` up, use the map option `@o30:20`

```
http://otfbm.io/@o30:20
```

### Image Size Limits

Currently, there is a 1mb background image size limit. We hope to raise this in future once we have optimised the way we handle things. If you run into this issue, we recommend converting your image from png to jpeg and/or resizing the image you want to use. If you found this image somewhere on the web. Download it, use an image editing program like Photoshop or Gimp to create a file that is under 1mb, upload it to Discord somewhere and copy the URL to use with OTFBM.