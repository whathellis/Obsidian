---
URL: https://discover.therookies.co/2024/08/02/realistic-character-design-techniques-you-need-to-know/
thumbnail: https://discover.therookies.co/content/images/size/w1000/2024/07/skin_01-1.jpg
site: "[[The Rookies]]"
date: 2024-09-15
duration: 
done: true
cover: ""
topics:
  - "[[Characters|Characters]]"
---
[[../../../01 Maps/Themes/Article|Article]]
!
# Realistic Character Design: Techniques You Need to Know
Vivienne Huo breaks down her workflow, techniques, and challenges, offering insights for fellow 3D artists and CG enthusiasts looking to create realistic 3D characters.

---

Vivienne Huo is a 3D Character Artist based in Montreal. Vivienne's 3D journey started with online tutorials and grew through formal training. During her time at [Think Tank Training Centre](https://www.therookies.co/schools/think-tank-training-centre?ref=discover-the-rookies), she created such pieces as my [Mia Goth portrait](https://www.therookies.co/entries/33722?ref=discover-the-rookies) and [Valerie](https://www.therookies.co/entries/33722?ref=discover-the-rookies).

In this article, Vivienne details her process for creating her 3D character ‘Valerie’ based on the concept by [Rui Guo](https://www.artstation.com/artwork/kDb9nn?ref=discover-the-rookies). She'll be breaking down her workflow, detailing important techniques she used, and dissecting the challenges she faced along the way. Whether you're a fellow 3D artist or simply curious about the CG creation process, Vivienne hopes you'll find this breakdown helpful - let's dive in!

## References

When embarking on a CG project it’s always essential to gather a bounty of reference at the outset. High resolution images, with informative light information, from as many angles as possible is my MO for this step. It’s not possible to get all the reference needed in one session prior to diving into a project. Thus, reference gathering is both a preliminary step and an iterative step throughout the project. I revisit reference gathering at different points throughout the project as new problems and perspectives present themselves. Like most CG artists, I rely on Pureref as my reference board software.

There were four main camps of focus for reference gathering throughout my Valerie project:  
1. Model/Form References (eg. Anatomy, Garments, Props)  
2. Texturing & Lookdev References (eg. Textiles, Makeup, Irises)  
3. Groom References (eg. Hair, Lashes, Brows)  
4. Lighting References

A lot of key references ended up informing more than one of these camps, but the intent when starting a reference gathering session was always centered around just one of these focuses.



## Modeling

### Anatomy

Modeling Valerie’s anatomy was a very time consuming and iterative process with most of my efforts concentrated on creating and refining the portrait. My approach to character modeling is the same as my approach to modeling anything - work big to small. Start with defining silhouettes and large volumes, then work my way through the hierarchy of forms. Define primary forms first and tertiary forms last. I limit my ability to work on high frequency tertiary forms early on in the modeling process by not subdividing until I am satisfied with the foundation I have set at the current highest subdivision level. This approach also helps prevent lumpy models caused by harsh brushwork while working with too much polygon resolution.



In [ZBrush](https://www.maxon.net/en/zbrush?ref=discover-the-rookies), there is a handy feature called Dynamic subdivision that allows you to preview your subdivided mesh without actually applying the smoothing algorithm - much like Smooth Mesh Preview in [Maya](https://www.autodesk.com.au/products/maya/overview?ref=discover-the-rookies). There’s even the ability to sculpt with Dynamic subdivision enabled. I don’t use this often for faces, but it’s a very useful feature for many types of models.



### Clothing & Fabric Props

All Valerie’s garments and fabric props were constructed using [Marvelous Designer](https://www.marvelousdesigner.com/?ref=discover-the-rookies). In Marvelous, I created 2D patterns, defined simulation properties, and manually nudged the simulation along to get the desired garment shapes and fold structures.



Once I was happy with the results, I used Marvelous Designer’s native retopology tools to create clean quaded topology. Next, I transferred the simulation meshes’ shape to my retopologized meshes by subdividing and transferring attributes (vertex position based on UV space) in Maya. Then, I reconstructed subdivisions in ZBrush on my retopologized mesh to get my original unsubdivided topology back.



### Character Pose & Clothing Pose

I used Accurig and Advanced Skeleton to create an automatically generated biped rig in Maya. Posing with a rig as opposed to baking transforms into the character model allowed me to pose non-destructively. I could parent assets such as the boots or pistol to joints and update the posed meshes at any point.

Since the automatically generated rig was far from perfect I did a manual sculpt pass on the posed anatomy and integrated it as a blendshape.

One thing that was very helpful for posing was having a friend take reference photos of myself in this pose from multiple angles.



I created an animation from A-pose to the rigged pose to the sculpted corrective blendshape in Maya and used this animation to simulate Valerie’s outfit to pose in Marvelous Designer. I made an additional ‘pressing down’ animation for any hard surface prop that was interacting with her outfit.



Once I was satisfied with the outfit simulation, I transferred the simulation shape over to my retopologised cloth meshes. Finally, in ZBrush I fixed any simulation artifacts on my garment and did a cloth sculpting pass.



### Clothing Detailing

To create stitches and zipper meshes, I used ZBrush IMM brushes. There’s many of these brushes available online or you can create your own. I used ZBrush’s handy frame mesh function to create the curve path for the IMM brush to follow. This is a quick way to intuitively deploy small and numerous meshes along organic surfaces.



### Hard Surface Props

I modeled all the props primarily using standard box modeling techniques. I aimed to create meshes completely in line with VFX production subdivision topology standards. This meant creating meshes that:  
 1) Are fully quaded  
 2) Have support edges for correct smoothing  
 3) Have appropriate polygon density  
 4) Have sufficient edges to minimise texture stretching



