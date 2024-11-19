---
URL: https://www.youtube.com/watch?v=MgZsVBVZ3Nc
thumbnail: https://i.ytimg.com/vi/MgZsVBVZ3Nc/default.jpg
channel: "[[FFuthoni]]"
date: 2024-08-09
published: 2023-10-05T22:31:55
duration: 960
tags:
  - video/3D/texture/shader
done: true
cover: "[[Pasted image 20240715174858.jpg]]"
q-data:
  leech-count: 0
  due-at: 2024-08-05T18:00:00.000Z
---
[time:: "16m"]
# Painting brush strokes with Geometry Nodes in Blender
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715174858.jpg]]
````
````col-md
flexGrow=1
===
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/MgZsVBVZ3Nc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Turn on CC for subtitles.
(Description:: A breakdown and demonstration on how to use the Geometry Nodes paint-over tool "Curve Painter" that was put together to help you create a painterly effect.)

The setup can be downloaded here:
https://ffuthoni.gumroad.com/l/curve-painter

Inspired by these great videos from these amazing artists:
@codygindy painterly effect:  [[./Making 3D animation look painterly (it's easier than you think)|Making 3D animation look painterly (it's easier than you think)]]
```NiftyLinks
url: https://youtu.be/s8N00rjil_4?si=JivsZEo68e0OiN9v
title: Making 3D animation look painterly (it's easier than you think)
description: In this video, I'll go over a surprisingly simple way to make your stylized 3D renders feel like a painting. I do it by painting over Object Space Normal Map...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/s8N00rjil_4/maxresdefault.jpg
```
@Tradigital live paint filter: [[../../3D/Don't have/Turning 3D Models into Masterpieces A Blender Tutorial|Turning 3D Models into Masterpieces A Blender Tutorial]]
```NiftyLinks
url: https://youtu.be/6uaJ0L4E390?si=zS0UBAvinjyQqZsv
title: Turning 3D Models into Masterpieces: A Blender Tutorial
description: In this video, I introduce my Blender Live Paint Filter, an incredible tool that can turn your 3D scenes into stunning paintings in Blender. I'll share the s...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/6uaJ0L4E390/maxresdefault.jpg
```

The "combine normals" node group is taken from here:
https://blenderartists.org/t/how-combine-merge-two-normal-output-not-normal-map/1189648/27

The driver formula example:
fmod((frame-1)/5, 3)
based on these Blender Stack Exchange answers:
https://blender.stackexchange.com/a/2413
https://blender.stackexchange.com/a/263879

I can be found elsewhere on the internet via:
https://futhoni.carrd.co

CHAPTERS:
00:00 Intro
00:34 Inspirations
01:36 Breakdown & Demo
03:13 Modifier settings
06:02 Painting brushes
07:32 Material settings
09:24 Layering brushes
10:26 Using the textures
10:58 Hand-painted feel
13:17 Things to note
15:30 Outro
# Transcript
[00:00](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=0) good morning everyone in this video I am going to show you how I made this painterly effect that is based on a method by Cody gindy that is to paint over a baked object space normal map but 
[00:12](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=12) instead of using dedicated painting program I used curves and geometry nodes in blender this is the geometry nodes setup that I've put together to do just that and I've compiled them into this 
[00:23](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=23) hopefully easy to use setup that I created to help you to paint over the normal map you can download the setup on my Gum Road for free I'll leave the link for that in the 
[00:34](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=34) description before we get started I would like to mention the two biggest Inspirations for this project the first one is of course this video by Cody gindy where he went into detail to 
[00:45](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=45) explain and demonstrate how the effect was created and why it works in the first place it's very simple and very easy to implement but the result is just really great so if you haven't seen the 
[00:57](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=57) video please do so otherwise wise the video you're currently watching won't make any sense the second one is this video by Alan Wyatt also known as tra digital where he shows how he created 
[01:10](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=70) his Live Paint filter using geometry nodes to turn your 3D render into a masterpiece painting I think this is the best one of its kind that has ever been made I even copied some of the nodes and 
[01:22](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=82) tricks he used in the filter that he shared alongside the video so be sure to check them out I'll leave the link link for both videos in the 
[01:31](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=91) description with that out of the way let's get started this will not exactly be a tutorial I'm not going to explain every single node I used I'm just going to go 
[01:43](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=103) over the general stuff of how this setup was put together so it begins with drawing curve or spline using the draw tool in the curve edit mode then we take that curve to Geometry nodes turn them 
[01:55](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=115) into points instance a plane or grid on those points control the the size of the instanced planes using the curve radius after that we take the object which we will paint over to Geometry 
[02:07](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=127) nodes as well capture the normal to use later and then we lay it out in the UV coordinate so we can easily sample and render the normal to sample the normal itself we will use the sample nearest 
[02:18](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=138) surface node then store them in those instances and the geometry node setup is pretty much finished there the rest is just added to make it easy to paint and render out those brushes 
[02:30](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=150) to make those instan planes to actually look like brushes we will use this kind of texture Atlas with brush Alpha masks I'll go more into it later in the video but for now let's see how to use this 
[02:42](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=162) setup after you download the blend file and open it by default this is what you would see I've included one object here and a curve object which have the geometry nodes set up that I already 
[02:54](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=174) drawn as an example when you use this you can delete the object and delete the curves spline in the edit mode and then append your own object into this file but for this example I'm just going to 
[03:06](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=186) duplicate the curve painter object and delete the curv spline and I'll show how to paint it later these are the settings that I provided in the modifier properties the 
[03:17](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=197) first one is of course to select the object that you want to paint on then insert the name of the UV map for your selected object this one here is the blender default name for UV V map UV 
[03:31](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=211) margin is used to extend the border of your UV Islands it helps to avoid visible seam when using the texture output from this setup this will only be used when you're not using the use baked 
[03:42](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=222) normal map option preview UV map wire will show the wireframe of your UV to help you paint and place your strokes use baked normal map it will switch to use normal map that you have already 
[03:53](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=233) baked to be sampled instead of the default one captured from the selected object this is useful if you have modified your normal before painting it using this setup baked normal map is to 
[04:04](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=244) select a baked normal map that you want to use preview brush stroke is useful to see the size and shape of the brush stroke brush size adjusts the size of the overall brush stroke keep in mind 
[04:16](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=256) that you can also control the size of the brush stroke in edit mode by changing the radius with alt plus S size ratio changes the shape of your brush the lower the value the longer the brush 
[04:27](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=267) will appear and the higher the value your brush will turn into [Music] square small stroke density changes the density of the brush in the area where 
[04:39](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=279) the brush size is small large stroke density is similar but will do it for the area with larger brush size distort Position will scatter the brush to give some variations for most 
[04:53](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=293) cases you would only want a small value for this setting offset by spline index is used to offset the brushes in the z-axis according to the index of the curv spline that you have drawn this is 
[05:05](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=305) done to prevent the brush plane from clipping to each other offset randomly it has similar purpose as the previous setting but we'll do it randomly instead to give a little more 
[05:16](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=316) [Music] variations seed is to randomize the brush stroke and to get slightly different result hide background is of course to hide the background 
[05:30](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=330) render option will choose which passes to render zero is the object space normal map one is the tangent space normal map two is the random per instance and three is the alpha 
[05:45](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=345) mask material is yes to pick which material to use the preview UV map wire and preview brush stroke are temporary settings and will be disabled in the render automatically it's useful if you 
[05:59](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=359) forget to turn them off before rendering now with the settings explained let's paint some brushes select the curve painter object and enter the edit mode and select the draw 
[06:11](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=371) tool in the tool settings I like to use poly option since it works best for me but both options is compatible with the setup now the projection depth should be set to cursor and make sure your cursor 
[06:24](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=384) is in the world origin or zero in the z-axis after painting each stroke you can use alt plus s to change the radius and thus changing the size of the brushes to 
[06:37](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=397) match the area you're painting on the nice thing about using this setup is you don't really need to worry where you place your Strokes on since it will still sample the normal color underneath 
[06:54](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=414) it all right I'm going to speed up the painting process from here since it's just a repeating process of placing stroke and adjusting the [Music] 
[07:28](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=448) size all right the painting process is done let's talk about the material now go to the Shader editor here there are a few node groups that I've prepared the brush stroke passes node group contains 
[07:42](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=462) All Passes that we would render later the first socket of that group is where we would plug in the brush Alpha mask texture Atlas I've included one that I've created here this texture is 
[07:54](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=474) controlled using this pick image tile node group to choose different tile per brush plane instance es this is one of the tricks that I got from Alan Wyatt and his Live Paint filter as I've 
[08:05](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=485) mentioned you can even make your own texture I used K to do this painted it one by one and then put it into this 6x6 grid the first setting in the pick image tile node group is to choose between 
[08:19](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=499) point or Texture it has to be the same as the transform type in the mapping node that this group is connected into the second one is how many tile in one axis your texture Atlas has in this case 
[08:32](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=512) it's 6x6 which totals to 36 tiles the random input socket is where you would plug in the random attribute from the geometry nodes the pick or offset socket when the random input socket is not 
[08:45](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=525) connected to anything it will work to select one single tile useful if you only want to use the same tile from the texture Atlas and when the random input socket is connected it will works as 
[08:57](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=537) some sort of offset the second socket and brush stroke passes node group is where you would connect your baked normal map if you have chosen the option in the modifier settings and the last 
[09:08](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=548) node groups here are these brush Strokes attributes containing the attributes that was captured and stored from the geometry nodes I think that is all with the 
[09:18](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=558) material now you can render them out and use the results as textures a quick explanation on how to add another layer of brushes in case you want to use different Alpha mask texture 
[09:30](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=570) for the brush duplicate the curv painter object move the object above the previous one enable the hide background option also move the camera above all of the brushes and before you start 
[09:43](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=583) painting again in object mode snap the cursor to the new brush object by pressing shift plus s and choose cursor to select it now duplicate the material and add a 
[09:55](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=595) different Alpha mask texture [Music] [Music] in the gumroad download page I've also 
[10:29](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=629) included an example seene blend file inside the blend file I show how I use those Textures in my Shader I usually use the random texture output to drive the color Hue and the 
[10:41](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=641) roughness variation and I combine the object space and tangent space normal like this this is a trick I got from this post on the blender artist's 
[10:58](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=658) forum as a bonus I'll show you how to achieve this looping frame by frame hand painted F render it's not the most ideal way of doing it and you'll see why back to the curve painter setup I rendered 
[11:12](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=672) three versions of each passes with different seed value and to make it easy I key frame the render option and the seed settings like so and then render them as image sequence and I renamed the 
[11:23](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=683) result according to the passes type then I load those images as image sequence and this is the important part I set the frames to one and enable the 
[11:43](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=703) auto refresh in the offset parameter I will add the hashtag frame driver and then I will add this formula something like this the a value is how long one frame will stay until 
[12:01](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=721) switching to the next one and the B value is how many images are in the image [Music] sequence don't try to St 
[12:13](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=733) me I feel my world is faster and faster the tears and the laughter I'm here for around yes yes I'm an emotional mess yes but you wouldn't want me any 
[12:35](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=755) less yes cuz you know how Wild it could get to loveing emotional man I then add the other image sequences with the same setting copy the mentioned driver and paste them to the 
[12:54](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=774) other and yeah loading those many images is definitely not the most ideal way of doing this and this is only for one object I can't imagine using this in a more complex scene and if with that we 
[13:07](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=787) use high resolution textures it's going to be really resource demanding so I don't really recommend doing this I just used it to showcase the 
[13:17](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=797) effect here are some things to note when using this setup first UV seam limitation since using this setup we currently have to paint essentially in 2D space thus UV seam will be 
[13:29](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=809) unavoidable unless you are being very careful when painting and avoid painting over the UV boundaries so be aware of that second one is as I mentioned we're not painting in 3D like say using the 
[13:42](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=822) blender texture painting mode or maybe a dedicated program like substance painter so it's not going to be easy to tell where the stroke we paint will going to end up on the object third to render the 
[13:54](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=834) brush Strokes we use EV and the alpha hashed option in the material IAL blend mode you may encounter this black spot that is caused by these planes clipping to each other to deal with this we can 
[14:06](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=846) just change the seed setting until the problem is gone or we can increase the offset by spline index and the offset randomly settings and then move the camera higher than The Strokes fourth 
[14:18](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=858) another thing about using the alpha hashed is that the area where there are transparency going on they're going to be grainy and the way I know to reduce the problem is just by increasing the 
[14:28](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=868) sample count not the most ideal I know but it is what it is unfortunately fifth this setup will not be suitable if your object has UV udm as the setup wasn't created with that in 
[14:40](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=880) mind so make sure that the UV islands are all in the same UV tile and lastly I found that this method is going to produce better result if we use higher resolution texture since using smaller 
[14:53](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=893) resolution we will kind of lose the smaller brush Strokes detail that we painted so keep that in mind mind all right those are some of limitations and drawbacks of using this setup that I've 
[15:04](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=904) encountered myself when testing it there are definitely more to add to this list but I've only tried this with my own workflow so this is where you come in download the setup test it with your own 
[15:14](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=914) unique workflow and if you stumbled upon problems that can be improved feel free to send them my way I can be found with this handle on Twitter Mastadon Instagram or Discord so let's do this 
[15:27](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=927) together all right that is all for this video and until next time good [Music] [Music] 
[15:57](https://www.youtube.com/watch?v=MgZsVBVZ3Nc&t=957) night 