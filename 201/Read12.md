### Article [Chart js](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

#### I learned from this article

1. Charts are easier to look at and convey data quickly, but they’re not always easy to create
1. Chart.js is a plugin that uses HTML5’s canvas element to draw the graph onto the page
1. first thing we need to do is download Chart.js then create a new html page and import the script then add a canvas element in the HTML
1. how to draw a line chart
1. how to draw a pie chart
1. how to draw a bar chart

### Article [Basic usage of canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)

#### I learned from this article

1. a `<canvas>` looks like the `<img>` element, with the only clear difference being that it doesn't have the src and alt attributes.
1. If your renderings seem distorted, try specifying your width and height attributes explicitly in the `<canvas>` attributes, and not using CSS.
1. to provide a fallback just insert the alternate content inside the `<canvas>` element. Browsers that don't support `<canvas>` will ignore the container and render the fallback content inside it
1. If this closing tag is not present, the rest of the document would be considered the fallback content and wouldn't be displayed
1. The `<canvas>` element has a method called getContext(), used to obtain the rendering context and its drawing functions
1. Scripts can also check for support programmatically by testing for the presence of the getContext() method

### Article [Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)

#### I learned from this article

1. ![Canvas Grid](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes/canvas_default_grid.png)
1. `<canvas>`only supports two primitive shapes: rectangles and paths
1. There are three functions that draw rectangles on the canvas
   - `fillRect(x, y, width, height)`: Draws a filled rectangle
   - `strokeRect(x, y, width, height)`: Draws a rectangular outline.
   - `clearRect(x, y, width, height)`: Clears the specified rectangular area, making it fully transparent.
1. functions used to make shapes using paths
   - `beginPath()`
   - Path methods: Methods to set different paths for objects.
   - `closePath()`: Adds a straight line to the path, going to the start of the current sub-path.
   - `stroke()`: Draws the shape by stroking its outline.
   - `fill()`: Draws a solid shape by filling the path's content area.
1. `moveTo(x, y)` Moves the pen to the coordinates specified by x and y.
1. `lineTo(x, y)` Draws a line from the current drawing position to the position specified by x and y.
1. `arc(x, y, radius, startAngle, endAngle, counterclockwise)`: Draws an arc which is centered at (x, y) position with radius r starting at startAngle and ending at endAngle going in the given direction indicated by counterclockwise (defaulting to clockwise)
1. `arcTo(x1, y1, x2, y2, radius)` Draws an arc with the given control points and radius, connected to the previous point by a straight line.
1. `quadraticCurveTo(cp1x, cp1y, x, y)`: Draws a quadratic Bézier curve from the current pen position to the end point specified by x and y, using the control point specified by cp1x and cp1y.
1. `bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)`: Draws a cubic Bézier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).
1. `rect(x, y, width, height)` Draws a rectangle whose top-left corner is specified by (x, y) with the specified width and height.
1. `Path2D()` The Path2D() constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.
1. `var p = new Path2D('M10 10 h 80 v 80 h -80 Z');`: SVG The path will move to point (M10 10) and then move horizontally 80 points to the right (h 80), then 80 points down (v 80), then 80 points to the left (h -80), and then back to the start (z).

### Article [Applying styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

#### I learned from this article

1. `fillStyle = color` Sets the style used when filling shapes.
1. `strokeStyle = color` Sets the style for shapes' outlines.
1. `globalAlpha = transparencyValue` Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (fully transparent) to 1.0 (fully opaque). This value is 1.0 (fully opaque) by default.
1. There are several properties which allow us to style lines.

   - `lineWidth = value` Sets the width of lines drawn in the future.
   - `lineCap = type` Sets the appearance of the ends of lines.
   - `lineJoin = type` Sets the appearance of the "corners" where lines meet.
   - `miterLimit = value` Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
   - `getLineDash()` Returns the current line dash pattern array containing an even number of non-negative numbers.
   - `setLineDash(segments)` Sets the current line dash pattern.
   - `lineDashOffset = value` Specifies where to start a dash array on a line.

1. Linecap There are three possible values for this property:
   -butt The ends of lines are squared off at the endpoints.
   - round The ends of lines are rounded.
   - square The ends of lines are squared off by adding a box with an equal width and half the height of the line's thickness.
1. lineJoin property:
   - round Rounds off the corners of a shape by filling an additional sector of disc centered at the common endpoint of connected segments. The radius for these rounded corners is equal to half the line width.
   - bevel Fills an additional triangular area between the common endpoint of connected segments, and the separate outside rectangular corners of each segment.
   - miter Connected segments are joined by extending their outside edges to connect at a single point, with the effect of filling an additional lozenge-shaped area. This setting is effected by the miterLimit property which is explained below.
1. We create a CanvasGradient object by using one of the following methods
   - `createLinearGradient(x1, y1, x2, y2)` Creates a linear gradient object with a starting point of (x1, y1) and an end point of (x2, y2).
   - `createRadialGradient(x1, y1, r1, x2, y2, r2)` Creates a radial gradient. The parameters represent two circles, one with its center at (x1, y1) and a radius of r1, and the other with its center at (x2, y2) with a radius of r2.
   - `createConicGradient(angle, x, y)` Creates a conic gradient object with a starting angle of angle in radians, at the position (x, y).
1. the createPattern() method.
   - `createPattern(image, type)` Creates and returns a new canvas pattern object. image is a CanvasImageSource (that is, an HTMLImageElement, another canvas, a `<video>` element, or the like. type is a string indicating how to use the image.
1. The type specifies how to use the image in order to create the pattern, and must be one of the following string values:
   - repeat Tiles the image in both vertical and horizontal directions.
   - repeat-x Tiles the image horizontally but not vertically.
   - repeat-y Tiles the image vertically but not horizontally.
   - no-repeat Doesn't tile the image. It's used only once.

### Article [Drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

#### I learned from this article

1. The canvas rendering context provides two methods to render text:
   - `fillText(text, x, y [, maxWidth])` Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
   - `strokeText(text, x, y [, maxWidth])` Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.
1. how to style text
