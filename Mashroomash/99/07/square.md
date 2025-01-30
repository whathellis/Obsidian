---
URL: https://p5js.org/reference/p5/square/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:40:43
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# square

Description:: Draws a square.

A square is a four-sided shape defined by the `x`, `y`, and `s` parameters. `x` and `y` set the location of its top-left corner. `s` sets its width and height. Every angle in the square measures 90˚ and all its sides are the same length. See [rectMode()](https://p5js.org/reference/p5/rectMode/) for other ways to define squares.

The version of `square()` with four parameters creates a rounded square. The fourth parameter sets the radius for all four corners.

The version of `square()` with seven parameters also creates a rounded square. Each of the last four parameters set the radius of a corner. The radii start with the top-left corner and move clockwise around the square. If any of these parameters are omitted, they are set to the value of the last radius that was set.

## Examples

## Syntax

`square(x, y, s, [tl], [tr], [br], [bl])`

## Parameters

x

Number:

x-coordinate of the square.

y

Number:

y-coordinate of the square.

s

Number:

side size of the square.

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

