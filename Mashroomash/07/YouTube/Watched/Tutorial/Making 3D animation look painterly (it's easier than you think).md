---
URL: https://www.youtube.com/watch?v=s8N00rjil_4
thumbnail: https://i.ytimg.com/vi/s8N00rjil_4/default.jpg
channel: "[[Cody Gindy]]"
date: 2024-07-02
published: 2023-09-18T01:31:30
duration: 485
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715175730.jpg]]"
---
[time:: "8m 5s"]
# Making 3D animation look painterly (it's easier than you think)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715175730.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Making 3D animation look painterly (it's easier than you think)" src="https://www.youtube.com/embed/s8N00rjil_4?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: In this video, I'll go over a surprisingly simple way to make your stylized 3D renders feel like a painting. I do it by painting over Object Space Normal Maps, which is not as scary as it sounds. This technique allows us to capture the feeling of a 2D painting while maintaining the flexibility of 3D. )

I used Blender, Substance Painter, Substance Designer, and Rebelle to make the stylized tea kettle scene. 

Thanks for watching :)

Instagram: instagram.com/codygindy/
TikTok: tiktok.com/@codygindy

Chapters:

0:00 Intro
0:18 Top Five Favorite Things (about this technique)
2:19 Prerequisites
2:50 3 Basic Steps
3:05 Demo
4:30 Why does this work?
5:30 How Normals Work
6:39 Base color?
7:27 Conversions


Frequently Asked Questions

How do you paint World Space in Substance Painter/How do you paint on two channels at the same time?
In this video, I'm painting on a custom channel. The only reason it's "world" is because that's what I named it. Substance has no idea what it actually is and you can't preview it as a normal map in the software. You'll have to export it to your renderer to test it. 

Tyson explains the setup in this video: 
```NiftyLinks
url: https://www.youtube.com/watch?v=snJXgLqXhb4
title: substance dual paint layers
description: texture set settings and set up custom sRGB 16F (double check what is going on for normal)Create a FILL layer with your custom channel and drop in the baked ...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/snJXgLqXhb4/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGFwgXChcMA8=&rs=AOn4CLDGR487TbDO6SExe87eE0EcIroiVg
```

How do you convert your painted object space map to tangent space?
You can just bake it again to a new image texture, but this time in tangent space. Just make sure your painterly object space normal map is plugged into your shader when you do it. 

