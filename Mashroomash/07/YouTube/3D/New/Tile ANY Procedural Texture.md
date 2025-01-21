---
URL: https://www.youtube.com/watch?v=B3PlAguibRc
thumbnail: https://i.ytimg.com/vi/B3PlAguibRc/default.jpg
channel: "[[Erindale]]"
date: 2024-07-16T15:29:02
published: 2023-01-29T09:37:51
duration: 1019
tags:
  - video/3D/texture/node
done: false
cover: "[[Pasted image 20240716152921.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "16m 59s"]
# Tile ANY Procedural Texture
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716152921.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Tile ANY Procedural Texture" src="https://www.youtube.com/embed/B3PlAguibRc?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
Check out my new procedural modelling bundle: https://www.nodegroup.xyz/procedural-columns-masterclass-bundle

Advanced Geometry Nodes course: https://www.canopy.games/p/advanced-geometry-nodes-for-blender-3-3-1?product_id=4353058?affcode=379023_i5skfa8n

(Description:: In this session you're going to learn to loop procedural noise, voronoi, musgrave etc textures inside Blender with a few math nodes.)

Grab the final lesson file: https://www.patreon.com/posts/77883952/

$40 off a holographic display? Yes please. https://look.glass/erin
Geometry Nodes Toolkit: https://gum.co/erintools
Merch? https://erindale.threadless.com/

Discord: https://discord.gg/erindalexyz

My Courses:
https://www.futurly.com/s/store/courses/description/Blender-Parametric
https://www.canopy.games/p/advanced-geometry-nodes-for-blender-3-3-1?product_id=4353058?affcode=379023_i5skfa8n
https://www.canopy.games/p/bcs-geometry-nodes-3x?affcode=379023_i5skfa8n
https://www.canopy.games/p/procedural-materials-in-blender?affcode=379023_i5skfa8n

Contents:
00:00 - Intro
01:20 - How the maths works
11:18 - Looped animation example

Patreon: https://www.patreon.com/erindale
Ko-fi: https://ko-fi.com/erindale
Twitter: https://twitter.com/erindale_xyz
Instagram: https://www.instagram.com/e.r.i.n.d.a.l.e/
Gumroad: https://gumroad.com/erindale
Blender Market: https://blendermarket.com/creators/erindale
# Transcript
[00:00](https://www.youtube.com/watch?v=B3PlAguibRc&t=0) these are all of the nodes that you're going to need to do looped noise or other procedural Textures in blender this setup will give you one full tile per UV space or if you're using 
[00:10](https://www.youtube.com/watch?v=B3PlAguibRc&t=10) something like object coordinates or the geometry position output which is World space then multiplying this by 6.283 or Tau or 2 pi that is going to give you that full wavelength every one meter but 
[00:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=25) why does this work what is this actually doing and what can we use it for a few examples of when you'd want to use this would be if you have a single tile that you want to export to 
[00:35](https://www.youtube.com/watch?v=B3PlAguibRc&t=35) a game and create something which Loops for example something like this where if I remove this smoothing and see that we get a bit of a desert 
[00:46](https://www.youtube.com/watch?v=B3PlAguibRc&t=46) some sand dunes right and from down here on the surface it really doesn't bother you that these are looped but we can see that we can really optimize our game by just having 
[01:01](https://www.youtube.com/watch?v=B3PlAguibRc&t=61) a single tile here and all we're exporting at this point is going to be a height map another reason you'd want to Loop noise is so that you can get displacement animated 
[01:10](https://www.youtube.com/watch?v=B3PlAguibRc&t=70) displacement moving across something in a way which is going to Loop so it's perfect for looped animations as well so going back to my nodes why does this work well let's jump into it we're going 
[01:20](https://www.youtube.com/watch?v=B3PlAguibRc&t=80) to be starting out here in Geometry nodes just to give this a little bit of a clearer explanation some of this stuff is going to be much easier for us to visualize here but you know we can use 
[01:29](https://www.youtube.com/watch?v=B3PlAguibRc&t=89) it in Geometry notes or we can be using this in shaders something that we need to understand is how to create a circle essentially we'd want our noise to start and end in the 
[01:40](https://www.youtube.com/watch?v=B3PlAguibRc&t=100) same place to give us a loop and so what better way to do it than to create circles go ahead and just add in a curve primitive curved line 
[01:50](https://www.youtube.com/watch?v=B3PlAguibRc&t=110) we are going to be adding a resample curve and then a set position node so far so good we can plug into our position a combine 
[02:03](https://www.youtube.com/watch?v=B3PlAguibRc&t=123) XYZ and we will plug into our x a spline parameter Factor just like this I'm going to go Ctrl H just to hide those other two sockets we 
[02:14](https://www.youtube.com/watch?v=B3PlAguibRc&t=134) don't need so a spline parameter Factor gives us a zero to one along the length of the spline the reason I'm doing this is because our UV map is also a length of 0 
[02:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=145) to 1 across its width this also is just going to help us visualize what's going on so a little bit of graphing for us here I might actually just skin this to make 
[02:36](https://www.youtube.com/watch?v=B3PlAguibRc&t=156) it easier to see as well so let's use a curve to mesh with a curved Circle just so we can see it nice and clearly there we go 
[02:51](https://www.youtube.com/watch?v=B3PlAguibRc&t=171) I'm gonna make a few more points on here let's go up to 32. and first of all let's try plugging our spline parameter into both X and Y so as we go from zero to one in X we go from zero to one in y 
[03:04](https://www.youtube.com/watch?v=B3PlAguibRc&t=184) now what happens if we add a sine function to this so utility math node let's just drop this onto that noodle going into the x-axis and instead of add 
[03:15](https://www.youtube.com/watch?v=B3PlAguibRc&t=195) let's set this to sine we're going to need a little bit more space so a sine wave or a cosine wave they have a wavelength 
[03:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=205) of 2 pi so we can just add another math node set to multiply drop it on here and multiply by you can either write 2 times pi or t a u 
[03:37](https://www.youtube.com/watch?v=B3PlAguibRc&t=217) all right so we've got ourselves a sine graph and you might be familiar with these from school sine graphs represent simple harmonic 
[03:50](https://www.youtube.com/watch?v=B3PlAguibRc&t=230) motion it goes up to a value of one and it goes back down to a value of -1 to change this over to a cosine graph well now we're starting at one and 
[04:03](https://www.youtube.com/watch?v=B3PlAguibRc&t=243) coming down and then going back up but it's the same graph it's just offset slightly and this is actually quite important because at this point 
[04:12](https://www.youtube.com/watch?v=B3PlAguibRc&t=252) what happens if we plug a sine and a cosine in at the same time is we get a full circle 
[04:24](https://www.youtube.com/watch?v=B3PlAguibRc&t=264) so why is this happening well when the spline parameter is zero cosine in the Y gives us one and then the sign in the X will give us zero and then as we track around here 
[04:36](https://www.youtube.com/watch?v=B3PlAguibRc&t=276) because we have simple harmonic motion and it is out of sync with itself we can actually track around a perfect circle so this is really the fundamentals of how we're doing our looped 
[04:48](https://www.youtube.com/watch?v=B3PlAguibRc&t=288) noise our looped mapping coordinates is we're creating a circle in the X and Y plane where we have a single gradient with a wavelength of 2 pi going through sine 
[05:01](https://www.youtube.com/watch?v=B3PlAguibRc&t=301) and cosine into two separate axes but it was a little bit more complicated than that when we did the noise texture so let's jump back into our Shader and have a look at what's different so to preview 
[05:12](https://www.youtube.com/watch?v=B3PlAguibRc&t=312) this I'm going to be using a boronoi because it gives us nice sharp edges let's have a look at this here we go and we're going to be plugging into the vector 
[05:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=325) this is just like our set position so plug into the vector a combine XYZ into the X we will plug in a sine and into the Y we will plug in a cosine so just exactly the same as we did 
[05:38](https://www.youtube.com/watch?v=B3PlAguibRc&t=338) before with geometry nodes now coming into this we need our gradient so for this we're going to be using the UV map or you could use any other mapping coordinates this is going to go through 
[05:46](https://www.youtube.com/watch?v=B3PlAguibRc&t=346) a separate XYZ just take the one gradient because this is our single gradient here so just the same as we had before right zero to one going through sine going 
[06:00](https://www.youtube.com/watch?v=B3PlAguibRc&t=360) through cosine and being combined so just after our UV map we're going to be adding a converter Vector math and we will set this to be scale just so that we're scaling in both axes at the 
[06:12](https://www.youtube.com/watch?v=B3PlAguibRc&t=372) same time now you might want to do this differently you might want to use a multiply node which depends on how big your tile is and which coordinates you're using 
[06:19](https://www.youtube.com/watch?v=B3PlAguibRc&t=379) Tau into your scale right so what we have this time is I mean it's essentially the same right if I turn on displacement on this material 
[06:31](https://www.youtube.com/watch?v=B3PlAguibRc&t=391) add some subdivisions set this to Adaptive and then if I just plug this into a displacement node and let's add one 
[06:45](https://www.youtube.com/watch?v=B3PlAguibRc&t=405) and then let's plug in for example our sine wave go into rendered well this is exactly what our geometry notes was giving us before right we have 
[06:58](https://www.youtube.com/watch?v=B3PlAguibRc&t=418) a continuous gradient in one axis sort of a linear gradient and then we're doing a sine wave and equally the cosine there is going to give us the same result we 
[07:09](https://www.youtube.com/watch?v=B3PlAguibRc&t=429) just displacing this graph now the problem is it's been displaced in the height and we're wanting to view this from above and because everything is coming off a single axis here the 
[07:21](https://www.youtube.com/watch?v=B3PlAguibRc&t=441) x-axis everything is simply traveling in the One Direction and that means as soon as this goes through a foreign texture well this isn't very interesting anymore 
[07:31](https://www.youtube.com/watch?v=B3PlAguibRc&t=451) but sure it does join an end at the same place because we have it starting going around up and back right so we need to add a second axis that's going to collapse these two nodes here 
[07:45](https://www.youtube.com/watch?v=B3PlAguibRc&t=465) so to add a second axis we are going to be coming off the y-axis now so now both our sine and our cosine come off in this direction what's actually happening here well 
[07:57](https://www.youtube.com/watch?v=B3PlAguibRc&t=477) if we plug the X and the Y into a separate sine and cosine we're still thinking about making a circle right we're using sine and we're using cosine one is going in the up and down axis one 
[08:07](https://www.youtube.com/watch?v=B3PlAguibRc&t=487) is going in the horizontal axis why does this not Loop perfectly as well well sine and cosine make up for each other's slowest points if we draw out these grids here 
[08:19](https://www.youtube.com/watch?v=B3PlAguibRc&t=499) where sine is steepest at this point here cosine is least steep it's at its flattest point right at the bottom of the Curve and when a sign is at its 
[08:34](https://www.youtube.com/watch?v=B3PlAguibRc&t=514) level list essentially the the slowest that it's moving across our texture here that is where cosine is at its fastest so these two make up for each other that's why when we use them for a circle 
[08:47](https://www.youtube.com/watch?v=B3PlAguibRc&t=527) it gives a perfect circle plot because you can get a nice continuous motion around the circle in the case of our texture though this isn't quite right 
[08:58](https://www.youtube.com/watch?v=B3PlAguibRc&t=538) so we need cosine to make up for sine in the x-axis but then we need more axes right so now we can use the y-axis with sine and cosine we will 
[09:10](https://www.youtube.com/watch?v=B3PlAguibRc&t=550) make up the Z here which has given us almost the right pattern but we still have this one slow section in the middle where our texture is being stretched quite a lot so we need an additional 
[09:24](https://www.youtube.com/watch?v=B3PlAguibRc&t=564) axis here so we'll plug this final cosine into our W of the 4D noise and now the cosine is making up for the slow points in sine so this is giving us perfectly tiling noise and importantly 
[09:38](https://www.youtube.com/watch?v=B3PlAguibRc&t=578) with a wavelength of 2 pi and that means that every time you have a distance of 2 pi in your gradient you have a full wavelength here important to note there are some 
[09:49](https://www.youtube.com/watch?v=B3PlAguibRc&t=589) limitations of this process we have four annoy texture here we are using a 4D voronoi however if for example I was to put this onto a monkey 
[10:05](https://www.youtube.com/watch?v=B3PlAguibRc&t=605) and rather than using the UV map let's go ahead and use a 3D coordinate space like object well now we're going to be getting stretching in the z-axis if I go from 
[10:16](https://www.youtube.com/watch?v=B3PlAguibRc&t=616) above it looks perfect if I go from the front we get stretching why is this happening it's because our original coordinates are only using the X and Y axis so even though 
[10:28](https://www.youtube.com/watch?v=B3PlAguibRc&t=628) our final texture is four dimensional in order to make full use of our Sines and cosines the texture is actually being mapped in the x y space only if you want to have a fully three-dimensional 
[10:41](https://www.youtube.com/watch?v=B3PlAguibRc&t=641) repeating pattern you can do this again sine and cosine of the Z but you're going to need to make your own 6D texture that might seem a little bit weird like we only exist in three 
[10:53](https://www.youtube.com/watch?v=B3PlAguibRc&t=653) dimensions how are we dealing with four dimensions noise texture boring eye texture they're all just mathematical formulas right any additional Dimensions that you add to them they're actually 
[11:01](https://www.youtube.com/watch?v=B3PlAguibRc&t=661) just like it's a variable blender and the math doesn't care if you're using space or if you're just using a value that's all that's going to be read as and it's going to go through the formula 
[11:10](https://www.youtube.com/watch?v=B3PlAguibRc&t=670) and treat it as a number so you can derive your own six dimensional formulas for doing 3D titling plots let's burn through a really quick setup here where we can do a looped animation in Geometry 
[11:23](https://www.youtube.com/watch?v=B3PlAguibRc&t=683) notes just to get something moving and repeating I'm back in Geometry nodes here I've just got a plain object as my container let's add a new geometry nodes call this one looped animation 
[11:35](https://www.youtube.com/watch?v=B3PlAguibRc&t=695) we're going to need something which is going to move so let's go ahead and use a point this is all we actually need at this point we're going to be controlling the 
[11:45](https://www.youtube.com/watch?v=B3PlAguibRc&t=705) position of the point so that it moves erratically through space but it returns to its original position we can then process this instance things on it however we want to afterwards and we 
[11:57](https://www.youtube.com/watch?v=B3PlAguibRc&t=717) should get a looped animation so let's take our point we are going to derive the position or offset the position by taking the position and adding a 
[12:09](https://www.youtube.com/watch?v=B3PlAguibRc&t=729) vector math add we will be adding noise texture but noise is between 0 and 1 so we are first of all going to be subtracting 0.5 from it 
[12:21](https://www.youtube.com/watch?v=B3PlAguibRc&t=741) so we take noise color into a subtract node subtract 0.5 we might want to scale this as well just give it a bit of a bigger effect and then we need to be driving our noise 
[12:35](https://www.youtube.com/watch?v=B3PlAguibRc&t=755) texture with our Newfound looping ability let's take 40 on here we're going to be combining XYZ for our vector and we will just be using a sine for the X 
[12:49](https://www.youtube.com/watch?v=B3PlAguibRc&t=769) cosine for the Y and then another sine and cosine for the Z and the w we can drive these off a separate XYZ X 
[13:01](https://www.youtube.com/watch?v=B3PlAguibRc&t=781) and Y for the second two and then these we can take off a position node here we go let's take our detail down to zero scale 
[13:13](https://www.youtube.com/watch?v=B3PlAguibRc&t=793) down to 0.5 or something like that so if we want our point to move around driven by our noise texture then we're going to need to add something to the original input position now if we think 
[13:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=805) about this we have our noise doing something like this right so it's coming through the sign the cosine so this is our mapping coordinates I need for one Loop 
[13:36](https://www.youtube.com/watch?v=B3PlAguibRc&t=816) essentially to move the current position over here by 2 pi that's all you got to do if you want one Loop you just have to move it 2 pi in some direction and you will result 
[13:51](https://www.youtube.com/watch?v=B3PlAguibRc&t=831) in whatever it is that you're doing being looped through that motion this is a little bit different to shaders where you'll want to be adding after the sine and cosine then in all 
[14:04](https://www.youtube.com/watch?v=B3PlAguibRc&t=844) likelihood that's not going to give you a loop in fact it won't give you a loop it'll just give you a new seed so if you're wanting to do the looped offset that needs to happen before you're 
[14:12](https://www.youtube.com/watch?v=B3PlAguibRc&t=852) separating XYZ go ahead and add a vector math node we're going to be using a combine XYZ I'm going to be using a map range into my X here 
[14:22](https://www.youtube.com/watch?v=B3PlAguibRc&t=862) and I'm going to find out what my frame range is so we are going to be looping from 1 to 100 our scene time frame output here 
[14:34](https://www.youtube.com/watch?v=B3PlAguibRc&t=874) from 1 to 100 is going to be from 0 to 2 pi or Tau Tau and actually here's a little bit of a kind of confusing one zero and two Pi in terms of a circle exactly the same 0 and 360 degrees right 
[14:50](https://www.youtube.com/watch?v=B3PlAguibRc&t=890) so to make sure that we don't get a double frame between 1 and 100 what we can do is make sure that we're actually starting here at zero so now zero and one hundred will be the same but we are 
[15:01](https://www.youtube.com/watch?v=B3PlAguibRc&t=901) animating from 1 to 100 so we will just get that continuous cyclic Loop so if I now play this should not see any stepping there we go we've just gone back to the beginning 
[15:15](https://www.youtube.com/watch?v=B3PlAguibRc&t=915) we're getting this kind of continuous movement amazing so let's go ahead and add a different seed value as well so I'm going to just add a math node afterwards 
[15:25](https://www.youtube.com/watch?v=B3PlAguibRc&t=925) after my cosine so I can just wait until I found some noise that I like here for a slightly higher scale on my noise if I want this to be faster 
[15:39](https://www.youtube.com/watch?v=B3PlAguibRc&t=939) you know if I wanted to go further in or yeah go through a more interesting noise in that distance and we can make this travel further with this final scale here 
[15:52](https://www.youtube.com/watch?v=B3PlAguibRc&t=952) so this little setup here this is going to give us a looped displacement of geometry over 100 frames so from 1 to 100 frames with a seed value that we can set over here that's 
[16:06](https://www.youtube.com/watch?v=B3PlAguibRc&t=966) in fact plug this in with a value node just to make sure that we've marked it as a seed so this is essentially your new W input is just by adding to that w 
[16:18](https://www.youtube.com/watch?v=B3PlAguibRc&t=978) and we're going to get a perfect Loop here so this provides a lot of opportunity for creating looped simulations looped animations interesting loot textures things like 
[16:27](https://www.youtube.com/watch?v=B3PlAguibRc&t=987) that so anywhere that you have access to a four-dimensional noise or for annoy or Musgrave or anything like that you can create a perfectly looped animation or whatever it is that you need to do these 
[16:40](https://www.youtube.com/watch?v=B3PlAguibRc&t=1000) are the nodes this has been a little bit of Maths for you hope you enjoyed it hope you've learned something I'll catch you in the next one [Music] 
[16:50](https://www.youtube.com/watch?v=B3PlAguibRc&t=1010) foreign [Music] 