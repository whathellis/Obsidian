---
URL: https://www.youtube.com/watch?v=ede4ouNOXyQ
thumbnail: https://i.ytimg.com/vi/ede4ouNOXyQ/default.jpg
channel: "[[Motion Design School]]"
published: 2023-06-22T04:17:30
duration: 1386
tags:
  - video/3D/4D
done: false
cover: "[[Pasted image 20240711163650.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "23m 6s"]
[[./Cinema 4D Free Course – Part 1 Modeling and Rigging|Cinema 4D Free Course – Part 1 Modeling and Rigging]]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240711163650.jpg]]
````
````col-md
flexGrow=1
===
<iframe width="400" height="200" src="https://www.youtube-nocookie.com/embed/ede4ouNOXyQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Download project files and check the rest of the course here:
https://motiondesign.school/courses/3d-motion-beast/
(Description:: Discover a treasure trove of Cinema 4D art and animation as the complete production pipeline comes together in one exceptional course and software. Prepare to embark on a mind-blowing journey encompassing 3D production, animation, editing, compositing, and screenwriting.)

# Transcript
[00:00](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=0) before we start rendering we have to solve one more problem let's take a look at reference you can see that in the first frame the body has white material and when the bubble starts to appear 
[00:12](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=12) they have completely different material so we need to use different materials on the same mesh but the problem is we use volume Builder and volume measure and topology changes every frame that means 
[00:25](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=25) that we cannot use UVS to project textures so we have to find some way to create a mask which we will use to blend different materials let me show you what we're going to do 
[00:38](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=38) select volume measure and create vertex map tag vertex map stores additional points information and to control this information we're going to use fields for instance if I create a linear field 
[00:51](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=51) red areas will have value 0 and yellows will have one we can use this information to create a black and white mask which we will use to mix two different materials 
[01:05](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=65) the simplest thing we can do is just use linear field and paint it so that the top is black and the bottom is white I think it is too boring I want to emphasize the shape of the bubbles so 
[01:17](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=77) for now I'll remove linear field and you can use not only Fields but also geometry for instance we can use the bubbles themselves it doesn't work with nulls and to make it work we need to 
[01:28](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=88) convert it to Geometry but I also don't want to convert it inside volume Builder so we're going to use instance so at first let's create instance of Bubbles and to make it work with vertex 
[01:40](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=100) map tag we need to create connect object just select an instance hold down alt and create connect I'll rename it to Bubble mask let's keep it organized so create a null 
[01:56](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=116) and call it masks in this null I'm gonna store all fields and objects for vertex map tag then place it inside an ALT called body right next to original snots and now we can use it as a field just 
[02:11](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=131) select vertex map tag then drag and drop bubble mask into Fields list we can see spheres intersect the volume measure if I disable it for a moment 
[02:22](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=142) this is actually bubble mask so let's just make it invisible now if you select the vertex map tag you will see how the geometry of the Spheres masks the points that are next to it 
[02:37](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=157) you can adjust the radius try to experiment with different modes such as Point surface or volume I'll tweak it just a little bit it looks fine already 
[02:49](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=169) we have some mask on bubbles but we also need to mask snots and in this case it will be easier to use linear field let's just create it and place inside masks 
[03:01](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=181) and make sure it's in a list of vertex map tag let's adjust its orientation and position I'll just move it approximately in the 
[03:11](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=191) middle of the bubbles so that it masks everything below I got something like this and now we need to animate these masks so that they appear not in the first frame but when 
[03:24](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=204) the bubbles appear and the easiest way is to use already existing linear field the one we used for animation of appearance of the bubbles let's find it inside the bubbles 
[03:36](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=216) now we have activate bubbles and it has Shader and linear field as you remember the linear field is animated and moves from left to right so let's use it to select vertex map 
[03:50](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=230) deck then drop linear field inside switch blending mode to subtract looks nice and when the marshmallow starts to scream we can animate the first linear field I want to smooth the 
[04:09](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=249) transition between two materials to emphasize the mountain effect you can find it in mask nulls and in this Frame I'm going to move it up and expand a little 
[04:24](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=264) nothing complicated I'm just creating two keyframes and animating the Y position on the length of the field you probably noticed every time you hit 
[04:37](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=277) play the shape of this Notch looks a bit different this is because of some simulation we used in track modifier attacks so before we start rendering we need to 
[04:46](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=286) bake the entire animation on this stage you can check everything you made maybe fix something and when you're happy with everything save the project and we're going to bake the marshmallow to alambic 
[05:01](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=301) for that just select volume measure right click and select back as alembic it can take some time you should get the volume measure alembic object and you can delete 
[05:16](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=316) everything except this object inside the body now it is recorded into one file as a single mesh and it works very fast another Advantage is that it stores vertex map 
[05:28](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=328) tags from this moment we lost the ability to adjust the animation so please save it as a new project also you can find the alembic itself in this path 
[05:47](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=347) now we can start rendering go to redshift menu around redshift render View and hit start button now let's create the first slide I'm gonna use area light it works the same 
[06:04](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=364) as softbox in real photo studio I'll change its error shape to disk and then adjust its location it will represent some kind of moonlight sky in the dark wood 
[06:19](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=379) in attributes I'll drop down the intensity bit and then scale it up a little to make it softer next I'll duplicate it while holding 
[06:32](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=392) down Ctrl command on Mac then move it back and a bit left to make some backlight then bring back condensed a little it is not very obvious but you can see it 
[06:46](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=406) later reflecting of snots I also want to illuminate it from the right side so I'll duplicate it again then adjust the scale and intensity the idea was that the marshmallow is 
[07:06](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=426) fried on the Fire so I'll duplicate it again and move it down in attributes I'll give it yellow orange color 
[07:15](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=435) and then make it a little brighter and to keep it clear let's rename all sources we don't need reference plane anymore so let's remove it and let's create some 
[07:36](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=456) materials hit create redshift material standard then right away drag and then drop onto marshmallow body double click on material to reveal the 
[07:50](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=470) node editor the node editor is pretty similar to Espresso now we have only standard material connected to Output so select the note and pick some light marshmallow color I'll make it a little 
[08:03](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=483) yellow the real life marshmallow has very pronounced subsurface scattering effect in standard material you can just scroll down and find subsurface tab I'll just 
[08:15](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=495) increase the weight and give it slightly yellowish color it looks too glossy for the marshmallow so let's adjust the roughness now when we created the first material I 
[08:35](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=515) want to adjust the lights a little more I just want to make it less intensive to make material for the lips and the eyelids I'll just duplicate the marshmallow material 
[08:51](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=531) then I'm going to adjust the subsurface color I'll select some pin color and then you can drag it and drop directly in the viewport 
[09:11](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=551) I want to make a gloss here so I'll decrease the roughness and then adjust the subsurface color a bit more just a little later 
[09:28](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=568) then duplicate it once again and make it material for the eyes and the teeth for now I'll make it yellow just to distinguish it from marshmallow material we cannot drag it and drop directly 
[09:40](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=580) because it is connect object you need to apply it to the Spheres so I'll do it in the object manager and I'll do the same for the teeth and then adjust the color a bit 
[10:01](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=601) after that I'll duplicate the pink material and I'm going to apply it to the tongue nothing special here just pick some violet color 
[10:19](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=619) I noticed some hard edges in the tongue so let's subdivide everything at once just select private null and create your achieved object tag in Geometry tab hit override enable then 
[10:34](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=634) set maximum subdivisions to 2. it works like subdivision surface but in render time I'll adjust the tongue material a bit more in particular I want to make it 
[10:45](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=645) rougher maybe a bit colder I also think its Cutters light too much so I'll decrease the subsurface scale a bit 
[11:13](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=673) I also want to create a material for this black plate I want to make sure that it doesn't receives any lights has no Reflections and it's completely black so I'll pick the black color and set 
[11:25](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=685) reflection way to zero you can also adjust the iris and pupil materials I'll just make the pupil darker now let's create a material for the 
[11:44](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=704) bubbles find marshmallow material then double click to reveal the node editor but first let's just duplicate this node and connect it to Output 
[11:57](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=717) go to subsurface tab and pick some pink color I want to make it glossier as it melts so I'll decrease roughness and next we're going to add some bumps 
[12:15](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=735) I will use normal map so just drag and drop it here while hovering above node editor hit C and type bump map in redshift you need this node if you want to use BUMP textures just connect it to 
[12:28](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=748) the input and the output to the bump map input of the material then select texture and to make it work correct we need to select the right color space for normal Maps always use 
[12:40](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=760) raw then select bump map node and set map type to tangent space normal now everything is correct let's see what we have with the UV coordinates now select the material tag of the body 
[12:56](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=776) the projection is UV mapping it means it uses UVS generated by a volume measure it looks not very good so let's try something different cubic looks okay for me 
[13:11](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=791) so let's tweak the material a little more I'll select the bump node and decrease the height bit I just want to make it less pronounced 
[13:21](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=801) just small details and reflections and then adjust other parameters just a little bit decrease the roughness I want to make snows more transparent so 
[13:34](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=814) I'll increase the subsurface scale a bit I'm okay with this material so let's tweak the first material just connect to Output this time I'm going to use some noise for bump 
[13:51](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=831) so hit C and find Max on noise if you want you can connect it directly to Output to see it in render View I'll set type to voranoi one 
[14:09](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=849) and then switch colors to make bumps White I want to add some contrast so I'll go to Output Tab and adjust high and low clip 
[14:28](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=868) to make it smaller you can go to input tab and decrease scale now let's connect the material to Output I'll duplicate bump map node but this 
[14:41](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=881) time I'll set it to height field this way we tell the redshift we use black and white map now let's connect everything and see how it looks I want to scale it down a bit more 
[14:58](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=898) I also want to decrease the intensity so I'll go to bump map node and decrease the height to 1.5 when both materials are ready hit C and find a material blender 
[15:17](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=917) now connected to Output then first material connect to color and second to material color and the third input we're going to connect the black and white map which we will use to blend two materials 
[15:29](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=929) for instance we can connect black and white noise or any other black and white Shader or Texture but this time I want to use vertex map tag to do so hit C and find vertex 
[15:43](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=943) attribute let's immediately connect it to blend color then find vertex map tag in object manager and drop it into attribute name 
[16:03](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=963) let's see how it looks in different frames in my case everything looks great but if you want you can modify it using ramp node 
[16:18](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=978) just hit C and find ramp then connect vertex attribute to alt input and then connect the ramp node to Output you can adjust this gradient to remap 
[16:34](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=994) the black and white values for instance you can make it sharper let's see how it looks with material blender I love the original one so I'll leave it 
[16:51](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1011) like this now let's create a background for this create a plane and make it the child of the camera then in coordinates tab zero out all the 
[17:05](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1025) coordinates in object tab switch the axis so that it perpendicular to the camera then move it along z-axis behind the scene and in camera view manually adjust the proportions 
[17:22](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1042) after you adjust the plane create new material I'm going to create standard redshift material and drag and drop it onto plane I prepared animated back plate 
[17:34](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1054) just drop the first frame into node editor then connect it directly to output and we don't need the material node so you can remove it the colors are incorrect 
[17:47](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1067) for now to fix this we need to set the right color space redshift uses Aces so we need to invert Aces now colors are correct and we need to enable animation 
[18:00](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1080) go to animation tab set mode to simple we use 12 frames per second and then hit detect frames scroll the time slider to make sure it 
[18:15](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1095) works and now when we have back plate I want to fix something the Shadows looks too dark so I'm gonna create another light source and this 
[18:26](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1106) time dome light it just evenly eliminates the scene from all sides I'll just fix intensity make it a bit smaller marshmallow is very tiny object and we can make it much more realistic if we 
[18:41](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1121) add some depth of field effect for this select camera and enable bokeh to make effect more noticeable we need to greatly reduce the aperture also we need to correct the focus 
[19:01](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1141) distance you can make it manually right here or you can use this dropper and pick the point in viewport I'll maybe increase your aperture back let's see how it looks in different 
[19:20](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1160) frames and the last thing that we'll have to do is the texture of the stick I'll create another standard thread shift material then find the stick in object manager 
[19:32](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1172) and apply the material I'm not going to do anything complicated I'll just drop this texture and connect it to color I want to make it more made so I'll 
[19:48](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1188) increase roughness we made it out of a cylinder so it has cylindrical UVs let's keep it simple just choose any projection that looks okay to you 
[20:05](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1205) I'll use cubic projection and then adjust it a little in texture mode now let's see how everything looks in different frames 
[20:35](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1235) if you're happy with the result let's make a test render for this just switch to bucket rendering at first I just want to render one frame this video is paired up four times and 
[20:50](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1250) you can see it renders too slow so I'll see how it looks and then adjust some settings the final result is pretty good so let's go to render settings 
[21:05](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1265) in output you can change the resolution I'll leave it like this then don't forget to set the frame rate to match the project in our case is 12. set frame range to all frames from 0 to 
[21:19](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1279) 55 in save tab select the path in which you want to save the animation all set format to jpg and in redshift tab I'll slightly change the settings you can use standard 
[21:37](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1297) presets but I use medium and it renders too slow that is why I'll switch mode to Advanced in global elimination tab I'll set secondary to Brute Force 
[21:51](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1311) we use limited frame rate so I'll disable the motion blur in sampling I'll set threshold to 0.05 and enable denoise now let's make another test render 
[22:05](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1325) now it renders much much faster the only thing is that because of denoise we lost a few details I'll save the project just in case then hit render to picture viewer 
[22:33](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1353) if the couple of frames are ready check if they appear in the folder and if everything is okay just complete the render and you can combine those frames in any 
[22:44](https://www.youtube.com/watch?v=ede4ouNOXyQ&t=1364) video editor such as after effects or Premiere and this is my result 