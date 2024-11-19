---
URL: https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi
thumbnail: https://i.ytimg.com/vi/jBT6MD7IzHU/default.jpg
channel: "[[Brandon 3D]]"
published: 2022-04-24T20:00:31
duration: 1108
tags:
  - video/3D/texture/node
done: false
cover: "[[Pasted image 20240715162546.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "18m 28s"]
[[./Learn the BASICS of Material Shading in BLENDER (Part 1)|Learn the BASICS of Material Shading in BLENDER (Part 1)]]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715162546.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Blender PBR Material Shading (Material Series Part 2)" src="https://www.youtube.com/embed/jBT6MD7IzHU?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: This Blender tutorial is all about PBR textures and PBR materials in Blender. I'll show you where to download free PBR materials, how to set up material nodes in the Blender node editor, some node wrangler shortcuts and more. In Cycles, PBR materials provide the most realistic renders for Blender. The nodes can be confusing, but I'm going to explain PBR materials in Blender for absolute beginners. )

This is part two of a Blender material shading tutorial series. Watch part one here: https://youtu.be/Wg244y2f9Fw

Here's the affiliate link to TOPAZ STUDIO. I earn a commission if you purchase with this link: https://topazlabs.com/studio/ref/1275/?campaign=YTMaterialTutorial

Topaz Studio Video Review: https://youtu.be/tFBrF9RiDTI

FAVORITES:
Here are some of my favorite things related to Blender and digital art: 

❤️ My favorite Blender add-ons: 
https://brandonsdrawings.com/best-blender-addons

❤️ Favorite Blender courses on Udemy: 
https://brandonsdrawings.com/blender-udemy-courses

❤️ Favorite gifts for digital artists:
https://brandonsdrawings.com/products-for-digital-artists

My Amazon shopping list for digital artists: 
https://a.co/9774wiw

As an Amazon Associate, I earn from qualifying purchase. 

Get more Blender and 3D content on my website (and subscribe to my e-mail list) at: https://brandonsdrawings.com

Instagram:                  https://www.instagram.com/brandonsdrawingsart/
Facebook:                   https://www.facebook.com/brandonsdrawingsart
Twitter:                        https://twitter.com/brandons_art
ArtStation:                  https://www.artstation.com/brandonsdrawings


TIMESTAMPS:
0:21 Intro to PBR Materials
3:02 Base Color Maps
3:29 Specular/Reflective Maps
4:45 PBR Texture Mapping
6:31 Roughness/Gloss Maps
7:50 Normal Maps 
9:39 Displacement Maps
13:10 Adjusting PBR Scale
14:37 A BETTER WAY!
15:45 Extra Tips

