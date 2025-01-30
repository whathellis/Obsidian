---
URL: https://p5js.org/reference/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:38:06
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Reference

[Skip to main content](https://p5js.org/reference/#main-content)

[](https://p5js.org/)

[](https://p5js.org/)[](https://p5js.org/)

- [Reference](https://p5js.org/reference/)
- [Tutorials](https://p5js.org/tutorials/)
- [Examples](https://p5js.org/examples/)
- [Contribute](https://p5js.org/contribute/)
- [Community](https://p5js.org/community/)
- [About](https://p5js.org/about/)

- [
    
    ](https://editor.p5js.org)

- [Start Coding](https://editor.p5js.org)
- [
    
    ](https://p5js.org/donate/)

- [Donate](https://p5js.org/donate/)

- [Shape](https://p5js.org/reference/#Shape)
- [Color](https://p5js.org/reference/#Color)
- [Typography](https://p5js.org/reference/#Typography)
- [Image](https://p5js.org/reference/#Image)
- [Transform](https://p5js.org/reference/#Transform)
- [Environment](https://p5js.org/reference/#Environment)
- [3D](https://p5js.org/reference/#3D)
- [Rendering](https://p5js.org/reference/#Rendering)
- [Math](https://p5js.org/reference/#Math)
- [IO](https://p5js.org/reference/#IO)
- [Events](https://p5js.org/reference/#Events)
- [DOM](https://p5js.org/reference/#DOM)
- [Data](https://p5js.org/reference/#Data)
- [Structure](https://p5js.org/reference/#Structure)
- [Constants](https://p5js.org/reference/#Constants)
- [Foundation](https://p5js.org/reference/#Foundation)

# Reference

Find easy explanations for every piece of p5.js code.

Looking for p5.sound? Go to the [p5.sound reference](https://p5js.org/reference/p5.sound/)!

## Shape

### 2D Primitives

[arc()

Draws an arc.

](https://p5js.org/reference/p5/arc/)

[circle()

Draws a circle.

](https://p5js.org/reference/p5/circle/)

[ellipse()

Draws an ellipse (oval).

](https://p5js.org/reference/p5/ellipse/)

[line()

Draws a straight line between two points.

](https://p5js.org/reference/p5/line/)

[point()

Draws a single point in space.

](https://p5js.org/reference/p5/point/)

[quad()

Draws a quadrilateral (four-sided shape).

](https://p5js.org/reference/p5/quad/)

[rect()

Draws a rectangle.

](https://p5js.org/reference/p5/rect/)

[square()

Draws a square.

](https://p5js.org/reference/p5/square/)

[triangle()

Draws a triangle.

](https://p5js.org/reference/p5/triangle/)

### 3D Models

[createModel()

Load a 3d model from an OBJ or STL string.

](https://p5js.org/reference/p5/createModel/)

[loadModel()

Loads a 3D model to create a p5.Geometry object.

](https://p5js.org/reference/p5/loadModel/)

[model()

Draws a p5.Geometry object to the canvas.

](https://p5js.org/reference/p5/model/)

### 3D Primitives

[beginGeometry()

Begins adding shapes to a new p5.Geometry object.

](https://p5js.org/reference/p5/beginGeometry/)

[box()

Draws a box (rectangular prism).

](https://p5js.org/reference/p5/box/)

[buildGeometry()

Creates a custom p5.Geometry object from simpler 3D shapes.

](https://p5js.org/reference/p5/buildGeometry/)

[cone()

Draws a cone.

](https://p5js.org/reference/p5/cone/)

[cylinder()

Draws a cylinder.

](https://p5js.org/reference/p5/cylinder/)

[ellipsoid()

Draws an ellipsoid.

](https://p5js.org/reference/p5/ellipsoid/)

[endGeometry()

Stops adding shapes to a new p5.Geometry object and returns the object.

](https://p5js.org/reference/p5/endGeometry/)

[freeGeometry()

Clears a p5.Geometry object from the graphics processing unit (GPU) memory.

](https://p5js.org/reference/p5/freeGeometry/)

[plane()

Draws a plane.

](https://p5js.org/reference/p5/plane/)

[sphere()

Draws a sphere.

](https://p5js.org/reference/p5/sphere/)

[torus()

Draws a torus.

](https://p5js.org/reference/p5/torus/)

### Attributes

[ellipseMode()

Changes where ellipses, circles, and arcs are drawn.

](https://p5js.org/reference/p5/ellipseMode/)

[noSmooth()

Draws certain features with jagged (aliased) edges.

](https://p5js.org/reference/p5/noSmooth/)

[rectMode()

Changes where rectangles and squares are drawn.

](https://p5js.org/reference/p5/rectMode/)

[smooth()

Draws certain features with smooth (antialiased) edges.

](https://p5js.org/reference/p5/smooth/)

[strokeCap()

Sets the style for rendering the ends of lines.

](https://p5js.org/reference/p5/strokeCap/)

[strokeJoin()

Sets the style of the joints that connect line segments.

](https://p5js.org/reference/p5/strokeJoin/)

[strokeWeight()

Sets the width of the stroke used for points, lines, and the outlines of shapes.

](https://p5js.org/reference/p5/strokeWeight/)

### Curves

[bezier()

Draws a Bézier curve.

](https://p5js.org/reference/p5/bezier/)

[bezierDetail()

Sets the number of segments used to draw Bézier curves in WebGL mode.

](https://p5js.org/reference/p5/bezierDetail/)

[bezierPoint()

Calculates coordinates along a Bézier curve using interpolation.

](https://p5js.org/reference/p5/bezierPoint/)

[bezierTangent()

Calculates coordinates along a line that's tangent to a Bézier curve.

](https://p5js.org/reference/p5/bezierTangent/)

[curve()

Draws a curve using a Catmull-Rom spline.

](https://p5js.org/reference/p5/curve/)

[curveDetail()

Sets the number of segments used to draw spline curves in WebGL mode.

](https://p5js.org/reference/p5/curveDetail/)

[curvePoint()

Calculates coordinates along a spline curve using interpolation.

](https://p5js.org/reference/p5/curvePoint/)

[curveTangent()

Calculates coordinates along a line that's tangent to a spline curve.

](https://p5js.org/reference/p5/curveTangent/)

[curveTightness()

Adjusts the way curve() and curveVertex() draw.

](https://p5js.org/reference/p5/curveTightness/)

### Vertex

[beginContour()

Begins creating a hole within a flat shape.

](https://p5js.org/reference/p5/beginContour/)

[beginShape()

Begins adding vertices to a custom shape.

](https://p5js.org/reference/p5/beginShape/)

[bezierVertex()

Adds a Bézier curve segment to a custom shape.

](https://p5js.org/reference/p5/bezierVertex/)

[curveVertex()

Adds a spline curve segment to a custom shape.

](https://p5js.org/reference/p5/curveVertex/)

[endContour()

Stops creating a hole within a flat shape.

](https://p5js.org/reference/p5/endContour/)

[endShape()

Begins adding vertices to a custom shape.

](https://p5js.org/reference/p5/endShape/)

[normal()

Sets the normal vector for vertices in a custom 3D shape.

](https://p5js.org/reference/p5/normal/)

[quadraticVertex()

Adds a quadratic Bézier curve segment to a custom shape.

](https://p5js.org/reference/p5/quadraticVertex/)

[vertex()

Adds a vertex to a custom shape.

](https://p5js.org/reference/p5/vertex/)

[

### p5.Geometry

](https://p5js.org/reference/p5/p5.Geometry/)

[calculateBoundingBox()

Calculates the position and size of the smallest box that contains the geometry.

](https://p5js.org/reference/p5.Geometry/calculateBoundingBox/)

[clearColors()

Removes the geometry’s internal colors.

](https://p5js.org/reference/p5.Geometry/clearColors/)

[computeFaces()

Computes the geometry's faces using its vertices.

](https://p5js.org/reference/p5.Geometry/computeFaces/)

[computeNormals()

Calculates the normal vector for each vertex on the geometry.

](https://p5js.org/reference/p5.Geometry/computeNormals/)

[faces

An array that lists which of the geometry's vertices form each of its faces.

](https://p5js.org/reference/p5.Geometry/faces/)

[flipU()

Flips the geometry’s texture u-coordinates.

](https://p5js.org/reference/p5.Geometry/flipU/)

[flipV()

Flips the geometry’s texture v-coordinates.

](https://p5js.org/reference/p5.Geometry/flipV/)

[normalize()

Transforms the geometry's vertices to fit snugly within a 100×100×100 box centered at the origin.

](https://p5js.org/reference/p5.Geometry/normalize/)

[saveObj()

The saveObj() function exports p5.Geometry objects as 3D models in the Wavefront .obj file format.

](https://p5js.org/reference/p5.Geometry/saveObj/)

[saveStl()

The saveStl() function exports p5.Geometry objects as 3D models in the STL stereolithography file format.

](https://p5js.org/reference/p5.Geometry/saveStl/)

[uvs

An array that lists the texture coordinates for each of the geometry's vertices.

](https://p5js.org/reference/p5.Geometry/uvs/)

[vertexNormals

An array with the vectors that are normal to the geometry's vertices.

](https://p5js.org/reference/p5.Geometry/vertexNormals/)

[vertices

An array with the geometry's vertices.

](https://p5js.org/reference/p5.Geometry/vertices/)

## Color

### Creating & Reading

[alpha()

Gets the alpha (transparency) value of a color.

](https://p5js.org/reference/p5/alpha/)

[blue()

Gets the blue value of a color.

](https://p5js.org/reference/p5/blue/)

[brightness()

Gets the brightness value of a color.

](https://p5js.org/reference/p5/brightness/)

[color()

Creates a p5.Color object.

](https://p5js.org/reference/p5/color/)

[green()

Gets the green value of a color.

](https://p5js.org/reference/p5/green/)

[hue()

Gets the hue value of a color.

](https://p5js.org/reference/p5/hue/)

[lerpColor()

Blends two colors to find a third color between them.

](https://p5js.org/reference/p5/lerpColor/)

[lightness()

Gets the lightness value of a color.

](https://p5js.org/reference/p5/lightness/)

[paletteLerp()

Blends multiple colors to find a color between them.

](https://p5js.org/reference/p5/paletteLerp/)

[red()

Gets the red value of a color.

](https://p5js.org/reference/p5/red/)

[saturation()

Gets the saturation value of a color.

](https://p5js.org/reference/p5/saturation/)

### Setting

[background()

Sets the color used for the background of the canvas.

](https://p5js.org/reference/p5/background/)

[beginClip()

Starts defining a shape that will mask any shapes drawn afterward.

](https://p5js.org/reference/p5/beginClip/)

[clear()

Clears the pixels on the canvas.

](https://p5js.org/reference/p5/clear/)

[clip()

Defines a shape that will mask any shapes drawn afterward.

](https://p5js.org/reference/p5/clip/)

[colorMode()

Changes the way color values are interpreted.

](https://p5js.org/reference/p5/colorMode/)

[endClip()

Ends defining a mask that was started with beginClip().

](https://p5js.org/reference/p5/endClip/)

[erase()

Starts using shapes to erase parts of the canvas.

](https://p5js.org/reference/p5/erase/)

[fill()

Sets the color used to fill shapes.

](https://p5js.org/reference/p5/fill/)

[noErase()

Ends erasing that was started with erase().

](https://p5js.org/reference/p5/noErase/)

[noFill()

Disables setting the fill color for shapes.

](https://p5js.org/reference/p5/noFill/)

[noStroke()

Disables drawing points, lines, and the outlines of shapes.

](https://p5js.org/reference/p5/noStroke/)

[stroke()

Sets the color used to draw points, lines, and the outlines of shapes.

](https://p5js.org/reference/p5/stroke/)

[

### p5.Color

](https://p5js.org/reference/p5/p5.Color/)

[setAlpha()

Sets the alpha (transparency) value of a color.

](https://p5js.org/reference/p5.Color/setAlpha/)

[setBlue()

Sets the blue component of a color.

](https://p5js.org/reference/p5.Color/setBlue/)

[setGreen()

Sets the green component of a color.

](https://p5js.org/reference/p5.Color/setGreen/)

[setRed()

Sets the red component of a color.

](https://p5js.org/reference/p5.Color/setRed/)

[toString()

Returns the color formatted as a String.

](https://p5js.org/reference/p5.Color/toString/)

## Typography

### Attributes

[textAlign()

Sets the way text is aligned when text() is called.

](https://p5js.org/reference/p5/textAlign/)

[textAscent()

Calculates the ascent of the current font at its current size.

](https://p5js.org/reference/p5/textAscent/)

[textDescent()

Calculates the descent of the current font at its current size.

](https://p5js.org/reference/p5/textDescent/)

[textLeading()

Sets the spacing between lines of text when text() is called.

](https://p5js.org/reference/p5/textLeading/)

[textSize()

Sets the font size when text() is called.

](https://p5js.org/reference/p5/textSize/)

[textStyle()

Sets the style for system fonts when text() is called.

](https://p5js.org/reference/p5/textStyle/)

[textWidth()

Calculates the maximum width of a string of text drawn when text() is called.

](https://p5js.org/reference/p5/textWidth/)

[textWrap()

Sets the style for wrapping text when text() is called.

](https://p5js.org/reference/p5/textWrap/)

### Loading & Displaying

[loadFont()

Loads a font and creates a p5.Font object.

](https://p5js.org/reference/p5/loadFont/)

[text()

Draws text to the canvas.

](https://p5js.org/reference/p5/text/)

[textFont()

Sets the font used by the text() function.

](https://p5js.org/reference/p5/textFont/)

[

### p5.Font

](https://p5js.org/reference/p5/p5.Font/)

[font

The font's underlying opentype.js font object.

](https://p5js.org/reference/p5.Font/font/)

[textBounds()

Returns the bounding box for a string of text written using the font.

](https://p5js.org/reference/p5.Font/textBounds/)

[textToPoints()

Returns an array of points outlining a string of text written using the font.

](https://p5js.org/reference/p5.Font/textToPoints/)

## Image

[createImage()

Creates a new p5.Image object.

](https://p5js.org/reference/p5/createImage/)

[saveCanvas()

Saves the current canvas as an image.

](https://p5js.org/reference/p5/saveCanvas/)

[saveFrames()

Captures a sequence of frames from the canvas that can be saved as images.

](https://p5js.org/reference/p5/saveFrames/)

### Loading & Displaying

[image()

Draws an image to the canvas.

](https://p5js.org/reference/p5/image/)

[imageMode()

Changes the location from which images are drawn when image() is called.

](https://p5js.org/reference/p5/imageMode/)

[loadImage()

Loads an image to create a p5.Image object.

](https://p5js.org/reference/p5/loadImage/)

[noTint()

Removes the current tint set by tint().

](https://p5js.org/reference/p5/noTint/)

[saveGif()

Generates a gif from a sketch and saves it to a file.

](https://p5js.org/reference/p5/saveGif/)

[tint()

Tints images using a color.

](https://p5js.org/reference/p5/tint/)

### Pixels

[blend()

Copies a region of pixels from one image to another.

](https://p5js.org/reference/p5/blend/)

[copy()

Copies pixels from a source image to a region of the canvas.

](https://p5js.org/reference/p5/copy/)

[filter()

Applies an image filter to the canvas.

](https://p5js.org/reference/p5/filter/)

[get()

Gets a pixel or a region of pixels from the canvas.

](https://p5js.org/reference/p5/get/)

[loadPixels()

Loads the current value of each pixel on the canvas into the pixels array.

](https://p5js.org/reference/p5/loadPixels/)

[pixels

An array containing the color of each pixel on the canvas.

](https://p5js.org/reference/p5/pixels/)

[set()

Sets the color of a pixel or draws an image to the canvas.

](https://p5js.org/reference/p5/set/)

[updatePixels()

Updates the canvas with the RGBA values in the pixels array.

](https://p5js.org/reference/p5/updatePixels/)

[

### p5.Image

](https://p5js.org/reference/p5/p5.Image/)

[blend()

Copies a region of pixels from another image into this one.

](https://p5js.org/reference/p5.Image/blend/)

[copy()

Copies pixels from a source image to this image.

](https://p5js.org/reference/p5.Image/copy/)

[delay()

Changes the delay between frames in an animated GIF.

](https://p5js.org/reference/p5.Image/delay/)

[filter()

Applies an image filter to the image.

](https://p5js.org/reference/p5.Image/filter/)

[get()

Gets a pixel or a region of pixels from the image.

](https://p5js.org/reference/p5.Image/get/)

[getCurrentFrame()

Gets the index of the current frame in an animated GIF.

](https://p5js.org/reference/p5.Image/getCurrentFrame/)

[height

The image's height in pixels.

](https://p5js.org/reference/p5.Image/height/)

[loadPixels()

Loads the current value of each pixel in the image into the img.pixels array.

](https://p5js.org/reference/p5.Image/loadPixels/)

[mask()

Masks part of the image with another.

](https://p5js.org/reference/p5.Image/mask/)

[numFrames()

Returns the number of frames in an animated GIF.

](https://p5js.org/reference/p5.Image/numFrames/)

[pause()

Pauses an animated GIF.

](https://p5js.org/reference/p5.Image/pause/)

[pixelDensity()

Gets or sets the pixel density for high pixel density displays.

](https://p5js.org/reference/p5.Image/pixelDensity/)

[pixels

An array containing the color of each pixel in the image.

](https://p5js.org/reference/p5.Image/pixels/)

[play()

Plays an animated GIF that was paused with img.pause().

](https://p5js.org/reference/p5.Image/play/)

[reset()

Restarts an animated GIF at its first frame.

](https://p5js.org/reference/p5.Image/reset/)

[resize()

Resizes the image to a given width and height.

](https://p5js.org/reference/p5.Image/resize/)

[save()

Saves the image to a file.

](https://p5js.org/reference/p5.Image/save/)

[set()

Sets the color of one or more pixels within an image.

](https://p5js.org/reference/p5.Image/set/)

[setFrame()

Sets the current frame in an animated GIF.

](https://p5js.org/reference/p5.Image/setFrame/)

[updatePixels()

Updates the canvas with the RGBA values in the img.pixels array.

](https://p5js.org/reference/p5.Image/updatePixels/)

[width

The image's width in pixels.

](https://p5js.org/reference/p5.Image/width/)

## Transform

[applyMatrix()

Applies a transformation matrix to the coordinate system.

](https://p5js.org/reference/p5/applyMatrix/)

[resetMatrix()

Clears all transformations applied to the coordinate system.

](https://p5js.org/reference/p5/resetMatrix/)

[rotate()

Rotates the coordinate system.

](https://p5js.org/reference/p5/rotate/)

[rotateX()

Rotates the coordinate system about the x-axis in WebGL mode.

](https://p5js.org/reference/p5/rotateX/)

[rotateY()

Rotates the coordinate system about the y-axis in WebGL mode.

](https://p5js.org/reference/p5/rotateY/)

[rotateZ()

Rotates the coordinate system about the z-axis in WebGL mode.

](https://p5js.org/reference/p5/rotateZ/)

[scale()

Scales the coordinate system.

](https://p5js.org/reference/p5/scale/)

[shearX()

Shears the x-axis so that shapes appear skewed.

](https://p5js.org/reference/p5/shearX/)

[shearY()

Shears the y-axis so that shapes appear skewed.

](https://p5js.org/reference/p5/shearY/)

[translate()

Translates the coordinate system.

](https://p5js.org/reference/p5/translate/)

## Environment

[cursor()

Changes the cursor's appearance.

](https://p5js.org/reference/p5/cursor/)

[deltaTime

A Number variable that tracks the number of milliseconds it took to draw the last frame.

](https://p5js.org/reference/p5/deltaTime/)

[describe()

Creates a screen reader-accessible description of the canvas.

](https://p5js.org/reference/p5/describe/)

[describeElement()

Creates a screen reader-accessible description of elements in the canvas.

](https://p5js.org/reference/p5/describeElement/)

[displayDensity()

Returns the display's current pixel density.

](https://p5js.org/reference/p5/displayDensity/)

[displayHeight

A Number variable that stores the height of the screen display.

](https://p5js.org/reference/p5/displayHeight/)

[displayWidth

A Number variable that stores the width of the screen display.

](https://p5js.org/reference/p5/displayWidth/)

[focused

A Boolean variable that's true if the browser is focused and false if not.

](https://p5js.org/reference/p5/focused/)

[frameCount

A Number variable that tracks the number of frames drawn since the sketch started.

](https://p5js.org/reference/p5/frameCount/)

[frameRate()

Sets the number of frames to draw per second.

](https://p5js.org/reference/p5/frameRate/)

[fullscreen()

Toggles full-screen mode or returns the current mode.

](https://p5js.org/reference/p5/fullscreen/)

[getTargetFrameRate()

Returns the target frame rate.

](https://p5js.org/reference/p5/getTargetFrameRate/)

[getURL()

Returns the sketch's current URL as a String.

](https://p5js.org/reference/p5/getURL/)

[getURLParams()

Returns the current URL parameters in an Object.

](https://p5js.org/reference/p5/getURLParams/)

[getURLPath()

Returns the current URL path as an Array of Strings.

](https://p5js.org/reference/p5/getURLPath/)

[gridOutput()

Creates a screen reader-accessible description of shapes on the canvas.

](https://p5js.org/reference/p5/gridOutput/)

[height

A Number variable that stores the height of the canvas in pixels.

](https://p5js.org/reference/p5/height/)

[noCursor()

Hides the cursor from view.

](https://p5js.org/reference/p5/noCursor/)

[pixelDensity()

Sets the pixel density or returns the current density.

](https://p5js.org/reference/p5/pixelDensity/)

[print()

Displays text in the web browser's console.

](https://p5js.org/reference/p5/print/)

[textOutput()

Creates a screen reader-accessible description of shapes on the canvas.

](https://p5js.org/reference/p5/textOutput/)

[webglVersion

A String variable with the WebGL version in use.

](https://p5js.org/reference/p5/webglVersion/)

[width

A Number variable that stores the width of the canvas in pixels.

](https://p5js.org/reference/p5/width/)

[windowHeight

A Number variable that stores the height of the browser's viewport.

](https://p5js.org/reference/p5/windowHeight/)

[windowResized()

A function that's called when the browser window is resized.

](https://p5js.org/reference/p5/windowResized/)

[windowWidth

A Number variable that stores the width of the browser's viewport.

](https://p5js.org/reference/p5/windowWidth/)

## 3D

### Camera

[camera()

Sets the position and orientation of the current camera in a 3D sketch.

](https://p5js.org/reference/p5/camera/)

[createCamera()

Creates a new p5.Camera object and sets it as the current (active) camera.

](https://p5js.org/reference/p5/createCamera/)

[frustum()

Sets the frustum of the current camera in a 3D sketch.

](https://p5js.org/reference/p5/frustum/)

[linePerspective()

Enables or disables perspective for lines in 3D sketches.

](https://p5js.org/reference/p5/linePerspective/)

[ortho()

Sets an orthographic projection for the current camera in a 3D sketch.

](https://p5js.org/reference/p5/ortho/)

[perspective()

Sets a perspective projection for the current camera in a 3D sketch.

](https://p5js.org/reference/p5/perspective/)

[setCamera()

Sets the current (active) camera of a 3D sketch.

](https://p5js.org/reference/p5/setCamera/)

### Interaction

[debugMode()

Adds a grid and an axes icon to clarify orientation in 3D sketches.

](https://p5js.org/reference/p5/debugMode/)

[noDebugMode()

Turns off debugMode() in a 3D sketch.

](https://p5js.org/reference/p5/noDebugMode/)

[orbitControl()

Allows the user to orbit around a 3D sketch using a mouse, trackpad, or touchscreen.

](https://p5js.org/reference/p5/orbitControl/)

### Lights

[ambientLight()

Creates a light that shines from all directions.

](https://p5js.org/reference/p5/ambientLight/)

[directionalLight()

Creates a light that shines in one direction.

](https://p5js.org/reference/p5/directionalLight/)

[imageLight()

Creates an ambient light from an image.

](https://p5js.org/reference/p5/imageLight/)

[lightFalloff()

Sets the falloff rate for pointLight() and spotLight().

](https://p5js.org/reference/p5/lightFalloff/)

[lights()

Places an ambient and directional light in the scene.

](https://p5js.org/reference/p5/lights/)

[noLights()

Removes all lights from the sketch.

](https://p5js.org/reference/p5/noLights/)

[panorama()

Creates an immersive 3D background.

](https://p5js.org/reference/p5/panorama/)

[pointLight()

Creates a light that shines from a point in all directions.

](https://p5js.org/reference/p5/pointLight/)

[specularColor()

Sets the specular color for lights.

](https://p5js.org/reference/p5/specularColor/)

[spotLight()

Creates a light that shines from a point in one direction.

](https://p5js.org/reference/p5/spotLight/)

### Material

[ambientMaterial()

Sets the ambient color of shapes’ surface material.

](https://p5js.org/reference/p5/ambientMaterial/)

[](https://p5js.org/reference/p5/baseColorShader/)

[baseColorShader()

Get the shader used when no lights or materials are applied.

](https://p5js.org/reference/p5/baseColorShader/)

[](https://p5js.org/reference/p5/baseMaterialShader/)

[baseMaterialShader()

Get the default shader used with lights, materials, and textures.

](https://p5js.org/reference/p5/baseMaterialShader/)

[](https://p5js.org/reference/p5/baseNormalShader/)

[baseNormalShader()

Get the shader used by normalMaterial().

](https://p5js.org/reference/p5/baseNormalShader/)

[](https://p5js.org/reference/p5/baseStrokeShader/)

[baseStrokeShader()

Get the shader used when drawing the strokes of shapes.

](https://p5js.org/reference/p5/baseStrokeShader/)

[createFilterShader()

Creates a p5.Shader object to be used with the filter() function.

](https://p5js.org/reference/p5/createFilterShader/)

[createShader()

Creates a new p5.Shader object.

](https://p5js.org/reference/p5/createShader/)

[emissiveMaterial()

Sets the emissive color of shapes’ surface material.

](https://p5js.org/reference/p5/emissiveMaterial/)

[loadShader()

Loads vertex and fragment shaders to create a p5.Shader object.

](https://p5js.org/reference/p5/loadShader/)

[metalness()

Sets the amount of "metalness" of a specularMaterial().

](https://p5js.org/reference/p5/metalness/)

[normalMaterial()

Sets the current material as a normal material.

](https://p5js.org/reference/p5/normalMaterial/)

[resetShader()

Restores the default shaders.

](https://p5js.org/reference/p5/resetShader/)

[shader()

Sets the p5.Shader object to apply while drawing.

](https://p5js.org/reference/p5/shader/)

[shininess()

Sets the amount of gloss ("shininess") of a specularMaterial().

](https://p5js.org/reference/p5/shininess/)

[specularMaterial()

Sets the specular color of shapes’ surface material.

](https://p5js.org/reference/p5/specularMaterial/)

[texture()

Sets the texture that will be used on shapes.

](https://p5js.org/reference/p5/texture/)

[textureMode()

Changes the coordinate system used for textures when they’re applied to custom shapes.

](https://p5js.org/reference/p5/textureMode/)

[textureWrap()

Changes the way textures behave when a shape’s uv coordinates go beyond the texture.

](https://p5js.org/reference/p5/textureWrap/)

[

### p5.Camera

](https://p5js.org/reference/p5/p5.Camera/)

[camera()

Sets the position and orientation of the camera.

](https://p5js.org/reference/p5.Camera/camera/)

[centerX

The x-coordinate of the place where the camera looks.

](https://p5js.org/reference/p5.Camera/centerX/)

[centerY

The y-coordinate of the place where the camera looks.

](https://p5js.org/reference/p5.Camera/centerY/)

[centerZ

The y-coordinate of the place where the camera looks.

](https://p5js.org/reference/p5.Camera/centerZ/)

[eyeX

The camera’s x-coordinate.

](https://p5js.org/reference/p5.Camera/eyeX/)

[eyeY

The camera’s y-coordinate.

](https://p5js.org/reference/p5.Camera/eyeY/)

[eyeZ

The camera’s z-coordinate.

](https://p5js.org/reference/p5.Camera/eyeZ/)

[frustum()

Sets the camera's frustum.

](https://p5js.org/reference/p5.Camera/frustum/)

[lookAt()

Points the camera at a location.

](https://p5js.org/reference/p5.Camera/lookAt/)

[move()

Moves the camera along its "local" axes without changing its orientation.

](https://p5js.org/reference/p5.Camera/move/)

[ortho()

Sets an orthographic projection for the camera.

](https://p5js.org/reference/p5.Camera/ortho/)

[pan()

Rotates the camera left and right.

](https://p5js.org/reference/p5.Camera/pan/)

[perspective()

Sets a perspective projection for the camera.

](https://p5js.org/reference/p5.Camera/perspective/)

[roll()

Rotates the camera in a clockwise/counter-clockwise direction.

](https://p5js.org/reference/p5.Camera/roll/)

[set()

Sets the camera’s position, orientation, and projection by copying another camera.

](https://p5js.org/reference/p5.Camera/set/)

[setPosition()

Sets the camera’s position in "world" space without changing its orientation.

](https://p5js.org/reference/p5.Camera/setPosition/)

[slerp()

Sets the camera’s position and orientation to values that are in-between those of two other cameras.

](https://p5js.org/reference/p5.Camera/slerp/)

[tilt()

Rotates the camera up and down.

](https://p5js.org/reference/p5.Camera/tilt/)

[upX

The x-component of the camera's "up" vector.

](https://p5js.org/reference/p5.Camera/upX/)

[upY

The y-component of the camera's "up" vector.

](https://p5js.org/reference/p5.Camera/upY/)

[upZ

The z-component of the camera's "up" vector.

](https://p5js.org/reference/p5.Camera/upZ/)

[

### p5.Shader

](https://p5js.org/reference/p5/p5.Shader/)

[copyToContext()

Copies the shader from one drawing context to another.

](https://p5js.org/reference/p5.Shader/copyToContext/)

[](https://p5js.org/reference/p5.Shader/inspectHooks/)

[inspectHooks()

Logs the hooks available in this shader, and their current implementation.

](https://p5js.org/reference/p5.Shader/inspectHooks/)

[](https://p5js.org/reference/p5.Shader/modify/)

[modify()

Returns a new shader, based on the original, but with custom snippets of shader code replacing default behaviour.

](https://p5js.org/reference/p5.Shader/modify/)

[setUniform()

Sets the shader’s uniform (global) variables.

](https://p5js.org/reference/p5.Shader/setUniform/)

## Rendering

[blendMode()

Sets the way colors blend when added to the canvas.

](https://p5js.org/reference/p5/blendMode/)

[clearDepth()

Clears the depth buffer in WebGL mode.

](https://p5js.org/reference/p5/clearDepth/)

[createCanvas()

Creates a canvas element on the web page.

](https://p5js.org/reference/p5/createCanvas/)

[createFramebuffer()

Creates and a new p5.Framebuffer object.

](https://p5js.org/reference/p5/createFramebuffer/)

[createGraphics()

Creates a p5.Graphics object.

](https://p5js.org/reference/p5/createGraphics/)

[drawingContext

A system variable that provides direct access to the sketch's element.

](https://p5js.org/reference/p5/drawingContext/)

[noCanvas()

Removes the default canvas.

](https://p5js.org/reference/p5/noCanvas/)

[resizeCanvas()

Resizes the canvas to a given width and height.

](https://p5js.org/reference/p5/resizeCanvas/)

[setAttributes()

Set attributes for the WebGL Drawing context.

](https://p5js.org/reference/p5/setAttributes/)

[

### p5.Framebuffer

](https://p5js.org/reference/p5/p5.Framebuffer/)

[autoSized()

Toggles the framebuffer's autosizing mode or returns the current mode.

](https://p5js.org/reference/p5.Framebuffer/autoSized/)

[begin()

Begins drawing shapes to the framebuffer.

](https://p5js.org/reference/p5.Framebuffer/begin/)

[color

An object that stores the framebuffer's color data.

](https://p5js.org/reference/p5.Framebuffer/color/)

[createCamera()

Creates a new p5.Camera object to use with the framebuffer.

](https://p5js.org/reference/p5.Framebuffer/createCamera/)

[depth

An object that stores the framebuffer's depth data.

](https://p5js.org/reference/p5.Framebuffer/depth/)

[draw()

Draws to the framebuffer by calling a function that contains drawing instructions.

](https://p5js.org/reference/p5.Framebuffer/draw/)

[end()

Stops drawing shapes to the framebuffer.

](https://p5js.org/reference/p5.Framebuffer/end/)

[get()

Gets a pixel or a region of pixels from the framebuffer.

](https://p5js.org/reference/p5.Framebuffer/get/)

[loadPixels()

Loads the current value of each pixel in the framebuffer into its pixels array.

](https://p5js.org/reference/p5.Framebuffer/loadPixels/)

[pixelDensity()

Sets the framebuffer's pixel density or returns its current density.

](https://p5js.org/reference/p5.Framebuffer/pixelDensity/)

[pixels

An array containing the color of each pixel in the framebuffer.

](https://p5js.org/reference/p5.Framebuffer/pixels/)

[remove()

Deletes the framebuffer from GPU memory.

](https://p5js.org/reference/p5.Framebuffer/remove/)

[resize()

Resizes the framebuffer to a given width and height.

](https://p5js.org/reference/p5.Framebuffer/resize/)

[updatePixels()

Updates the framebuffer with the RGBA values in the pixels array.

](https://p5js.org/reference/p5.Framebuffer/updatePixels/)

[

### p5.Graphics

](https://p5js.org/reference/p5/p5.Graphics/)

[createFramebuffer()

Creates a new p5.Framebuffer object with the same WebGL context as the graphics buffer.

](https://p5js.org/reference/p5.Graphics/createFramebuffer/)

[remove()

Removes the graphics buffer from the web page.

](https://p5js.org/reference/p5.Graphics/remove/)

[reset()

Resets the graphics buffer's transformations and lighting.

](https://p5js.org/reference/p5.Graphics/reset/)

[

### p5.Renderer

](https://p5js.org/reference/p5/p5.Renderer/)

## Math

### Calculation

[abs()

Calculates the absolute value of a number.

](https://p5js.org/reference/p5/abs/)

[ceil()

Calculates the closest integer value that is greater than or equal to a number.

](https://p5js.org/reference/p5/ceil/)

[constrain()

Constrains a number between a minimum and maximum value.

](https://p5js.org/reference/p5/constrain/)

[dist()

Calculates the distance between two points.

](https://p5js.org/reference/p5/dist/)

[exp()

Calculates the value of Euler's number e (2.71828...) raised to the power of a number.

](https://p5js.org/reference/p5/exp/)

[floor()

Calculates the closest integer value that is less than or equal to the value of a number.

](https://p5js.org/reference/p5/floor/)

[fract()

Calculates the fractional part of a number.

](https://p5js.org/reference/p5/fract/)

[lerp()

Calculates a number between two numbers at a specific increment.

](https://p5js.org/reference/p5/lerp/)

[log()

Calculates the natural logarithm (the base-e logarithm) of a number.

](https://p5js.org/reference/p5/log/)

[mag()

Calculates the magnitude, or length, of a vector.

](https://p5js.org/reference/p5/mag/)

[map()

Re-maps a number from one range to another.

](https://p5js.org/reference/p5/map/)

[max()

Returns the largest value in a sequence of numbers.

](https://p5js.org/reference/p5/max/)

[min()

Returns the smallest value in a sequence of numbers.

](https://p5js.org/reference/p5/min/)

[norm()

Maps a number from one range to a value between 0 and 1.

](https://p5js.org/reference/p5/norm/)

[pow()

Calculates exponential expressions such as 23.

](https://p5js.org/reference/p5/pow/)

[round()

Calculates the integer closest to a number.

](https://p5js.org/reference/p5/round/)

[sq()

Calculates the square of a number.

](https://p5js.org/reference/p5/sq/)

[sqrt()

Calculates the square root of a number.

](https://p5js.org/reference/p5/sqrt/)

### Noise

[noise()

Returns random numbers that can be tuned to feel organic.

](https://p5js.org/reference/p5/noise/)

[noiseDetail()

Adjusts the character of the noise produced by the noise() function.

](https://p5js.org/reference/p5/noiseDetail/)

[noiseSeed()

Sets the seed value for the noise() function.

](https://p5js.org/reference/p5/noiseSeed/)

### Random

[random()

Returns a random number or a random element from an array.

](https://p5js.org/reference/p5/random/)

[randomGaussian()

Returns a random number fitting a Gaussian, or normal, distribution.

](https://p5js.org/reference/p5/randomGaussian/)

[randomSeed()

Sets the seed value for the random() and randomGaussian() functions.

](https://p5js.org/reference/p5/randomSeed/)

### Trigonometry

[acos()

Calculates the arc cosine of a number.

](https://p5js.org/reference/p5/acos/)

[angleMode()

Changes the unit system used to measure angles.

](https://p5js.org/reference/p5/angleMode/)

[asin()

Calculates the arc sine of a number.

](https://p5js.org/reference/p5/asin/)

[atan()

Calculates the arc tangent of a number.

](https://p5js.org/reference/p5/atan/)

[atan2()

Calculates the angle formed by a point, the origin, and the positive x-axis.

](https://p5js.org/reference/p5/atan2/)

[cos()

Calculates the cosine of an angle.

](https://p5js.org/reference/p5/cos/)

[degrees()

Converts an angle measured in radians to its value in degrees.

](https://p5js.org/reference/p5/degrees/)

[radians()

Converts an angle measured in degrees to its value in radians.

](https://p5js.org/reference/p5/radians/)

[sin()

Calculates the sine of an angle.

](https://p5js.org/reference/p5/sin/)

[tan()

Calculates the tangent of an angle.

](https://p5js.org/reference/p5/tan/)

### Vector

[createVector()

Creates a new p5.Vector object.

](https://p5js.org/reference/p5/createVector/)

[

### p5.Vector

](https://p5js.org/reference/p5/p5.Vector/)

[add()

Adds to a vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/add/)

[angleBetween()

Calculates the angle between two vectors.

](https://p5js.org/reference/p5.Vector/angleBetween/)

[array()

Returns the vector's components as an array of numbers.

](https://p5js.org/reference/p5.Vector/array/)

[clampToZero()

Replaces the components of a p5.Vector that are very close to zero with zero.

](https://p5js.org/reference/p5.Vector/clampToZero/)

[copy()

Returns a copy of the p5.Vector object.

](https://p5js.org/reference/p5.Vector/copy/)

[cross()

Calculates the cross product of two vectors.

](https://p5js.org/reference/p5.Vector/cross/)

[dist()

Calculates the distance between two points represented by vectors.

](https://p5js.org/reference/p5.Vector/dist/)

[div()

Divides a vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/div/)

[dot()

Calculates the dot product of two vectors.

](https://p5js.org/reference/p5.Vector/dot/)

[equals()

Checks whether all the vector's components are equal to another vector's.

](https://p5js.org/reference/p5.Vector/equals/)

[fromAngle()

Creates a new 2D vector from an angle.

](https://p5js.org/reference/p5.Vector/fromAngle/)

[fromAngles()

Creates a new 3D vector from a pair of ISO spherical angles.

](https://p5js.org/reference/p5.Vector/fromAngles/)

[heading()

Calculates the angle a 2D vector makes with the positive x-axis.

](https://p5js.org/reference/p5.Vector/heading/)

[lerp()

Calculates new x, y, and z components that are proportionally the same distance between two vectors.

](https://p5js.org/reference/p5.Vector/lerp/)

[limit()

Limits a vector's magnitude to a maximum value.

](https://p5js.org/reference/p5.Vector/limit/)

[mag()

Calculates the magnitude (length) of the vector.

](https://p5js.org/reference/p5.Vector/mag/)

[magSq()

Calculates the magnitude (length) of the vector squared.

](https://p5js.org/reference/p5.Vector/magSq/)

[mult()

Multiplies a vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/mult/)

[normalize()

Scales the components of a p5.Vector object so that its magnitude is 1.

](https://p5js.org/reference/p5.Vector/normalize/)

[random2D()

Creates a new 2D unit vector with a random heading.

](https://p5js.org/reference/p5.Vector/random2D/)

[random3D()

Creates a new 3D unit vector with a random heading.

](https://p5js.org/reference/p5.Vector/random3D/)

[reflect()

Reflects a vector about a line in 2D or a plane in 3D.

](https://p5js.org/reference/p5.Vector/reflect/)

[rem()

Performs modulo (remainder) division with a vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/rem/)

[rotate()

Rotates a 2D vector by an angle without changing its magnitude.

](https://p5js.org/reference/p5.Vector/rotate/)

[set()

Sets the vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/set/)

[setHeading()

Rotates a 2D vector to a specific angle without changing its magnitude.

](https://p5js.org/reference/p5.Vector/setHeading/)

[setMag()

Sets a vector's magnitude to a given value.

](https://p5js.org/reference/p5.Vector/setMag/)

[slerp()

Calculates a new heading and magnitude that are between two vectors.

](https://p5js.org/reference/p5.Vector/slerp/)

[sub()

Subtracts from a vector's x, y, and z components.

](https://p5js.org/reference/p5.Vector/sub/)

[toString()

Returns a string representation of a vector.

](https://p5js.org/reference/p5.Vector/toString/)

[x

The x component of the vector

](https://p5js.org/reference/p5.Vector/x/)

[y

The y component of the vector

](https://p5js.org/reference/p5.Vector/y/)

[z

The z component of the vector

](https://p5js.org/reference/p5.Vector/z/)

## IO

### Input

[httpDo()

Method for executing an HTTP request.

](https://p5js.org/reference/p5/httpDo/)

[httpGet()

Method for executing an HTTP GET request.

](https://p5js.org/reference/p5/httpGet/)

[httpPost()

Method for executing an HTTP POST request.

](https://p5js.org/reference/p5/httpPost/)

[loadBytes()

This method is suitable for fetching files up to size of 64MB.

](https://p5js.org/reference/p5/loadBytes/)

[loadJSON()

Loads a JSON file to create an Object.

](https://p5js.org/reference/p5/loadJSON/)

[loadStrings()

Loads a text file to create an Array.

](https://p5js.org/reference/p5/loadStrings/)

[loadTable()

Reads the contents of a file or URL and creates a p5.Table object with its values.

](https://p5js.org/reference/p5/loadTable/)

[loadXML()

Loads an XML file to create a p5.XML object.

](https://p5js.org/reference/p5/loadXML/)

### Output

[createWriter()

Creates a new p5.PrintWriter object.

](https://p5js.org/reference/p5/createWriter/)

[p5.PrintWriter

A class to describe a print stream.

](https://p5js.org/reference/p5/p5.PrintWriter/)

[save()

Saves a given element(image, text, json, csv, wav, or html) to the client's computer.

](https://p5js.org/reference/p5/save/)

[saveJSON()

Saves an Object or Array to a JSON file.

](https://p5js.org/reference/p5/saveJSON/)

[saveStrings()

Saves an Array of Strings to a file, one per line.

](https://p5js.org/reference/p5/saveStrings/)

[saveTable()

Writes the contents of a Table object to a file.

](https://p5js.org/reference/p5/saveTable/)

### Time & Date

[day()

Returns the current day as a number from 1–31.

](https://p5js.org/reference/p5/day/)

[hour()

Returns the current hour as a number from 0–23.

](https://p5js.org/reference/p5/hour/)

[millis()

Returns the number of milliseconds since a sketch started running.

](https://p5js.org/reference/p5/millis/)

[minute()

Returns the current minute as a number from 0–59.

](https://p5js.org/reference/p5/minute/)

[month()

Returns the current month as a number from 1–12.

](https://p5js.org/reference/p5/month/)

[second()

Returns the current second as a number from 0–59.

](https://p5js.org/reference/p5/second/)

[year()

Returns the current year as a number such as 1999.

](https://p5js.org/reference/p5/year/)

[

### p5.Table

](https://p5js.org/reference/p5/p5.Table/)

[addColumn()

Use addColumn() to add a new column to a Table object.

](https://p5js.org/reference/p5.Table/addColumn/)

[addRow()

Use addRow() to add a new row of data to a p5.Table object.

](https://p5js.org/reference/p5.Table/addRow/)

[clearRows()

Removes all rows from a Table.

](https://p5js.org/reference/p5.Table/clearRows/)

[columns

An array containing the names of the columns in the table, if the "header" the table is loaded with the "header" parameter.

](https://p5js.org/reference/p5.Table/columns/)

[findRow()

Finds the first row in the Table that contains the value provided, and returns a reference to that row.

](https://p5js.org/reference/p5.Table/findRow/)

[findRows()

Finds the rows in the Table that contain the value provided, and returns references to those rows.

](https://p5js.org/reference/p5.Table/findRows/)

[get()

Retrieves a value from the Table's specified row and column.

](https://p5js.org/reference/p5.Table/get/)

[getArray()

Retrieves all table data and returns it as a multidimensional array.

](https://p5js.org/reference/p5.Table/getArray/)

[getColumn()

Retrieves all values in the specified column, and returns them as an array.

](https://p5js.org/reference/p5.Table/getColumn/)

[getColumnCount()

Returns the total number of columns in a Table.

](https://p5js.org/reference/p5.Table/getColumnCount/)

[getNum()

Retrieves a Float value from the Table's specified row and column.

](https://p5js.org/reference/p5.Table/getNum/)

[getObject()

Retrieves all table data and returns as an object.

](https://p5js.org/reference/p5.Table/getObject/)

[getRow()

Returns a reference to the specified p5.TableRow.

](https://p5js.org/reference/p5.Table/getRow/)

[getRowCount()

Returns the total number of rows in a Table.

](https://p5js.org/reference/p5.Table/getRowCount/)

[getRows()

Gets all rows from the table.

](https://p5js.org/reference/p5.Table/getRows/)

[getString()

Retrieves a String value from the Table's specified row and column.

](https://p5js.org/reference/p5.Table/getString/)

[matchRow()

Finds the first row in the Table that matches the regular expression provided, and returns a reference to that row.

](https://p5js.org/reference/p5.Table/matchRow/)

[matchRows()

Finds the rows in the Table that match the regular expression provided, and returns references to those rows.

](https://p5js.org/reference/p5.Table/matchRows/)

[removeColumn()

Use removeColumn() to remove an existing column from a Table object.

](https://p5js.org/reference/p5.Table/removeColumn/)

[removeRow()

Removes a row from the table object.

](https://p5js.org/reference/p5.Table/removeRow/)

[removeTokens()

Removes any of the specified characters (or "tokens").

](https://p5js.org/reference/p5.Table/removeTokens/)

[rows

An array containing the p5.TableRow objects that make up the rows of the table.

](https://p5js.org/reference/p5.Table/rows/)

[set()

Stores a value in the Table's specified row and column.

](https://p5js.org/reference/p5.Table/set/)

[setNum()

Stores a Float value in the Table's specified row and column.

](https://p5js.org/reference/p5.Table/setNum/)

[setString()

Stores a String value in the Table's specified row and column.

](https://p5js.org/reference/p5.Table/setString/)

[trim()

Trims leading and trailing whitespace, such as spaces and tabs, from String table values.

](https://p5js.org/reference/p5.Table/trim/)

[

### p5.TableRow

](https://p5js.org/reference/p5/p5.TableRow/)

[get()

Retrieves a value from the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/get/)

[getNum()

Retrieves a Float value from the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/getNum/)

[getString()

Retrieves an String value from the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/getString/)

[set()

Stores a value in the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/set/)

[setNum()

Stores a Float value in the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/setNum/)

[setString()

Stores a String value in the TableRow's specified column.

](https://p5js.org/reference/p5.TableRow/setString/)

[

### p5.XML

](https://p5js.org/reference/p5/p5.XML/)

[addChild()

Adds a new child element and returns a reference to it.

](https://p5js.org/reference/p5.XML/addChild/)

[getAttributeCount()

Returns the number of attributes the element has.

](https://p5js.org/reference/p5.XML/getAttributeCount/)

[getChild()

Returns the first matching child element as a new p5.XML object.

](https://p5js.org/reference/p5.XML/getChild/)

[getChildren()

Returns an array with the element's child elements as new p5.XML objects.

](https://p5js.org/reference/p5.XML/getChildren/)

[getContent()

Returns the element's content as a String.

](https://p5js.org/reference/p5.XML/getContent/)

[getName()

Returns the element's name as a String.

](https://p5js.org/reference/p5.XML/getName/)

[getNum()

Return an attribute's value as a Number.

](https://p5js.org/reference/p5.XML/getNum/)

[getParent()

Returns the element's parent element as a new p5.XML object.

](https://p5js.org/reference/p5.XML/getParent/)

[getString()

Return an attribute's value as a string.

](https://p5js.org/reference/p5.XML/getString/)

[hasAttribute()

Returns true if the element has a given attribute and false if not.

](https://p5js.org/reference/p5.XML/hasAttribute/)

[hasChildren()

Returns true if the element has child elements and false if not.

](https://p5js.org/reference/p5.XML/hasChildren/)

[listAttributes()

Returns an Array with the names of the element's attributes.

](https://p5js.org/reference/p5.XML/listAttributes/)

[listChildren()

Returns an array with the names of the element's child elements as Strings.

](https://p5js.org/reference/p5.XML/listChildren/)

[removeChild()

Removes the first matching child element.

](https://p5js.org/reference/p5.XML/removeChild/)

[serialize()

Returns the element as a String.

](https://p5js.org/reference/p5.XML/serialize/)

[setAttribute()

Sets an attribute to a given value.

](https://p5js.org/reference/p5.XML/setAttribute/)

[setContent()

Sets the element's content.

](https://p5js.org/reference/p5.XML/setContent/)

[setName()

Sets the element's tag name.

](https://p5js.org/reference/p5.XML/setName/)

## Events

### Acceleration

[accelerationX

The system variable accelerationX always contains the acceleration of the device along the x axis.

](https://p5js.org/reference/p5/accelerationX/)

[accelerationY

The system variable accelerationY always contains the acceleration of the device along the y axis.

](https://p5js.org/reference/p5/accelerationY/)

[accelerationZ

The system variable accelerationZ always contains the acceleration of the device along the z axis.

](https://p5js.org/reference/p5/accelerationZ/)

[deviceMoved()

The deviceMoved() function is called when the device is moved by more than the threshold value along X, Y or Z axis.

](https://p5js.org/reference/p5/deviceMoved/)

[deviceOrientation

The system variable deviceOrientation always contains the orientation of the device.

](https://p5js.org/reference/p5/deviceOrientation/)

[deviceShaken()

The deviceShaken() function is called when the device total acceleration changes of accelerationX and accelerationY values is more than the threshold value.

](https://p5js.org/reference/p5/deviceShaken/)

[deviceTurned()

The deviceTurned() function is called when the device rotates by more than 90 degrees continuously.

](https://p5js.org/reference/p5/deviceTurned/)

[pAccelerationX

The system variable pAccelerationX always contains the acceleration of the device along the x axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pAccelerationX/)

[pAccelerationY

The system variable pAccelerationY always contains the acceleration of the device along the y axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pAccelerationY/)

[pAccelerationZ

The system variable pAccelerationZ always contains the acceleration of the device along the z axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pAccelerationZ/)

[pRotationX

The system variable pRotationX always contains the rotation of the device along the x axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pRotationX/)

[pRotationY

The system variable pRotationY always contains the rotation of the device along the y axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pRotationY/)

[pRotationZ

The system variable pRotationZ always contains the rotation of the device along the z axis in the frame previous to the current frame.

](https://p5js.org/reference/p5/pRotationZ/)

[rotationX

The system variable rotationX always contains the rotation of the device along the x axis.

](https://p5js.org/reference/p5/rotationX/)

[rotationY

The system variable rotationY always contains the rotation of the device along the y axis.

](https://p5js.org/reference/p5/rotationY/)

[rotationZ

The system variable rotationZ always contains the rotation of the device along the z axis.

](https://p5js.org/reference/p5/rotationZ/)

[setMoveThreshold()

The setMoveThreshold() function is used to set the movement threshold for the deviceMoved() function.

](https://p5js.org/reference/p5/setMoveThreshold/)

[setShakeThreshold()

The setShakeThreshold() function is used to set the movement threshold for the deviceShaken() function.

](https://p5js.org/reference/p5/setShakeThreshold/)

[turnAxis

When a device is rotated, the axis that triggers the deviceTurned() method is stored in the turnAxis variable.

](https://p5js.org/reference/p5/turnAxis/)

### Keyboard

[key

A String system variable that contains the value of the last key typed.

](https://p5js.org/reference/p5/key/)

[keyCode

A Number system variable that contains the code of the last key typed.

](https://p5js.org/reference/p5/keyCode/)

[keyIsDown()

Returns true if the key it’s checking is pressed and false if not.

](https://p5js.org/reference/p5/keyIsDown/)

[keyIsPressed

A Boolean system variable that's true if any key is currently pressed and false if not.

](https://p5js.org/reference/p5/keyIsPressed/)

[keyPressed()

A function that's called once when any key is pressed.

](https://p5js.org/reference/p5/keyPressed/)

[keyReleased()

A function that's called once when any key is released.

](https://p5js.org/reference/p5/keyReleased/)

[keyTyped()

A function that's called once when keys with printable characters are pressed.

](https://p5js.org/reference/p5/keyTyped/)

### Mouse

[doubleClicked()

A function that's called once when a mouse button is clicked twice quickly.

](https://p5js.org/reference/p5/doubleClicked/)

[exitPointerLock()

Exits a pointer lock started with requestPointerLock.

](https://p5js.org/reference/p5/exitPointerLock/)

[mouseButton

A String system variable that contains the value of the last mouse button pressed.

](https://p5js.org/reference/p5/mouseButton/)

[mouseClicked()

A function that's called once after a mouse button is pressed and released.

](https://p5js.org/reference/p5/mouseClicked/)

[mouseDragged()

A function that's called when the mouse moves while a button is pressed.

](https://p5js.org/reference/p5/mouseDragged/)

[mouseIsPressed

A Boolean system variable that's true if the mouse is pressed and false if not.

](https://p5js.org/reference/p5/mouseIsPressed/)

[mouseMoved()

A function that's called when the mouse moves.

](https://p5js.org/reference/p5/mouseMoved/)

[mousePressed()

A function that's called once when a mouse button is pressed.

](https://p5js.org/reference/p5/mousePressed/)

[mouseReleased()

A function that's called once when a mouse button is released.

](https://p5js.org/reference/p5/mouseReleased/)

[mouseWheel()

A function that's called once when the mouse wheel moves.

](https://p5js.org/reference/p5/mouseWheel/)

[mouseX

A Number system variable that tracks the mouse's horizontal position.

](https://p5js.org/reference/p5/mouseX/)

[mouseY

A Number system variable that tracks the mouse's vertical position.

](https://p5js.org/reference/p5/mouseY/)

[movedX

A Number system variable that tracks the mouse's horizontal movement.

](https://p5js.org/reference/p5/movedX/)

[movedY

A Number system variable that tracks the mouse's vertical movement.

](https://p5js.org/reference/p5/movedY/)

[pmouseX

A Number system variable that tracks the mouse's previous horizontal position.

](https://p5js.org/reference/p5/pmouseX/)

[pmouseY

A Number system variable that tracks the mouse's previous vertical position.

](https://p5js.org/reference/p5/pmouseY/)

[pwinMouseX

A Number variable that tracks the mouse's previous horizontal position within the browser.

](https://p5js.org/reference/p5/pwinMouseX/)

[pwinMouseY

A Number variable that tracks the mouse's previous vertical position within the browser.

](https://p5js.org/reference/p5/pwinMouseY/)

[requestPointerLock()

Locks the mouse pointer to its current position and makes it invisible.

](https://p5js.org/reference/p5/requestPointerLock/)

[winMouseX

A Number variable that tracks the mouse's horizontal position within the browser.

](https://p5js.org/reference/p5/winMouseX/)

[winMouseY

A Number variable that tracks the mouse's vertical position within the browser.

](https://p5js.org/reference/p5/winMouseY/)

### Touch

[touchEnded()

A function that's called once each time a screen touch ends.

](https://p5js.org/reference/p5/touchEnded/)

[touchMoved()

A function that's called when the user touches the screen and moves.

](https://p5js.org/reference/p5/touchMoved/)

[touchStarted()

A function that's called once each time the user touches the screen.

](https://p5js.org/reference/p5/touchStarted/)

[touches

An Array of all the current touch points on a touchscreen device.

](https://p5js.org/reference/p5/touches/)

## DOM

[changed()

Calls a function when the element changes.

](https://p5js.org/reference/p5/changed/)

[createA()

Creates an element that links to another web page.

](https://p5js.org/reference/p5/createA/)

[createAudio()

Creates a hidden element for simple audio playback.

](https://p5js.org/reference/p5/createAudio/)

[createButton()

Creates a element.

](https://p5js.org/reference/p5/createButton/)

[createCapture()

Creates a element that "captures" the audio/video stream from the webcam and microphone.

](https://p5js.org/reference/p5/createCapture/)

[createCheckbox()

Creates a checkbox element.

](https://p5js.org/reference/p5/createCheckbox/)

[createColorPicker()

Creates a color picker element.

](https://p5js.org/reference/p5/createColorPicker/)

[createDiv()

Creates a element.

](https://p5js.org/reference/p5/createDiv/)

[createElement()

Creates a new p5.Element object.

](https://p5js.org/reference/p5/createElement/)

[createFileInput()

Creates an element of type 'file'.

](https://p5js.org/reference/p5/createFileInput/)

[createImg()

Creates an element that can appear outside of the canvas.

](https://p5js.org/reference/p5/createImg/)

[createInput()

Creates a text element.

](https://p5js.org/reference/p5/createInput/)

[createP()

Creates a element.

](https://p5js.org/reference/p5/createP/)

[createRadio()

Creates a radio button element.

](https://p5js.org/reference/p5/createRadio/)

[createSelect()

Creates a dropdown menu element.

](https://p5js.org/reference/p5/createSelect/)

[createSlider()

Creates a slider element.

](https://p5js.org/reference/p5/createSlider/)

[createSpan()

Creates a element.

](https://p5js.org/reference/p5/createSpan/)

[createVideo()

Creates a element for simple audio/video playback.

](https://p5js.org/reference/p5/createVideo/)

[input()

Calls a function when the element receives input.

](https://p5js.org/reference/p5/input/)

[removeElements()

Removes all elements created by p5.js, including any event handlers.

](https://p5js.org/reference/p5/removeElements/)

[select()

Searches the page for the first element that matches the given CSS selector string.

](https://p5js.org/reference/p5/select/)

[selectAll()

Searches the page for all elements that matches the given CSS selector string.

](https://p5js.org/reference/p5/selectAll/)

[

### p5.Element

](https://p5js.org/reference/p5/p5.Element/)

[addClass()

Adds a class to the element.

](https://p5js.org/reference/p5.Element/addClass/)

[attribute()

Adds an attribute to the element.

](https://p5js.org/reference/p5.Element/attribute/)

[center()

Centers the element either vertically, horizontally, or both.

](https://p5js.org/reference/p5.Element/center/)

[child()

Attaches the element as a child of another element.

](https://p5js.org/reference/p5.Element/child/)

[class()

Adds a class attribute to the element using a given string.

](https://p5js.org/reference/p5.Element/class/)

[doubleClicked()

Calls a function when the mouse is pressed twice over the element.

](https://p5js.org/reference/p5.Element/doubleClicked/)

[dragLeave()

Calls a function when a file is dragged off the element.

](https://p5js.org/reference/p5.Element/dragLeave/)

[dragOver()

Calls a function when a file is dragged over the element.

](https://p5js.org/reference/p5.Element/dragOver/)

[draggable()

Makes the element draggable.

](https://p5js.org/reference/p5.Element/draggable/)

[drop()

Calls a function when the user drops a file on the element.

](https://p5js.org/reference/p5.Element/drop/)

[elt

The element's underlying HTMLElement object.

](https://p5js.org/reference/p5.Element/elt/)

[hasClass()

Checks if a class is already applied to element.

](https://p5js.org/reference/p5.Element/hasClass/)

[height

A Number property that stores the element's height.

](https://p5js.org/reference/p5.Element/height/)

[hide()

Hides the current element.

](https://p5js.org/reference/p5.Element/hide/)

[html()

Sets the inner HTML of the element, replacing any existing HTML.

](https://p5js.org/reference/p5.Element/html/)

[id()

Sets the element's ID using a given string.

](https://p5js.org/reference/p5.Element/id/)

[mouseClicked()

Calls a function when the mouse is pressed and released over the element.

](https://p5js.org/reference/p5.Element/mouseClicked/)

[mouseMoved()

Calls a function when the mouse moves over the element.

](https://p5js.org/reference/p5.Element/mouseMoved/)

[mouseOut()

Calls a function when the mouse moves off the element.

](https://p5js.org/reference/p5.Element/mouseOut/)

[mouseOver()

Calls a function when the mouse moves onto the element.

](https://p5js.org/reference/p5.Element/mouseOver/)

[mousePressed()

Calls a function when the mouse is pressed over the element.

](https://p5js.org/reference/p5.Element/mousePressed/)

[mouseReleased()

Calls a function when the mouse is released over the element.

](https://p5js.org/reference/p5.Element/mouseReleased/)

[mouseWheel()

Calls a function when the mouse wheel scrolls over the element.

](https://p5js.org/reference/p5.Element/mouseWheel/)

[parent()

Attaches the element to a parent element.

](https://p5js.org/reference/p5.Element/parent/)

[position()

Sets the element's position.

](https://p5js.org/reference/p5.Element/position/)

[remove()

Removes the element, stops all audio/video streams, and removes all callback functions.

](https://p5js.org/reference/p5.Element/remove/)

[removeAttribute()

Removes an attribute from the element.

](https://p5js.org/reference/p5.Element/removeAttribute/)

[removeClass()

Removes a class from the element.

](https://p5js.org/reference/p5.Element/removeClass/)

[show()

Shows the current element.

](https://p5js.org/reference/p5.Element/show/)

[size()

Sets the element's width and height.

](https://p5js.org/reference/p5.Element/size/)

[style()

Applies a style to the element by adding a CSS declaration.

](https://p5js.org/reference/p5.Element/style/)

[toggleClass()

Toggles whether a class is applied to the element.

](https://p5js.org/reference/p5.Element/toggleClass/)

[touchEnded()

Calls a function when the user stops touching the element.

](https://p5js.org/reference/p5.Element/touchEnded/)

[touchMoved()

Calls a function when the user touches the element and moves.

](https://p5js.org/reference/p5.Element/touchMoved/)

[touchStarted()

Calls a function when the element is touched.

](https://p5js.org/reference/p5.Element/touchStarted/)

[value()

Returns or sets the element's value.

](https://p5js.org/reference/p5.Element/value/)

[width

A Number property that stores the element's width.

](https://p5js.org/reference/p5.Element/width/)

[

### p5.File

](https://p5js.org/reference/p5/p5.File/)

[data

A string containing the file's data.

](https://p5js.org/reference/p5.File/data/)

[file

Underlying File object.

](https://p5js.org/reference/p5.File/file/)

[name

The file name as a string.

](https://p5js.org/reference/p5.File/name/)

[size

The number of bytes in the file.

](https://p5js.org/reference/p5.File/size/)

[subtype

The file subtype as a string.

](https://p5js.org/reference/p5.File/subtype/)

[type

The file MIME type as a string.

](https://p5js.org/reference/p5.File/type/)

[

### p5.MediaElement

](https://p5js.org/reference/p5/p5.MediaElement/)

[addCue()

Schedules a function to call when the audio/video reaches a specific time during its playback.

](https://p5js.org/reference/p5.MediaElement/addCue/)

[autoplay()

Sets the audio/video to play once it's loaded.

](https://p5js.org/reference/p5.MediaElement/autoplay/)

[clearCues()

Removes all functions scheduled with media.addCue().

](https://p5js.org/reference/p5.MediaElement/clearCues/)

[connect()

Sends the element's audio to an output.

](https://p5js.org/reference/p5.MediaElement/connect/)

[disconnect()

Disconnect all Web Audio routing, including to the main output.

](https://p5js.org/reference/p5.MediaElement/disconnect/)

[duration()

Returns the audio/video's duration in seconds.

](https://p5js.org/reference/p5.MediaElement/duration/)

[hideControls()

Hide the default HTMLMediaElement controls.

](https://p5js.org/reference/p5.MediaElement/hideControls/)

[loop()

Plays the audio/video repeatedly in a loop.

](https://p5js.org/reference/p5.MediaElement/loop/)

[noLoop()

Stops the audio/video from playing in a loop.

](https://p5js.org/reference/p5.MediaElement/noLoop/)

[onended()

Calls a function when the audio/video reaches the end of its playback.

](https://p5js.org/reference/p5.MediaElement/onended/)

[pause()

Pauses a media element.

](https://p5js.org/reference/p5.MediaElement/pause/)

[play()

Plays audio or video from a media element.

](https://p5js.org/reference/p5.MediaElement/play/)

[removeCue()

Removes a callback based on its ID.

](https://p5js.org/reference/p5.MediaElement/removeCue/)

[showControls()

Show the default HTMLMediaElement controls.

](https://p5js.org/reference/p5.MediaElement/showControls/)

[speed()

Sets the audio/video playback speed.

](https://p5js.org/reference/p5.MediaElement/speed/)

[src

Path to the media element's source as a string.

](https://p5js.org/reference/p5.MediaElement/src/)

[stop()

Stops a media element and sets its current time to 0.

](https://p5js.org/reference/p5.MediaElement/stop/)

[time()

Sets the media element's playback time.

](https://p5js.org/reference/p5.MediaElement/time/)

[volume()

Sets the audio/video volume.

](https://p5js.org/reference/p5.MediaElement/volume/)

## Data

### Array Functions

[append()

Adds a value to the end of an array.

](https://p5js.org/reference/p5/append/)

[arrayCopy()

Copies an array (or part of an array) to another array.

](https://p5js.org/reference/p5/arrayCopy/)

[concat()

Concatenates two arrays, maps to Array.concat().

](https://p5js.org/reference/p5/concat/)

[reverse()

Reverses the order of an array, maps to Array.reverse()

](https://p5js.org/reference/p5/reverse/)

[shorten()

Decreases an array by one element and returns the shortened array, maps to Array.pop().

](https://p5js.org/reference/p5/shorten/)

[shuffle()

Shuffles the elements of an array.

](https://p5js.org/reference/p5/shuffle/)

[sort()

Sorts an array of numbers from smallest to largest, or puts an array of words in alphabetical order.

](https://p5js.org/reference/p5/sort/)

[splice()

Inserts a value or an array of values into an existing array.

](https://p5js.org/reference/p5/splice/)

[subset()

Extracts an array of elements from an existing array.

](https://p5js.org/reference/p5/subset/)

### Conversion

[boolean()

Converts a String or Number to a Boolean.

](https://p5js.org/reference/p5/boolean/)

[byte()

Converts a Boolean, String, or Number to its byte value.

](https://p5js.org/reference/p5/byte/)

[char()

Converts a Number or String to a single-character String.

](https://p5js.org/reference/p5/char/)

[float()

Converts a String to a floating point (decimal) Number.

](https://p5js.org/reference/p5/float/)

[hex()

Converts a Number to a String with its hexadecimal value.

](https://p5js.org/reference/p5/hex/)

[int()

Converts a Boolean, String, or decimal Number to an integer.

](https://p5js.org/reference/p5/int/)

[str()

Converts a Boolean or Number to String.

](https://p5js.org/reference/p5/str/)

[unchar()

Converts a single-character String to a Number.

](https://p5js.org/reference/p5/unchar/)

[unhex()

Converts a String with a hexadecimal value to a Number.

](https://p5js.org/reference/p5/unhex/)

### Dictionary

[createNumberDict()

Creates a new instance of p5.NumberDict using the key-value pair or object you provide.

](https://p5js.org/reference/p5/createNumberDict/)

[createStringDict()

Creates a new instance of p5.StringDict using the key-value pair or the object you provide.

](https://p5js.org/reference/p5/createStringDict/)

[p5.StringDict

A simple Dictionary class for Strings.

](https://p5js.org/reference/p5/p5.StringDict/)

### LocalStorage

[clearStorage()

Removes all items in the web browser's local storage.

](https://p5js.org/reference/p5/clearStorage/)

[getItem()

Returns a value in the web browser's local storage.

](https://p5js.org/reference/p5/getItem/)

[removeItem()

Removes an item from the web browser's local storage.

](https://p5js.org/reference/p5/removeItem/)

[storeItem()

Stores a value in the web browser's local storage.

](https://p5js.org/reference/p5/storeItem/)

### String Functions

[join()

Combines an array of strings into one string.

](https://p5js.org/reference/p5/join/)

[match()

Applies a regular expression to a string and returns an array with the first match.

](https://p5js.org/reference/p5/match/)

[matchAll()

Applies a regular expression to a string and returns an array of matches.

](https://p5js.org/reference/p5/matchAll/)

[nf()

Converts a Number into a String with a given number of digits.

](https://p5js.org/reference/p5/nf/)

[nfc()

Converts a Number into a String with commas to mark units of 1,000.

](https://p5js.org/reference/p5/nfc/)

[nfp()

Converts a Number into a String with a plus or minus sign.

](https://p5js.org/reference/p5/nfp/)

[nfs()

Converts a positive Number into a String with an extra space in front.

](https://p5js.org/reference/p5/nfs/)

[split()

Splits a String into pieces and returns an array containing the pieces.

](https://p5js.org/reference/p5/split/)

[splitTokens()

Splits a String into pieces and returns an array containing the pieces.

](https://p5js.org/reference/p5/splitTokens/)

[trim()

Removes whitespace from the start and end of a String without changing the middle.

](https://p5js.org/reference/p5/trim/)

[

### p5.NumberDict

](https://p5js.org/reference/p5/p5.NumberDict/)

[add()

Add the given number to the value currently stored at the given key.

](https://p5js.org/reference/p5.NumberDict/add/)

[div()

Divide the given number with the value currently stored at the given key.

](https://p5js.org/reference/p5.NumberDict/div/)

[maxKey()

Return the highest key currently used in the Dictionary.

](https://p5js.org/reference/p5.NumberDict/maxKey/)

[maxValue()

Return the highest number currently stored in the Dictionary.

](https://p5js.org/reference/p5.NumberDict/maxValue/)

[minKey()

Return the lowest key currently used in the Dictionary.

](https://p5js.org/reference/p5.NumberDict/minKey/)

[minValue()

Return the lowest number currently stored in the Dictionary.

](https://p5js.org/reference/p5.NumberDict/minValue/)

[mult()

Multiply the given number with the value currently stored at the given key.

](https://p5js.org/reference/p5.NumberDict/mult/)

[sub()

Subtract the given number from the value currently stored at the given key.

](https://p5js.org/reference/p5.NumberDict/sub/)

[

### p5.TypedDict

](https://p5js.org/reference/p5/p5.TypedDict/)

[clear()

Removes all previously stored key-value pairs from the Dictionary.

](https://p5js.org/reference/p5.TypedDict/clear/)

[create()

Creates a new key-value pair in the Dictionary.

](https://p5js.org/reference/p5.TypedDict/create/)

[get()

Returns the value stored at the given key.

](https://p5js.org/reference/p5.TypedDict/get/)

[hasKey()

Returns true if the given key exists in the Dictionary, otherwise returns false.

](https://p5js.org/reference/p5.TypedDict/hasKey/)

[print()

Logs the set of items currently stored in the Dictionary to the console.

](https://p5js.org/reference/p5.TypedDict/print/)

[remove()

Removes the key-value pair stored at the given key from the Dictionary.

](https://p5js.org/reference/p5.TypedDict/remove/)

[saveJSON()

Converts the Dictionary into a JSON file for local download.

](https://p5js.org/reference/p5.TypedDict/saveJSON/)

[saveTable()

Converts the Dictionary into a CSV file for local download.

](https://p5js.org/reference/p5.TypedDict/saveTable/)

[set()

Updates the value associated with the given key in case it already exists in the Dictionary.

](https://p5js.org/reference/p5.TypedDict/set/)

[size()

Returns the number of key-value pairs currently stored in the Dictionary.

](https://p5js.org/reference/p5.TypedDict/size/)

## Structure

[disableFriendlyErrors

Turns off the parts of the Friendly Error System (FES) that impact performance.

](https://p5js.org/reference/p5/disableFriendlyErrors/)

[draw()

A function that's called repeatedly while the sketch runs.

](https://p5js.org/reference/p5/draw/)

[isLooping()

Returns true if the draw loop is running and false if not.

](https://p5js.org/reference/p5/isLooping/)

[loop()

Resumes the draw loop after noLoop() has been called.

](https://p5js.org/reference/p5/loop/)

[noLoop()

Stops the code in draw() from running repeatedly.

](https://p5js.org/reference/p5/noLoop/)

[pop()

Ends a drawing group that contains its own styles and transformations.

](https://p5js.org/reference/p5/pop/)

[preload()

A function that's called once to load assets before the sketch runs.

](https://p5js.org/reference/p5/preload/)

[push()

Begins a drawing group that contains its own styles and transformations.

](https://p5js.org/reference/p5/push/)

[redraw()

Runs the code in draw() once.

](https://p5js.org/reference/p5/redraw/)

[remove()

Removes the sketch from the web page.

](https://p5js.org/reference/p5/remove/)

[setup()

A function that's called once when the sketch begins running.

](https://p5js.org/reference/p5/setup/)

## Constants

[AUTO

AUTO allows us to automatically set the width or height of an element (but not both), based on the current height and width of the element.

](https://p5js.org/reference/p5/AUTO/)

[DEGREES

A String constant that's used to set the angleMode().

](https://p5js.org/reference/p5/DEGREES/)

[HALF_PI

A Number constant that's approximately 1.5708.

](https://p5js.org/reference/p5/HALF_PI/)

[HSB

HSB (hue, saturation, brightness) is a type of color model.

](https://p5js.org/reference/p5/HSB/)

[P2D

The default, two-dimensional renderer.

](https://p5js.org/reference/p5/P2D/)

[PI

A Number constant that's approximately 3.1416.

](https://p5js.org/reference/p5/PI/)

[QUARTER_PI

A Number constant that's approximately 0.7854.

](https://p5js.org/reference/p5/QUARTER_PI/)

[RADIANS

A String constant that's used to set the angleMode().

](https://p5js.org/reference/p5/RADIANS/)

[TAU

A Number constant that's approximately 6.2382.

](https://p5js.org/reference/p5/TAU/)

[TWO_PI

A Number constant that's approximately 6.2382.

](https://p5js.org/reference/p5/TWO_PI/)

[VERSION

Version of this p5.js.

](https://p5js.org/reference/p5/VERSION/)

[WEBGL

One of the two render modes in p5.js, used for computationally intensive tasks like 3D rendering and shaders.

](https://p5js.org/reference/p5/WEBGL/)

[WEBGL2

One of the two possible values of a WebGL canvas (either WEBGL or WEBGL2), which can be used to determine what capabilities the rendering environment has.

](https://p5js.org/reference/p5/WEBGL2/)

## Foundation

[class

A template for creating objects of a particular type.

](https://p5js.org/reference/p5/class/)

[console

Prints a message to the web browser's console.

](https://p5js.org/reference/p5/console/)

[for

A way to repeat a block of code when the number of iterations is known.

](https://p5js.org/reference/p5/for/)

[function

A named group of statements.

](https://p5js.org/reference/p5/function/)

[if

A way to choose whether to run a block of code.

](https://p5js.org/reference/p5/if/)

[let

Declares a new variable.

](https://p5js.org/reference/p5/let/)

[Array

A list that keeps several pieces of data in order.

](https://p5js.org/reference/p5/Array/)

[Boolean

A value that's either true or false.

](https://p5js.org/reference/p5/Boolean/)

[Number

A number that can be positive, negative, or zero.

](https://p5js.org/reference/p5/Number/)

[Object

A container for data that's stored as key-value pairs.

](https://p5js.org/reference/p5/Object/)

[String

A sequence of text characters.

](https://p5js.org/reference/p5/String/)

[while

A way to repeat a block of code.

](https://p5js.org/reference/p5/while/)

p5.js

Resources

- [Reference](https://p5js.org/reference)
- [Tutorials](https://p5js.org/tutorials)
- [Examples](https://p5js.org/examples)
- [Contribute](https://p5js.org/contribute)
- [Community](https://p5js.org/community)
- [About](https://p5js.org/about)
- [Start Coding](https://editor.p5js.org)
- [Donate](https://p5js.org/donate)

Information

- [Download](https://p5js.org/download)
- [Contact](https://p5js.org/contact)
- [Copyright](https://p5js.org/copyright)
- [Privacy Policy](https://p5js.org/privacy-policy)
- [Terms of Use](https://p5js.org/terms-of-use)

Socials

- [GitHub](https://github.com/processing/p5.js)
- [Instagram](https://www.instagram.com/p5xjs/)
- [X](https://twitter.com/p5xjs)
- [YouTube](https://www.youtube.com/@ProcessingFoundation)
- [Discord](https://discord.gg/SHQ8dH25r9)
- [Forum](https://discourse.processing.org/c/p5js)

[

Looking for the old p5.js site? Find it here!

](https://archive.p5js.org)
