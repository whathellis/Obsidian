---
URL: https://p5js.org/reference/p5/line/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:40:29
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# line

Description:: Draws a straight line between two points.

A line's default width is one pixel. The version of `line()` with four parameters draws the line in 2D. To color a line, use the [stroke()](https://p5js.org/reference/p5/stroke/) function. To change its width, use the [strokeWeight()](https://p5js.org/reference/p5/strokeWeight/) function. A line can't be filled, so the [fill()](https://p5js.org/reference/p5/fill/) function won't affect the line's color.

The version of `line()` with six parameters allows the line to be drawn in 3D space. Doing so requires adding the `WEBGL` argument to [createCanvas()](https://p5js.org/reference/p5/createCanvas/).

## Examples

## Syntax

`line(x1, y1, x2, y2)``line(x1, y1, z1, x2, y2, z2)`

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

z1

Number:

the z-coordinate of the first point.

z2

Number:

the z-coordinate of the second point.

