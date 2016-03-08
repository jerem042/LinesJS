## LinesJS

By [Carl Gorringe](http://carl.gorringe.org)

This is the Javascript version of my ***Lines!*** app.  It's like a screensaver where lines move and bounce off the walls, and smoothly transition between multiple colors.  It renders inside an html **canvas** tag.  

Visit my [demo page](http://carl.gorringe.org/pub/code/javascript/LinesJS/) to see it run!

[![](img/badge_demosite.png)](http://carl.gorringe.org/pub/code/javascript/LinesJS/)

Also check out [Lines-watchOS](https://github.com/cgorringe/Lines-watchOS), the Objective-C version for the Apple Watch.


![](img/screenshot1.jpg)

## How To Use

It's really simple to use.  Just insert a **canvas** tag and the **lines.js** javascript file somewhere into your HTML's body like so:

```html
<canvas id="canvasId" width="400" height="400"></canvas>

<script src="lines.js"></script>
<script>
	LinesJS.setup("canvasId");
</script>

```
The code creates a single object **LinesJS** with methods that you may call.  You must first call the `setup()` method with the id of your canvas, as shown above.

You may optionally set these other parameters prior to calling _setup()_. If you don't set these, then the default values will be used.

```html
<script>
	// set optional parameters first
	LinesJS.skipMin =  5;  // lines skip between min and max pixels
	LinesJS.skipMax = 15;
	LinesJS.numLines = 30;
	LinesJS.timeInterval = 50;  // milliseconds between frames

	// then call setup (which is required)
	LinesJS.setup("canvasId");
</script>
```
Then call `LinesJS.start()` to start the lines animation, and `LinesJS.stop()` to pause it.  Calling _start()_ again will continue where it left off.  Other useful methods are `LinesJS.reset()` to reset the lines position and color, and `LinesJS.clear()` to clear the canvas area.

All of these functions are demonstrated in the example **lines.html** file.

_____

## License

Copyright (c) 2016 Carl Gorringe. All rights reserved.

Licensed under the the terms of the [GNU General Public License version 3 (GPLv3)](http://www.gnu.org/licenses/gpl-3.0.html).
