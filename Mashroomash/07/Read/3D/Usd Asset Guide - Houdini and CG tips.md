---
URL: https://www.tokeru.com/cgwiki/UsdAssetGuide.html
thumbnail: 
site: "[[]]"
date: 2024-09-23T17:19:24
duration: 17
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Usd Asset Guide - Houdini and CG tips

### Introduction [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#introduction)

alt layout.... [UsdAssetGuide2](https://www.tokeru.com/cgwiki/UsdAssetGuide2.html "wikilink")

A few people from Sidefx, Epic, Foundry, Tangent, ALA got together to have a chat about USD. We noticed a substantial knowledge gap between having a poke around kitchen.usd vs actually implementing USD for a studio.

After some back and forth, we felt it'd be handy to give a field guide of how to get started with USD, trying to stay as platform agnostic and jargon free as possible.

Step 1 was to look at assets.

Shawn Dunn from Epic wrote an asset brief, Mike Lydon from SideFx had a go at following the brief in Solaris, eventually roping in Rob Stauffer and Chris Rydalch to help. This is a WIP document to explain those concepts in plain English.

Chris went above and beyond though. He had a think and went and made the component builder workflow in lops. It's really really good, you can just skip this entire guide and put a component builder in your lops scene. He's also made a great video to go with it, set aside an hour and watch, you'll thank me for it.

[https://youtu.be/EgTqz6y\_oAs](https://youtu.be/EgTqz6y_oAs)

### Basic asset [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#basic-asset)

The most simple definition of an asset would be a 3D mesh. Lets assume we want something *slightly* more complex than that, and want an asset that contains a mesh and a material.

As such we need a few things:

-   A mesh
-   A material
-   A way to assign that material to a mesh.

On top of these, we'll likely need a few other things:

-   Names for the mesh and the material
-   Scene hierarchy locations for the mesh and material
-   On-disk location(s) to save this asset.

The first is self evident, the others need a little explaining.

#### Scene hierarchy location [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#scene-hierarchy-location)

![](https://www.tokeru.com/cgwiki/assets/Treeviews.2e7f8b5e.png)*Example scene hierarchy in Houdini (Solaris), Maya Outliner, Katana, USDView*

Scene hierarchy simply refers to where in a tree view of your asset the various bits live. This tree view goes by several names in different packages, but should be immediately recognizable for your preferred app:

-   Maya Outliner, or...

-   Unreal World Outliner
-   Katana Scene Graph
-   Unity Hierarchy window
-   Max Scene Explorer
-   C4D Objects Tab
-   Blender Outliner/Scene Collection
-   Houdini Tree View

Some of those applications will only have 3d objects in the hierarchy, things like materials and material nodes will live somewhere else. In USD nothing is hidden, so meshes, materials, render nodes are all visible in this hierarchy, called the **Scene Graph**.

We should be able to say 'the mesh will be found at...

`/Assets/myAsset/geometry/mesh` 

...and the material at...

`/Assets/myAsset/materials/mymaterial`

...for example. Those locations and names are up to you, but they need to be defined.

#### On disk location(s) [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#on-disk-location-s)

We need to say where the file is saved, that's intuitive enough. But why would we need to define multiple save locations?

The short answer: USD allows you to say up front, 'the bucket asset lives at Bucket**Asset**.usd', but under the hood BucketAsset.usd might point to 2 other USD files, Bucket**Mesh**.usd and Bucket**Surfacing**.usd.

Modelling and surfacing save to their respective files, downstream departments just load the high level asset, and it all works.

The longer answer:

Production pipeline diagrams will show a nice straight line between modelling and surfacing. It implies modelling save a file, it flows down to surfacing, they save a material on top of the file, it flows down to the next department.

The reality is the departments work in parallel, publishing at at different rates. Surfacing might start work on a material weeks before a model is ready, in other cases modelling might have many assets published, and need to see it in shots for context. Using the simplistic pipeline either surfacing couldn't start anything until models are ready, and modelling could never see their work until surfacing published a material for every mesh.

But what if you could break that? What if you could specify a location on disk for modelling to save their work, another for surfacing, and have a third location that combines the two? That way modelling could save as often as they want, surfacing could even start before modelling, and the asset will always get the combo of both.

In USD, it's possible to break an asset into layers, and define different save locations for each layer. In this case we'll define the geometry in one layer which is our final output, save the material into a different layer with its own save location, and import it to the final asset.

#### Refined asset steps [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#refined-asset-steps)

Let's go through these steps again in more detail:

-   Create a 'main' layer, and store the mesh in it and a hierarchy location (called a **primitive path or prim path** in USD)
-   Create a layer, define a material in it and a save location
-   Reference the material layer into the main layer and set its prim path
-   Assign the material
-   Write a USD file

#### Implementation and output [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#implementation-and-output)

Here's how that looks in Houdini's Solaris. Solaris represents USD operations as nodes, you can see this represents a flowchart of the steps we just defined pretty closely:

![](https://www.tokeru.com/cgwiki/assets/Selection_209.072c3988.png)

It creates a layer to load a model, defines another layer for materials and sets a save location, combines the layers, assigns materials, saves a file.

The end result of this is a few usd files on disk. USD can be saved as binary (the default) or plain text, here's the plain text result with some highlighting for the important bits:

![](https://www.tokeru.com/cgwiki/assets/Usd01_overlay.e179bbe3.png)

Here's the same in a collapsed text box if you want to copy/paste into an editor and have a play:

BucketAsset.usda

JSON

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    subLayers = [
        @./Bucket.usdc@
    ]
    timeCodesPerSecond = 24
    upAxis = "Y"
)

over "BucketAsset"
{
    def "Materials" (
        append references = @./Materials/BucketMaterials.usda@</BucketAsset/Materials>
    )
    {
    }

    over "Render"
    {
        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }
    }
}
```

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    subLayers = [
        @./Bucket.usdc@
    ]
    timeCodesPerSecond = 24
    upAxis = "Y"
)

over "BucketAsset"
{
    def "Materials" (
        append references = @./Materials/BucketMaterials.usda@</BucketAsset/Materials>
    )
    {
    }

    over "Render"
    {
        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }
    }
}
```

That file refers to BucketMaterials.usda, you'll find that below. You can see it stores all the nodes that make up the shading network, and the connections between the nodes.

BucketMaterials.usda

JSON

```
#usda 1.0
(
    metersPerUnit = 1
    upAxis = "Y"
)

def Xform "BucketAsset"
{
    def Xform "Materials"
    {
        def Material "BucketMat"
        {
            token outputs:displacement.connect = </BucketAsset/Materials/BucketMat/BucketUSDPreview.outputs:displacement>
            token outputs:karma:displacement.connect = </BucketAsset/Materials/BucketMat/BucketMat_displace.outputs:displacement>
            token outputs:karma:surface.connect = </BucketAsset/Materials/BucketMat/BucketMat_surface.outputs:surface>
            token outputs:surface.connect = </BucketAsset/Materials/BucketMat/BucketUSDPreview.outputs:surface>

            def Shader "BucketMat_surface"
            {
                uniform token info:implementationSource = "sourceAsset"
                uniform asset info:sourceAsset = @opdef:/Vop/principledshader::2.0?SurfaceVexCode@
                int inputs:baseBumpAndNormal_enable = 1
                vector3f inputs:basecolor = (1, 1, 1)
                asset inputs:basecolor_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_BaseColor.png@
                int inputs:basecolor_useTexture = 1
                asset inputs:baseNormal_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Normal.png@
                float inputs:metallic = 1
                asset inputs:metallic_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Metallic.png@
                int inputs:metallic_useTexture = 1
                float inputs:rough = 1
                asset inputs:rough_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Roughness.png@
                int inputs:rough_useTexture = 1
                token outputs:surface
            }

            def Shader "BucketMat_displace"
            {
                uniform token info:implementationSource = "sourceAsset"
                uniform asset info:sourceAsset = @opdef:/Vop/principledshader::2.0?DisplacementVexCode@
                int inputs:dispTex_enable = 1
                float inputs:dispTex_scale = 0.005
                asset inputs:dispTex_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Height.png@
                token outputs:displacement
            }

            def Shader "BucketUSDPreview"
            {
                uniform token info:id = "UsdPreviewSurface"
                color3f inputs:diffuseColor.connect = </BucketAsset/Materials/BucketMat/usduvtextureBaseColor.outputs:rgb>
                float inputs:metallic = 1
                float inputs:metallic.connect = </BucketAsset/Materials/BucketMat/usduvtextureMetallic.outputs:r>
                normal3f inputs:normal.connect = </BucketAsset/Materials/BucketMat/usduvtextureNormal.outputs:rgb>
                float inputs:roughness.connect = </BucketAsset/Materials/BucketMat/usduvtextureRoughness.outputs:r>
                token outputs:displacement
                token outputs:surface
            }

            def Shader "usduvtextureBaseColor"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_BaseColorA.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                vector3f outputs:rgb
            }

            def Shader "usdprimvarreader_st"
            {
                uniform token info:id = "UsdPrimvarReader_float2"
                token inputs:varname = "st"
                float2 outputs:result
            }

            def Shader "usduvtextureMetallic"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Metallic.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                float outputs:r
            }

            def Shader "usduvtextureRoughness"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Roughness.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                float outputs:r
            }

            def Shader "usduvtextureNormal"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Normal.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                vector3f outputs:rgb
            }
        }
    }
}
```

```
#usda 1.0
(
    metersPerUnit = 1
    upAxis = "Y"
)

def Xform "BucketAsset"
{
    def Xform "Materials"
    {
        def Material "BucketMat"
        {
            token outputs:displacement.connect = </BucketAsset/Materials/BucketMat/BucketUSDPreview.outputs:displacement>
            token outputs:karma:displacement.connect = </BucketAsset/Materials/BucketMat/BucketMat_displace.outputs:displacement>
            token outputs:karma:surface.connect = </BucketAsset/Materials/BucketMat/BucketMat_surface.outputs:surface>
            token outputs:surface.connect = </BucketAsset/Materials/BucketMat/BucketUSDPreview.outputs:surface>

            def Shader "BucketMat_surface"
            {
                uniform token info:implementationSource = "sourceAsset"
                uniform asset info:sourceAsset = @opdef:/Vop/principledshader::2.0?SurfaceVexCode@
                int inputs:baseBumpAndNormal_enable = 1
                vector3f inputs:basecolor = (1, 1, 1)
                asset inputs:basecolor_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_BaseColor.png@
                int inputs:basecolor_useTexture = 1
                asset inputs:baseNormal_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Normal.png@
                float inputs:metallic = 1
                asset inputs:metallic_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Metallic.png@
                int inputs:metallic_useTexture = 1
                float inputs:rough = 1
                asset inputs:rough_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Roughness.png@
                int inputs:rough_useTexture = 1
                token outputs:surface
            }

            def Shader "BucketMat_displace"
            {
                uniform token info:implementationSource = "sourceAsset"
                uniform asset info:sourceAsset = @opdef:/Vop/principledshader::2.0?DisplacementVexCode@
                int inputs:dispTex_enable = 1
                float inputs:dispTex_scale = 0.005
                asset inputs:dispTex_texture = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_%(UDIM)d_Height.png@
                token outputs:displacement
            }

            def Shader "BucketUSDPreview"
            {
                uniform token info:id = "UsdPreviewSurface"
                color3f inputs:diffuseColor.connect = </BucketAsset/Materials/BucketMat/usduvtextureBaseColor.outputs:rgb>
                float inputs:metallic = 1
                float inputs:metallic.connect = </BucketAsset/Materials/BucketMat/usduvtextureMetallic.outputs:r>
                normal3f inputs:normal.connect = </BucketAsset/Materials/BucketMat/usduvtextureNormal.outputs:rgb>
                float inputs:roughness.connect = </BucketAsset/Materials/BucketMat/usduvtextureRoughness.outputs:r>
                token outputs:displacement
                token outputs:surface
            }

            def Shader "usduvtextureBaseColor"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_BaseColorA.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                vector3f outputs:rgb
            }

            def Shader "usdprimvarreader_st"
            {
                uniform token info:id = "UsdPrimvarReader_float2"
                token inputs:varname = "st"
                float2 outputs:result
            }

            def Shader "usduvtextureMetallic"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Metallic.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                float outputs:r
            }

            def Shader "usduvtextureRoughness"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Roughness.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                float outputs:r
            }

            def Shader "usduvtextureNormal"
            {
                uniform token info:id = "UsdUVTexture"
                asset inputs:file = @../Textures/repacked_BucketWithRopeHandle/repacked_BucketWithRopeHandle_UV_1001_Normal.png@
                float2 inputs:st.connect = </BucketAsset/Materials/BucketMat/usdprimvarreader_st.outputs:result>
                vector3f outputs:rgb
            }
        }
    }
}
```

The mesh geometry is stored in Bucket.usdc, a binary format, here a download link:

[Bucket.usdc](https://www.tokeru.com/cgwiki/Bucket.usdc)

While this could be stored in plain text as well, there's often no need for it, as its unlikely to be looked at by humans. Binary is better for size on disk and loading speed.

### Adding Render and Proxy meshes with Purpose [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#adding-render-and-proxy-meshes-with-purpose)

Most studios want an asset available in various formats. A final quality one for rendering, a low res one for layout for example.

USD allows this by tagging meshes with a 'purpose'. USD allows 3 kinds of purpose out of the box:

-   Render
-   Proxy
-   Guide

As implied **render** is final hero geometry, **proxy** is a lightweight standin, **guide** might be for anim controls for example.

So to extend this setup, we'll define another layer, load the proxy mesh into there. We then combine the hero and low-res meshes together into a single heirarchy, assign the purpose tag to the hero and low res meshes, and assign material as before:

Here's the Solaris overview of that:

![](https://www.tokeru.com/cgwiki/assets/Selection_001.f3ac6e4d.png)

A sublayer is one of several ways of combining hierarchies of things. It does a 'dumb' merge, so it just takes all the stuff from each of the inputs and throws them together.

In this gif you can see one node has a hierarchy under /BucketAsset/Render,the other under /BucketAsset/Proxy, the sublayer combines so that we end up with a tree with both Proxy and Render under /BucketAsset:

![](https://www.tokeru.com/cgwiki/assets/Sublayer_combine.db21e813.gif)

With the render and proxy models sitting together in the hierarchy, they get their purpose tag's set.

The rest is as same as before, create a layer to bring in the materials, assign, write out a file.

In terms of the usd file itself the changes are pretty straightforward; it now loads in 2 meshes via the sublayer command, and sets the purpose tags:

![](https://www.tokeru.com/cgwiki/assets/Render_and_proxy_usd.d745a693.jpg)

Here's the full usda file:

BucketAssetWithProxy.usda

JSON

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    subLayers = [
        @./BucketProxy.usdc@,
        @./Bucket.usdc@
    ]
    timeCodesPerSecond = 24
    upAxis = "Y"
)

over "BucketAsset"
{
    over "Proxy"
    {
        uniform token purpose = "proxy"

        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }
    }

    over "Render"
    {
        uniform token purpose = "render"

        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
            rel proxyPrim = </BucketAsset/Proxy/Bucket>
            uniform token purpose = "render"
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
            rel proxyPrim = </BucketAsset/Proxy/Rope>
            uniform token purpose = "render"
        }
    }

    def "Materials" (
        append references = @./Materials/BucketMaterials.usda@</BucketAsset/Materials>
    )
    {
    }
}
```

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    subLayers = [
        @./BucketProxy.usdc@,
        @./Bucket.usdc@
    ]
    timeCodesPerSecond = 24
    upAxis = "Y"
)

over "BucketAsset"
{
    over "Proxy"
    {
        uniform token purpose = "proxy"

        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
        }
    }

    over "Render"
    {
        uniform token purpose = "render"

        over "Bucket"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
            rel proxyPrim = </BucketAsset/Proxy/Bucket>
            uniform token purpose = "render"
        }

        over "Rope"
        {
            rel material:binding = </BucketAsset/Materials/BucketMat>
            rel proxyPrim = </BucketAsset/Proxy/Rope>
            uniform token purpose = "render"
        }
    }

    def "Materials" (
        append references = @./Materials/BucketMaterials.usda@</BucketAsset/Materials>
    )
    {
    }
}
```

### Adding mesh variations [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#adding-mesh-variations)

It's pretty common in a production to find assets like car01 car02 car03, tree01 tree02 tree03 etc. Most of the time these are defined as unique assets, everyone assumes this is how it has to be.

With USD however, you could have a single 'car' asset, or a single 'tree' asset, and have the ability to choose from a range of cars or trees. These are called **variants**.

Variants go beyond just pointing to different models on disk though. You could also have variants that only swap between materials (eg clean car vs a dirty car), or get really tricky and selectively hide and show parts of a mesh within a variant.

'So what' you might say, 'we can do that in \[insert 3d app\] fine'. You might also say 'separate asset definitions are good enough'. The big win here is once again this is available to all 3d apps that can talk USD. So while this asset might be authored in Houdini, the layout department can be loading cars and trees in maya, and swapping between different variants. And then further downstream again in Katana, lighters can access and swap between variants if there's a last minute change, without having to go all the way back to layout, or modelling, or a callsheet for the assets belonging to a shot or set.

Here's the Solaris method for adding a geometry variant:

![](https://www.tokeru.com/cgwiki/assets/Selection_002.305f2855.png)

In this example Mike has taken the bucket asset, hidden the handle, and made that a variant. What's cool about this method is USD will be smart enough not to save the entire bucket to disk with the handle, then entire bucket again without a handle, it's smart enough to just store the difference between the models. Not impressive with a bucket, but that could save huge amounts of memory and disk space for massive assets with relatively small changes between variants.

### Adding level of detail [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#adding-level-of-detail)

What if you need more than just a highres ('render') and lowres ('proxy') version of your asset? Variants can be used for this too. While the previous example was a swap between a handle and no-handle version of bucket, (and we might name that variant 'handle'), we could have a a variant selection called 'lod', and put high/medium/low res meshes into those variants.

The Solaris network below is showing off by procedurally creating those mesh reductions, but the steps involved would be the same for any other app or pipeline:

-   take your highres mesh
-   create medium and low res reductions (as many as you feel you require)
-   define a variant called 'lod' (or whatever name you want)
-   attach those reductions to the variant

This network goes the extra mile and also defines lod's for both the render and proxy purposes. You could argue you don't need those, but hey, choice is good right?

![](https://www.tokeru.com/cgwiki/assets/Selection_003.eb55c918.png)

### Adding material variation [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#adding-material-variation)

And here we go all the way, setting material variations as well as model variations. You can see the network is getting pretty baroque, but the base idea is the same:

-   bring in the mesh
-   create the LOD's
-   create several materials
-   assign materials to lods
-   create a variant set that lets you choose between materials and lods

![](https://www.tokeru.com/cgwiki/assets/Selection_004.06f417c0.png)

### Versioning [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#versioning)

A modeller publishes v027 of a chair. A surfacing artist publishes v12 of a chair material. A layout artist pulls a chair in back when it was v011, and surfacing hasn't started, publishes a set as v002. Then lighting get the set and are asked what version of the chair they're using, and make sure to skip v08 of the surfacing, but use the latest chair.

This nightmare of versions and departments is all too common in production, which is why USD has the concept of 'which asset should I load' built into its core.

In an ideal scenario a studio's production system (Shotgun, f-track, internal systems) will keep track of which versions are available for any given asset. USD files themselves can talk directly to that production database, so that collections of USD elements don't need paths on disk, just the right way to ask the database 'which version should I load?'. A studio could choose to have all assets default to the latest available, or to a set of known 'approved' assets, or whatever other configuration needed.

The part of USD that deals with this is called the Asset Resolver, and while powerful when implemented properly, could bring a studio to its knees if done badly. Imagine a scene involving a forest next to a city; when the shot is loaded it'll suddenly hit the production database with hundreds and thousands of queries. These need to run in parallel and quickly, so the tech requirements on an Asset Resolver are high.

In its vanilla form USD ships with a simple Asset Resolver; simply one that points to regular paths on disk. If you haven't take the plunge to implement an Asset Resolver, what can you do?

One possible option is simlinks. As modellers publish chair\_geo\_v01.usd, chair\_geo\_v02.usd, the publish code creates chair\_geo.usd, which is a simlink to the latest version. That way a layout artist downstream can just point to it, and as the modellers update, they too will get the update.

### Sets [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#sets)

Sets in a simple form can be just a combination of other USD files. Previously we used sublayers to do a 'dumb' combination of files, but for a set we would want more control. You wouldn't expect all the items for a bedroom set to just all be sitting in a flat hierarchy at the top of the outliner, you'd want items organised into logical groups.

References give you this functionality to organise, so you can reference a usd file on disk like you would do with a maya reference, but you have the ability to only refer to sub-sections of that file if you want, and also to be explicity and say 'this will be parented beneath /bedroom/wardrobe/topshelf/'

A simple set could look like this:

![](data:image/png;base64,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)

Which under the hood is just a set of references to usd files on disk, and their transforms:

set.usda

JSON

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    timeCodesPerSecond = 24
    upAxis = "Y"
)

def Xform "set" (
    kind = "group"
)
{
    def "PigAsset" (
        kind = "component"
        add payload = @./PigAsset.usda@
    )
    {
        matrix4d xformOp:transform = ( (0.33999316950907743, 0, -0.22122418961586124, 0), (0, 0.4056297540664673, 0, 0), (0.22122418961586127, 0, 0.33999316950907743, 0), (-1.3854224424692467, 0.3093985690746131, 0.11506395521922762, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]
    }

    def "BoxAsset" (
        kind = "component"
        add payload = @./BoxAsset.usda@</BoxAsset>
    )
    {
        matrix4d xformOp:transform = ( (0.30488509121989554, 0, 0, 0), (0, 0.30488509121989554, 0, 0), (0, 0, 0.30488509121989554, 0), (0.1113539646492816, 0, -2.087946345947296, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]
    }

    def Xform "props" (
        kind = "group"
    )
    {
        matrix4d xformOp:transform = ( (1, 0, 0, 0), (0, 1, 0, 0), (0, 0, 1, 0), (0, 0, 0, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]

        def Xform "buckets" (
            kind = "group"
        )
        {
            def "BucketAsset" (
                kind = "component"
                add payload = @./BucketAsset.usda@</BucketAsset>
            )
            {
                matrix4d xformOp:transform = ( (0.5121324183710805, 0, 0.8589065060024802, 0), (0, 1, 0, 0), (-0.8589065060024802, 0, 0.5121324183710805, 0), (-0.5144985079553781, 6.454063949945521e-9, -1.0041869573334419, 1) )
                uniform token[] xformOpOrder = ["xformOp:transform"]
            }

            def "BucketAsset2" (
                kind = "component"
                add payload = @./BucketAsset.usda@</BucketAsset>
            )
            {
                matrix4d xformOp:transform = ( (1, 0, 0, 0), (0, 1, 0, 0), (0, 0, 1, 0), (0, 0, 0, 1) )
                uniform token[] xformOpOrder = ["xformOp:transform"]
            }
        }
    }
}
```

```
#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    timeCodesPerSecond = 24
    upAxis = "Y"
)

def Xform "set" (
    kind = "group"
)
{
    def "PigAsset" (
        kind = "component"
        add payload = @./PigAsset.usda@
    )
    {
        matrix4d xformOp:transform = ( (0.33999316950907743, 0, -0.22122418961586124, 0), (0, 0.4056297540664673, 0, 0), (0.22122418961586127, 0, 0.33999316950907743, 0), (-1.3854224424692467, 0.3093985690746131, 0.11506395521922762, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]
    }

    def "BoxAsset" (
        kind = "component"
        add payload = @./BoxAsset.usda@</BoxAsset>
    )
    {
        matrix4d xformOp:transform = ( (0.30488509121989554, 0, 0, 0), (0, 0.30488509121989554, 0, 0), (0, 0, 0.30488509121989554, 0), (0.1113539646492816, 0, -2.087946345947296, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]
    }

    def Xform "props" (
        kind = "group"
    )
    {
        matrix4d xformOp:transform = ( (1, 0, 0, 0), (0, 1, 0, 0), (0, 0, 1, 0), (0, 0, 0, 1) )
        uniform token[] xformOpOrder = ["xformOp:transform"]

        def Xform "buckets" (
            kind = "group"
        )
        {
            def "BucketAsset" (
                kind = "component"
                add payload = @./BucketAsset.usda@</BucketAsset>
            )
            {
                matrix4d xformOp:transform = ( (0.5121324183710805, 0, 0.8589065060024802, 0), (0, 1, 0, 0), (-0.8589065060024802, 0, 0.5121324183710805, 0), (-0.5144985079553781, 6.454063949945521e-9, -1.0041869573334419, 1) )
                uniform token[] xformOpOrder = ["xformOp:transform"]
            }

            def "BucketAsset2" (
                kind = "component"
                add payload = @./BucketAsset.usda@</BucketAsset>
            )
            {
                matrix4d xformOp:transform = ( (1, 0, 0, 0), (0, 1, 0, 0), (0, 0, 1, 0), (0, 0, 0, 1) )
                uniform token[] xformOpOrder = ["xformOp:transform"]
            }
        }
    }
}
```

Note that I've parented the entire thing under a top level /set folder. This is important if we want to load this set into shots later. In the same way that assets were referenced into the set, the set will be referenced into shots. Reference can only point to a single primitive. So if there are multiple top level nodes, a reference will only display one.

*Structure? Supersets? Payloads? Naming schemes?*

### Shots [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#shots)

A shot in turn references in the set, and and whatever other per shot stuff required (cameras, lights, animation caches etc)

You can see that there's an interesting inversion of complexity; the shot itself might contain a big complex set, lots of materials, animation and whatnot, but the usd file itself is very minimal and clean:

![](data:image/png;base64,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)

shot.usda

JSON

```

#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    timeCodesPerSecond = 24
    upAxis = "Y"
)

def "set" (
    prepend references = @./set.usda@</set>
)
{
}

def Xform "camera"
{
    def "shotcam" (
        prepend references = @./shotcam.usda@</cameras>
    )
    {
    }
}

def Xform "anim"
{
    def "dave" (
        prepend references = @./dave.usd@
    )
    {
    }
}
```

```

#usda 1.0
(
    endTimeCode = 1
    framesPerSecond = 24
    metersPerUnit = 1
    startTimeCode = 1
    timeCodesPerSecond = 24
    upAxis = "Y"
)

def "set" (
    prepend references = @./set.usda@</set>
)
{
}

def Xform "camera"
{
    def "shotcam" (
        prepend references = @./shotcam.usda@</cameras>
    )
    {
    }
}

def Xform "anim"
{
    def "dave" (
        prepend references = @./dave.usd@
    )
    {
    }
}
```

*References vs sublayers?*

### Multi shot workflow [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#multi-shot-workflow)

Sequence as master file, then shot overrides?

Idea of grouping similar facing shots into 'scenes', scenes can refer to their own set.

### Shot overrides [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#shot-overrides)

Stuff about shot overrides here, specific for departments, eg charfx on top of anim caches, fx replacing elements in a set.

'I want to move the chair in these 30 shots, but move the table in these 8 shots. Do I move it for the majority, then um-move it for the rest of them, or split the set to have this in these shots, and that in those shots' etc.

### Lighting [​](https://www.tokeru.com/cgwiki/UsdAssetGuide.html#lighting)

How does this dovetail in with the rest of it all? Are we replacing or overriding?

