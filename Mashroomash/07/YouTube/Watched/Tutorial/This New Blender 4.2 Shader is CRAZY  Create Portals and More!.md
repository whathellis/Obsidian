---
URL: https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s
thumbnail: https://i.ytimg.com/vi/i3jXz0A77iA/default.jpg
channel: "[[SouthernShotty]]"
date: 2024-07-21
published: 2024-06-06T23:30:28
duration: 619
tags:
  - video/3D/tutorial
done: true
cover: "[[Pasted image 20240715183338.jpg]]"
---
[time:: "10m 19s"]
# This New Blender 4.2 Shader is CRAZY | Create Portals and More!
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715183338.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="This New Blender 4.2 Shader is CRAZY | Create Portals and More!" src="https://www.youtube.com/embed/i3jXz0A77iA?start=7&amp;feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
CREDITS
[[../../../../01 Maps/YouTube/Channels/CGMatter|CGMatter]]/[[../../../../01 Maps/YouTube/Channels/Default Cube|Default Cube]]: https://www.youtube.com/watch?v=kOCIEoezyJo
Cartesian Caramel: [[../../3D/New/Blender 4.2 Portals using the Ray Portal node!|Blender 4.2 Portals using the Ray Portal node!]]
https://www.youtube.com/live/1ZvwhLRPM3M?si=EO5eUqK1S8fLOtp5
Chiu_hans: https://x.com/chiu_hans?lang=en

👇My Products 👇
Dynamic VFX Pack (Free Sample Pack): https://blendermarket.com/products/blender-dynamic-vfx---elemental-asset-pack
Crafty Asset Pack (Free Sample Pack): https://blendermarket.com/products/crafty-asset-pack
Patreon: https://www.patreon.com/southernshotty
Skillshare (affiliate link): https://www.skillshare.com/r/user/southernshotty

Tag me in your artwork on Instagram and Twitter @SouthernShotty

Instagram: https://www.instagram.com/southernshotty/
Twitter: https://twitter.com/SouthernShotty

Prepare to be amazed by the capabilities of the latest shader in Blender 4.2! This groundbreaking tool isn't just an update—it's a revolution in the way we think about and create visual effects in 3D environments. In this video, we explore the insane potential of this new shader that lets you create realistic portals, dynamic reflections, and much more.

(Description:: We'll dive deep into a hands-on tutorial where you'll learn how to harness the power of this new shader to craft mesmerizing portals that look like they're straight out of a sci-fi movie. From setting up the basic shader nodes to fine-tuning the effects for maximum impact, we'll cover all the steps necessary to bring these fantastical elements into your projects.)

