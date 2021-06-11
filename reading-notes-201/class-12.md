# Chart.js  

***Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. They’re easier to look at and convey data quickly, but they’re not always easy to create.*** 

***A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.*** 

![chart.js](https://miro.medium.com/max/1400/1*IotA2ju74bOmsTO84HzYEw.png)

> Creating a Chart 

*All that's required is the script included in your page along with a single (canvas) node to render the chart.*

![creating a chart](https://forum.vuejs.org/uploads/default/original/2X/8/84ee7f99bcc4d5ee467e56742e9601ef5028edbd.JPG)

# Basic usage of canvas 

## The (canvas) element 

**At first sight a (canvas) looks like the (img) element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the (canvas) element has only two attributes, width and height. These are both optional and can also be set using DOM properties**

## Fallback content 

**The (canvas) element differs from an (img) tag in that, like for (video), (audio), or (picture) elements, it is easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers** 

**Providing fallback content is very straightforward: just insert the alternate content inside the (canvas) element. Browsers that don't support (canvas) will ignore the container and render the fallback content inside it. Browsers that do support (canvas) will ignore the content inside the container, and just render the canvas normally.**

## Required (/canvas) tag

**As a consequence of the way fallback is provided, unlike the (img) element, the (canvas) element requires the closing tag (/canvas). If this tag is not present, the rest of the document would be considered the fallback content and wouldn't be displayed.**

## The rendering context 

**The (canvas) element creates a fixed-size drawing surface that exposes one or more rendering contexts, which are used to create and manipulate the content shown.**

## Checking for support

**The fallback content is displayed in browsers which do not support (canvas). Scripts can also check for support programmatically by testing for the presence of the getContext() method.** 

# Drawing shapes with canvas 

## Drawing rectangles

**Unlike SVG, (canvas) only supports two primitive shapes: rectangles and paths** 

> There are three functions that draw rectangles on the canvas: 

* fillRect(x, y, width, height) 
Draws a filled rectangle. 

* strokeRect(x, y, width, height)
Draws a rectangular outline. 

* clearRect(x, y, width, height)
Clears the specified rectangular area, making it fully transparent. 

> Drawing paths 

**Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:**

1. First, you create the path.
2. Then you use drawing commands to draw into the path.
3. Once the path has been created, you can stroke or fill the path to render it.

*Here are the functions used to perform these steps:* 

* beginPath()
Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.

* Path methods
Methods to set different paths for objects.

* closePath()
Adds a straight line to the path, going to the start of the current sub-path.

* stroke()
Draws the shape by stroking its outline.

* fill()
Draws a solid shape by filling the path's content area. 

> Moving the pen 

* moveTo(x, y)
Moves the pen to the coordinates specified by x and y.

> Lines 

*For drawing straight lines, use the lineTo() method.*

* lineTo(x, y)
Draws a line from the current drawing position to the position specified by x and y.

> Arcs 

* arc(x, y, radius, startAngle, endAngle, counterclockwise)

*Draws an arc which is centered at (x, y) position with radius r starting at startAngle and ending at endAngle going in the given direction indicated by counterclockwise (defaulting to clockwise).* 

* arcTo(x1, y1, x2, y2, radius)

*Draws an arc with the given control points and radius, connected to the previous point by a straight line.* 

> Path2D objects 

* The Path2D() 

*constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.* 

# Applying styles and colors 

## Colors 

**we can use: fillStyle and strokeStyle.** 

* fillStyle = color

*Sets the style used when filling shapes.* 

* strokeStyle = color

*Sets the style for shapes' outlines.* 

## Line styles 

**There are several properties which allow us to style lines.** 

* lineWidth = value

*Sets the width of lines drawn in the future.*

* lineCap = type
*Sets the appearance of the ends of lines.*

* lineJoin = type

*Sets the appearance of the "corners" where lines meet.*

* miterLimit = value

*Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.*

* getLineDash()

*Returns the current line dash pattern array containing an even number of non-negative numbers.*

* setLineDash(segments)

*Sets the current line dash pattern.*

* lineDashOffset = value

*Specifies where to start a dash array on a line.* 

## Gradients 

* createLinearGradient(x1, y1, x2, y2)

*Creates a linear gradient object with a starting point of (x1, y1) and an end point of (x2, y2).*

* createRadialGradient(x1, y1, r1, x2, y2, r2)

*Creates a radial gradient. The parameters represent two circles, one with its center at (x1, y1) and a radius of r1, and the other with its center at (x2, y2) with a radius of r2.* 

* createConicGradient(angle, x, y)

*Creates a conic gradient object with a starting angle of angle in radians, at the position (x, y).* 

## Patterns 

**we used a series of loops to create a pattern of images. There is, however, a much simpler method: the createPattern() method.** 

**The type specifies how to use the image in order to create the pattern, and must be one of the following string values:** 

* repeat

*Tiles the image in both vertical and horizontal directions.*

* repeat-x

*Tiles the image horizontally but not vertically.*

* repeat-y

*Tiles the image vertically but not horizontally.*

* no-repeat

*Doesn't tile the image. It's used only once.*

## Shadows 

* shadowOffsetX = float

*Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.*

* shadowOffsetY = float

*Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.*

* shadowBlur = float

*Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.*

* shadowColor = color

*A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.* 

# Drawing text 

**The canvas rendering context provides two methods to render text:** 

* fillText(text, x, y [, maxWidth])

*Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.*

* strokeText(text, x, y [, maxWidth])

*Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.*

## Styling text 

* font = value

*The current text style being used when drawing text. This string uses the same syntax as the CSS font property. The default font is 10px sans-serif.*

* textAlign = value

*Text alignment setting. Possible values: start, end, left, right or center. The default value is start.*

* textBaseline = value

*Baseline alignment setting. Possible values: top, hanging, middle, alphabetic, ideographic, bottom. The default value is alphabetic.*

* direction = value

*Directionality. Possible values: ltr, rtl, inherit. The default value is inherit.*

## Advanced text measurements 

* measureText()

*Returns a TextMetrics object containing the width, in pixels, that the specified text will be when drawn in the current text style.*