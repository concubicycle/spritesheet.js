# Credit
I didn't make this, this is created by [krzystof-o](https://github.com/krzysztof-o). I just forked and fixed some security issues by changing up dependencies.

![spritesheet.js](http://i.imgur.com/RcHZ2qZ.png)
==============

Spritesheet.js is command-line spritesheet (a.k.a. Texture Atlas) generator written in node.js.

### Supported spritesheet formats ###
* Starling / Sparrow
* JSON (i.e. PIXI.js)
* Easel.js
* cocos2d (i.e. version 2.x)
* cocos2d-v3 (i.e. version 3.x) 
* CSS (new!)

### Usage ###
**Command Line**
```bash
$ spritesheet-js assets/*.png
```
Options:
```bash
$ spritesheet-js
Usage: spritesheet-js [options] <files>

Options:
-f, --format  format of spritesheet (starling, sparrow, json, pixi.js, easel.js, cocos2d)                                                          [default: "json"]
-n, --name    name of generated spritesheet                                                                                                        [default: "spritesheet"]
-p, --path    path to export directory                                                                                                             [default: "."]
--fullpath    include path in file name                                                                                                            [default: false]
--prefix      prefix for image paths (css format only)                                                                                             [default: ""]
--trim        removes transparent whitespaces around images                                                                                        [default: false]
--square      texture should be s square                                                                                                           [default: false]
--powerOfTwo  texture width and height should be power of two                                                                                      [default: false]
--validate    check algorithm returned data                                                                                                        [default: false]
--algorithm   packing algorithm: growing-binpacking (default), binpacking (requires passing --width and --height options), vertical or horizontal  [default: "growing-binpacking"]
--width       width for binpacking                                                                                                                 [default: undefined]
--height      height for binpacking                                                                                                                [default: undefined]
--padding     padding between images in spritesheet                                                                                                [default: 0]
--scale       percentage scale                                                                                                                     [default: "100%"]
--fuzz        percentage fuzz factor (usually value of 1% is a good choice)                                                                        [default: ""]
```
**Node.js**
```javascript
var spritesheet = require('spritesheet-js');

spritesheet('assets/*.png', {format: 'json'}, function (err) {
if (err) throw err;

console.log('spritesheet successfully generated');
});
```
  
  
### Trimming / Cropping ###
Spritesheet.js can remove transparent whitespace around images. Thanks to that you can pack more assets into one spritesheet and it makes rendering a little bit faster.

*NOTE: Some libraries such as Easel.js dont't support this feature.*
![Trimming / Cropping](http://i.imgur.com/76OokJU.png)

### Installation ###
1. Install [ImageMagick](http://www.imagemagick.org/)
    - On versions 7.x and higher you must install the optional Legacy Tools
2. ```npm install spritesheet-js -g```

### Test ###
```
mocha test
```

--------------
Thanks [Przemys??aw Piekarski](http://www.behance.net/piekarski) for logo design and assets in examples.
