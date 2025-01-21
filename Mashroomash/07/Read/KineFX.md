---
URL: https://www.sidefx.com/docs/houdini/character/kinefx/index.html
thumbnail: 
site: "[[]]"
date: 2024-10-02T12:49:11
duration: 2
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[../../01 Maps/Themes/Article|Article]] 
# KineFX

Description:: #### What is KineFX?

KineFX is a rigging and animation framework and toolset that allows you to create and edit characters all at the *geometry level*. You can create your own KineFX characters from scratch, or use special KineFX SOPs and regular Houdini SOPs to edit imported characters and animation.

-   For definitions of KineFX terminology, see the [Glossary](https://www.sidefx.com/docs/houdini/character/kinefx/glossary.html).
    

#### Procedural rigging

The KineFX framework is built on the principles of *procedural rigging*. Procedural rigging allows you to iterate on your rigs quickly, experiment non-destructively, and explore set-ups without fear of breaking anything like you would a static graph system. With KineFX, you can reconfigure a rig while animating, delete entire parts of an animated hierarchy and not lose its skin or animation, or unparent all your points and retain their positions (world space transforms).

APEX (All-Purpose EXecution) is the graph evaluation framework that is used for building and evaluating character rigs. APEX graphs are geometry that are used to represent a character’s rig logic. Users can procedurally build and assemble rig logic pieces, and choose to evaluate the rig logic at a later point in the network. This idea of delayed evaluation allows the rig logic and rig evaluation to be decoupled, resulting in significant performance improvements.

KineFX is the SOP-level rigging and animation framework, and APEX is the graph evaluation engine that runs underneath it. KineFX makes use of APEX, with some of the KineFX infrastructure now using APEX graph evaluation.

![](https://www.sidefx.com/docs/houdini/images/char/kinefx_apex.jpg)

#### Animation and the packed character format

![](https://www.sidefx.com/docs/houdini/images/char/kinefx_packedcharformat_levels.png)

Packed character format hierarchy in the rig tree view

To support the APEX animation and rigging workflows, the *packed character format* is a way to define, bundle, and organize the data that is needed to create and animate one or more characters in the viewport. The packed character format consists of geometry data that is organized in a folder structure similar to a directory structure on disk, with the data added as nested [packed primitives](https://www.sidefx.com/docs/houdini/model/packed.html).

In the packed character format, the elements of a character (skeleton, shape, rig) are added to a character container to build up a character, and characters are added to a scene container to assemble an animation scene. This animation scene is then passed to an [![](https://www.sidefx.com/docs/houdini/icons/SOP/apex-sceneanimate.svg)APEX Scene Animate SOP](https://www.sidefx.com/docs/houdini/nodes/sop/apex--sceneanimate.html "Edits the animation on an APEX scene."), where animation can be performed in the node’s *animate state*.