# Transcript
[00:00](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=0) Welcome to Part 2 of my Blender Tutorial 
on material shading. If you stumbled across   this video first, there is a Part 1 that covers 
the absolute basics of shading in Blender. Part   2 is all about PBR materials. What they are, 
where you get them and how to set them up.   With a bunch of extra tips 
along the way and at the end.  I will be using Cycles for this tutorial. Most 
of this will work in Eevee too so let’s go. 
[00:21](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=21) The PBR in “PBR materials” stands 
for Physically Based Rendering.   It’s a workflow for using physical information images to generate textures. You could make   your own PBR textures, but don’t because 
there are tons of them already out there.   PBR textures are generally going to look much more 
realistic than procedural textures which are made   by combining inputs like we did in part one.
When you obtain a PBR texture, you’re going to   
[00:42](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=42) get a series of images with specific labels. Each 
image controls a different effect of the material.  So where do you get PBR materials? Lots of 
places. I often use Poliigon which has both   free and paid materials. I’ve been happy 
with them and will include an affiliate   link in the description. But, there are other 
places to get free PBR materials for Blender.  Ambient CG is one place I would check out, but I’m 
going to be using Poliigon. You can see they have   
[01:04](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=64) a pretty large library of really good materials.
When you choose a PBR material, also referred to   as a PBR texture, you have different resolution 
options. For example here, we have from 1K all   the way up to 16K. Poliigon uses jpg images, but 
some sites have JPEG’s which are smaller files but   can be lower quality. Which size you choose will 
generally be based on how far away the material   is going to be in your scene. For things in the 
background and honestly for most of your scene,   
[01:30](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=90) 1K is probably fine. If it’s going to be close up 
to the camera, consider going up a size or two.   Generally I find 3K to be fine for almost 
anything. The larger the resolution,   the more it adds to memory draw and render time.
These are all the different maps the texture comes   with. I know I won’t use all of them, in fact 
the two bump maps and two displacement maps are   just different size options you can use with this 
material. But they don’t cost any extra, so I’ll   
[01:55](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=115) just download them all. They’ll all download into 
a zip file which you can unzip on your computer.   It’s generally a good idea to store all of your 
PBR textures in an organized file system. You can   change the names of the folders but don’t rename 
the actual images themselves. They’re named the   way they are so that they can be recognized 
by certain addons which we’ll see later.  Let’s go back into Blender and just start with 
a new plane with a new material. I’ll name it   
[02:19](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=139) Poliigon, then let’s go into the shader editor.
We’ve got our default Principled BSDF shader.   I also have the file folder open with 
the files I downloaded from Poliigon.com.  We can bring these files into the shader 
editor a number of ways. We could press   Shift+A and add an image texture. This is 
the node that plugs images into your node   tree. We can press “open” and navigate to 
the folder where the material files are.   
[02:43](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=163) Or, if we have the folder open, we can simply 
drag and drop an image into the shader editor.   Blender will automatically add 
it into an image texture node.   A side note, you can navigate to and open these 
image files even if they’re not extracted. But,   dragging and dropping the files won’t work unless 
you extract the zip file. That’s good to know. The first file we are going to start with is the 
one labeled “color.” Actually, there are different   
[03:06](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=186) variations provided with this material. These are 
just slightly different color options you have   with this material. I’ll pick one and I’ll drag 
it into Blender. Since this is our base color,   we are going to drag the color output (the 
yellow) into the base color input of the   Principled shader (which is also yellow). 
Now, we’ve got our PBR base color laid out. If you’ve made it this far,   
[03:25](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=205) please hit that like button - it would 
mean the world to me. Thank you so much! Next we’re going to work on our specular 
input. Remember in part one I said there   are two workflows, specular and metallic.
Let me just go back to Poliigon for a   second. For certain metal materials, 
you’ll see an option for workflow.   You can choose “metalness” or specular. These are 
the two workflows I mentioned in part 1. There   
[03:46](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=226) are different reasons to use each one, it seems 
metalness is more popular for metal materials.   Either one you want to use is fine, it’ll 
just change one map that you have to plug in.  But for materials that are not metal, you won’t 
see a metalness map and you’ll use a specular   map. But notice we don’t have an image labeled 
specular here either. Sometimes specular maps   are called “reflection” maps. We do have 
a map labeled “reflection” and that’s the   
[04:10](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=250) one we’re going to use right here. Drag the 
reflection map into Blender and connect it to   the specular socket. Reflection equals specular.
Now, we have an issue here. We just plugged a   yellow socket into a grey socket. This isn’t the 
end of the world, but when using an image texture   but NOT using it for color data, we need 
to change this drop down box from “sRGB”   which means color, to “non-color.” This tells 
Blender that even though this is a yellow output,   
[04:36](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=276) it’s not putting out color information with 
this particular map. The end result will   usually be just a little off if you don’t 
change this setting for non-color maps. There’s one step we’ve missed here though. 
And that is the mapping we covered in part 1.   We want to make sure these image maps are being 
mapped properly to the object. We need to add   both a mapping node and a texture coordinate 
node. Luckily, since we have the node wrangler   
[04:58](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=298) addon activated, there’s a shortcut. Select 
one of the image textures and press “Control+T”   and it automatically adds both nodes. 
And it told the texture coordinate node   to use the UV mapping which is what we want.
I will very quickly explain UV’s. When we take   a 2 dimensional texture and place it on a 3 
dimensional object, we need to essentially   unwrap the object. Imagine printing a 
label directly onto a cylindrical soda can.   
[05:21](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=321) UV unwrapping would be like cutting the soda 
can open to lay it out flat so that a printer   can print on it. The U and the V represent the 2 
axes of the 2 dimensional texture because the 3D   object already has the X, Y and Z axes labeled.
Unwrapping a plane is pretty much unnecessary   but it’s absolutely necessary for more complex 
objects. To unwrap an object, we go into edit   mode, select what we want to unwrap. (You 
CAN unwrap different parts separately).   
[05:47](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=347) Go to UV at the top and there are actually 
different ways to unwrap an object. Usually,   I recommend “Smart UV Project.” Select 
that. It has some options. Normally you   don’t have to change anything. Press OK.
We don’t actually need to do this here,   but if you wanted to edit your UV map, you can go 
to the UV Editing workspace. This is our UV. It’s   a very, very simple UV, but a UV nonetheless. 
There are plenty of Blender tutorials for UV   
[06:12](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=372) unwrapping, this was just the bare minimum to 
understand. So let’s go back to our shader editor.  So this color image is mapped through the 
mapping node and this specular map is not.   We want to connect this mapping node 
to the specular map as well. Remember   an output can go to multiple inputs, but only 
one output can go into a single input socket. Back to our material files, the next thing we 
want to map is our roughness. But again, there   
[06:36](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=396) is no map labeled roughness. It’s because other 
softwares use “gloss” maps instead of roughness -   so you don’t always get a roughness map. But it’s 
ok, I’ll show you how to work with this gloss map.  Let’s drag the gloss map into the shader editor. 
We will again change “sRGB” to “non-color” because   this isn’t providing color information to the 
Principled Shader. It’s providing black and white   data. And we’ll also connect it to the mapping 
node. All of the image textures we use will   
[07:01](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=421) get plugged into the same mapping node because 
we need them to all line up with one another.  Now when we connect this gloss map to the 
roughness socket, we see a noticeable difference   in the material - that is if we’re in render 
preview mode. A roughness map will make a material   look more realistic. But there’s a problem 
because the gloss map is actually the inverse   of a roughness map. What’s black on a gloss map is 
white on the roughness map and vice versa. So the   
[07:23](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=443) parts that are supposed to be rough are not rough 
and the parts that are not supposed to be rough   are rough. To fix this there’s a handy node we can 
add between the gloss map and the roughness input   that flips this all around. It’s called an invert 
node. Shift+A and search for “invert” Drop this   right between the two nodes. This node takes data 
in from the left - like all nodes do. It flips,   or inverts, the black and white values. Then 
it spits out the new information on the right. 
[07:50](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=470) There’s another map in this pack that will add 
a lot of realism. And that’s the normal map.   Normal maps, as mentioned in part 1, fake depth 
by manipulating how light hits the material.   They are not very draining on your 
computer but add enough realism to   be used as long as they’re not 
right up in front of the camera.   The normal map is this purple map. It’s 
a specific type of color mapping that I   
[08:09](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=489) don’t fully understand but that Blender does. So 
let’s drop the normal map into the shader editor.  We again need to connect this to our mapping node 
and we again need to change it to non-color data.   This normal map needs to be plugged into the 
normal input of the principled shader. But look,   we have a different problem here. We have a 
yellow going into a purple and that’s a no-no.  So what we drop between these nodes is a normal 
map node. Shift+A and search for normal map. This   
[08:36](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=516) node takes yellow socket color information and 
turns it into a purple output specifically for   normal maps. This is the strength of the normal 
map. Let’s click on it and change it to ten to   really emphasize what this normal map is doing.
Boom. Did you see that? How much realism the   normal map added when we turned the strength 
up. This is one area where these materials   work a lot better in Cycles than they do in 
Eevee. If we turned this strength up in Eevee,   
[09:00](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=540) it really won’t do anything. Cycles is just 
much more capable of handling details like this. A quick break because Youtube pays me practically 
nothing for these videos. Topaz Studio is one of   my favorite tools to use after I render in 
Bleder. It’s a collection of very powerful   filters. I use it on every single render. Here’s 
an example of a render straight out of Blender   and here’s what it looked like after using 
Topaz Studio. I am not sponsored but I made an   
[09:24](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=564) entire video on Topaz Studio and have an 
affiliate link in the description. There   are endless adjustments you can make 
to improve your render and the best   part - it’s a one time purchase 
with no ongoing subscription.   Please support my channel by checking it out with 
the affiliate link in the description. Thank you! Displacement maps in Blender give you another 
level of realism. I’m going to turn down the   
[09:44](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=584) normal value to demonstrate this. We can drag 
the displacement map into the scene, change it   to non-color data because it’s not going into 
a color socket. We also want to map this to our   UV by connecting it to the mapping node. Now, this 
map is going to run into the displacement channel,   not the surface channel like the others.
If we drag it directly into the displacement   channel, it’s not going to work because 
we have a yellow going into a purple.  
[10:07](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=607) Similar to the normal map, we need a specific 
converter to change the information from this   greyscale image into the information Blender needs 
to make this displacement work. This time we are   going to use a displacement node and drop it 
between the displacement map and the final output   shader. But, this automatically plugs the input 
into the normal socket. We actually want this   image, with black and white color information, 
to affect the height of the displacement - not   
[10:32](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=632) the normal because it isn’t a normal map.
To actually see the changes for this,   we need to be in render preview mode. 
They won’t show up in material preview.  When we plug the displacement into the socket, 
a couple things happen. We do see more detail   in the “bump” of the material. Also, you might 
have noticed the entire object kind of shifted.   The shifting is because of this midlevel 
setting. It offsets the entire geometry and   
[10:54](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=654) most of the time, I’ve found I don’t want 
it to do that so I change this to zero.  Ok, this added a little bit of bump but what’s the 
big deal? Well, to really show you the power of   displacement, I’m going to duplicate this plane. 
Let’s go to the material panel and scroll down   until we see the settings tab. Open settings and 
under surface, we find a setting for displacement.  This setting tells Blender how to use 
this displacement map either as a true   
[11:18](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=678) displacement map or something called a bump 
map - which is similar to a normal map as far   as the end result. There’s also an option to 
use both bump and displacement which is going   to give you the most realistic effect probably.
What it defaults to is the bump map, which is what   we see here, a little more detail without any more 
geometry needed. Let’s change to displacement.   Nothing really happens. This is because true 
displacement uses the geometry of the mesh   
[11:43](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=703) and this plane only has one face on it. 
Let’s select this plane, tab into edit   mode and subdivide the plane a few times.
Now when we tab into object mode we see   the displacement has done something but this is 
not right. On the displacement node, this scale   setting affects how strong the displacement is 
and the default of one is just way too high.   Changing it to .1 is probably more appropriate.
But it’s still not great because we only have so   
[12:07](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=727) much geometry here. Adding a subdvision surface 
modifier will help and we should change it from   catmull to simple because we don’t need 
the smoothing that the catmull provides,   just the geometry. This is alright. There 
are a couple ways to make it better. We could   use more subdivisions or a higher resolution 
displacement map. But realize that now we are   significantly impacting the performance. We’ve 
added a ton of geometry to this plane already.  
[12:30](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=750) The absolute best way to do this is actually 
to use adaptive subdivision. And I fear this   section of the tutorial is already dragging 
on way too long. But, adaptive subdivision is   intelligent subdivision that subdivides the 
mesh more the closer it is to the camera   and it’s perfect for this. To use it, you 
have to be in cycles, you have to turn on   “experimental” in the render settings and 
then on your subdivision surface, you’ll   
[12:53](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=773) have an option for adaptive subdivision. Check 
that and you’re going to have this displacement   be about as realistic as you can get it.
For a lot of things, normal maps and bump   maps are going to be just fine but this 
was an overview of displacement for you. Hey, remember to hit that like button 
if you’re still here. Thank you so much! Ok, so we’ve just created a basic PBR texture. 
Let’s say this texture was either too big or too   
[13:16](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=796) small for what we wanted. We can go back to our 
mapping node and adjust the scale. We generally   want to adjust the scale uniformly across all 
axes. It’d be annoying to have to adjust all three   of these values so we can do one of two things.
Under scale, either click the top value and drag   down. This will allow you to type in a number on 
the top and have it applied to all three numbers.   Or what I prefer to do is Shift+A and add a 
value node. Plug it into the scale of the input.   
[13:41](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=821) And now you can slide the value of this up and 
down or type in a value. The larger the scale,   the smaller the texture gets and it will 
eventually start to repeat. Smaller scale   will make the texture bigger on the object.
But, understand that we may have this texture   applied to multiple objects and making it bigger 
or smaller right here will change the settings   on every object that is using this material. 
So an alternative, and probably the way you   
[14:03](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=843) should do it, is to go into the UV editor and 
adjust the scale of the object’s UV instead.  This on the left is our UV for what 
we have selected. In this case,   it’s the entire object’s mesh. We can press 
“A” to make sure everything is selected.   Then press “S” to scale the UV instead of the 
actual material. This will only affect the scale   of the material on this object and actually only 
on the portion of the object you have selected.   
[14:27](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=867) Pressing G will allow you to move it around 
if you want to line it up how you want.   And R will let you rotate the UV - again 
not affecting the actual material itself. That was a ton of work just to set up 
one PBR. And it was a lot to remember.   Well it’s important that you got a basic 
understanding of PBR material setups,   but you don’t need to do this every single time 
you set up a new material in Blender. Let’s remove   
[14:51](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=891) this material and start from scratch with a new 
Principled shader. This is only going to work   with node wrangler activated in the preferences, 
which we discussed in part 1 but as a reminder,   make sure you go into your preferences - addons 
and check on the box next to “node wrangler.”  Select the Principled BSDF shader by clicking 
on it. Press “Control Shift T” and this file   navigator opens. Navigate to the folder where 
your PBR texture files are. Select the maps   
[15:16](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=916) that you want to add. I’ll choose color, 
gloss, reflection, normal and displacement.   Press Principled Texture Setup.
Amazing. Blender just added all these   maps into the shader editor and connected them 
exactly as I already showed you how to before.   It even organized the textures into 
frames and added a reroute node.   It inverted the gloss and added the normal map. 
It changed the appropriate image textures to   
[15:40](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=940) non-color for us. Super easy. And that’s 
really how you add PBR materials in Blender. And as I promised, here are a few extra tips as 
a reward for making it this far in the video. Once you have your PBR texture set up, there 
are a few common but optional things you can do.   For some of these black and white 
nodes like roughness and specular,   you can feed them through a colorramp node. This 
will give you some control over how reflective the   
[16:02](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=962) material is by either sliding the control points 
or darkening the white values. You could put them   through separate colorramp nodes or through a 
single node to control both of them together.  When you have color information traveling 
from one node to another, there are a few   nodes that you can actually use to adjust the 
colors. Let’s first start with a hue/saturation   node and plug it in here. Changing the hue 
could give a stylized look to the material.   
[16:23](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=983) The saturation setting can add saturation to 
the base color or lower it to have a more black   and white look. And with the value slider, you 
can lower the value to make the material darker   or increase it to make it lighter.
With any node selected, you can press   “M” on your keyboard to mute the node. This 
removes all of that node’s calculations without   having to remove the node itself. It’s a good way 
to quickly see if you prefer the material with or   
[16:47](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=1007) without the changes made by this node.
Another node you can add here is an RGB   curves node. You may or may not be familiar 
with using curves for color correction,   but in short there’s a red, green and blue 
channel as well as a combined channel that   controls all of them at once. There’s 
an entire science behind using curves to   adjust colors if you wanted to look into that.
These reroute nodes are handy when you have one   
[17:09](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=1029) output going to multiple inputs. You can add one 
by pressing Shift+A and searching for “reroute.”   Or if your nodes are already connected 
and you have node wrangler turned on,   you can hold down shift, click and drag across 
the multiple connections and Blender will add   a reroute node for you. If you want to move the 
reroute node, you need to select it and press G   to move it round like you would with an object.
If you want these nodes to take up less space,   
[17:32](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=1052) you can click this expand arrow at the top left 
of a node, to collapse it down to just this.   It removes clutter but you can quickly 
expand it back out when you need it.  When you have a big node like the Principled 
BSDF, but you’re not using all of the sockets,   you can select the node and go to Node - Toggle 
Hidden Node Sockets (or you can press Control+H)   and it hides the sockets you’re not using.
These connections, that are also called   
[17:56](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=1076) “noodles” by the way in Blender. You 
can control how straight or curvy   they are. I think they might actually be 
straight by default but I don’t remember.   Go to edit - preferences - themes - then find node 
editor and expand this part. Go all the way down   to the bottom and there’s a setting called “noodle 
curving.” I have it set to four. Changing it to   zero will make the noodles completely straight. 
Increasing it will change the curviness of the   
[18:19](https://youtu.be/jBT6MD7IzHU?si=ZB81bHSXXiNGZ_Qi&t=1099) noodle, you can adjust to your own liking.
My name is Brandon, don’t forget to hit that   like button and subscribe if you haven’t 
already. Thank you so much for watching! 