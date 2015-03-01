# canvasBlurRect

Real-time (30+ FPS) iOS-style box blur + saturation with HTML5 Canvas

[Demo available here!](http://keithwhor.com/blur)

canvasBlurRect extends the `CanvasRenderingContext2D` prototype to add a
  `_blurRect()` method which should perform a box blur + saturation of
  a rectangle on your canvas and function at > 30FPS on most modern machines.

It does this by shrinking your canvas, bluring the smaller image in JavaScript,
and using your browser's built-in hardware accelerated scaling to "blow up" your
blurred image back to full screen.

For best results please use Chrome or Safari (desktop or iOS). Firefox seems
to not like to perform any "simulated blurring" when it resizes images and will
give poor results.

# Usage

Include `canvas_blur_rect.js` in your dependencies using:

```html
<script src="canvas_blur_rect.js"></script>
```

Once you have a canvas created, you can blur with the following:

HTML:

```html
<canvas id="my-canvas" width="500" height="500"></canvas>
```

JavaScript:

```javascript
var canvas = document.getElementById('my-canvas');
var context = canvas.getContext('2d');

var x = 0;
var y = 0;
var width = 500;
var height = 500;
var blurEffect = 1;
var saturationValue = 2;

context._blurRect(x, y, width, height, blurEffect, saturationValue);
```

# Reference

```
CanvasRenderingContext2d#_blurRect(
  [Integer] x,
  [Integer] y,
  [Integer] w,
  [Integer] h,
  [Optional Integer] blur,
  [Optional Number] sv
)
```

returns self

`x`: The x position corresponding to the upper-left corner of the rectangular area to blur

`y`: The y position corresponding to the upper-left corner of the rectangular area to blur

`w`: The width of the corresponding rectangular area to blur

`h`: The height of the corresponding rectangular area to blur

`blur`: Optional. The value of the blur effect. Corresponds to a blur radius multiplied by 32
 (for performance reasons.) Default is 1.

 `sv`: Optional. Saturation value. Provide a value between 0 (completely desaturated, black + white) and
 2, with 1 being normal saturation. Default is 1.

 # Want to Help?

 The code was whipped together quickly, and I've repeated myself over a number
 of methods for performance reasons. If you can milk better performance out of
 this library, PRs are welcome! Thanks!

 # Acknowledgements

 This is a small library, made for fun. Wanted to see if I could pull off
 fast box blurring in canvas. Enjoy! :)

 Follow me on Twitter, [@keithwhor](http://twitter.com/keithwhor)

 Or check out my personal website at [keithwhor.com](http://keithwhor.com)
