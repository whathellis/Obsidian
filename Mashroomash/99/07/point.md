---
URL: https://p5js.org/reference/p5/point/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:39:50
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# point

Description:: Draws a single point in space.

A point's default width is one pixel. To color a point, use the [stroke()](https://p5js.org/reference/p5/stroke/) function. To change its width, use the [strokeWeight()](https://p5js.org/reference/p5/strokeWeight/) function. A point can't be filled, so the [fill()](https://p5js.org/reference/p5/fill/) function won't affect the point's color.

The version of `point()` with two parameters allows the point's location to be set with its x- and y-coordinates, as in `point(10, 20)`.

The version of `point()` with three parameters allows the point to be drawn in 3D space with x-, y-, and z-coordinates, as in `point(10, 20, 30)`. Doing so requires adding the `WEBGL` argument to [createCanvas()](https://p5js.org/reference/p5/createCanvas/).

The version of `point()` with one parameter allows the point's location to be set with a [p5.Vector](https://p5js.org/reference/p5/p5.Vector) object.

## Examples

## Syntax

`point(x, y, [z])``point(coordinateVector)`

## Parameters

x

Number:

the x-coordinate.

y

Number:

the y-coordinate.

z

Number:

the z-coordinate (for WebGL mode).

coordinateVector

p5.Vector:

the coordinate vector.

