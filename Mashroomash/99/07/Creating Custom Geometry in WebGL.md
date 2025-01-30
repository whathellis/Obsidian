---
URL: https://p5js.org/tutorials/custom-geometry/
thumbnail: https://p5js.org/_astro/custom-geometry.BRGFYHSn.png
site: 
date: 2025-01-25T16:36:48
duration: 5
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Creating Custom Geometry in WebGL

Description:: p5.js has a number of built-in basic shapes, like `box()` and `sphere()`. It can also render complex custom geometry, both from 3D model files or code. This tutorial will walk through how to import 3D models into p5.js, as well as how to create geometry from scratch.

## Loading 3D models from file

Custom geometry can be imported into p5.js using either OBJ or STL files. These files are usually generated in a 3D modeling tool like Blender, which offers much more control when constructing a 3D scene. This is done using the `loadModel()` method, which should be used within `preload()`. Then, you can use the `model()` function to draw the model, as demonstrated in the example below.

A common issue that can come up with custom models is scaling. Depending on how the model is constructed, it might be a very different size when drawn in p5.js, or be too small to be drawn at all. The `loadModel()` method includes a `normalize` parameter that will resize the model to something that works better in p5.js.

*Note that there is currently no support for loading materials and colors from model files. You can add color, materials, and textures manually after loading a model.*

## Creating procedural geometry

Geometry can also be defined procedurally using code. This is a great way to create geometry that moves or is formed using your own set of rules. There are a number of methods that can be used to create 3D geometry in a way that is similar to 2D drawing. For example, functions like `quad()`, `triangle()`, `rect()`, and `circle()` each have extra parameters that make it possible to use them in 3D.

There are other functions that offer greater control of the geometry. A shape can be defined point-by-point using `beginShape()`, `vertex()`, and `endShape()`. The following example shows how these functions can be used to construct a 3D shape.

##### Try this!

Can you create a 3D bolt of lightning using `beginShape(QUAD_STRIP)`?

## Reusing procedural geometry

This method is great for creating custom shapes that change over time. Sometimes, you might only need a fixed shape or want an efficient way to draw a shape many times. For this, p5.js has a function called buildGeometry() to turn your custom shapes into the same format as a loaded model. If you are planning on making a particle system, this is a good tool to reach for.

It takes in a function that draws some shapes. It will then output geometry that you can draw with model() as often as you like.

##### Try this!

Try making a few snowflakes using `buildGeometry`, and then use them to create a big snowfall!

## Smooth shading

A normal is the direction that is perpendicular to the face, which helps p5.js calculate lighting across the surface.

![A triangular face with an arrow pointing directly out of it representing its normal](https://p5js.org/_astro/face-normal.29r1NfX3_1r0Oil.webp)

A triangular face with an arrow pointing directly out of it representing its normal

As long as every vertex shared between touching faces has the same normal, then shading will look smooth. You can specify normals manually by calling `normal(x, y, z)` before each `vertex(x, y, z)`, but p5.js includes functionality to calculate these for you. The following example uses `geometry.calculateNormals(SMOOTH)` to create a warped tube with smooth lighting.

##### Try this!

Try making a smooth, organic shape in p5. Can you create buildings in the style of [Frank Gehry](https://en.wikipedia.org/wiki/Guggenheim_Museum_Bilbao#/media/File:Museo_Guggenheim,_Bilbao_(31273245344).jpg), built out of smooth, wavy strips?

## Advanced geometry techniques

Sometimes, you need even more flexibility when making shapes. For example, sometimes you want vertices to be connected irregularly into faces rather than through a grid, or you want to use custom normals or texture coordinates calculated after having generated all your vertices. The `p5.Geometry` class gives full flexibility in creating vertices, faces, texture coordinates, and normals. p5.js uses `p5.Geometry` internally for `loadModel()` and `buildGeometry()`.

In 3D, a face refers to a collection of three points that make up a surface, giving our geometry the appearance of being solid. In `p5.Geometry`, you create faces by:

1.  Putting all the points you will use into a big array in the `geometry.vertices` property, and remembering the **order** the points are added.
2.  Putting sets of three indices at a time into the `geometry.faces` array. The **index** of a point refers to its position in the array, determined by the order in which it was added. Index 0 corresponds to the first point you added, index 1 corresponds to the second, index 2 corresponds to the third, etc.

![An illustration of how to create faces by referring to vertices by their positions in the array. Four vertices are created in a square in a left-to-right then top-to-bottom order. A trianlge is formed in the bottom left of the square with indices [0, 3, 2], and a triangle is formed in the top right with indices [0, 1, 3].](https://p5js.org/_astro/faces.C1tUZifO_ury2J.svg)

An illustration of how to create faces by referring to vertices by their positions in the array. Four vertices are created in a square in a left-to-right then top-to-bottom order. A trianlge is formed in the bottom left of the square with indices \[0, 3, 2\], and a triangle is formed in the top right with indices \[0, 1, 3\].

The following example uses this method of creating vertices and faces to create a custom tetrahedron shape.

You can also push a `p5.Vector` into the `geometry.normals` array for each vertex you push into `geometry.vertices`. However, you can still call `geometry.computeNormals()` for custom `p5.Geometry` just like you can for geometry built with `buildGeometry()`.

##### Try this!

A tetrahedron is part of a group of shapes called [Platonic solids](https://en.wikipedia.org/wiki/Platonic_solid/). Try generating more of them as `p5.Geometry`!

## Conclusion

Now, you should be able to create custom geometry, making it possible to create unique shapes, both from other tools and from code. Spend some time working with a variety of 3D modeling tools so you can find the one that works best for you. If you find bugs please raise an issue on [Github](https://github.com/processing/p5.js/), or if you run into trouble, feel free to ask questions [on Discord](https://discord.gg/SHQ8dH25r9/) or the [Processing Foundation Discourse forum](https://discourse.processing.org/).

## Glossary

#### Procedural

Meaning that something is defined mathematically, instead of from stored data, like a file.

#### Model

A representation of geometry.

#### STL

STL (most often standing for “standard tesselation language”) is a file format for 3D models. It only stores information about the geometry.

#### OBJ

OBJ is an open file format that stores geometry data as well as some material and texture data. In p5.js, we are limited to its geometry, although an image can still be mapped to the surface using textures.

#### Vertices

The points of a shape that make up the corners of its faces.

#### Faces

The solid surface that is generated between three points.

#### Normals

The direction that is perpendicular to a face which is often needed when calculating lighting or using materials.

#### Normalization

Changing something so that it fits within a standard range.

#### Indices

Positions in the array of vertices. Faces reference vertices by these positions.

#### `loadModel()`

A p5.js function to load a shape from an OBJ or STL file.

#### `p5.Geometry`

A class that p5.js uses to store shapes.

#### `model()`

A p5.js function to draw a shape to the screen.

#### `buildGeometry()`

A p5.js function to record all the shapes that get drawn and save them into a new `p5.Geometry` object.

#### `computeNormals()`

A method that can be called on `p5.Geometry` to calculate the direction coming out of each face so that they don’t need to be manually created.

