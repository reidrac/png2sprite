png2scr.py
==========

This is a simple tool to convert a 24 or 32 bit PNG image to
ZX Spectrum sprite to be used with SP1 library.

For example:
```
$ png2sprite.py -i ship ship.png > ship.h
```

The tool will generate a C array with the sprite data.

The colors used are:

 * ink: white (rgb 205, 205, 205)
 * paper: red (rgb 205, 0, 0)
 * mask: black (rgb 0, 0, 0)

When including several sprites in your project, SP1 will need padding before and after each sprite. If the sprites are put one after the other, you'll only need to add padding before the first included one like this:

```
// assuming masked sprites
const uchar sprite_pad[] = { 0xff, 0x0, 0xff, 0x0, 0xff, 0x0, 0xff, 0x0 };
#include "sprite1.h"
#include "sprite2.h"
...
```


Requirements
------------

The tool requires `PIL` library (or `Pillow`) and `argparse` if
you're using Python 2 < 2.7.

It should work both in Python 2 and Python 3.


License
-------

The tool is distribute under MIT license (read the beginning of
the script for a copy of the license).