Can I do this procedurally or semi-procedurally?
Yeah! Check out these videos:
Painterly shader with nodes: [[../../3D/New/2d style materials in 3d animation|2d style materials in 3d animation]]
```NiftyLinks
url: https://youtu.be/AtetvOEcZt8?si=dNj-8toj3XQxE4aO&t=890
title: 2d style materials in 3d animation
description: To try everything Brilliant has to offer—free—for a full 30 days, visit https://brilliant.org/joeyc . The first 200 of you will get 20% off Brilliant’s annua...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/AtetvOEcZt8/maxresdefault.jpg
```
Brush strokes with geometry nodes: [[./Painting brush strokes with Geometry Nodes in Blender|Painting brush strokes with Geometry Nodes in Blender]]
```NiftyLinks
url: https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=9s
title: Painting brush strokes with Geometry Nodes in Blender
description: Turn on CC for subtitles.A breakdown and demonstration on how to use the Geometry Nodes paint-over tool "Curve Painter" that was put together to help you cre...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/MgZsVBVZ3Nc/maxresdefault.jpg
```
Snapping normals (this one's in Korean, but is still pretty easy to follow from just the visuals): 
```NiftyLinks
url: https://www.youtube.com/watch?v=_wxvwwYWZHs&t=141s
title: 알려주는 사람이 없어서 영상을 만들었습니다
description: 
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/_wxvwwYWZHs/maxresdefault.jpg
```
Can I paint the normal map in Blender?
Yes! Check out these videos:
```NiftyLinks
url: https://www.youtube.com/watch?v=WyxPN2HRaFk
title: 3d paintings in blender! My two cents on hand-painting normal maps.
description: Here I tried to guide you throughout some works of mine based on hand-painted normals. Lets explore the possibility of this super cool technique.artstation: ...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/WyxPN2HRaFk/maxresdefault.jpg
```
```NiftyLinks
url: https://www.youtube.com/watch?v=IoIwVWmdqL4
title: Painterly Blender Shader Technique You should know about
description: Painterly Blender Shader Technique:In this tutorial, I explain how a painterly blender style can be achieved in blender in both hand-painted way and a proced...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/IoIwVWmdqL4/maxresdefault.jpg
```


# Transcript
[00:00](https://www.youtube.com/watch?v=s8N00rjil_4&t=0) in today's video I'll show you how to create this 
painterly 3d effect. I did it by painting over   an object space normal map, which is not as scary 
as it sounds. This technique allows us to capture   the feeling of a 2d painting while maintaining the 
flexibility of 3D. Also, compared to other methods   it's not that hard. To start, here are my top five 
favorite things about this technique. Number one,   the brush Strokes react to the lighting. The 
vibe of this scene is definitely morning tea,   
[00:28](https://www.youtube.com/watch?v=s8N00rjil_4&t=28) but if we wanted to make it midnight tea we can 
just move the lights around change the colors and   the image still feels painterly. If we want to 
add a little more mystery, maybe some intrigue,   we can do that too. Or maybe we want 
things to feel more eerie and otherworldly.   You definitely have to light with the brush 
strokes in mind, but in general this tea kettle   looks pretty good in any lighting setup. Number 
two, you can move the camera. It's easy to add   
[00:57](https://www.youtube.com/watch?v=s8N00rjil_4&t=57) cinematic camera moves just like you would in a 
more traditional 3D scene. You can also change   the focal length, which is helpful for making 
things look flatter or just weirder. Number three,   it's artist friendly. Similar techniques require 
dozens, even hundreds of nodes. For reference this   is the node tree for our kettle. It's super 
manageable because most of the effect comes   from painting image textures and painting image 
textures is a lot more intuitive for artists who   
[01:24](https://www.youtube.com/watch?v=s8N00rjil_4&t=84) have limited programming skills. Number four, it 
works with metallic and glossy materials. Because   we're using blender's default principled BSDF 
node, we can make our brush strokes look metallic,   rough, or glossy. There are also a lot of other 
inputs we can experiment with to get unique   effects. Number five, we have a ton of creative 
control over the brush strokes. Since we have   the option of hand painting our brush strokes, 
there's an opportunity to create looks that are   
[01:51](https://www.youtube.com/watch?v=s8N00rjil_4&t=111) unique to our scene and authentic to our style. A 
lot of other techniques just add brush Strokes to   surfaces randomly. They treat the brush strokes 
more like noise. And to be clear there are a lot   of times when automating your textures is a 
great option, but it's important to keep in   mind that brush strokes can actually do things. 
They can contribute to the mood, the composition,   and the story. Real quick, this is my first full 
video on this channel so you'd be helping me out   
[02:17](https://www.youtube.com/watch?v=s8N00rjil_4&t=137) a lot if you liked, subscribed, and left me a 
little comment. Anyway, here's what you probably   should know before you try this technique. Number 
one, the basics of a 3D program. I use Blender,   but Maya, Cinema 4D, Unreal, they should all work 
fine. Number two, UV unwrapping. This is just   because we're working with textures, but you don't 
even have to really be good at it to get started,   just the basics! Number three, Normal Maps. I'll 
explain these later in the video but, in short,   
[02:43](https://www.youtube.com/watch?v=s8N00rjil_4&t=163) we're taking a normal map that looks like this and 
making it look like this. So it helps to at least   know a little bit about how Normal Maps work. 
Alright, so there are three basic steps. First,   you bake an object space normal map. Then you 
paint over over it with brush strokes. Finally,   you take your painted normal map and you plug 
it into your shader. What's great is that you   can build off of these steps and construct 
a variation that works for you. So we start   
[03:07](https://www.youtube.com/watch?v=s8N00rjil_4&t=187) with our completed, UV unwrapped 3D model. To 
make an object-space normal map in Blender,   we'll start in the shader workspace where we'll 
add an image texture node. From there, we'll add   a new image. You can name it whatever you want 
and you can make it whatever size you want. Next,   under render properties, we'll make sure our 
render engine is set to Cycles. Then a bit further   down in render properties we'll open up the bake 
section. Let's change the bake type to normal   
[03:32](https://www.youtube.com/watch?v=s8N00rjil_4&t=212) and the space to object. Make sure your model and 
image texture are both selected then click bake.   From the image editor we can then save it onto our 
computer. Once that's done, we'll open the normal   map in our painting software. We want to cover our 
normal map with brush strokes, but we need to make   sure that the colors of the brush strokes match 
the colors of the normal map underneath. The most   straightforward way is to color pick, then place 
a brush stroke in the same area that you picked   
[04:00](https://www.youtube.com/watch?v=s8N00rjil_4&t=240) the color from. Then repeat. The software is up 
to you, Substance Painter, Photoshop, Procreate.   Completely depends on what you're comfortable 
with. I made this little brush stroke generator in   Substance Designer, which is a fun way to automate 
things. You can also use some sort of filter like   this one from Tradigital. As a last step, we bring 
it on back to whatever software we started with   and we plug it in. Here's the shader setup in 
Blender. It's important that the color space on   
[04:25](https://www.youtube.com/watch?v=s8N00rjil_4&t=265) our painterly normal map is set to non-color and 
that the normal map node is set to object space.   I think of this whole process as just a weird way 
of sculpting. If I sculpt facets into the base of   our kettle the result has a lot of similarities 
to our painterly effect. When we shine a light   on it we get these big blocks of uniform color, 
which is exactly how we want our brush strokes to   behave. And if I move the light the big blocks of 
color react accordingly. Of course, we have some   
[04:53](https://www.youtube.com/watch?v=s8N00rjil_4&t=293) problems. With the sculpting method we tend to get 
this pattern of connected cells. It's kind of like   a Voronoi pattern. But we want our brush strokes 
to overlap. We also get pretty orderly edges,   but we want the option to make our edges complex 
and organic. So the facets give us the general   behavior we want but they still don't look like 
brush strokes. That's where normal maps come in.   By painting our normal map we're making our object 
look like it's covered in facets, and crucially,   
[05:20](https://www.youtube.com/watch?v=s8N00rjil_4&t=320) those facets are shaped like brush strokes. So 
each brush stroke is being rendered as if it's   a flat surface, which is why for the most part 
each one ends up as a solid color. It helps a   lot to understand how normals work. So in 3D, 
normals tell us which way a surface is facing.   To show this let's assign each direction 
a color. We've got the Magenta Direction,   the pale blue Direction, the cyan Direction, 
you get the idea. And we've got this cube in the   
[05:48](https://www.youtube.com/watch?v=s8N00rjil_4&t=348) center so let's color the faces of the cube based 
on which direction they're facing. We just created   an object space normal map. Here it is flattened 
out. Of course surfaces can face more than six   directions, so let's bevel this cube and you'll 
see we unlock a bunch more colors. If we round our   bevel you'll see we get a gradient in our normal 
map. As the surface gradually changes direction,   so do the colors. This is the main takeaway. In 
an object-space normal map, a gradual shift in   
[06:15](https://www.youtube.com/watch?v=s8N00rjil_4&t=375) color represents a rounded or curved surface, 
while solid stretches of color represent flat   surfaces. So let's sample the color from our 
gradient here. Then let's paint over this rounded   bevel with a solid color. You'll see that when 
we render it, Blender treats the area I painted   over as if it's a flat surface, even though if we 
look look at the silhouette it's very clearly not.   Adding a base color with brush strokes creates 
some additional color variation. Also sometimes   
[06:45](https://www.youtube.com/watch?v=s8N00rjil_4&t=405) your 3D model needs to be more than one color. 
Ideally the brush strokes in the base color are   the exact same shape and positions as the ones 
in the normal map. That way everything's lined   up. otherwise it can feel sort of discordant. So 
figuring out how to do this is kind of tricky. I   like to use Substance Painter, where you 
can paint two separate channels with two   separate colors at the same time. I just set up 
color jitter for the base color brush strokes,   
[07:12](https://www.youtube.com/watch?v=s8N00rjil_4&t=432) then focus on the normal map. If you're using a 
2d painting software, you can try painting your   brush strokes on several separate layers, then 
use clipping masks to change the colors. I would   love to work out a better method for this so let 
me know if you come up with something. So a couple   of things about conversions and compatibility. 
If you want to use this on a moving character,   you may need to convert your map from object space 
to tangent space. You would do this after you did   
[07:36](https://www.youtube.com/watch?v=s8N00rjil_4&t=456) your brush strokes. I still haven't tested this 
effect on an animated character so I have no idea   if it looks good. Also, different programs use 
different kinds of normal maps, so depending on   your workflow you may need to convert them 
by flipping the green channel. Alright,   that's all I got for now thank you so much for 
watching. Remember to subscribe here on YouTube   and you can also find me on Instagram and TikTok. 
So leave a comment if you have any questions. 
[08:02](https://www.youtube.com/watch?v=s8N00rjil_4&t=482) foreign 