---
URL: https://p5js.org/reference/p5/loadModel/
thumbnail: https://p5js.org/assets/img/p5js.png
site: 
date: 2025-01-25T16:42:36
duration: 2
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# loadModel

Description:: Loads a 3D model to create a [p5.Geometry](https://p5js.org/reference/p5/p5.Geometry) object.

`loadModel()` can load 3D models from OBJ and STL files. Once the model is loaded, it can be displayed with the [model()](https://p5js.org/reference/p5/model/) function, as in `model(shape)`.

There are three ways to call `loadModel()` with optional parameters to help process the model.

The first parameter, `path`, is always a `String` with the path to the file. Paths to local files should be relative, as in `loadModel('/assets/model.obj')`. URLs such as `'https://example.com/model.obj'` may be blocked due to browser security.

The first way to call `loadModel()` has three optional parameters after the file path. The first optional parameter, `successCallback`, is a function to call once the model loads. For example, `loadModel('/assets/model.obj', handleModel)` will call the `handleModel()` function once the model loads. The second optional parameter, `failureCallback`, is a function to call if the model fails to load. For example, `loadModel('/assets/model.obj', handleModel, handleFailure)` will call the `handleFailure()` function if an error occurs while loading. The third optional parameter, `fileType`, is the model’s file extension as a string. For example, `loadModel('/assets/model', handleModel, handleFailure, '.obj')` will try to load the file model as a `.obj` file.

The second way to call `loadModel()` has four optional parameters after the file path. The first optional parameter is a `Boolean` value. If `true` is passed, as in `loadModel('/assets/model.obj', true)`, then the model will be resized to ensure it fits the canvas. The next three parameters are `successCallback`, `failureCallback`, and `fileType` as described above.

The third way to call `loadModel()` has one optional parameter after the file path. The optional parameter, `options`, is an `Object` with options, as in `loadModel('/assets/model.obj', options)`. The `options` object can have the following properties:

```
let options = {
  // Enables standardized size scaling during loading if set to true.
  normalize: true,

  // Function to call once the model loads.
  successCallback: handleModel,

  // Function to call if an error occurs while loading.
  failureCallback: handleError,

  // Model's file extension.
  fileType: '.stl',

  // Flips the U texture coordinates of the model.
  flipU: false,

  // Flips the V texture coordinates of the model.
  flipV: false
};

// Pass the options object to loadModel().
loadModel('/assets/model.obj', options);
```

Models can take time to load. Calling `loadModel()` in [preload()](https://p5js.org/reference/p5/preload/) ensures models load before they're used in [setup()](https://p5js.org/reference/p5/setup/) or [draw()](https://p5js.org/reference/p5/draw/).

Note: There’s no support for colored STL files. STL files with color will be rendered without color.

