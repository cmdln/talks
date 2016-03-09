# Real-time Drawing with Canvas

* Example, cut the rope game
  * Entire scene of the game rendered in a canvas element
  * Can mix-match other HTML elements, like buttons and input widgets
* Use requestAnimationFrame
  * Hooks into builtin rendering loop
  * Executes your animation callback when it is best to do so
  * Preferred over other means of rendering animation over and over via setInterval, et. al.
* Canvas itself doesn't expose everything needed to draw
  * Rather can get a rendering context from canvas
  * That context provides the full drawing API
  * https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D
* Coordinate system defaults to top-left
  * Can translate to move origin to other places, like centered
  * Useful when drawing different kinds of animations
  * Clock example makes sense when centered, for instance
* save and restore
  * Saves and restores the state of the canvas
  * Useful when doing transforms to make it easier to place shapes, text
* More efficient way to render non-animated parts of canvas
  * Use an off screen canvas and re-use that as needed with animated parts
  * document.createElement('canvas') without adding to visible DOM
  * Use drawImage to render off screen canvas onto visible canvas
* Cost of rotations
  * For shapes, try using path functions to draw directly
  * Math can often be pretty similar to that used in a transform
  * Can improve frame rate drastically at the expense of more complex code
* Test to understand what works best for your application
* Minimizing changes to globals, like styles, can help with frame rate
  * Can think about grouping or layers
  * Set styling then perform all operations with that style at once
  * Just be aware of how this might produce slightly different visual results
  * Can also group some operations, like fill on shapes
* General performance tips
  * Keep track of what is painted, only re-paint things that change
  * Cache whatever you can
  * Avoid text rendering
  * Avoid image re-sizing
  * Avoid floating point coordinates, smoothing is expensive
  * Use multiple canvases to simplify scene rendering by defining layers
  * Keep testing performance as browser's change/improve all the time
* Exercise
  * Implementing a paint program in browser
  * https://github.com/dinazil/fluent-2016-canvas
