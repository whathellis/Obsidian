---
URL: https://p5js.org/reference/p5/arc/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:38:37
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# arc

Description:: Draws an arc.

An arc is a section of an ellipse defined by the `x`, `y`, `w`, and `h` parameters. `x` and `y` set the location of the arc's center. `w` and `h` set the arc's width and height. See [ellipse()](https://p5js.org/reference/p5/ellipse/) and [ellipseMode()](https://p5js.org/reference/p5/ellipseMode/) for more details.

The fifth and sixth parameters, `start` and `stop`, set the angles between which to draw the arc. Arcs are always drawn clockwise from `start` to `stop`. Angles are always given in radians.

The seventh parameter, `mode`, is optional. It determines the arc's fill style. The fill modes are a semi-circle (`OPEN`), a closed semi-circle (`CHORD`), or a closed pie segment (`PIE`).

The eighth parameter, , is also optional. It determines how many vertices are used to draw the arc in WebGL mode. The default value is 25.

## Examples

## Syntax

`arc(x, y, w, h, start, stop, [mode], [detail])`

## Parameters

x

Number:

x-coordinate of the arc's ellipse.

y

Number:

y-coordinate of the arc's ellipse.

w

Number:

width of the arc's ellipse by default.

h

Number:

height of the arc's ellipse by default.

start

Number:

angle to start the arc, specified in radians.

stop

Number:

angle to stop the arc, specified in radians.

mode

Constant:

optional parameter to determine the way of drawing the arc. either CHORD, PIE, or OPEN.

detail

Integer:

optional parameter for WebGL mode only. This is to specify the number of vertices that makes up the perimeter of the arc. Default value is 25. Won't draw a stroke for a detail of more than 50.

