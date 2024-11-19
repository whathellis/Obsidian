---
URL: https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7
thumbnail: https://i.ytimg.com/vi/hpamCaVrbTk/default.jpg
channel: "[[Joey Carlino]]"
date: 2024-07-25
published: 2021-04-03T02:00:18
duration: 1231
tags:
  - video/3D/texture/node
done: true
cover: "[[Pasted image 20240716161910.jpg]]"
---
[time:: "20m 31s"]
# Turn Anything Into A Painting with Shader Nodes || Blender 2.92
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716161910.jpg]]
````
````col-md
flexGrow=1
===
<iframe src="https://www.youtube.com/embed/hpamCaVrbTk?list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: ⚠️ There will soon be an easier way to do this with the real-time compositor. Watch this to learn more: [[../../Inspo/The new ways of Blender|The new ways of Blender]] )
```NiftyLinks
url: https://youtu.be/K-L2eIHu7ic
title: The new ways of Blender
description: Blender updates and features are changed or added pretty often. Not only that, I just find better ways of doing things, so this video will talk about new way...
favicon: https://www.youtube.com/s/desktop/a39b93b0/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/K-L2eIHu7ic/maxresdefault.jpg
```

Also, Alan Wyatt has made a much more realistic paint filter:
https://gumroad.com/a/20930003
https://youtu.be/6uaJ0L4E390?si=6MX6fqi10nD9Thzu

Patreon, Gumroad Shop, Discord, and other stuff:
https://linktr.ee/Joeycarlino
 
Watch this video to learn more about distortion: [[../../3D/New/Turn Anything Into ASCII Art with Shader Nodes  Blender 2.92|Turn Anything Into ASCII Art with Shader Nodes  Blender 2.92]]
```NiftyLinks
url: https://youtu.be/9R_JBq3Hm6E
title: Turn Anything Into ASCII Art with Shader Nodes || Blender 2.92
description: ⚠️ There is another way to do this with geometry nodes! Watch this to learn more: https://youtu.be/K-L2eIHu7icGet it on Gumroad: https://joeycarlino.gumroad....
favicon: https://www.youtube.com/s/desktop/a39b93b0/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/9R_JBq3Hm6E/maxresdefault.jpg
```


Intro sounds by Samaquias Lorta:
https://www.samaquiaslorta.com/

Timestamps:
Intro 0:00
Scene Setup 0:37
Mosaic 1:29
Adding Variety 3:36
Masking Our Textures 5:42
Distortion 7:29
On/Off Switch 10:39
UV Coordinates 11:15
Random Seed 13:17
Bump Map 14:39
Masking The Strength 17:06
Outro 20:05

🔗Links
2nd YouTube Channel: https://www.youtube.com/@JoeyC-quel
Patreon: https://www.patreon.com/joeycarlino
Discord Server: https://discord.gg/dvmAZdwf5e
Gumroad Shop: https://gumroad.com/joeycarlino?a=844339507
Blender Market Shop: https://blendermarket.com/creators/joeycarlino
Second Channel: https://www.youtube.com/@JoeyC-quel
TikTok: https://www.tiktok.com/@joey_carlino
Instagram: https://www.instagram.com/robospunk/
Twitter: https://twitter.com/joey_carlino
Personal Email: JoeyCarlino@gmail.com
Busniness Email: JoeyCarlino@makrwatch.com

💰Support me by checking out these affiliate links:
https://linktr.ee/joeycarlinoaffiliate

🧠Things I Recommend (not affiliated)
Blender Launcher: https://github.com/Victor-IX/Blender-Launcher-V2
Blender Beginner Playlist: https://youtube.com/playlist?list=PLa1F2ddGya_-UvuAqHAksYnB0qL9yWDO6

🫂Places To Donate:
https://www.nrdc.org/
https://wck.org/
https://blacklivesmatters.carrd.co/
https://www.catf.us/
https://www.evergreenaction.com/
https://350.org/
https://www.conservationfund.org/
https://www.nature.org/en-us/
https://communitychangeaction.org/
https://www.aclu.org/
https://www.wri.org/
https://www.edf.org/