## UV Mapping

I unwrapped and packed the UVs in Maya. One tool I love to use when creating my UV seams is the 3D Cut & Sew UV Tool in Maya. I organized my UDIMs based on shaders to minimize the number of texture inputs per shader. Apart from the face skin textures which are 4k, I packed my tiles for mostly 2k and some 1k texture maps, since that was all the resolution that I needed for my shots.



## Groom

### XGen

Valerie’s hairstyle was my first attempt at a VFX groom and my first time using any grooming software. I decided to create a solid starting blueprint for myself by creating a hair sketch in ZBrush. The purpose of sculpting a hair sketch was to define the silhouette/volume, flow, and big clumping groups within the hairstyle. Getting a first pass at solving these artistic elements before diving into XGen helped me immensely.



Then, once in XGen, I could focus on learning how to use the tools and solving the layering within the hairstyle. It was a challenge to solve the layering in a long hairstyle where the hair is swept forwards - making sure where a guide starts from and where it ends up makes sense and does not conflict with neighboring guides. [[../../YouTube/Creating Realistic Hair with Maya XGen|Hadi Karimi's XGen tutorial]] was incredibly insightful for me. He takes you though the entire process of creating all descriptions for a 3D female portrait.

For Valerie I created seven XGen descriptions for the hair: main hair, flyaways, baby hairs, upper lashes, lower lashes, eyebrows, and peach fuzz.



I chose to create my groom using XGen Core since it already comes with Maya. With Core you sacrifice a bit of artistic controllability compared to XGen Interactive, but the advantage is that you have the ability to work procedurally. The groom was done by placing and shaping hair guides and using expressions to drive different attributes. About 80% of my time spent on the groom was spent sculpting the guides and the remaining 20% was spent painting maps and tweaking modifiers.

Through this project, I learned how to identify hair clumping and sub-clumping in my hair references and began to translate those forms into my CG groom. The largest clumps were defined per guide, while the sub-clumps were defined by clumping modifiers with procedurally generated clumping points.

### Hair Shading in Arnold

It’s easy to overlook shading the groom and simply stick with the basic settings in AiStandardHair. However, I believe it was worth the extra effort to set up variables in the XGen groom so I could reference them in my hair shader. I set up IDs for the different clumping modifiers as well as individual hair strands so I could get color and roughness variation that was specific to the clumps in my groom. This helped the different clumps read clearly. It also added an extra sense of dimensionality to the groom. For help with setting up these variables, check out [Jesus Fernadez’s Arnold Hair Shading Tutorial Series](https://jesusfc.net/tutorials/ai-standard-hair?ref=discover-the-rookies).

Lastly, with AiStandardHair it’s very hard to get ginger coloured hair by just tweaking the basic settings, even with the melanin redness set to 1. My workaround for this was to color the 2nd specular tint and transmission tint.

### Setting up XGen

XGen is notriously fickle and there are lot of 'gotchas' when setting up a Maya project to work with XGen. I recommend [[../3D/Beginners guide to XGen pipeline|Micheal Cauchi's blog article]] for help getting set up with the plugin for the first time. Lots of experienced XGen users still have tales of broken or disappearing grooms. It's important to take lots of care to set up the project correctly from the start.

## Texturing & Lookdev

In my workflow for personal projects, texturing and lookdev are extremely intertwined and iterative processes. I often set up my shaders in Arnold before authoring textures. I treat textures simply as inputs/data to be further manipulated in shader. I opt to create shaders first with simple inputs and fill in the missing detail and variation with texture inputs as I go along. This allows me to see the shading holistically and iterate quickly with the relationships between material properties. I prefer this as a first step instead of baking data early on into texture maps and having to make software round trips to iterate on the shading. [Adam O'Donnell's tutorials](https://www.patreon.com/Adamocg/posts?ref=discover-the-rookies) are great resource on texturing/lookdev for realistic CG portraits. Consulting his tutorials was invaluable for me on this project.

### Skin

### Texturing in [Mari](https://www.foundry.com/products/mari?ref=discover-the-rookies)

I used Texturing XYZ’s Vface texture maps as a base for the face skin textures and 3D Scan Store’s female base mesh textures as a base for the body skin. I used [R3DS Wrap](https://www.russian3dscanner.com/?ref=discover-the-rookies) followed by a texture transfer in XNormal to transfer the textures from the Vface and ScanStore base models onto my model. I graded the 3D Scan Store texture until the seam where the face texture transitions into the body texture was not visible anymore.

With the base correctly applied, I painted masks isolating areas of the anatomy so I could target them later across texture channels.



For the Albedo channel, I introduced layers of color variation observed from photographs of the model the texture came from, as well as supplemental references of skin. I also cleaned up data in the Vface skin texture I didn’t want, such as reducing the amount of freckles on the lower cheeks.

For the Specular channel, I created a cavity map from my displacement map data in [Nuke](https://www.foundry.com/products/nuke-family/nukex?ref=discover-the-rookies). The blue channel of the utility map in the Vface pack works well as a starting point for this also. However, for this project I altered my tertiary details significantly in ZBrush and wanted a cavity map that was faithful to the final sculpt. The goal for the specular channel was to have a sharp high contrast map that masks out cavities on the face. Since displacement alone often isn’t enough to completely kill the specular reflection in cavities, the spec map is an essential map to support the tertiary details in the render.



For the Roughness channel, I approached this map as a zoning map with some organic breakup layered in. I used my anatomy isolating masks I created earlier to tell the shader through the roughness map which areas I want to have more or less rough. It’s not necessary to have high frequency detail in the roughness map and high contrast detail here is not advisable for realistic skin.

For the Coat channel, which is optional, I created a T-zone mask multiplied by my cavity map to mimic the distribution of oil/sebum present on skin

### Shading in Arnold

I used the AiStandardSurface to create the skin. Skin is the most well known SSS material so the SSS Weight should be set to 1. I played around with my skin shader quite a bit and here are some of the values I found that worked well for my renders:

SSS Color: Use albedo map  
SSS type: randomwalk_v2  
Scale: 0.1 - 0.13  
SSS Radius: Pick a fleshy color that matches the average color of the albedo. Make sure the color is not too saturated as this can cause weird results in the SSS and introduce lots of SSS noise

### Makeup

I painted masks for the makeup in Mari. I found multiplying the makeup masks by my cavity map gave a result that was more naturalistic. I exported the masks as RGB packed maps to save on texture memory in Arnold. All the makeup such as eyeliner and lip tint is layered in shader using AiLayerShader. None of the makeup data was baked into my channel exports from Mari, which allowed me complete control of the look of the makeup in shader. For the shiny eyeshadow shader, I used the AiFlakes node to create a fine milled glitter effect.

### Eyes

My CG eye setup is pretty standard and consists of 3 main geometries: sclera, iris, and caruncle. There is also a mesh for the tear line. It’s important that the sclera is, in principle, a sphere with a round protrusion at the cornea, but the geometry should also have organic lumps and bump mapping. It’s important that these imperfect lumps and bumps do not affect the lens area, as this surface should be smooth for the refracted iris to look nice.

For the eye textures I used TexturingXYZ’s legacy iris textures and EvilTriangle’s sclera photograph textures as bases. For the caruncles I used the edges of the sclera texture where it’s more pink/red.

I controlled the blending between the sclera and the iris behind it using ramps. Additionally, in the sclera shader, I used an aiAmbientOcclusion node to multiply in some redness. This helped create some extra sense of contact with the eyelids and gave Valerie a slightly teary red eyed look.



### Textiles

All my cloth shaders consist of 2 main inputs - UV based texture detail and a tileable fabric weave. In Substance painter, I manipulated data from Painter’s bake maps to lay down asset specific variation such as edge wear, color variation, and staining. Then, in shader, I layered a tileable fabric weave on top of these base textures, affecting data in the displacement and albedo channels. For this project I sourced my fabric tileables from Texturing XYZ’s microfabrics.

Cloth shaders have unique fresnel effects due to the way light interacts with cloth fibers, especially at grazing angles. AiStandardSurface has a sheen channel that facilitates this effect. Lastly, cloth is an SSS material, so for this project I mixed in about 0.25 SSS weight on most of my textile shaders.



### Tattoo

I created the image for the tattoo in [Photoshop](https://www.adobe.com/au/products/photoshop.html?ref=discover-the-rookies) using masking to define color zones so I could keep procedural control. The illustrations I used as the linework were found online. I used the handy 3D wrap project feature in [Substance 3D Painter](https://www.adobe.com/creativecloud/3d-ar.html?ref=discover-the-rookies) to project the tattoo. Then, in Mari, I multiplied the tattoo with my base color and added additional blurring to mimic the scatter and edge bleeding typical of tattoos. Finally, I created an extremely blurred version of my tattoo image for the SSS radius shader input.



### Guns

I created textures for the hard surface assets using Substance 3D Painter. Painter’s smart masking tools, high quality grunges, and 3D painting feature make it quick to detail hardsurface assets. Painter’s layer based workflow has more limitations than Mari’s nodes. I try to work around this by employing a pseudo node-like workflow where I create lots of anchor point masks at the base of the texture stack, which can then be referenced at any point higher up in the stack. This is somewhat like creating masks and making them available to reference using a Teleport node in Mari.




## Lighting

Form and light shape each other and the shader facilitates their interaction. It can't be overstated how impactful lighting is on the quality of the final render. It’s a skill every 3D asset artist needs to harness to be able to properly showcase their asset, regardless of their specific specialisation. For me, as lighting is not my specialty, my main goal was to create a simple 3-point lighting rig that was inoffensive and did not create a bottleneck in the presentation of the asset.

## Compositing

Using Nuke I graded the final renders and added some subtle lens effects such as diffusion, hallation, and chromatic aberration. Having rendered out AOVs from Arnold, I used the different passes to further tune the render. Here I made changes mostly with the specular passes. Technically, most of the changes I made in post could be reverse engineered and implemented at the lookdev stage, but that would have added lots of additional re-render time for this project.

## Conclusion

Creating Valerie has been a labor of love. This project allowed me to delve deep into various aspects of 3D character creation - from anatomy and cloth simulation to CG grooming and shader development.

A special thanks to my mentor [Alex Huguet](https://www.artstation.com/metamesh?ref=discover-the-rookies) who was as generous with his knowledge as he was skilled at everything 3D.



What I've come to appreciate most throughout this process is the interplay between technical knowledge and artistic vision. While knowledge of tools and techniques is crucial, I continually find that it's the application of artistic principles that dictates the success of the final image.

Thank you so much for checking out my article! If you have any further questions about my process creating 3D art, feel free to reach out on [The Rookies](https://www.therookies.co/u/viviennehuo?ref=discover-the-rookies) where all my accounts are listed. Check out the complete reel of my CG work [here](https://vimeo.com/925733003?ref=discover-the-rookies).