# Transcript
[00:00](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=0) blender 4.2 is already shaping up to be a massive update with a lot of really cool new features including the ray portal node the ray portal node allows us to access portals within the blender 
[00:10](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=10) Shader menu opening up the possibility for some really interesting effects and Illusions in this video we'll talk about the basics of what the ray portal node is and then we're also going to create 
[00:20](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=20) this illusionary effect where as you rotate this Cube you can see into multiple scenes from different angles I'll also spend a portion of this video pointing you to some other tutorials 
[00:29](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=29) that die deeper into the vector math and the complexities of the node if you'd like to go further after this tutorial but with that being said let's dive in all right to get to the good stuff we 
[00:40](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=40) first have to kind of go through this boring example of how the a portal node works so here we just have a cube down here and up here we just have a plane called portal with just a regular Shader 
[00:51](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=51) on it we're going to go ahead delete that default drag this out and add a portal and at first nothing cool is going to happen it's just going to look like a transparent shape 
[01:00](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=60) but we can control the position and the direction of our portal here from within the Shader so let's show what that looks like let's go ahead here add a texture coordinate and then we'll drag off the 
[01:11](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=71) object and add it to a mapping Vector node and then if we go ahead and plug this into the position you'll see that suddenly it cuts off and if we move around there we can see that we're 
[01:21](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=81) getting this weird effect well the actual plane here is 2 m in the sky so when we unplug that we just see right through it but now we're altering the position so we're now we're telling it 
[01:33](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=93) via the Shader that we are actually appearing at 0 m so if I was to bump this up to 2 m you'll see that it gets the same exact effect so we're actually kind of moving the position of the 
[01:43](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=103) portal there you can see how moving up and down in the space there let's go ahead and set that to two and you can see that we can begin altering some of these including rotating the effects 
[01:53](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=113) which can cause some glitches in some instances and you can see that we can move it around and you can see how very quickly this can become powerful likewise we can also change the 
[02:04](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=124) direction here as well and get some pretty interesting effects now let's look at a bit more of a complicated setup just a quick shout out to my patreon I've been posting project files 
[02:15](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=135) like this on my patreon and I've also been doing some kind of breakdowns and walkthroughs of my short film if you'd like to see that as well but let's get back to the 
[02:25](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=145) tutorial now if you want to follow along with me you can so what we're going to do is we're going going to grab a plane here and we're going to bring this up on the z-axis and we're going to add a new 
[02:35](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=155) material to it we're going to call that material portal one so if you want to recreate this effect this is a part of the tutorial where you'll want to follow along so you may want to make sure you 
[02:44](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=164) have 4.2 downloaded we're going to grab that portal material on our plane there and what we can do is just delete that drag out the surface and we're going to add a rare portal now we're going to do 
[02:54](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=174) some interesting Vector math here and I actually discovered this math node setup from CG matter who has an entire video diving into like how Vector math works with these notes specifically so credit 
[03:07](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=187) to him for figuring out the setup for now let's begin kind of our node setup here so let's add a tangent node here we're going to change this to a UV map and we're going to select UV map now if 
[03:18](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=198) you're following along with me the default UV map on the plane should work for you now what we can do is add a geometry node and we will duplicate that geometry node and set that down here and 
[03:30](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=210) then what we'll do is we will grab that geometry node and we are going to do normal drag that off and choose cross product and that'll put it into the top node there of a vector math we're going 
[03:40](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=220) to take that tangent and put that into the bottom there perfect now what we're going to do is drag off the incoming here and put this into a vector math scale perfect and we want to make sure 
[03:51](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=231) that that is in the top and then we're going to do neg1 perfect now we can grab that drag this Vector off into a DOT product and make sure this is plugged into the bottom and then we're going to 
[04:03](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=243) duplicate this one three times and you're going to plug that scale into the bottom of all three just like that then grab the normal from the geometry here and for the bottom one plug it into the 
[04:16](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=256) top Vector of the dot product there for the middle dot product here we're going to take this cross product math node that we have and plug that into the top and then for this last one up here we're 
[04:27](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=267) going to take that tangent and plug that into the the top now we have three coordinates that we can combine into a new Vector system so hit shift a look for combine XY Z and then you're going 
[04:38](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=278) to plug them in top middle and bottom accordingly now we have all these that we can plug into the direction and right now you're going to see that not much here has changed quite yet so to finish 
[04:49](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=289) it off and give us some control we're going to add a texture coordinate we're going to drag that object off into a mapping Vector node and they're going to drag that vector and put it into the 
[04:58](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=298) position by default here it's going to give us a black result and that's because we are inside of this Cube we have here we could go ahead and move that Cube down and you can see how it's 
[05:08](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=308) offset so this is now sitting at the 0 0 position so you can either move this up on the math node so that it sits above it but I prefer to leave this at zero and we're just going to move our Cube 
[05:22](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=322) down so I'm going to come over here to the 3D viewport switched to the side view here and if we move our 3D cube down here we'll see that now appears in there and what we're basically getting 
[05:31](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=331) right now is almost a one: one because we have the plane up here but according to the Shader it thinks that the plane is essentially sitting like this so now what we can do is grab this box right 
[05:43](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=343) here we'll grab this top face here we'll press I to inset that ever so slightly and extrude down inwards like that and you can see that now we are looking into this little room just like that and 
[05:56](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=356) because of that nice Mass Zone setup that we got from CG matter we can take this and we can move it anywhere and you can see that we can look around and we can rotate this and we can look into our 
[06:06](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=366) little room there so now you can place whatever you want in this little room and create that Cube effect let me show you how I set that up a little bit more okay so now we have this right here 
[06:19](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=379) called portal one let's name this plane here portal one just like its Shader name and then we're going to duplicate this plane and move it over on the X x axis so let's can name this one Portal 2 
[06:33](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=393) and you can move this wherever you want but just for a simple math I'm going to go ahead and move this on the xais 5 m so now this is positioned over here so let's go ahead grab this Cube down here 
[06:44](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=404) I'm going to hit shift d and let's also move this one over five now let's make these different colors just so that we can make this for illustration purpose perfect so you can see that even though 
[06:56](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=416) we've moved this plane over it's still positioned here because of the Shader so we actually want this portal here to view inside of this Cube so we will come to the Shader menu there and then we can 
[07:08](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=428) grab this portal node here we'll click new let's name this Portal 2 and then we need to just move the position of our Shader portal over this cube right here and since we did that simple math of 
[07:21](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=441) five we only need to move it over five on The X and now we can see that it's there so you can see just that shifting this just kind of moves it from from one to the other so if we move that there 
[07:32](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=452) the portals are now positioned directly above these cubes so you can use each one of these cubes to build out your environment or your set or your scene and we can kind of create that depth 
[07:41](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=461) Parallax effect let me show you how to use these planes and put them together so let's add a suzan mesh inside of these cubes just to make this a little bit more obvious we'll make one that way 
[07:54](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=474) and then we'll rotate this one 90° so that we can see there different so now you can take these planes and then you can go ahead and use them to build your own Cube so I'm going to move these 
[08:07](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=487) planes off to the distance here and I'm going to hit alt R make sure that the rotation set I'm going to rotate these up 90° on the X AIS then I'm going to rotate one of these 90° on the Z axis 
[08:23](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=503) it's 90° there and then we can match these up here so that the verts are matched up there and then now when we look at these planes you can see that as we rotate around these planes we are 
[08:36](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=516) able to see inside of our cubes so I showed you how to set up the Shader but you might be wondering how I went about creating a more complicated setup like this well let me show you it's actually 
[08:45](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=525) pretty simple if I go into my top view mode here you can actually see that my Cube and the planes which I've already taught you how to set up are just sitting over here off to the side and 
[08:54](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=534) then you can see out in space here I've imported my environments so rather than just filling up those cubes you can just import your environments or model or whatever you want to toss in front of 
[09:04](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=544) those other portals and then just go ahead and move them around and rotate them until you get them somewhere you're happy so you can see here I have everything parented to the floor and I 
[09:12](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=552) can just move that floor around until I get it at an angle I'm happy with and then I can go and rotate around to view in there so it's pretty simple just toss everything you want in front of those 
[09:22](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=562) portal placements now as I mentioned I wanted to point you to some other resources to dive a bit deeper on this node as I mentioned earlier in the video default 
[09:34](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=574) Cube or CG matter already has a video up on this I credited that and I'll link it below an incredible Deep dive into just the vector math of how everything works he does a really good job of explaining 
[09:46](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=586) it another YouTube channel that always has amazing artwork is cartisian caramel I believe I'm pronouncing that correctly and on this channel there's already a couple videos up doing some really cool 
[09:58](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=598) effects in particular I love this portal effect that's being done on the channel and there's already a couple other things as well they're live streams so they're just realtime walkthroughs of 
[10:08](https://www.youtube.com/watch?v=i3jXz0A77iA&t=7s&t=608) the process very cool stuff definitely recommend checking out this channel as well I'm really excited to see what you create from this so please tag me at Southern chotti so I can follow along 