---
URL: https://p5js.org/reference/p5/rect/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:40:05
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# rect

Description:: Draws a rectangle.

A rectangle is a four-sided shape defined by the `x`, `y`, `w`, and `h` parameters. `x` and `y` set the location of its top-left corner. `w` sets its width and `h` sets its height. Every angle in the rectangle measures 90˚. See [rectMode()](https://p5js.org/reference/p5/rectMode/) for other ways to define rectangles.

The version of `rect()` with five parameters creates a rounded rectangle. The fifth parameter sets the radius for all four corners.

The version of `rect()` with eight parameters also creates a rounded rectangle. Each of the last four parameters set the radius of a corner. The radii start with the top-left corner and move clockwise around the rectangle. If any of these parameters are omitted, they are set to the value of the last radius that was set.

## Examples

## Syntax

`rect(x, y, w, [h], [tl], [tr], [br], [bl])``rect(x, y, w, h, [detailX], [detailY])`

## Parameters

x

Number:

x-coordinate of the rectangle.

y

Number:

y-coordinate of the rectangle.

w

Number:

width of the rectangle.

h

Number:

height of the rectangle.

tl

Number:

optional radius of top-left corner.

tr

Number:

optional radius of top-right corner.

br

Number:

optional radius of bottom-right corner.

bl

Number:

optional radius of bottom-left corner.

detailX

Integer:

number of segments in the x-direction (for WebGL mode).

detailY

Integer:

number of segments in the y-direction (for WebGL mode).

