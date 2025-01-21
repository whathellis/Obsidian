---
URL: https://discover.therookies.co/2024/07/16/call-of-duty-inspired-garrison-ue5-interior-breakdown/
thumbnail: 
site: "[[The Rookies]]"
date: 
duration: 
done: false
cover: "[[]]"
topics: 
---
[[Read it Later|Read it Later]] [[../../01 Maps/Themes/Article|Article]]
[Projects](https://www.therookies.co/projects)[Contests](https://www.therookies.co/contests)[Schools](https://www.therookies.co/schools)[Find Talent](https://www.therookies.co/members)[Discover](https://discover.therookies.co/)

More

[](https://www.therookies.co/about)[](https://discord.gg/Wt95sGn)[](https://shop.therookies.co/)

- [All Posts](https://discover.therookies.co/)
- [News](https://discover.therookies.co/tag/news/)
- [Resources](https://discover.therookies.co/resources/)
- [Weekly Drills](https://discover.therookies.co/weekly-drills/)
- [Studios](https://discover.therookies.co/studios/)

Search

![Call of Duty Inspired Garrison: UE5 Interior Breakdown](https://discover.therookies.co/content/images/size/w1000/2024/06/rookies_article2.jpg)

[Inspiration](https://discover.therookies.co/tag/inspiration/)

# Call of Duty Inspired Garrison: UE5 Interior Breakdown

Hayden Harding McManus, a Champlain College student delves into an Unreal Engine creation inspired by Call of Duty's interior environment.

- [](https://discover.therookies.co/author/hayden/)

#### [hayden](https://discover.therookies.co/author/hayden/)

Jul 16, 2024 • 10 min read

 Round of applause for our sponsors

Hayden Harding McManus is a student at [Champlain College](https://www.therookies.co/schools/champlain-college?ref=discover-the-rookies) whose dream is to work as a level artist on a Halo or Fallout game, hoping to make the same impact on others as those games did on them. In this article, he explores the interior of a Call of Duty-inspired environment created in [Unreal Engine](https://dev.epicgames.com/community/unreal-engine/learning?ref=discover-the-rookies).

---

## Finding Concept Art and Searching for References

The first thing I did was hunt for a concept that fit my ideal theme and level of detail. I decided to go with a concept piece from Call of Duty Black Ops: Cold War by Kevin Jick on ArtStation. I wanted to tackle this piece with a good mix of realism and military grit. To avoid recreating the original concept art one-for-one, I opted to move the theme to the other side of the Iron Curtain during the Cold War. After making this decision, I gathered references and put them into PureRef, focusing on the objects in the scene that needed to be switched around with their Western counterparts.

![](https://discover.therookies.co/content/images/2024/06/rookies_article-image_1.jpeg)

PureRef Example

After gathering and organizing all the references for the objects and tank for the scene, I reviewed my backlog of previously made objects and props to improve my past modeling skills. I had to make early cuts to keep the project manageable, as I was also balancing four other classes that required much of my focus during the semester. Most of the early pre-production work was allocated to exploring references from my backlogs and past projects.

## The Tank Model

My mentor had advised me to reuse a tank from a previous project and improve it to the quality planned for this project. The tank in question was a failed summer project from 2021 when I had only a semester of 3D modeling experience with basic skills in Maya. The original idea was to make a game-ready tank with animated tracks and a turret, but it fell through due to my lack of time and skill. Initially, I wanted to create an all-new tank and push it to the desired quality, but my mentor suggested working on the old model for a week to see what I could learn. After that week, I managed to remake and remodel around 80% of the tank, significantly reducing the project's scope.

![](https://discover.therookies.co/content/images/2024/06/rookies_article-image_3.jpeg)

Summer 2021 tank (left) Spring 2024 revision tank (right

Revisiting the older tank model and correcting the mistakes I made two years ago was invigorating. Although fixing and UV mapping the model took a lot of effort, the results were well worth it.

## Unreal Engine Block Out

The next major part of this project was to get into Unreal and block out a scene that matched the scale and depth shown in the concepts. This began with Unreal’s modeling tool, using basic primitives and the old tank model to lay out the scene accurately. It took many iterations to get the size close enough to the concept art. The biggest struggle was achieving the general scale of the tank and reconciling the different sizes from reference images, which made the initial days challenging. Once the scale was settled, the scene required a basic lighting pass to illuminate it effectively. At this early stage, I worked without ray tracing, relying only on Lumen to determine the ideal lighting scheme.

![](https://discover.therookies.co/content/images/2024/06/rookies_article-image_4.jpeg)

Block out in Unreal over 2 weeks 

The end result of this blocking out allowed me to know what scale I was working at and how large certain objects had to be once I started modeling. This early stage of the block out and pre-production were the most important parts of the project.

## Working in Maya

Jumping right into Maya was a pleasant return after a semester of learning [3ds Max](https://www.autodesk.com.au/products/3ds-max/overview?term=1-YEAR&%3Btab=subscription&ref=discover-the-rookies) abroad in Montreal. Modeling began with the basic blockout of most of the objects in the scene from the Unreal blockout. The first model wasn't significant but served as a quality test: a Soviet ammo box. This helped establish the desired quality early on. The primary focus afterward was the walls and floors for the environment. Getting them modeled quickly and into the engine was paramount to ensure that walls, floors, and windows aligned nicely. These walls were made with basic shapes and no backsides to save on poly count and textures, with almost all the windows and walls requiring booleans to create the desired shapes.

![](https://discover.therookies.co/content/images/2024/06/rookies_article-image_5.jpeg)

Large props (top left) prop (top right) modules (bottom left) walls ( bottom right) 

After the walls were modeled, the tank was next, with the barrel adjusted to look more stationary. Once the essential models were complete, I moved on to smaller props for set dressing, such as barrels, crates, and wood pallets. These props had a lower polygon count than the larger models and were made using more primary forms. They featured minimal secondary modeling and almost no tertiary modeling, relying on texture work for specific details.

## Texturing and UVs

UV mapping was straightforward, as many objects had simple shapes and could be placed on a single texture sheet, often sharing the same UVs at different scales. Combining multiple objects into single texture sets helped save memory and ensured a smoother workflow. I maintained consistent texel density across all props to ensure a cohesive look in the scene, including walls and floors.

![](https://discover.therookies.co/content/images/2024/06/rookies_article_image_6.jpeg)

Crate UVs 

After completing the UV mapping, the props were brought into a texturing program like [Substance 3D Painter or Substance 3D Designer](https://www.adobe.com/creativecloud/3d-ar.html?ref=discover-the-rookies). In Substance 3D Designer, the workflow began by generating the base shape using a tile or brick generator for the brick material. This initial generator was modified with a slope blur grayscale node and noise to adjust the shape of the bricks, ensuring they weren't perfectly straight. Subsequent nodes were used to add detailed textures to the bricks until achieving the desired quality in roughness, normals, and height maps.

Once satisfied with the texture details, gradient maps, and blend nodes were applied based on the original base to achieve the desired brick colouration. For colour variation, a black-and-white gradient map node was blended with a normal gradient map containing the desired brick colours. After completing the texturing process, the textures were exported into Unreal Engine for testing on objects. Any necessary adjustments were made and re-exported to ensure optimal appearance in the final scene.

![](https://discover.therookies.co/content/images/2024/06/all_mats-2.jpeg)

substance designer examples

The next round of texturing involved most major props in the scene using texture sheets created in Substance Painter and Photoshop. These props generally utilized 2K texture resolutions, while larger and more prominent props like the Tank required a 4K resolution.

Starting with a base colour for each prop, Hayden then adjusted roughness and metalness to match real-world counterparts. After establishing the base colour, he introduced colour variations or secondary colours where needed. Following this, Hayden added scratch details using black masks and fill layers, aiming to enhance curves and crevices for better visibility.

Further layers of colour-fill were applied to emphasize colour variation and dust details, adjusting roughness accordingly to simulate dust amounts. Depending on the prop, a tertiary pass included additional textures for details like writing, rust, surface layers of paint, or accumulated dust.

![](https://discover.therookies.co/content/images/2024/06/rookies_article-image_2.jpeg)

Substance Painter Texture Example

Once I've completed the textures for the props in Substance, I export them to Unreal using a packed texture set. This method combines RGBA colour channels for roughness, ambient occlusion, and metalness into a single texture, which makes it straightforward to apply in Unreal Engine. Depending on the specific prop in my scene, I sometimes interchange the A channel in RGBA for height maps or emissive textures to achieve the desired visual effects.

![](https://discover.therookies.co/content/images/2024/06/master_material_walls-6_6_2024-4_15_33-PM.jpeg)

master material in unreal

Finally, in Unreal Engine, I create a master material that governs all other materials instantiated from it. This master material aims for versatility by incorporating variables with open parameters multiplied by roughness, normals, height, emissive, and color values for better control. Additionally, I develop a separate master material specifically for vertex painting within Unreal Engine. I utilize the UV material tiling node from the Substance Painter plugin for Unreal to manage texture tiling, available for free on the marketplace. All primary textures connected to the material nodes are converted into parameters and renamed, simplifying the creation and experimentation of instance materials.

![](https://discover.therookies.co/content/images/2024/06/m_vertex_color-6_6_2024-4_14_34-PM.jpeg)

Master material vertex painting

## Working in Unreal Engine

Once a prop or wall was completed in Maya, it was imported into Unreal Engine, and once textured and UV-mapped, it replaced the placeholder model/texture. Time spent in Unreal Engine, apart from lighting and set dressing, focused on adjusting the camera, Niagara system, and post-processing effects.

Initially, I settled on a camera angle and kept it consistent to build around, but adjusting the focal distance and aperture required significant effort due to my limited experience with Unreal's camera system. I primarily adjusted values such as manual exposure in the volume and reflections for both Lumen and ray tracing until achieving the desired look.

Niagara proved essential yet challenging in Unreal Engine. Similar to the material editor, understanding Niagara without prior experience was daunting. I mainly used Niagara to add dust particles to enhance the ambiance of the scene. I developed a custom material node for the dust within the particle generator using Unreal's material editor. I adjusted the opacity and slowed down the particle movement to simulate dust particles in a sunbeam, aiming to capture a frozen moment in time.

![](https://discover.therookies.co/content/images/2024/06/ScreenShot00006.jpeg)

Niagara Particles

### Set Dressing in Unreal Engine

The scene's set dressing aimed for a worn, cluttered appearance, with trash and debris strewn across the floor and overflowing from trashcans. It needed to resemble a workshop with chaotic disorganization, following references closely for accuracy. Active disorder, with tank parts and equipment scattered and stacked haphazardly, was crucial for conveying the desired atmosphere—not abandoned, but actively used and organized to the mechanics' liking.

Once objects were positioned and textures tested in the scene, attention turned to balancing areas of rest. Each section needed to avoid feeling overly cluttered or empty, except for designated player pathways highlighted by large red-painted floor areas created with decals. Most of the grungy details inside were achieved using performance-friendly methods, and decals sourced from Unreal's Quixel Bridge played a significant role in enhancing the scene's realism.

![](https://discover.therookies.co/content/images/2024/06/rookies_article4.jpeg)

Floor Decal

The final aspect of set dressing involved creating wires using a blueprint I developed. This blueprint utilizes a simple cylinder mesh and spline component. The construction script connects these components to obtain positions at the spline points node. Additionally, the spline component is aligned using a set forward axis node set to the z-axis, allowing control over the spline's direction. The blueprint is completed with a set start and end node where all components are connected to finalize its setup. This blueprint offers versatility akin to using extrusions in Maya or other 3D software, enabling placement, shape, and orientation adjustments within the scene.

![](https://discover.therookies.co/content/images/2024/06/rookies_article5-1.jpeg)

blueprint script

Once the objects and decals were in place, I focused on adding more variation to the scene to achieve a realistic feel. Using Unreal's paint mode, I meticulously aligned it with the vertices, which was crucial for maintaining the room's vibe and atmosphere alongside the textures. I strategically utilized vertices placed in Maya to enhance the realism of the bricks, creating unique variations. Similarly, I applied this technique to the concrete floor, ensuring some areas appeared properly poured with smooth surfaces, while others showed rougher pours with visible air holes and discolouration.

![](https://discover.therookies.co/content/images/2024/06/rookies_article3.jpeg)

vertex paint mode

### Lighting in Unreal

The lighting of the scene underwent multiple iterations and utilized various engine features. I experimented with Lumen several times and aimed to incorporate it because of its ability to create beautiful sunbeams through the windows. However, due to the scene's extensive use of metal and the need for bounce light, Lumen didn't provide sufficient bounce. Therefore, I switched on ray tracing, which affected my ability to create sunbeams easily but still allowed for excellent overall lighting effects.

![](https://discover.therookies.co/content/images/2024/06/rookies_article.jpeg)

Lumen on no raytracing

To achieve raytraced shadows and sunbeams, I experimented with various techniques, some yielding impressive results while others were less favorable. One approach involved using planes with a texture resembling fog and dust, but this effect didn't meet my expectations after experiencing the quality of Lumen's sunbeams. Thus, I continued searching for an alternative method to achieve the desired effect.

![](https://discover.therookies.co/content/images/2024/06/textureplanetest.jpeg)

Raytraced shadows with fog texture planes 

The sunbeams were eventually achieved after extensive testing and adjusting the load order of lights. The effect was created using two directional lights initially impacting performance, which was resolved by designating one as the primary scene light with raytracing enabled and no scattering to avoid fog or dust effects. The second light utilized Lumen, positioned closely above the primary light with high scatter intensity, low light intensity, and no shadows.

![](https://discover.therookies.co/content/images/2024/06/raytracing-on-and-sunbeams_v1-1.jpeg)

Raytracing and lumen working simultaneously

Besides the major exterior light, I needed to use interior lighting skills ensuring they complemented the main light without overshadowing it. I used rect lights overhead to illuminate the main garrison workshop, with smaller ones serving as wall lights. Spotlights were strategically placed alongside the rect lights on the walls to cast visible light traces on the walls and objects below.

![](https://discover.therookies.co/content/images/2024/06/ScreenShot00001-2.jpeg)

light stacking example

The final pass of lights involved adding rim lighting to enhance objects and other components in the scene, using rect lights and spotlights with low intensity and a short attenuation radius to avoid spillover.

Each decision had it's pros and cons, with some impacting performance while achieving appealing effects, like the stacked lights that contributed to the scene's liveliness without causing significant issues.

## Project Roundup

This project was a rewarding test of my artistic skills, leveraging Unreal Engine and Substance 3D Designer to explore new workflows and experiment with raytracing. Revisiting and revitalizing an old project like the tank taught me the joy of progress and self-improvement. If you have unfinished projects, don't hesitate to revisit them—it can change your perspective on your skills and work.

I hope you enjoyed reading about my Call of Duty-inspired garrison environment breakdown. This project was a learning experience I deeply appreciated. Lastly, I want to thank my mentor, Jennifer Carlin, for her invaluable critiques, and The Rookie for the opportunity to share this breakdown with you all.

---

Check out more of Hayden's work via his Rookies profile [here](https://www.therookies.co/u/HaydenMcManus?ref=discover-the-rookies).

## Sign up for more like this.

[

Enter your email

Subscribe](https://discover.therookies.co/2024/07/16/call-of-duty-inspired-garrison-ue5-interior-breakdown/#/portal)

[![Creating a Complete Animated Scene For Your Demo Reel](https://discover.therookies.co/content/images/size/w600/2024/07/scene00-1.jpg)](https://discover.therookies.co/2024/08/12/creating-animated-scene-demo-reel/)

[

## Creating a Complete Animated Scene For Your Demo Reel

In this article, SF Film School student Nayon Park presents "Pinocchio," a demo reel inspired by the 2022 film.

](https://discover.therookies.co/2024/08/12/creating-animated-scene-demo-reel/)

Aug 12, 20249 min read

[![Immersive Virtual Worlds Through 3D Environment Re-creation](https://discover.therookies.co/content/images/size/w600/2024/07/PROJET_KENOPSIA.jpg)](https://discover.therookies.co/2024/08/11/immersive-virtual-worlds-3d-environment-re-creation/)

[

## Immersive Virtual Worlds Through 3D Environment Re-creation

Passionate about visual effects and photography, VFX-Workshop graduate, Matthieu Mangez, dedicated nearly eight months to this large-scale environment project.

](https://discover.therookies.co/2024/08/11/immersive-virtual-worlds-3d-environment-re-creation/)

Aug 11, 20248 min read

[![Designing a Conceptual Brand For Your Graphic Design Portfolio](https://discover.therookies.co/content/images/size/w600/2024/08/habillage-exterieur.jpg)](https://discover.therookies.co/2024/08/10/designing-brand-for-your-graphic-design-portfolio/)

[

## Designing a Conceptual Brand For Your Graphic Design Portfolio

Bérangère Magalhaes, a student at e-artsup, presents "Tea Time Club," a branding exercise which involved independent work on all aspects of brand design, from the logo to the storefront display.

](https://discover.therookies.co/2024/08/10/designing-brand-for-your-graphic-design-portfolio/)

Aug 10, 20245 min read

[](https://discover.therookies.co/)

[](https://www.facebook.com/TheRookiesCO)[](https://www.instagram.com/therookiesco/)[](https://twitter.com/TheRookiesCO)[](https://www.youtube.com/therookiesco)

#### About Us

- [About](https://www.therookies.co/about)
- [Team](https://www.therookies.co/about/team)
- [Advertise](https://www.therookies.co/about/advertise)
- [Media Kit](https://www.dropbox.com/sh/84j5l2fmprak4iq/AACW0Dw0pRiTiOoxXEMWbOqDa?dl=0)
- [Helpdesk](https://help.therookies.co/)

#### The Rookies

- [Projects](https://www.therookies.co/projects)
- [Contests](https://www.therookies.co/contests)
- [Find Talent](https://www.therookies.co/members)
- [Rookie Awards](https://www.therookies.co/rookieawards)
- [Discord](https://discord.gg/Wt95sGn)
- [Shop](https://shop.therookies.co/)

#### Discover

- [All Posts](https://discover.therookies.co/)
- [Find a School](https://www.therookies.co/schools)
- [School Rankings](https://www.therookies.co/schools/rankings/)
- [Resources](https://discover.therookies.co/resources)
- [Weekly Drills](https://discover.therookies.co/weekly-drills)

[Privacy Policy](https://www.therookies.co/privacy_policy) • [Terms & Conditions](https://www.therookies.co/terms_and_conditions)