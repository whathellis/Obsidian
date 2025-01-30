---
URL: https://p5js.org/reference/p5/ellipse/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:39:41
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# ellipse

Description:: Draws an ellipse (oval).

An ellipse is a round shape defined by the `x`, `y`, `w`, and `h` parameters. `x` and `y` set the location of its center. `w` and `h` set its width and height. See [ellipseMode()](https://p5js.org/reference/p5/ellipseMode/) for other ways to set its position.

If no height is set, the value of width is used for both the width and height. If a negative height or width is specified, the absolute value is taken.

The fifth parameter, , is also optional. It determines how many vertices are used to draw the ellipse in WebGL mode. The default value is 25.

## Examples

## Syntax

`ellipse(x, y, w, [h])``ellipse(x, y, w, h, [detail])`

## Parameters

x

Number:

x-coordinate of the center of the ellipse.

y

Number:

y-coordinate of the center of the ellipse.

w

Number:

width of the ellipse.

h

Number:

height of the ellipse.

detail

Integer:

optional parameter for WebGL mode only. This is to specify the number of vertices that makes up the perimeter of the ellipse. Default value is 25. Won't draw a stroke for a detail of more than 50.

