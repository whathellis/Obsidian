---
date: 2024-09-15
topics: 
dg-publish: true
---

[[../../07/YouTube/Study/3D USD Masterclass Scene Assembly and Rendering|3D USD Masterclass Scene Assembly and Rendering]]
> [!bug] Scene Asscembly
> Placing elements into a scene to build an arrangement of lights, cameras, geometry, materials, etc.

> [!bug] Scene Description
> A translated set of code describing a scene assembly to a particular render engine.
> **.IFD**, **.blend**, etc.

> [!tldr] USD (Universal Scene Description)
> A framework developed by Pixar for a universally understood scene description that allow interchangeability between software packages.

> [!example] USD Primitive
> Any element in you USD scene. Each primitive can perform a different function, but fundamentally they are the most basic building blocks of USD.

> [!bug] Primitive Type
> The type of the primitive defined by its function in the scene. Cameras, lights, meshes and materials are all types of primitives.
> > **Xform**
> > A parent primitive which can be moved around. Any primitive which is a child of an xform will inherit its transform
> 
> > **Scope**
> > A parent primitive which cannot be moved around. This is useful for organizing your scene and nesting primitives within other primitives.

> [!bug] Primitive Kinds
> A tagged function of USD for defining the use of a primitive within the scene.
> > **Component**
> > A single asset which is not made up of other assets. A door, a leaf, etc.
> 
> > **Assembly**
> > An important compiled asset made up of various other assets. A house made up of windows, walls, doors, etc.
> 
> > **Groups**
> > Arbitrary groupings of other primitives. This can be parent to any set of familiar or similar components/assemblies