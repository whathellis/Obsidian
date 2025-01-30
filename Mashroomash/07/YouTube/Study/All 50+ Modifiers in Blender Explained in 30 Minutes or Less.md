---
URL: https://www.youtube.com/watch?v=8BQYAwDW6IE
thumbnail: https://i.ytimg.com/vi/8BQYAwDW6IE/default.jpg
channel: "[[Daniel Krafft]]"
published: 2020-04-25T06:55:00
duration: 1936
tags:
  - video/3D/tutorial/blender
done: false
cover: "[[3qrvogfudi69ykkh8cptgs3i1lnd.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "32m 16s"]
[[../../../05 Notes/3D/50 terms|50 terms]]
`````col
````col-md
flexGrow=1
===
![[3qrvogfudi69ykkh8cptgs3i1lnd.jpg]]
````
````col-md
flexGrow=1
===
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/8BQYAwDW6IE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
*NEW* PDF Version: https://gumroad.com/l/modifierspdf
Instagram: https://www.instagram.com/danielkkrafft/
Discord server: https://discord.gg/wKhe3ss
(Description:: In this video, I'll be explaining every single modifier available in Blender. This took a long time so a like or sub is appreciated as always.)

Timestamps and Links:
Timestamps by ukropian:
0:00 Introduction
- Modify
1:22 Data Transfer
1:49 Mesh Cache
3:02 Mesh Sequence
3:07 Normal Edit
3:44 Weighted Normal
4:22 UV Project
4:37 UV Warp
5:00 Vertex Weight Edit
5:34 Vertex Group Mix
5:54 Vertex Weight Proximity
- Generate
7:22 Array
8:01 Bevel
8:24 Boolean
9:21 Build
9:41 Decimate
10:12 Edge Split
10:28 Mask
10:43 Mirror
11:06 Multiresolution
11:40 Remesh
12:00 Screw
12:17 Skin
12:54 Solidify
13:20 Subdivision Surface
13:58 Triangulate
14:15 Wireframe
14:23 Weld
- Deform
14:53 Armature
15:38 Cast
15:57 Curve
17:13 Displace
17:32 Hook
18:22 Laplacian Deform
19:17 Lattice
20:04 Mesh Deform
20:30 Shrinkwrap
21:03 Simple Deform
21:37 Smooth
22:00 Smooth Corrective
22:15 Laplacian Smooth
22:40 Surface Deform
23:58 Warp
25:00 Wave
- Simulation
25:29 Cloth
26:54 Collision
27:25 Dynamic Paint
28:19 Explosion
29:09 Ocean
29:37 Particle Instance
29:48 Particle System
30:17 Fluid Simulation
30:34 Soft Body

31:31 Outro. Thanks for watching and stuff

Modifier Documentation: https://docs.blender.org/manual/en/latest/modeling/modifiers/index.html
A more in-depth video my Mr Sorbias:
https://www.youtube.com/watch?v=z-SG_DcJF5I&t=5861s
Glab Alexandrov on Normals: 
https://www.youtube.com/watch?v=sqGFhiP-2mc&t=802s
--------------------------------------------------------------------
My Keyboard: https://amzn.to/2B5E4ji
My Mouse: https://amzn.to/2X2LJqY
My Drawing Tablet: https://amzn.to/2yBkY3J
--------------------------------------------------------------------
[insert epic affiliate link disclosure here]

Outro music by soundcloud.com/lakeyinspired
Video by Daniel Krafft

# Transcript
[00:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=0) hey everyone welcome to this video where i stay up late and explain to you all the modifiers in blender so what i want to do first before i get into it is tell you a couple of the settings that show 
[00:09](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=9) up a lot so i don't have to keep explaining them first of all if you see any setting that has to do with subdivisions resolution iterations anything like that all it means is that 
[00:16](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=16) it's going to usually increase the quality of whatever operation you're doing at the expense of computational power something else you'll see a lot is vertex groups symbolized by this icon 
[00:26](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=26) right here usually what this means is that you can limit the effects of whatever modifier you're doing to a vertex group so i'm going to go over really fast how to create one of those 
[00:34](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=34) first you're going to go into your mesh data tab click the plus now you've got a vertex group go into edit mode choose the vertices you want to be part of this group click assign you can always see 
[00:43](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=43) what vertices are in your group by clicking select in this case it's only these and if you want to remove them you can click remove to select the vertex group you would go back into your 
[00:50](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=50) modifier settings and choose that group and now you can see it's only affecting those vertices so why did i make this video well i wanted something like this when i was starting out and people were 
[00:59](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=59) really helped out by my last video about all the material nodes so i figured i'd make one for modifiers too i do want to point out that this is an overview so that people can use it as a reference 
[01:07](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=67) there are some other youtubers who have made longer videos that go much more in depth but condensing information is something that i do a lot so i figured there might be a place for this type of 
[01:15](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=75) video and of course i don't expect this to get the kind of reception that my last one did but i want to make sure that this information is accessible so here we go 
[01:24](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=84) the data transfer modifier does exactly as the name would suggest transfers one type of data from one object to another one of the most common ways you'll see people use this is to create custom 
[01:33](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=93) normals utilizing the custom normals option under face corner data you can literally take the normals from one object and project them directly onto the other object however it's common for 
[01:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=105) artifacts to be left over there are other ways to achieve things like this after all now this next modifier is called the mesh cache modifier and basically what it does is it imports and 
[01:55](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=115) applies different types of animation files the two that are supported being mdd and pc2 so right now i set up a ball bouncing animation and i enabled the mdd import export add-on which is included 
[02:08](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=128) by default with blender so all you have to do is go into add-ons and check the box then go to file export mdd and then once you've exported your mdd of course then you go to file path on your mesh 
[02:18](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=138) cache node click that file button go to wherever you saved it and import that mdd and so you'll notice right away this stuff is starting to happen because the animation has been applied to the object 
[02:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=150) and you have a few options such as influence to kind of affect the animation after you've already imported it and in some cases you may need to flip the axis depending on what program 
[02:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=160) you imported it from i personally don't know a lot of people who use this in their workflow but that's okay because some people i'm sure do now something important to keep in mind if you import 
[02:49](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=169) something like an obj to make this work when you go to import it you're going to need to go under geometry and choose keep vert order because this modifier depends on all the vertices being in the 
[02:59](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=179) exact same spot as they were before if they're not it's not going to work the mesh sequence cache on the other hand does something similar with alembic files the normal edit modifier allows 
[03:09](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=189) you to alter the normals of an object using another object as a reference in this case i have it set to directional editing these plane axes as the target and i did manage to find a practical use 
[03:21](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=201) of this effect on the blender documentation you can download this blend file from there at any time i will link that in the description for you here you can see a common effect in 
[03:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=210) games editing the normals of leaves to look like they're facing the camera this is a sort of illusion that makes the branches seem fuller as you can see here the branches look far more sparse 
[03:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=220) compared to this image and that is all thanks to the normal added modifier the weighted normal modifier tightens up the normals of your objects so that they're more likely to point towards the 
[03:49](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=229) direction of your face normals instead of out in the middle of nowhere as you see right here here we've got 1736 vertices here we've got 24 vertices this one clearly looks a lot better but 
[04:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=240) let's just go ahead and add a weighted normal modifier slide the weight all the way up and the fact that these are even comparable is ridiculous just for the heck of it let's add one with one more 
[04:09](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=249) with one more level of subdivision depth coming in at 56 vertices smooth auto smooth throw on a weighted normal modifier bring the weight all the way up and i can hardly tell the difference 
[04:19](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=259) between these two this modifier is awesome the uv project modifier allows you to select an object to use as a projector and then use that for custom uv projections just like i have this 
[04:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=270) arrow here projecting the uv map onto this susanne it stays that way even if you rotate the subject why does it look like he's moving the uv warp modifier allows you to use external objects such 
[04:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=280) as an empty or something else and then use it to alter the projection of uvs onto your other object so in this instance i'm using an empty plane axes you know you can rotate scale move all 
[04:52](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=292) the typical things it's actually possible to accomplish this with the object output of the texture coordinate but this one has a few other options with it these next three are all 
[05:01](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=301) about weight painting the first one is called vertex weight edit for it to work first you're going to need to select the vertex group you're trying to edit and from there it depends on what you want 
[05:11](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=311) to do you're going to want to check these boxes group add and group remove depending on what you want to do to the weight painting job you've already done so if you check group ad one of the 
[05:19](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=319) things you can do is change the default weight by sliding this slider here nothing that you've already painted will be affected by this unless you want it to and you can adjust that fall off with 
[05:29](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=329) this parameter here you can also check this group remove box to scale back your weight painting now this next one is vertex group mix and i kind of see it like a mixed node if it were a node for 
[05:39](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=339) vertex weights and so basically you have a vertex group a and a vertex group b and next you have a bunch of mixed nodes available to you you can add to weight paint groups you can subtract you can 
[05:50](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=350) multiply you can divide just like you would with any other kind of data finally we have the vertex weight proximity modifier first thing i'm going to do is create a new group and assign 
[06:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=360) all of the vertices to it now what you're going to do is set that group to be the vertex group option in vertex weight proximity and here's how we're going to demonstrate the way this works 
[06:08](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=368) i'm going to put my 3d cursor somewhere in the center of this topology i guess you could say and now i'm going to add in an empty i'm just going to make it a cube i think and i'm 
[06:18](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=378) going to scale it down one thing i've noticed is that the scale doesn't affect it at all it is just about where it is and so now what i'm going to do is i'm going to select that cube as a target 
[06:27](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=387) object i'm going to set the distance to geometry because this is going to change everything now as i go into weight paint mode you can see what's happening it's 
[06:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=396) changing the vertex group based on where this empty is and you can adjust this falloff with the lowest and highest values here keep in mind that blue is zero and red is one you can also adjust 
[06:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=406) the falloff type with this parameter here so i'm going to put this right before the wireframe modifier now let's go back into object mode to see what we're working with as you can see 
[06:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=414) it's a pretty dense wire frame and we're going to go for like a cool fade effect that you might see in like a hologram or something so if you select this vertex group you'll see that something starts 
[07:03](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=423) to happen but then you're going to click this invert button now tell me that isn't the best fade effect you've ever seen like i 
[07:11](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=431) realize this may not be realistic for something like a game but if you're going for full geometry man this is the best starting us off with the generate 
[07:23](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=443) modifiers is the array modifier now this is one that you probably know about already basically you've got a count slider which when increased creates new instances of your mesh based on an 
[07:34](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=454) offset now there's actually three different types of offsets here we've got relative offset which offsets based on the size of your original object we've got constant offset which is based 
[07:44](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=464) on the actual coordinates and my personal favorite object offset where you can use something like an empty to rotate scale or remove the array on its own that's something that i use all the 
[07:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=474) time and i'm sure you'll find it useful now there's a couple other settings in here that i want to talk about but we're going to have to get to them later when we get to these other modifiers next up 
[08:02](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=482) we've got the bevel modifier now this one does exactly what you might expect it to do creates a bevel on all of the edges of your model now if you want to you can actually choose to only bevel 
[08:12](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=492) vertices and there's a few other options that we're going to go over namely the offset when you adjust the offset you can actually adjust how much of an effect you've got here segments adjust 
[08:21](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=501) the resolution of your bevel this is a huge one for beginners next up we have the boolean modifier and this is probably one of the most important modifiers that you need to know about 
[08:29](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=509) especially as a beginner so for a boolean modifier we need two objects now this is kind of similar to pathfinder if you're used to illustrator or something like that we have the operations 
[08:39](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=519) difference union and intersect so i'm going to explain each of them to you very briefly first you're going to need to select an object in this case i will be selecting this cube and in the case 
[08:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=528) of difference what's going to happen here pardon me while i go into viewport display and choose displays bounce so that we can actually see what's going on you can see that what difference does is 
[08:58](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=538) uses this object to cut out of it now you can use any object here it doesn't have to be a cube it's an essential modeling feature that you're going to need to get used to next up we have the 
[09:06](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=546) intersect function now this is probably the one that i use the least but in this case it uses the object to cut out everything except what intersects with it and then finally in the case of union 
[09:16](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=556) it will combine them all and make them hollow in the center just make sure that both of them are closed meshes for this to work properly next up we have the build modifier now this one is a bit 
[09:24](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=564) more special case when you add the build modifier what's gonna happen is you're gonna notice that things start disappearing if you scrub down the timeline you'll notice that it is being 
[09:32](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=572) built face by face and that's kind of cool effect i'm sure someone will come up with something really cool with this i personally have never really used it though now this next one i can say i've 
[09:42](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=582) used a lot here you can see this object has 31 000 faces however when you bring this slider down what it essentially does is takes all those faces and then just collapses them 
[09:52](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=592) into this giant mess it tries to keep the shape the best it can and usually does a pretty good job there's a few different things you can do to help it i guess namely the symmetry tool which 
[10:01](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=601) does its best to keep all the faces the same on either side this probably isn't the best retopology workflow but i've used a lot for artistic purposes actually namely the low poly style can 
[10:11](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=611) be helped a lot the edge split modifier splits edges from other edges either based on an angle or whatever you've marked sharp once applied you can see that these faces are all separate from 
[10:20](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=620) each other there's of course the rip region tool which i use probably a lot more than this but i'm sure that someone else has come up with a better use for it the mask modifier literally just 
[10:29](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=629) hides your objects now you can do that based on a vertex group or an armature now don't get me wrong i'm sure that there's a good use for this but as of yet i've never really had to use it i've 
[10:39](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=639) never really found a reason to so let me know in the comments and that will probably help someone else next up we've got the mirror modifier now let me get this clear right off the bat the mirror 
[10:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=646) modifier is your best friend it will mirror one side of your mesh to the other side so that you don't have to worry about symmetry you can just edit one side and it will automatically edit 
[10:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=656) the other side as well it goes pretty deep actually to the point where you could add a mirror modifier check all the other axes work on one side and then use symmetry on all other sides at the 
[11:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=665) same time the multi-resolution modifier i've always kind of seen it as a subdivision service modifier on steroids you've got so many options here and i've heard this was very popular back before 
[11:17](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=677) dynamic topology because as you can imagine when you're sculpting with not very much geometry it doesn't look very good but since the introduction of dynamic topology which was like a long 
[11:26](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=686) time ago the farther you zoom in the more geometry it creates right at that spot so while it's definitely not even topology at least there's less of it and do keep in mind that you're gonna 
[11:37](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=697) need to do some retopology for this look good sorry i had to say it okay let's move on the remesh modifiers offers a few different ways for you to change the topology of your models here we have the 
[11:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=706) sharp option here we have the smooth option and here we have the blocks option which has sort of a voxel look even though they're technically not voxels people have sent 
[11:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=714) me some extremely cool abstract art made from this modifier so if that's the kind of thing you're into go check it out the screw modifier takes an object usually i like to use a 2d object such as a circle 
[12:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=725) and then it coils it around based on the angle the screw value the iterations and a couple of other things so basically use this for springs or anything else that resembles this shape it's probably 
[12:15](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=735) going to be the most efficient way for you to do so the skin modifier generates a sort of chats around all the edges of your model i really like to use this one with just one vertex or one edge as you 
[12:25](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=745) can see i just merged a cube together with alt m and as i control click i can kind of create my own edges here and if i put a skin modifier on it it will create geometry around it and the cool 
[12:34](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=754) thing is if i select the vertex and then press ctrl a i can scale this thing in and out this is probably the easiest way you will ever create a low poly tree or any tree for that matter if you go ahead 
[12:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=765) and slap some other modifiers on there just control and click control and click control and click it's super easy barely an inconvenience and let's go ahead and move on the solidify modifier this one 
[12:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=776) is an easy beer a tier now i'm going to go ahead and show you what it does with a two-dimensional object but it works with pretty much any objects so if you add a solidify modifier onto this 
[13:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=785) basically what it does is it adds thickness that's what most people will be using it for because you've got to admit it is super nice to just be able to work two dimensions and it 
[13:14](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=794) automatically be made into three dimensions i mean that's the kind of stuff that the procedural workflow is for in the first place but anyways next up we have the best modifier in blender 
[13:23](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=803) the subdivision surface and honestly if i had to choose one modifier out of all of these just one that i could keep it would be the subdivision service modifier i use 
[13:33](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=813) it in pretty much every single workflow you've got these options for subdivisions down here one of them is for the view this is how many subdivisions you want to see happen 
[13:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=820) while you're editing and then the render which increases the quality when you hit the render button usually i like to keep the render just one level higher than the viewport because i'm usually working 
[13:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=828) in a higher resolution when i render things case in point this uh funko pop model i made of my girlfriend for most of it i was working with a subdivision surface level of one but then in the 
[13:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=836) render i increased it to two all right let's go ahead and speedrun these last couple modifiers in the generate category first of all we have the triangulate modifier this is going to 
[14:03](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=843) take your phases and turn them into tries instead of quads now you've got a few different algorithms to run through to find your perfect triangulated topology i'm not going to explain all of 
[14:11](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=851) them but if some of them are giving you errors it is definitely worth trying some of the other ones wireframe i love this modifier so much you can adjust the thickness and basically it takes all of 
[14:19](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=859) your edges generates another chassis around them to create what looks like a wireframe and finally the weld modifier is from what i can tell a sort of merge by distance modifier 
[14:28](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=868) here you can see we've got a cube and one collection of vertices that seem to be pretty close together and if i increase the distance on this weld modifier you can see that it just gets 
[14:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=876) merged together and that's essentially what it's for because sometimes when you're doing things like hard surface models you end up with vertices that are so close together that you probably 
[14:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=885) meant them to be merged but for some reason that didn't happen starting us off in the d4 modifiers is the armature modifier i usually don't go about adding this modifier straight from 
[15:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=900) the modifier menu because essentially what it does is it helps you add a rig to your model so you can animate it now if you've ever looked at a tutorial on this topic you know that usually you 
[15:09](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=909) make the rig first and then parent your object to it so i'm going to go ahead and do that i'm just going to add a quick rig here i'm going to select the object and then the bone structure press 
[15:17](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=917) control p and click armature deform with automatic weights now if we look in the cubes modifiers we can see that an armature modifier has automatically been added except the difference is now we 
[15:27](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=927) have automatic weight painting and now if you select the rig and go into pose mode you can rotate and position your i guess character in really any way you want so that's the 
[15:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=936) armature modifier let's move on the cast modifier specializes in turning things into either spheres cylinders or cuboids let's check it out with this subdivided cube right now i have it set to cast 
[15:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=946) type sphere and if i up the factor you can see that it tries to become a sphere a factor of one is pretty much exactly what you want to entirely morph it anything above or below will exaggerate 
[15:57](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=957) the effect next up on the roster is the curve modifier now i'm gonna combine a few modifiers here to show you a cool trick i found so i'm gonna add a wireframe modifier to give it a little 
[16:07](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=967) bit of depth i'm going to add in a curve and a path and i'm going to and then i'm going to scale it up a little bit apply all the transforms you know the drill now i'm going to add an array modifier 
[16:16](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=976) and choose fit curve for the fit type that means that instead of choosing a number for the amount of objects that you want it'll choose that number for you based on a curve and in this case 
[16:26](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=986) it's this path curve and as we increase the size of the curve we get more objects and that's super cool but here's where the curve modifier comes in because essentially allows you to deform 
[16:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=996) an object along a curve and in this case it works perfectly since we're already basing the number on the length anyways so yes this means you can literally go and mess around with a curve and create 
[16:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1005) instances of an object along that curve perfectly now this is really great for things like chains i can imagine it's good for things like ropes specifically the really detailed ones oh and fun fact 
[16:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1016) if you delete everything in that path and then click this tool over here draw you can draw the curve and have everything duplicate along it perfectly it does bug me a little bit that you 
[17:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1025) can't just keep doing that but uh oh well but either way it's a really cool effect i'm sure people are gonna do really cool things with it who keeps putting these things in my video the 
[17:13](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1033) displaced modifier uses a texture to move the vertices of your mesh up and down now this one's really useful for materials for landscapes and for pretty much anything that you need extra detail 
[17:22](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1042) but you don't actually want to go and sculpt or model that detail something to look out for is these texture coordinates it's set to local by default but in some cases you're going to want 
[17:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1050) it set to your uv map this next one is called the hook modifier and it essentially allows you to use an object such as an empty to edit the geometry of another object such as this cube so 
[17:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1060) first i'm going to subdivide this a whole bunch of times and i'm going to go into the vertex groups and go ahead and add one and let's just do all these phases in the front go ahead click 
[17:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1068) assign now you're gonna go ahead and now you're gonna go and add a modifier in this case it's gonna be the hook modifier choose the empty as the object you're gonna want the radius to be 
[17:55](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1075) something pretty small at this size and make sure to choose the vertex group one way to test if your radius is good is just to bring it out a little bit and then go ahead and adjust the radius 
[18:03](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1083) until you get an effect that you like something like that's pretty cool interestingly this is one of the ways that you can animate in edit mode you can add multiple different hooks and if 
[18:10](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1090) you go into edit mode you can actually choose individual faces or sets of faces to be hooked by pressing the ctrl h key and then you can hook to a new object assigned to one of your other hooks 
[18:20](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1100) and well it's it's a fun time all around next up we've got the laplacian deform modifier now i'm going to be using the blender documentations example blend file here it's a horse in case you can't 
[18:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1110) tell here's what you're going to need you're going to need a vertex group to be the anchors and well that's kind of it essentially what they've done is they've taken this base mesh and they've 
[18:37](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1117) attached hooks to some of these vertices and then used those to reposition the horse and the reason why the replation the reason why the laplacian deform modifier is there 
[18:50](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1130) is because of this uh i need to go to bed so yeah this is a very serious business uh only professional uses for this modifier here 
[19:01](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1141) clearly does a pretty good impromptu job i mean it's a very powerful modifier here you can see that we have transformed a zebra into a giraffe all jokes aside if you do incorporate a lot 
[19:10](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1150) of hooks and deformation into your workflow this is a great modifier to get you started so that you don't end up with a the lattice modifier is another great 
[19:19](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1159) deformation one if you go into add and you've seen this lattice option you may not have known what it does before but if you click on it and scale it up it's actually got a few use cases the main 
[19:29](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1169) one being the lattice modifier one thing that you should do first is increase the resolution of your lattice to do that go into your lattice options go into resolution and up all of these to at 
[19:38](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1178) least three in my opinion now click on your monkey or whatever else you need add a lattice modifier go ahead and select the lattice and now here's what you're going to be able to 
[19:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1186) do go into edit mode on the lattice as you drag these corners in that you'll notice that it's deforming the object base on the lattice which is of course super helpful especially with higher 
[19:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1196) density objects where it's impractical to move around and deform the original mesh things like this help that become a reality the mesh deform modifier is pretty much the same as the lattice 
[20:07](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1207) modifier except you can use a mesh instead so in this case i've chosen a cylinder i've clicked the bind button that's going to attach it but but do keep in mind that could take a 
[20:17](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1217) while especially for the larger objects but that being said it does afford you some extra customization so let's play around with it and see how it works turns out it works like a charm so if 
[20:26](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1226) lattice just isn't cutting it for you go ahead and use the mesh to form next up we've got the shrink wrap modifier now this is one that is really popular with re topology specifically you're going to 
[20:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1236) take an object such as a plane or something that can be projected onto something else and then you're going to and then you're going to add a shrinker modifier to it and select your target 
[20:46](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1246) and as you can see it's just going to slap that thing down on the object there are a whole bunch of mode settings in here to go through so i recommend that you actually check out the documentation 
[20:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1256) or better tutorial on retopology for that kind of thing because retopology is an important part of your workflow however it's not the primary topic of this video next up is the simple deform 
[21:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1265) modifier now we've got a whole bunch of options in here to cover first of them being the twist option now you're going to choose your axis and then you use the deform angle to twist your object like 
[21:14](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1274) so pretty cool effect next up is the bend again select your axis and begin deforming next up is taper the effects of which you can see on the screen now now things like this are really good for 
[21:24](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1284) creating trippy objects such as this tunnel which extends forever and no just kidding it's a wormhole that does that there's a lot of creative freedom to be 
[21:32](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1292) enjoyed in here and i'm sure that someone is creating incredible procedural models with this next up we've got the smooth modifier what it does is pretty apparent right 
[21:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1300) from the start the main option that you're going to want to work with is this repeat slider as you increase it the iterations of this smoothing algorithm are increased and it will 
[21:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1308) continue to smooth your objects until they've had enough internet for today the factor is something that you can adjust to change the strength of the effect to instantly go from suzanne to 
[21:56](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1316) something that i can only hope exists not beyond this screen the smooth corrective modifier is meant to be used to fix mistakes that happen when you deform an object using an armature now 
[22:05](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1325) these effects are going to start to be a lot more beneficial as you get into very complex characters because let's be real even if you do a really nice weight paint job there's still things that are 
[22:13](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1333) going to turn out wrong laplacian smooth now this one is probably the cream of the crop here here you've got a repeat slider which is going to determine the iterations of this modifier the factor 
[22:24](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1344) value will change the strength of the effect on most of the surface you can also go inverted to have an opposite sort of effect where it emphasizes the imperfections now the border setting 
[22:33](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1353) does the exact same thing for borders that's why i uh removed suzanne's eyes sorry about that suzanne ever wanted to know how to make blinds that get affected by the 
[22:42](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1362) wind or something like that well it doesn't matter because you're about to make your blinds then make a plane this plane needs to have some resolution to be able to bend 
[22:50](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1370) essentially what we're going to be using here is called the surface deform modifier we're going to be transforming the def the deformation of this object over to this object since it's going to 
[22:59](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1379) be difficult to do something like a cloth simulation for this one we might as well do it on this one right so go ahead and add a service deform modifier on your curtains or your blinds or 
[23:08](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1388) whatever or whatever object you want to i'm sure there's a million other uses for this go ahead and target your plane and then click bind and then to test it go ahead and 
[23:17](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1397) grab some of those edges and move it around with proportional editing just to make sure everything's working okay then you're going to go ahead and in the case of this example you're going to go ahead 
[23:25](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1405) and add these vertices to a new vertex group these are going to be your pins go ahead and go to the physics tab add a claw simulation head all the way down to shape go to pin group and choose that 
[23:35](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1415) vertex group that you made the pins with and then if you want some wind all you have to do is press shift a go to force field and wind and then adjust the settings however you like you can hide 
[23:43](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1423) that original plane if you want and then as you can see as we play it it is deforming the plane which is the actual claw simulation and then transferring that over to these 
[23:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1434) blinds so clearly you could get really creative with this it's all up to you now next up we've got a pretty niche modifier it's called the warp modifier and i'm pretty sure i'll never use it 
[24:04](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1444) but i'll explain it to you anyways so you know how we have all those other d4 modifiers right well this one chooses to do it in a pretty unique way so you're gonna need to add two empties not just 
[24:14](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1454) one i'm gonna just duplicate these and then what you're going to do is choose one empty and then choose another one and what it's going to do is based on the 
[24:23](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1463) strength and radius and falloff it's going to create a sort of proportional editing based on both the starting point and the ending point it's very it's actually very interesting and one thing 
[24:32](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1472) that you can do if you go down to curve for the falloff type is you can create a unique uh customized falloff type as i said it's very interesting it reminds me of 
[24:41](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1481) some of those animations i've seen where they have they have a character walking around that's actually interacting with its environment and creating displacement and all that that being 
[24:49](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1489) said we do have a lot of those kinds of modifiers already is this one redundant no because it adds a new layer of complexity to it i just don't think that i'll be using it that much and a lot of 
[24:58](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1498) you beginner users might not either the wave modifier you've seen it you've heard of it this is what it does now i have it offset on the x you can use this you can 
[25:07](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1507) use these two options to do that both the position x and y if you have that at zero and zero it's going to be a radial wave and that's that's cool too now as you can see there's a bit of a delay 
[25:16](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1516) when it starts and that's because the waves are still coming from that point off to the side so to help with that you're going to decrease the offset a little bit and that way it should get 
[25:24](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1524) going right from the get-go claw simulations are a great way to add some atmosphere to your scene and while this is mostly a physics type of thing and not a modifier type of thing you can 
[25:36](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1536) add them wear modifiers so that means we go over them first i'll add in a plane and i'm going to scale it to about the right size and rotate it so that it's basically in line now i'm going to 
[25:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1545) subdivide it a bunch of times to give it the topology it needs to deform next we need to create the pin groups so i'm going to select these edges on the side and add them to a vertex group and now 
[25:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1554) when we add the cloth modifier we can go into the physics tab down to shape and choose that group as the pin group now if you reset the timeline you'll notice that when we play the animation it 
[26:03](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1563) actually starts to work all the settings for this are going to be in the physics tab and as you can tell there are way too many in here to even discuss in a video twice the length is this but some 
[26:12](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1572) of them that you're going to want to take care of are the stiffness and physical properties settings if you if you reduce the tensions in bending for example you'll get more of a dip in the 
[26:22](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1582) center as there's going to be less stiffness in this whole object one thing i like to do with things like this is cut out part of the fabric especially first especially for a stylized look i 
[26:31](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1591) think it looks really good the way i do that is with the knife tool with k and then i cut out a line and press x and delete the faces once you've got something that you like 
[26:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1600) you can of course let the class simulation run and maybe add more objects in there and make it and just have fun with it or if you find a keyframe that you actually really like 
[26:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1608) and you just want to leave it there you can always just apply the cloth simulator and there it will stay but that actually leads us perfectly into our next modifier which is the collision 
[26:57](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1617) modifier i'm gonna go ahead and add in a sphere and shade it smooth just because and then i'm going to add a collision modifier on here of course all these things can be added within the physics 
[27:08](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1628) tab and that's maybe even recommended so if that's the way you want to do it go ahead but as you can see the collision modifier allows objects to collide with each other the nature of the cloth 
[27:17](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1637) simulation means it already has object collision enabled but for objects that are not part of the simulation already you're going to need to add a collision modifier to them next up is the dynamic 
[27:26](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1646) paint modifier now for this thing to work you're going to need two different types of objects you're going to need a canvas object which in this case is going to be a subdivided plane for me 
[27:35](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1655) and you're going to need a brush and i'm think i'm just going to use i think i'm just going to use a rock generator from the extra objects add-on which comes default with blender by the way and then 
[27:45](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1665) on the canvas i'm going to add a dynamic paint modifier or you can add it from the physics tab and then go back to the physics tab and change the type to canvas and click add canvas now do the 
[27:54](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1674) same thing for your brush object except change the type to brush and click add brush now you're going to change the type of the surface now there's a few different types here you could make this 
[28:03](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1683) be a paint brush some of my favorite types are waves so that if you play the animation you can see that waves start to happen and as you play with the brush object it 
[28:13](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1693) dynamically creates waves there's also displacement which allows you to displace the geometry as you might expect next up is the explosion modifier i'm going to use another object from 
[28:22](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1702) extra objects first off i'm going to add an explode modifier except right away you'll notice nothing happening even if your animation is playing so here's what you're going to have to do you have to 
[28:31](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1711) go into your particle settings add a new particle system and in this case i'm going to use emitter and then go back to modifiers make sure that goes before the explode modifier because what this is 
[28:42](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1722) going to attempt to do is use the particles to break faces off of your object until it is completely gone and do things such as reduce the number of particles total to 
[28:53](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1733) choose the amount of pieces that your object will break into you can change the frame start and frame end to define the range now something else you're going to want to do is work with the 
[29:02](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1742) rotation i usually just drag randomize all the way and for some reason that makes it not randomized all the way next up we're going to make the ocean so go ahead add a plane scale it up give it 
[29:13](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1753) some vertices go ahead and add a modifier and add an ocean modifier this one actually works pretty much right out of the box you just have to adjust the scale of all this so i'm going to go 
[29:23](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1763) ahead and bring the size value down now here's a quick overview of some of the settings that you need to know about the repeat settings you could kind of think of like an array the time setting is 
[29:31](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1771) where in the animation this is going to be it doesn't animate by default you'd actually have to go and animate this time value right here the particle instance modifier allows you to 
[29:40](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1780) basically copy the particle settings from one particle system all the way over to another particle system with a different object or something of your choice there the particle system 
[29:49](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1789) modifier is added automatically whenever you add a particle system or of course you can add it with the modifier you can click this properties button or go to the particle settings to open up your 
[29:59](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1799) particle settings now you can either have an emitter particle system or a hair particle system both of which can be a lot of fun to play with but are extremely complicated 
[30:08](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1808) dealing with different types of physics you will be able to find extensive tutorials on each of these and as this is not a particle tutorial i won't waste your time fluid simulation is one of 
[30:18](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1818) those things where it takes two different objects to make it work first you've got to have your flow and then you've got to have your domain object and while i'm not much of a fluid 
[30:27](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1827) simulation guy myself i do know that cg geek has an excellent video on the topic that you might check out if you want to go deeper into this and finally for all of the modifiers we have the soft body 
[30:38](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1838) modifier now for this one i just went and made a cube with this much geometry it's much less taxing to create less geometry to start with and then subdivide it 
[30:48](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1848) afterwards as i'm doing here as it would be to do another subdivision level right here that would be insane so as always the settings are for these settings for soft bodies are in the physics tab 
[31:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1860) something that you're going to want to uncheck is goal because that's going to cause it to stay in one spot you can mess with stiffness settings aerodynamics self-collision there is a 
[31:09](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1869) lot of good stuff in here as we play it you can see that it bounces beautifully in fact this is how you make jello tetris have you ever seen that video here i'll i'll do it real fast i'll add 
[31:20](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1880) another one this is how you make jello tetris now just add a whole bunch more of them and a really powerful pc and you'll be working with something 
[31:30](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1890) pretty fast so thank you so much for watching this has been how to make jello tetris how to turn a zebra into a giraffe and how to not lose your mind while making blender tutorials at 2 am 
[31:42](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1902) if my energy varied throughout the video i'm very sorry for that they do take quite a while to film and now i've got an editing session but uh it's all worth it because i know that somewhere out 
[31:52](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1912) there is someone who's gonna benefit from this information if you learn something new a like and subscribe is always appreciated helps me keep these videos running i don't really have 
[32:00](https://www.youtube.com/watch?v=8BQYAwDW6IE&t=1920) anything else to say besides i hope you all are staying safe with that being said my name is daniel craft i hope you have an excellent day and happy blending you 