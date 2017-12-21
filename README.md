## LinesJS

By [Carl Gorringe](http://carl.gorringe.org)

This is the Javascript version of my ***Lines!*** app.  It's like a screensaver where lines move and bounce off the walls, and smoothly transition between multiple colors.  It renders inside an html **canvas** tag.  

Visit my [demo page](http://carl.gorringe.org/pub/code/javascript/LinesJS/) to see it run!

[![](img/badge_demo.png)](http://carl.gorringe.org/pub/code/javascript/LinesJS/)

Also check out [Lines-watchOS](https://github.com/cgorringe/Lines-watchOS), the Objective-C version for the Apple Watch.


![](img/screenshot1.jpg)

## How To Use

It's really simple to use.  Just insert a **canvas** tag and the **lines.js** javascript file somewhere into your HTML's body like so:

```html
<canvas id="lines-canvas" width="400" height="400"></canvas>

<script src="lines.js"></script>
<script>
	var lines = new LinesJS({ canvasId: 'lines-canvas' });
</script>

```
The code assigns a **LinesJS** object to **lines** which has methods that you may call.  You must pass in the canvas id so that it knows where to draw.

You may optionally set additional parameters as shown below, or else the default values will be used.

```javascript
var lines = new LinesJS({
	canvasId: 'lines-canvas',
	skipMin: 5,       // lines skip between min and max pixels
	skipMax: 15,
	numLines: 30,
	timeInterval: 50  // milliseconds between frames
});

```
Then call `lines.start()` to start the lines animation, and `.stop()` to pause it.  Calling _start()_ again will continue where it left off.  Other useful methods are `.reset()` to reset the lines position and color, and `.clear()` to clear the canvas area.

All of these functions are demonstrated in the example **lines.html** file.


## Install using NPM &amp; Browserify

Using this method may be an extra step, but may be worth it if you're already using Node and wish to bundle all of your JavaScript into a single file for faster loading.

First install [Browserify](http://browserify.org) for web support:

```
npm install -g browserify
```
Then install LinesJS which is called **lines-demo**:

```
npm install lines-demo
```
To use Browserify, you'll want to place all of your JavaScript code in a separate file, like so:

```javascript
// lines-test.js
var LinesJS = require('lines-demo');
window.lines = new LinesJS({
	canvasId: 'lines-canvas',
	skipMin: 5,
	skipMax: 15,
	numLines: 30,
	timeInterval: 50
});
```
Note the use of **window.lines** above, which will make sure that **lines** is scoped globally, but which can be named anything.

Now generate your JavaScript bundle:

```
browserify lines-test.js > lines-bundle.js
```
And in your HTML, a single script tag to import the bundle:

```html
<script src="lines-bundle.js"></script>
```


Now you can call methods such as `lines.start()` to start the lines animation.  See examples in **lines.html**.

_____

## License

Copyright (c) 2016 Carl Gorringe. All rights reserved.

Licensed under the the terms of the [GNU General Public License version 3 (GPLv3)](http://www.gnu.org/licenses/gpl-3.0.html).
