# suzi.grid.js

## A JavaScript implementation of [Suzi's grid system](http://codepen.io/stowball/pen/JBACc) for rapid development

So everybody knows that [Suzi](https://github.com/izilla/Suzi)'s grids are awesome.

However, during development, it can be a pain when setting and tweaking the appropriate width classes and breakpoints in both the markup and Sass mixin.

This JavaScript implementation means that all you have to do is write the markup, and the relevant classes will be generated on the fly.

It also allows you to tweak any grid values after page load, and provides you with the relevant list values to pass in to the `grid()` mixin.

### Note

This should be used as a **development aide only** and should not be used as a replacement for outputting the required CSS with the Sass `grid()` mixin. It adds an un-necessary overhead, and does not work in IE < 9.

### Usage

#### Initial loading

Include the plugin in your page. I recommend lazy-loading with Modernizr when an appropriate condition is met, such as when the page url contains a querystring parameter of `suzigrid`.

```js
if (window.location.search.match(/suzigrid/g))
	Modernizr.load('/js/suzi.grid.min.js');
```

If valid `.grid_container`s and `.grid_item`s are found, the plugin will generate the classes and media queries The console will log a string of breakpoints and percentages to copy and paste in to the `grid()` mixin.

Something like:

```
(500, 640, 900), (20, 25, 33.3333, 50, 100)
```

#### Custom gutters

You can set a global, custom gutter for the grid with a querystring parameter of `gutter=X`.

#### Tweaking grid values

If your initial grid classes aren't correct, you can edit them in the browser's Dev Tools and then run `suzigrid()` in the console to refresh and recalculate all of the grid classes.

As before, the console will log the appropriate values to pass in to the `grid()` mixin.

---

Copyright (c) 2014 Matt Stow  
Licensed under the MIT license (see LICENSE for details)  
Minified version created with Online YUI Compressor: http://www.refresh-sf.com/yui/