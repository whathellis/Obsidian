---
URL: https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#rendering-poly-as-subdiv
thumbnail: 
site: "[[]]"
date: 2024-09-23T17:42:30
duration: 5
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[../../01 Maps/Themes/Article|Article]] 
# Subdivision Surfaces | Multiverse

Description:: ## [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#writing-poly-as-subdiv) Writing poly as subdiv

In Multiverse you can specify which Maya poly mesh geometry should be described as a subdivision surface when writing your asset to a USD file. This process is rendering agnostic, all you need is either:

-   Hit `3` on the keyboard with a poly mesh shape selected. This will also draw it as subdivision on the viewport (and can be optionally disabled in the smooth mesh options).
    
-   Set the smooth mesh preview attributes on the attribute editor.
    

When writing your asset as a USD file, Multiverse will check whether this attribute is set and tag the mesh accordingly.

Important

It is important to understand that if a mesh is set to be a subdivision in Maya with any of the above methods, when Multiverse writes the USD file it will ignore the "Normals" flag in the Mutiverse write UI and ensure that Normals are NOT written to USD, this because when rendering a subdivision surface the original normals are ignored and new ones are computed on-the-fly by each renderer. Multiverse does this since Normals take considerable space for animated / deforming geometric assets (as they are big arrays of per-mesh-point data), and is wasteful to write them if you are rendering a subdivision surface.

Note

You can always set a poly mesh to render as subdivisions after you have written your USD asset.

![](https://j-cube.jp/solutions/multiverse/docs/assets/img/smoothpoly.25586c40.png)

## [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#rendering-poly-as-subdiv) Rendering poly as subdiv

Multiverse honors geometry tagged as subdivision surface (see the previous section) and renders it as such with the renderers capable of analytically compute subdivisions at render-time: these are **3DelightNSI** and **Renderman**.

For the **Arnold**, **Redshift** and **VRay** renderers more information is needed to render a mesh as a subdivision surface: specifically they all need the number of subdivision iterations to be set before rendering (other parameters may be needed depending on the renderer).

There are several ways to set these attributes, and there is an override order:

-   In the Attribute Editor of the Multiverse Compound (shape node) you can set your renderer equivalents for "render as a subdivision" and "iteration number". These are typically under each renderer extension attributes, which appear on the compound shape node. When doing so, all contents of the Compound will render as subdivisions.
    
-   If you have previously written overrides, and they are set as a layer in your Compound, upper layers will override lower layers according to their contents.
    
-   In MEOW, on a item/prim you can assign an attribute override on the desired item location (remember that children will inherit if not further overridden) This will override the settings on the Compound and on the layers (once these) overrides are written they can be then loaded as a layer and the stacking order will matter. Again you can apply new overrides in MEOW, and again these overrides will override the layers in the Compound.
    

## [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#rendering-subdivisions-a-panorama) Rendering subdivisions: a panorama

Each renderer handles subdivision surfaces in a a different way.

Note that subdivision surfaces are closely related to displacement: most of the time you want to displace on subdivision surfaces rather than on “raw” polygons.

Here's an overview for each renderer:

### [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#_3delight-subdivs) 3Delight Subdivs

3Delight analytically computes subdivision surfaces *at render time* in a completely automatic way and without the need to set any additional attributes for UV interpolation and dicing: everything is handled automatically.

This has several major advantages:

-   Does not require any additional attribute
-   Works perfectly with displacement
-   Produces infinitely smooth subdivision surfaces
-   It is fast and much more memory efficient

Note

When benchmarking against another renderer that pre-tessellates subdivs, make sure to set a decent number of subdivision iterations to produce a meaningful and comparable benchmark, ideally your benchmarks should perform renders at different camera distance from the subject.

### [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#arnold-subdivs) Arnold Subdivs

Arnold pre-tessellates subdivision surfaces *before rendering*. This has several major drawbacks:

-   It requires a lot of Arnold shape attributes to control the look of subdivision surfaces. This increases workflow complexity.
-   Impacts directly displacement which relies on subdivision surfaces for high quality results. Arnold relies on a gimmick called “auto-bump” which tries to mitigate the need of high number of subdivision iterations by extrapolating bump from high frequency detail in a texture. This produces images with much lower image quality and increases workflow complexity.
-   Produces subdivision surfaces are not infinitely smooth (meaning that zooming into the geometry will exhibit polygonal faceting at some point). This requires pre-planning with camera zooms.
-   Requires very large amount of memory and slows down a lot when rendering high number of subdivision iterations are necessary, and when rendering HQ displacements.
-   Hides Arnold incapability to efficiently deal with displacement and introduces a bias as it requires a higher level of competence for the user to produce results that are comparable between renderers.

In addition to that, with the GPU version of Arnold memory implications become significant when subdividing to a high level and when using displacement on subdivided geometry.

### [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#redshift-subdivs) Redshift Subdivs

Redshift pre-tessellates subdivision surfaces *before rendering* and incurs in the same limitations as Arnold and VRay.

In addition to that, being a GPU-only renderer, memory implications are significant when subdividing to a high level and when using displacement on subdivided geometry.

### [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#renderman-subdivs) Renderman Subdivs

Similarly to 3Delight, Renderman also analytically computes subdivision surfaces *at render time*, but it does so in a "semi-automatic" way: the user still needs to set additional attributes for interpolation and dicing as well other attributes are needed for geometry and displacement. This adds complexity to the workflow and requires more know-how on the user side.

Note

When benchmarking against another renderer that pre-tessellates subdivs, make sure to set a decent number of subdivision iterations to produce a meaningful and comparable benchmark, ideally your benchmarks should perform renders at different camera distance from the subject.

### [#](https://j-cube.jp/solutions/multiverse/docs/usage/subdivision-surfaces.html#vray-subdivs) VRay Subdivs

VRay pre-tessellates subdivision surfaces *before rendering* and incurs in the same drawbacks mentioned in the Arnold section.

In addition to that, with the GPU version of VRay memory implications become significant when subdividing to a high level and when using displacement on subdivided geometry.

Last Updated: 6/29/2023, 7:46:52 AM

