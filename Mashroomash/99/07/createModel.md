---
URL: https://p5js.org/reference/p5/createModel/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:42:28
duration: 1
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# createModel

Description:: Load a 3d model from an OBJ or STL string.

OBJ and STL files lack a built-in sense of scale, causing models exported from different programs to vary in size. If your model doesn't display correctly, consider using `loadModel()` with `normalize` set to `true` to standardize its size. Further adjustments can be made using the `scale()` function.

Also, the support for colored STL files is not present. STL files with color will be rendered without color properties.

-   Options can include:

-   `modelString`: Specifies the plain text string of either an stl or obj file to be loaded.
-   `fileType`: Defines the file extension of the model.
-   `normalize`: Enables standardized size scaling during loading if set to true.
-   `successCallback`: Callback for post-loading actions with the 3D model object.
-   `failureCallback`: Handles errors if model loading fails, receiving an event error.
-   `flipU`: Flips the U texture coordinates of the model.
-   `flipV`: Flips the V texture coordinates of the model.

## Examples

## Syntax

`createModel(modelString, [fileType], normalize, [successCallback], [failureCallback])``createModel(modelString, [fileType], [successCallback], [failureCallback])``createModel(modelString, [fileType], [options])`

## Parameters

modelString

String:

String of the object to be loaded

fileType

String:

The file extension of the model (`.stl`, `.obj`).

normalize

Boolean:

If true, scale the model to a standardized size when loading

successCallback

function(p5.Geometry):

Function to be called once the model is loaded. Will be passed the 3D model object.

failureCallback

Function(Event):

called with event error if the model fails to load.

## Returns

p5.Geometry: the [p5.Geometry](https://p5js.org/reference/p5/createModel/#/p5.Geometry) object

