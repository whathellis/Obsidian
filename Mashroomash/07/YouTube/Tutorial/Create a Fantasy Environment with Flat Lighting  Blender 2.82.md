---
URL: https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19
thumbnail: https://i.ytimg.com/vi/z-tI-WqeqKk/default.jpg
channel: "[[Joey Carlino]]"
date: 2024-07-16T16:27:33
published: 2020-03-25T09:08:42
duration: 1553
tags:
  - video/3D/tutorial
done: false
cover: "[[Pasted image 20240716162755.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "25m 53s"]
# Create a Fantasy Environment with Flat Lighting || Blender 2.82
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716162755.jpg]]
````
````col-md
flexGrow=1
===
<iframe src="https://www.youtube.com/embed/z-tI-WqeqKk?list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: This shader works in both Eevee and Cycles.)

Patreon, Gumroad, Discord, and other stuff:
https://linktr.ee/Joeycarlino

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
[00:03](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=3) hey everyone I made this a few days ago and people have been asking how I did it so that's what I'm gonna show you today basically things in this scene are changing color based on how far away 
[00:12](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=12) from the camera they are okay so here we are in blender 2.8 - I believe just have a basic scene setup right here and we're gonna be using Eevee today I'm gonna get rid of this cube for now and it'll lay a 
[00:26](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=26) plane down I'm going to scale it by 50 and then I'm going to apply the scale and then we're gonna go into the shading tab up here and I'm going to select our plane make sure that's selected and then 
[00:44](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=44) select the material over here and delete this principle B SDF we're going to work on the shader first so I'm going to add an emission look that in here ctrl T on here if you have the node Wrangler 
[00:59](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=59) that'll add texture coordinate and mapping it's going to delete this image add a separate XYZ plug the X into the color of the emission right now I'm going to change the texture coordinate 
[01:16](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=76) to object we're gonna set the object to camera so now the texture of the plane right now is going to follow a camera that's that's what that means when you select that so if we switch into 
[01:31](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=91) rendered view right now this is what it looks like and it might not be very clear what's going on yet we have to rotate on the y-axis negative 90 and now when we move our camera we can see that 
[01:47](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=107) the texture should follow it and right now this is a glow now and there's a lot of bloom going on usually white is a value of 1 but when you're in the filmic color mode values over 1 will actually 
[02:03](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=123) make it brighter and so that's what's happening especially with us being in a mission shader so if we clamp that I'm just gonna Pat mix RGB into here and make sure that the X is plugged into 
[02:16](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=136) the factor and I'm going to change the top one to black it's going to look just like before basically except when we clamp it we we shouldn't get all that bloom going on another thing I'm going 
[02:29](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=149) to do is change the world lighting over here I'm just going to turn that all the way down and I'm going to get rid of this light because we won't really be needing it since we're mainly dealing 
[02:41](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=161) with emission shaders okay and so I'm just gonna add a cube back in we're gonna use this for reference right now make sure you add that material to the cube as well and I'm just gonna switch 
[02:54](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=174) into layout mode for a second and add an array modifier just so we have a bunch of cubes going on 25 should be good for now you know switch back into shading press 0 to go and to look through the 
[03:14](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=194) camera make sure your camera selected and I'm just gonna pull it to the side okay so now we can see all these cubes and right now they all look the same color and there's no lighting on any of 
[03:28](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=208) them they're all flat because it's using the emission shader and what I want is like a more gradual like dark in the front and moving to light in the back so I'm just gonna select the cube and the 
[03:42](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=222) way we do that is by affecting the scale and what you can do is just make this smaller but it's hard to adjust it because the numbers have to be pretty small so what I like to do is add a math 
[03:54](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=234) node and change this to divide and change the top value to one and what's going on is one is just being divided by whatever number is on the bottom so really you can just keep turning this up 
[04:07](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=247) and it's never technically going to reach zero it just gets closer and closer to zero and it's just a little easier to control it so as you can see when we turn this up the front is 
[04:16](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=256) getting darker and it's becoming a little more gradual if you look at it from the top it's a little more apparent the gradient is literally just extending there's just scaling up really 
[04:27](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=267) so I'm just gonna set this to 100 okay and to achieve the rainbow look what we do is take this mix RGB and replace it with a color lamp plug it in here and change this from RGB to HSL and select 
[04:46](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=286) the first color I'm just going to turn the scale of the saturation and the value all the way up going to hover over here press ctrl C to copy that and go to the next flag and paste that we're going 
[04:59](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=299) to change this right here from near to far and what this means is it's looking at the two hues and saying take like the far the farthest route to get from one to the other let me explain this by 
[05:14](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=314) changing the second color to this like purple over here so what's happening is the first one is here and the second one is here and it's saying go all the way around this way to get to the other flag 
[05:28](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=328) if we set this to near instead it's going from here to here it's taking the shorter route instead of it just being red to red it goes all the way around to go back to 
[05:39](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=339) the same point and that's why we get this full spectrum and if you want the gradient to start in a different place relative to the camera you can just change the location up here okay next 
[05:50](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=350) I'm just going to take this plane press free to go into side view I'm just going to move that down pretty far rotate it on the X 90 degrees I'm going to look through the camera looks like we need to 
[06:07](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=367) change our camera settings click on your camera and change the clip end value to a thousand for now that should be fine and so now we can see that plane out there it was cutting it off before we 
[06:19](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=379) just select that and scale it up a little bit so it's a covering our frame and now when we go into render view you can see that far away everything is red so that when we move the camera so that 
[06:36](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=396) when we move the camera the stuff that's far away just fades into the background and because the shader location is tied to the camera when we move it it follows and so I'm just gonna tweak these 
[06:47](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=407) settings a little to make this location back to zero and I'm going to have this be 1/100 and now that we're done with the shader we can move on to building our scene so 
[06:57](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=417) I'm going to switch back into layout mode over here I'm just gonna delete these cubes and I'm gonna make sure that our camera is in the very center just reset the rotation and location I'm 
[07:12](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=432) going to rotate it not nd on the X okay so first thing we're gonna do here is add a plane I'm just going to scale this by 30 and then I'm going to apply the scale go into edit mode and subdivide 
[07:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=445) this a little say 25 times that should be good I'm going to come in here and add a displacement modifier I'm going to add a new texture and I'm going to set this to clouds and basically we're just 
[07:40](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=460) going to make the start surface slightly uneven and before I edit any of these settings I'm just gonna add an array modifier also and I'm going to change this from relative offset constant and 
[07:52](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=472) I'm going to put this 50 on the Y normally I would have this value set to 60 so they meet up exactly but as you can see there's are some gaps because of the modifier stack if we put the array 
[08:05](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=485) at the top of this wouldn't happen but it's easier to loop if the array is after basically of saying just place this plane and then repeat it rather than repeating it and then just placing 
[08:15](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=495) all of them so instead of 60 I'm just going to set this to 50 so they overlap slightly and we don't get the gap right here I'm just going to set this to 5 so it goes a little further and make sure 
[08:27](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=507) that we have the material for this plane set to the material that we made so we switch into render view we can see that it's applied right there and if we move our camera up just a little and then 
[08:43](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=523) preview it we can affect the displacement amount and you can see it makes our terrain just a little honey then I'm actually just going to leave this at the default right now I 
[08:57](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=537) think that's good enough for what we're making I'm just going to shut this array off for now and I'm actually going to apply the displacement cuz we're done with that next I'm going to make these 
[09:07](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=547) uh kind of blobby Bush looking things so to do that we're going to add an eco sphere I'm just going to set that to four okay and then I'm going to add a displacement modifier and I'm gonna use 
[09:22](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=562) the first texture we made but I'm gonna go into the settings and change that from clouds to lure annoy and right now this is going the opposite way we want so I'm going to come in two colors click 
[09:35](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=575) the color ramp option and I'm just going to flip the color room and I'm gonna control two on the ICO sphere to add a subdivision surface modifier I'm gonna come into the modifier stack and move it 
[09:50](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=590) to the top that way we get a little more detail I'm going to go back into our displacement settings and change the size of this up a little maybe around 0.5 that looks good and under the 
[10:06](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=606) modifier settings I'm going to change this from local to global when it's set to local you can move it around and the texture won't move the displacement texture but when you set it to global 
[10:21](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=621) it's tied to the global settings which is like the center of the world so when you move it it deforms like that and that I actually want that because I'm gonna duplicate this a few times so I'm 
[10:32](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=632) just gonna shift D on here and move it to the side on the x-axis I'm going to duplicate it one more time just so we have three total and this first one right here I'm going to apply at all 
[10:48](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=648) that's our first one and our second one I'm just going to change it slightly going to change the size of the displacement just to make it look a little different we want some variety so 
[11:02](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=662) point six five should be fine for this I'm going to apply all on that one and this one here I'm going to again move the texture size up slightly and if you want this to be smoother you can 
[11:19](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=679) change this from linear to ease so I'm gonna do that for this last one the other ones are fine and I'm gonna come back into the modifier settings and just push this out a little like that and I'm 
[11:33](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=693) going to fly off now select all of these add a decimate I'm just gonna turn these down a little what we're looking for here when we decimate it is that it maintains a good silhouette when you 
[11:48](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=708) look through the camera with this when the shader is applied all you're seeing is the silhouette you're not seeing any of the lighting touching it so that's important for this and you can collapse 
[11:57](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=717) it pretty far to the point where it's really low poly and it'll still look good so I think that's all right I'm just going to ctrl L to link all of the modifiers so now all of them are 
[12:13](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=733) being decimated I'm just going to apply that and on all of them so all of them should be applied now and I also want to make sure that these are using the right material here and I'm also going to link 
[12:33](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=753) that materials so now we can see it's basically just a silhouette at this point and they still look fine even though they're very low poly okay next I'm going to take all three of these 
[12:44](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=764) press em to move them to a new collection I already have one that's just called collection by default and there's nothing in it except for these three 
[12:53](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=773) I chose spheres I'm just gonna move these off to the side so I'm going to select our plane and go into the particle properties over here and add a new particle system change that to hair 
[13:04](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=784) click advanced and I'm just gonna change this to 104 now we might change that later the source is okay being set to faces okay next we go to render settings here and render as collection and then 
[13:19](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=799) just select the collection that has the ICO fears in them and so if we sent this to one you would think that they would be the same size in there but because by 
[13:29](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=809) default the hair length is set to four there are actually four times the size they should be so if you want them to be the same size you just change this to one and so now these if you have the 
[13:41](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=821) scale set to one over here and the hair lengths that's a one they should match but I'm actually gonna make this bigger I'm gonna make this three because I want some of them to be large and I want some 
[13:49](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=829) of them to be small so I'm just gonna add some randomness I'm going to change this to 0.7 and then I'm going to go into rotate rotation change this to normal randomize I'm gonna turn it all 
[14:02](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=842) the way up phase I'm gonna turn all the way up and then phase randomized phase I'm gonna settle one so now all of these should be rotated and pretty random directions and right now these bushes 
[14:14](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=854) are covering our camera so what I'm gonna do is select the plane and tab into edit mode switch to the top view I'm just going to select the first few edges down down the center right there 
[14:30](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=870) and I'm going to ctrl I to invert that selection come into object data properties over here and add a vertex group and assign it to the first group that you made okay and then what the 
[14:44](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=884) planes still selected go back into your particle settings and go to vertex groups for density use that group that you just made and so that should mostly avoid things being in the center and you 
[14:58](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=898) can mess with your your numbers and your your seat up here until it looks good to you I think a hundred is fine for what we're going for here and now that we're done with these make sure you have your 
[15:09](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=909) plane selected go into modifiers and convert your particle settings right here and that will turn all these particles into separate objects and then go into your particle settings over here 
[15:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=925) and just get rid of that particle system and with all of these still selected you can select your plane here and press ctrl J and this will turn all of them into one object so now 
[15:37](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=937) the bushes are part of the plan if we've happen to edit we can see that it lets us edit everything over here which means that if we turn our array modifier back on this should still continue looping 
[15:48](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=948) right here and it looks like it placed one of those in the very center so I'm just going to deselect everything in edit mode and press L on the one that's in the center I'm just going to delete 
[15:59](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=959) that okay so next I'm going to animate the camera I'm just going to go into a rendered mode here press 0 and make sure that your camera is selected and that it's as high as you want it and if you 
[16:14](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=974) want it higher or lower just press the Z G sorry press G and then Z and move it up and down on the z axis and I think it's good where we had it then press n to open up 
[16:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=985) the side panel make sure you're on frame 0 I to insert a keyframe in the location and then move to frame 250 over here move this 50 on the Y because that's how far apart our planes are and we wanted 
[16:40](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1000) to loop seamlessly so I'm going to insert a keyframe there also and what with both of these keyframes selected Krusty and change the interpolation to linear and so now if we look through our 
[16:53](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1013) camera and rendered view this should loop seamlessly and it does so moving on next we're going to work on the stalactite looking things right here and next I'm going to add a plane right here 
[17:12](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1032) and I'm going to scale that up times 30 just like our other one before then I'm going to apply the scale I'm going to pull it up you can see it a little better tab into edit mode and I'm going 
[17:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1045) to subdivide this a few times gonna change move this up to 50 okay and then we're going to add a displacement modifier and we can use the one that we made last time for now I'm going to turn 
[17:38](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1058) the strength up a little higher so we can see it a little better I'm going to come into the texture properties over here and I'm going to turn 
[17:47](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1067) sighs up a little higher and see how that looks and I'm also going to I think the color ramp is still on just going to turn that off okay and we're just gonna mess with this until it's a size that we 
[17:58](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1078) enjoy I think maybe five and might be good and and I can go back into modifiers and affect the strength so we can view this properly I'm going to add an array modifier and set it to the same 
[18:13](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1093) values as another one which was a fifty apart on the Y I'm just gonna make five of these so when we look through our camera we can see it change it into render view and make sure that you have 
[18:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1105) the material set correctly to that one material that we keep using I'm just gonna move this down on the Z until it's in a spot that we like and it's okay to move it pretty loved it seems pretty 
[18:40](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1120) good so back into a solid View mode I'm gonna get rid of that array modifier and I'm gonna apply this and then I'm going to select the stalactites and then select our lower plane and ctrl J and 
[18:56](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1136) now both of these are part of the same object once again next we're going to work on these little floaty things right here so to do that first we're going to add a plane and I'm going to size that 
[19:09](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1149) up the same size as the other one which was scaling up by 30 and then I'm going to apply the scale and move it down a little tab into edit mode and subdivide that so the way we're doing this each of 
[19:27](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1167) vertex is going to have a little ball on it so when you subdivide it pay attention to how far apart the vertices are I think I'm going to set this to 25 okay tap out of edit mode next I'm going 
[19:38](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1178) to add in I Coast fear and I'm gonna turn the subdivisions all the way down it's okay to be pretty low poly bring that down a little and I'm gonna parent it to this plane right here and then 
[19:55](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1195) select the plane come into object properties and scroll to instancing and press verts so what this is doing is taking anything that's parented to this plane and placing one 
[20:07](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1207) of those objects on each of them furnaces if you select the ICO sphere you can scale that to however big you want it and I'm gonna make that pretty small I should be okay and also it's 
[20:21](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1221) important to have this render instance or checked off that way when we render it you don't see this playing well we see the instances next we're going to add a displacement modifier here and I'm 
[20:36](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1236) going to set that to the texture that we keep using but I'm gonna change that from Voronoi to clouds and then turn this up pretty high I think I'm going to turn it to ten for now and I'm gonna 
[20:48](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1248) make sure that the displacement is working on the Z and I'm gonna make the strength pretty high I'm just gonna bring that up so the little floaties are in our scene so if we look through the 
[21:02](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1262) camera we'll be able to see it a little better gonna press G and then Z to move it up and remember that the plane isn't going to be rendered so I think that's high enough and I'm going to change the 
[21:17](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1277) texture coordinates to object I'm going to set that to the camera and so now the displacement texture is bound to our camera and just like our material and so when the camera moves the displacement 
[21:30](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1290) texture moves like that since this plane is where we want it I'm gonna come back into the object properties and I'm going to click this display instance that way we don't see the plane and I want our 
[21:42](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1302) little floaties to move more than just up and down the way they are right now so I'm going to copy this and I'm also going to make it move on the X and that will make these move side to side like 
[21:56](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1316) this and then when we have both of them going to move up and down in side to side which gives them a little more of a random movement and then I'm going to add an array modifier and make sure that 
[22:09](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1329) this is set to the same amount as our plane before which was 50 on why and I'm just gonna set this to five alsa and then we're going to select that ecosphere 
[22:20](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1340) it was in here and make sure that that has the right material on it and so now if we look through our camera this is the scene that we're left with and I think the displacement is a little too 
[22:33](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1353) strong what I'm going to do is select our plane over here come into the displacement settings over here and I think I'm gonna change the size of this up a little higher I think 25 is good 
[22:44](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1364) it's now these are moving a little slower the only thing that we forgot to do to make this loop properly we want to move the array modifier to the very top and 
[22:54](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1374) so now they should loop properly so the only thing left now are some finishing touches we can come back over to shading I'm just going to look through the camera over here for reference and I'm 
[23:07](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1387) just going to affect the scale and the location until it's in a place that I want I think I'm just gonna move the location back a little because I want the foreground in the background to be 
[23:19](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1399) to match pretty closely I think that's a good setting I like the way that looks so I think this is a pretty interesting technique and you can do quite a few things with it if you just wanted it to 
[23:40](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1420) be two colors you can use the mix RGB I'll plug that in just so you can see when you have it this way the scene just looks kind of misty but if you flip it around it's a little more like going 
[23:54](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1434) into darkness instead of going into the darkness you could have this be a different color like that it gives it a really interesting stylized look especially because everything is flat 
[24:04](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1444) like this but if you don't want it to look flat you could instead use this texture to drive a mix shader' for example you could plug this into here you can actually just plug the X 
[24:16](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1456) directly into the factor and then we can plug the emission down below I believe and principle psdf up top and make sure that we plug the mix shader' into the surface right here so now 
[24:29](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1469) things in the foreground are using this principle D SDF and things in the background are using the emission so we could change this to like whatever color we want and as long as we have some 
[24:41](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1481) lighting in the scene I'll change the world lighting back up to one we can see that there is some reflection and things like that this is an easy way to add mist into your scene without using 
[24:54](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1494) volumetrics it seems a little more lightweight or if you want things to be like descending into darkness you could make this black and you don't have to worry about as 
[25:04](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1504) much lighting in your scene which is nice too again it's a pretty stylized look but I think it's kind of neat or you know you could just change this to some weird color if you want some like 
[25:16](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1516) toxic mist or something like that I think it's a pretty interesting look and so that's pretty much how I made the scene if you enjoyed this video give me a like and subscribe it helps me out a 
[25:25](https://www.youtube.com/watch?v=z-tI-WqeqKk&list=PLzg4_2BrWAVwLdL4OCqNR882C49gtojHt&index=19&t=1525) lot and if you want to see what else I'm making you can check out my Instagram I hope you learned something thanks for watching you 