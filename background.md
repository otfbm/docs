# Background Images

You can add images to your battle map by providing a link to an external image.

**Custom Backgrounds**
Callers can add custom backgrounds to their maps by providing the image's url in the map request.

Maps provided by callers are expected to meet the following requirements:

* Maps are expected to have a grid scale of 40 px
* Maps are expected to be fitted to the grid size requested in the url. So if a map is 23x12, then the caller is expected to provide a size of 23x12 when making a map request.

_**Example - Background**_
```
http://otfbm.io/E7p-Zombie/I3p-Zombie?bg=https://i.imgur.com/k99s0ch.jpg
```

**NOTE** - At this time there is a 1MB size limit to background images.

## Simple guide to making maps work with otfbm

Using software like Photoshop or GIMP:

* crop the image to top left/bottom right squares
* Count the number of squares wide and tall
* Resize the image to squares x 40 pixels