⚙️What's On My Desk?
GPU: EVGA GeForce RTX 2070 SUPER
CPU: AMD Ryzen 9 3900X
Motherboard: Asus PRIME X570-PRO
Memory: Team T-FORCE VULCAN Z 64 GB (2 x 32 GB) DDR4-3200
Monitor: LG 25UM58-P 25.0" 2560x1080 60 Hz
Drawing Tablet: XP-PEN Artist 15.6Pro
Mouse: Logitec MX Master 3s
Keyboard: Redragon K580 VATA
Speakers: Mackie CR3-X
Headphones: Beyerdynamic DT 700 Pro X
Microphone: Beyerdynamic M70 Pro X
Audio Interface: Universal Audio Volt 2
# Transcript
[00:06](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=6) hey everyone i'm back with another viewport compositing video so this time we'll be in the shader editor and not the compositor this time i'm making a filter to turn 
[00:14](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=14) your images videos and textures into paintings compared to the last video this one's going to be way more simple and as usual you can grab this on gumroad if you 
[00:21](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=21) don't want to build it yourself it's set up in a way that makes it easy to use and adjust i have some other stuff over there too like the ascii art generator that i made last video 
[00:29](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=29) the glitch effect lightning models as well as some free stuff and if you need extra help or anything check out the discord server links are always in the description 
[00:36](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=36) all right let's get started alright so for this one i'm in blender 2.92 um first thing i'm going to do is get our camera set up so i'm just gonna select our camera hit alt g and r 
[00:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=48) and drag it up slightly and i'm dragging it up slightly because we're going to add in a plane and then you just want to look through your camera and make sure that the plane 
[00:58](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=58) is filling the screen so instead of scaling the plane up i'm just gonna select the camera and move it down like that so it's filling our frame and if you have any lights you can leave 
[01:09](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=69) them there or get rid of them it doesn't really matter so now we're just going into the shader editor now that we're in here you just want to 
[01:15](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=75) make sure you're either in render view or look dev i'm staying in look dev for this one and i guess it's also worth noting that i'm using 
[01:22](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=82) the node wrangler so if you go to edit preferences add-ons you just have to check off node wrangler all right so select your plane add a new material oh 
[01:32](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=92) yeah anime and eevee i'm using eevee for this one so i'm just gonna look through the camera right here and first thing we're gonna do is we're going to bring in 
[01:40](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=100) the image that we want to use so i'm going to bring in the image texture and just plug that in you can use a video for this also so i'm 
[01:50](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=110) going to use a video this is the one i'm using oh yeah and if you're using a video you just want to make sure that you put the amount of frames your 
[01:58](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=118) video has right here and then also and also make sure uh cyclic and auto refresh are checked so then when you play it this will play 
[02:06](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=126) and to make this not all stretched out you can bring in a texture coordinate and just plug in the window and this should work fine as long as 
[02:17](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=137) you have the same resolution here that your video is if it looks stretched or anything you're just going to have to adjust these to match your video or your image or 
[02:27](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=147) whatever all right so most of the work we're going to be doing is actually going to be between our texture coordinate and our image 
[02:35](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=155) so i'm just going to drag this back right here and the first thing i'm going to add in is a voronoi texture and you can just pop that right here and 
[02:44](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=164) plug in the position to the vector and right now it looks like just like a colorful mosaic but if you turn the scale up you'll see it's actually displaying our 
[02:56](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=176) image just kind of pixelated and i'm going to bring this down again you can see we have these weird jagged lines to fix that you're just going to want to 
[03:04](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=184) change this from linear to closest and that should clear up and also instead of setting this to repeat instead of setting this to repeat i'm going to change this to extend 
[03:15](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=195) that way if anything peaks over the edge it's just the same color it basically just takes the edge pixels and just stretches them out so if you want to leave it like this and 
[03:24](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=204) just have it looking like a mosaic that's fine but i want to make this a little more complex so i'm actually going to be using 
[03:30](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=210) three different voronoi textures with different resolutions and mixing them together i'll show you how to do that first i'm going to shift and right click and drag to create 
[03:40](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=220) this reroute node and i'm just going to create three of these like this and i'm going to set the first one to 
[03:50](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=230) basically the the biggest resolution that we want so i'm going to set this to 10 for now and i'm actually going to bring in a value node right 
[04:00](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=240) here and change this to 10 this is going to be our first one you can plug that into the scale all right and to mix these together i'm going to bring in 
[04:09](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=249) a mix rgb like this you can plug the position into the second color right there and then you want to create a second one plug the mix 
[04:21](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=261) into the first color and the position right here into the second color like that and then you can put this color into the vector and now these are 
[04:30](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=270) mixed together and if we just bring it back like this it'll show only the first one the way you can think of this is if this is zero it's using the first color 
[04:41](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=281) if you set this to one it's using the second color so right now this one is saying use the first color which is pointing to this mix shader so this is our first color right here our 
[04:51](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=291) second color i'm going to use a math node for this and i'm just going to set this to multiply and the bottom one to two 
[05:01](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=301) and plug the value into the first value right here so now this is just taking our base value and multiplying it by two we're going to plug that in here 
[05:12](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=312) and we can take a look by moving this over here so this is our second resolution and i'm going to take this again and once again do the same thing 
[05:25](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=325) so now it's taking this value and multiplying it by two again so it's just getting more and more detailed like that so we have three levels 
[05:34](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=334) and when we change this um all of these will change because they're all based on the same value just multiplied in different amounts so right now this isn't really doing a 
[05:44](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=344) whole lot if we put these like halfway it's kind of mixing but it doesn't really make a whole lot of sense what i'm going to do is i'm going to use these like their masks and put plug 
[05:54](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=354) textures into here into the factors so to do that i'm going to bring in a noise texture right here and just make sure you plug the vector in 
[06:05](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=365) and this is what our noise texture looks like i'm just going to turn the detail all the way down and what you can do is plug that into the factor right here and take a look and this is hard to tell 
[06:15](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=375) what's going on so just to clear up what's happening i'm going to use a math node just put it right here and change that to greater than so now 
[06:23](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=383) this is like a hard fall off it's just on and off right there so now if we check this out you can see in here it's using our like bigger 
[06:32](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=392) texture and in here it's using the smaller one like that but i don't want to make more than one noise texture really we don't need more than one to make a mask 
[06:41](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=401) but i want the mask for both of these to be different and a way you can do that without making multiple noise textures because that just 
[06:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=408) the more textures you add the slower it gets basically what we can do is add a separate rgb and instead of using the factor we can use the color plug that into here 
[06:59](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=419) and that will give us three slightly different noise textures to choose from so we can just plug the red right here into the factor and the green 
[07:09](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=429) into the second one and then we can check it out so now we have it so that parts of our painting right here are using this one parts are using this 
[07:20](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=440) one and parts are using that and they're it's not all just overlaid but you can see it looks pretty angular still and so to fix that i'm going to distort everything right 
[07:32](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=452) here and i'm not going to explain this super in depth i have another tutorial where i go through distorting and you can check that out i'll link it in the 
[07:41](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=461) description and also put a little pop-up over here so to do this i'm going to add a noise texture right here when i plug it in you can see 
[07:49](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=469) it'll immediately get really messed up and i'm also going to bring in a vector math node right here and i'm just going to plug the noise texture into the first 
[07:59](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=479) one the second one and in the first one i'm going to put our vector right there and then i'm going to add a few more um 
[08:08](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=488) math notes so oh yeah and also the the factor should be going in here we're not using the color so this i'm going to change to subtract by 0.5 
[08:20](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=500) and then the one after it is going to be multiply and this is basically controlling the strength of our distortion so if we set this to zero 
[08:29](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=509) this goes back to normal i'm going to turn this up a little higher maybe 20 so we can see a little more clearly so when this is set to zero we're not going to get any distortion and when we 
[08:37](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=517) bring it up it'll start to distort you can see that so i'll set this to something like 0.2 for now and just mess with the scale until we get something we like 
[08:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=528) resolution is set to 20 right now so let's just see what 20 looks like one for one i'm also going to turn the roughness up to 0.8 
[08:58](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=538) and the detail to something like five we can see that's already starting to break it up so you can mess with the distortion if you want with this value right here 
[09:07](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=547) i'll set it to 0.1 looks all right i think point one is better i'm also going to turn the distortion up to one so we get some swirlies right there 
[09:18](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=558) i think that looks neat maybe 0.5 i don't want to be too drastic also if this gizmo is bothering you at any time you can just shut them off right here with the 
[09:28](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=568) overlays and give gizmo button basically what we want to do is when the resolution gets lower we want this to get higher and when the resolution gets higher we want this to get lower 
[09:41](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=581) and to do that we're just going to bring in a math node right here change this to divide bring our value right here our resolution and put that on the bottom and right now 
[09:52](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=592) this is 0.1 and we want to leave it at that so i know that 2 divided by 20 should give us the same value but you can just 
[10:01](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=601) tweak this until you get something that you like so when i plug it in you can see that's the same and if you want it to be like more or less you can just 
[10:10](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=610) you know change this value so if you want it to just always look more distorted that's what this value will do um and now when we make this really low it distorts more and when we make it 
[10:23](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=623) high eventually it'll just start looking clear like that and i like keeping it attached that way you don't have to constantly like 
[10:30](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=630) oh you make it higher resolution and then you have to adjust this you make it lower and then you have to adjust this you just have one control for everything and i like how 
[10:38](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=638) it's simple to control one other thing you can do to change like the overall strength of the effect is bring another mix node in here just right there 
[10:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=648) and plug this into the second come over here and grab our vector and just plug that into the top the first color and now you can see when 
[10:59](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=659) this is zero it's just off it's not using the effect and when we put this to one it's using the effect so anywhere in between is just going to be 
[11:08](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=668) just a partial effect and i think it's nice to have just like an overall on off switch like that if we try to look at this from a different angle it doesn't work 
[11:18](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=678) right this is because we're using the window vector and that's how it works it'll just be the same shape as the window you're 
[11:27](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=687) looking through so if you do want to look at this from different angles like if you're creating a painting or something that you want to put on a wall and 
[11:34](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=694) render something like that so you can use the uv texture coordinate for this if you want and that'll allow you to look from a different angle 
[11:42](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=702) you can see this stretched this is supposed to be 1920x1080 which is a 16x9 aspect ratio so if you know the resolution of the image an easy way to get it to be the right 
[11:56](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=716) shape first of all you can use the images as plains add-on everybody um really likes using that it's built in so you can just turn that on 
[12:04](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=724) under preferences and add-ons but if you don't want to use that if you just want to use a plane and put your image on it and have it be shaped right you just want to select 
[12:13](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=733) your plane right here and once again we have our overlays off so if you shut those off make sure you turn them on so you can see what you want to do is change the scale 
[12:22](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=742) right here we want to make this smaller so if you know your aspect ratio and mine is 1920x1080 i can just do 1080 divided by 1920 right here and now it'll be 
[12:36](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=756) shaped right and the reason i know to use those numbers in that order is because i want this to be a smaller number like that and to get a smaller number you want to 
[12:46](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=766) put your smaller number first when you're doing the division so you can see the smaller numbers first if you wanted to 
[12:55](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=775) change like this value instead you would put the big number on top so 1920 divided by 1080 like that but i like putting it here so that when you 
[13:06](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=786) look through your camera it's still pretty close to the window texture coordinate there is a slight difference but they're pretty close oh yeah and 
[13:14](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=794) this also works animated so yeah you can change your paint effect by just tweaking these values here if you want it to be like more um like 
[13:23](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=803) soft and smooth you can turn the detail down like that so now it looks wet or if you turn it up really high with the roughness 
[13:32](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=812) it'll look more dry and if you change this to 4d you can also change the seed if you're trying to make this look like it's an animated painting 
[13:42](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=822) that's not just through a filter you could take your seed right here and just type in hash and then frame and hit enter and that'll just make it match the frame 
[13:51](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=831) you're on so this will just jitter now if you're gonna do this i recommend you change all of these to be 4d textures also 
[14:00](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=840) and just use the same value for all of them so let's just delete the driver here and type in hash frame for 
[14:10](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=850) this value right here and we can just plug this into all of the w fields like that so now all of them will be 
[14:20](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=860) animated you know if you don't want to animate this if you just want to change the seeds of all of them just to get a different result you can do that also and you can see right now 
[14:29](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=869) we're just plugging this uh directly into the surface like that and that's the equivalent of using an emission shader but if you want you can also 
[14:37](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=877) plug this into like if you wanted to you know actually catch light like a real painting would you can plug this into something else like a principled bsdf you would 
[14:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=888) just want to plug it into the color like that but you can see it's perfectly smooth so if you want to add some bump you can add in a bump node plug it into the normal 
[14:59](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=899) right there and when we have multiple textures it might start taking a while to compile so i said this one is more simple than the last one it's more simple to 
[15:08](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=908) set up there's less math and fewer steps but it is a little more intensive on your computer so keep that in mind for the bump i'm just going to plug in 
[15:17](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=917) the factor of our noise texture over here so you can just take that factor and plug it in right there into the height and then i like to take 
[15:26](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=926) the strength and distance and just set them to 0.1 and if you don't like how strong this is you can just turn these down so i'll set this to like .05 or something like that 
[15:39](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=939) right now i'm just using the point light i'll just press um alt g to clear the location if you're in look dev right here you might just wanna click this arrow 
[15:47](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=947) right here and turn on uh scene world and scene lights for this one i'm just gonna shut off all the world lighting so you can see just with the light and i'm gonna take 
[15:57](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=957) our light and just drag it up right here like that now you can see some bump and if you want this to look more sharp i'd recommend using 
[16:07](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=967) a sun just change that to something lower and you just want to change the angle to something close to 90 degrees but not quite so this one i have is set to like 
[16:20](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=980) negative 80 like that you want to turn the angle down to zero and that'll give you like a really hard shadow and then you just want to turn the 
[16:28](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=988) strength up until it looks good to you and that'll let you see a lot of the detail so i just turn this up to something like maybe 20. seems all right and now when 
[16:38](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=998) we render it might take a second for all of the shaders to compile this is what we're left with you're actually getting some of the bump 
[16:45](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1005) which is kind of nice and if you want you can you know change the bump up a little if you were going to change it you could use something like a color 
[16:53](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1013) ramp something like that so i'll grab a color ramp in here to make parts of it look flat and other parts look smooth change this to 
[17:01](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1021) b spline pull this a little closer and i think that'll look all right oh yeah one other thing you can do if you want certain parts to be clear and other parts to be 
[17:11](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1031) not clear that's where this comes in handy right here you can use this like a mask also you can bring in another texture coordinate and this time we're going to be using 
[17:20](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1040) the object texture coordinate so for that i'm just going to set up an object that i want to use and i'm going to use an empty i'm just going to use a sphere 
[17:30](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1050) right here and i just gotta turn on my overlays and gizmos so we can see it and then i'm gonna come into the transforms i'm just gonna lock this on the z-axis that way um i can't move 
[17:40](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1060) it and i can only move it around like that you can see right here it went away so you want to click on your painting 
[17:48](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1068) and if you use this little push pin right here it'll make it so that this window this material always stays on even if i select the empty so i'm going 
[17:58](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1078) to select right here where it says object select the empty and then we can plug the object into here so in between here i'm going to bring in 
[18:08](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1088) a vector math node and i'm going to change this to length i want to make sure that's plugged into the factor and i'm also going to clamp this 
[18:16](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1096) so no values go over one or below zero and now this should be working so now when we scale this down and move it around you can see that the center of this is 
[18:26](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1106) going to be clear so if i want the face to be clear i can put it over the face if i want outside the window to be clear you can put it over there and if you 
[18:37](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1117) want to change like how how clear it gets or the fall off or anything like that i'd use a map range node um you could also use uh like a color 
[18:46](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1126) ramp or something like that but i like using the map range because you can actually set the values right here if you change the zero to be closer to 
[18:54](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1134) one that'll make the edge harder so if i set this to like point nine you'll see it's like a really hard edge and if we look at this you can actually see what's going 
[19:03](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1143) on like that and if you change the zero that's how clear it is so one is completely distorted zero is not distorted at all 
[19:13](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1153) so if you want it to be still looking like a painting you can change this to something like point two or something like that and so in the circle we'll there will 
[19:22](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1162) still be like a kind of paint effect just not that much not as much as everything outside um and this can come in 
[19:30](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1170) handy especially if you're just trying to like have a focal point so if i want the face to be clear i can change this to something like point five or something like that and you can 
[19:40](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1180) turn the um the value down like pretty low so something like i don't know five something like that and then you can just adjust 
[19:49](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1189) how distorted you want it to be like that and also change this to back to zero and make it bigger our face is more clear and has more detail than everything else over here 
[20:02](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1202) because it's just not being distorted as much and yeah this can work for you know any other videos or images or you know if you want even if you want to use photographs you can use it for that 
[20:13](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1213) too do something like this make it look like it's like an actual animated painting all right and that's it for this one once again you can grab this node setup 
[20:21](https://www.youtube.com/watch?v=hpamCaVrbTk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=7&t=1221) on gumroad if you don't want to make it thanks for watching have a good one 