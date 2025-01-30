---
URL: https://p5js.org/reference/p5/quad/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:40:38
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# quad

Description:: Draws a quadrilateral (four-sided shape).

Quadrilaterals include rectangles, squares, rhombuses, and trapezoids. The first pair of parameters `(x1, y1)` sets the quad's first point. The next three pairs of parameters set the coordinates for its next three points `(x2, y2)`, `(x3, y3)`, and `(x4, y4)`. Points should be added in either clockwise or counter-clockwise order.

The version of `quad()` with twelve parameters allows the quad to be drawn in 3D space. Doing so requires adding the `WEBGL` argument to [createCanvas()](https://p5js.org/reference/p5/createCanvas/).

The thirteenth and fourteenth parameters are optional. In WebGL mode, they set the number of segments used to draw the quadrilateral in the x- and y-directions. They're both 2 by default.

## Examples

## Syntax

`quad(x1, y1, x2, y2, x3, y3, x4, y4, [detailX], [detailY])``quad(x1, y1, z1, x2, y2, z2, x3, y3, z3, x4, y4, z4, [detailX], [detailY])`

## Parameters

x1

Number:

the x-coordinate of the first point.

y1

Number:

the y-coordinate of the first point.

x2

Number:

the x-coordinate of the second point.

y2

Number:

the y-coordinate of the second point.

x3

Number:

the x-coordinate of the third point.

y3

Number:

the y-coordinate of the third point.

x4

Number:

the x-coordinate of the fourth point.

y4

Number:

the y-coordinate of the fourth point.

detailX

Integer:

number of segments in the x-direction.

detailY

Integer:

number of segments in the y-direction.

z1

Number:

the z-coordinate of the first point.

z2

Number:

the z-coordinate of the second point.

z3

Number:

the z-coordinate of the third point.

z4

Number:

the z-coordinate of the fourth point.

