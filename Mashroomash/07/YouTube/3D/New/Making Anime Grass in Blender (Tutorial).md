---
URL: https://www.youtube.com/watch?v=F7_btP0Vhzo
thumbnail: https://i.ytimg.com/vi/F7_btP0Vhzo/default.jpg
channel: "[[Tawan Sunflower]]"
date: 
published: 2024-06-29T01:00:06
duration: 667
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715182410.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "11m 7s"]
# Making Anime Grass in Blender (Tutorial)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715182410.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Making Anime Grass in Blender (Tutorial)" src="https://www.youtube.com/embed/F7_btP0Vhzo?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Today I will show you how to make an animated grass in Blender!)

Send me your Grass Animation here! ✨
https://forms.gle/uthQdkK9tqZ7LXXV7

👇Parts👇
00:00 - Introduction
00:53 - Chapter 1 : Geometry Nodes
05:13 - Chapter 2 : Wind
07:52 - Chapter 3 : Adding Colors
09:15 - Optional Step

📙Colors Codes📙
Color Ramp Colors:
1: B9B954
2: CCD530
3: 49674F

Mix 1 Colors:
B input: 425B30

Mix 2 Colors:
B input: D8D83F

❤️ SUPPORT THE CHANNEL ❤️
Patreon: https://www.patreon.com/TawanSunflower
Gumroad (Free Tutorial Files): https://tawansunflower.gumroad.com/

💬Socials💬
Linktree: https://linktr.ee/tawansunflower
Twitter: https://twitter.com/himawari_hito

# Transcript
[00:01](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=1) [Music] hello everyone the On's here normally people create St grass using the particle system today we're dishing that and we're diving to the wonderful world 
[00:12](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=12) of geometry nose to create some grass geometry nose are super powerful and way more versatile than partical system now as you can see from the title this is the first part which should give you the 
[00:22](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=22) foundation of geometry notes before we dive into the second part which will be creating this now as a special bonus I'm giving away one of the items in my gunver for free to the first five people 
[00:33](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=33) successfully made a grass animation using the technique in this video Speaking of awesome things I also have a patreon now you guys don't have to support me over there you know just have 
[00:43](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=43) fun with blender but if you do I would be eternally grateful and you will get these exclusive rewards like scene files and assets all right with that out of the way let's get 
[00:55](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=55) started first thing first make sure that you are using blender 4.1 or higher there are some killer features in there which will make our lives a whole lot easier now we know what to do let's 
[01:05](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=65) delete this Cube deleting it increase your success by 90% well maybe not but it certainly can hurt now let's create a plane just hit shift a then press tab to go into edit mode scare it up to a nice 
[01:17](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=77) size then we go back to object mode we also want a cube in there for good measures because why not this will be the foundation of our grassy Paradise now if our plane selected let's Unleash 
[01:28](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=88) the Power of one of the most underrated features of blender hair hit shift a go to curve section and click empty hair open geomy nose Tab and you will see that one no appear automatically the 
[01:40](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=100) deform curves on Surface node this little guy ensures that the hair sticks to the geometry even after we deform the mesh but right now our plane is pretty much bald so we're going to add another 
[01:51](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=111) node called generated hair curves this Nifty node group came from the team behind blender because they want to make hair curves easier to use plug the curve into the out put and grab that eye 
[02:01](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=121) dropper to select our plane and you can crank up the density using this parameter now currently our grass doesn't show any thickness so first go into the render properties and set the 
[02:11](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=131) curve shape to strip then grab a set curve radius node and put it here then adjust this value while pressing shift for final controls and now we got some basic grass growing on our plane now one 
[02:24](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=144) important thing to remember the grass and the plane are separate objects the grass is automatically par to the plane meaning that you can move the plane around and your grass will follow along 
[02:34](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=154) we've got the grass set up but it looks pretty much Bland but don't worry the real magic is about to begin for those who are new to Geometry noes it's basically a non-destructive way to 
[02:44](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=164) manipulate your mesh p with like giving your model super powers with the power of nodes unfortunately most of it is just math don't worry if math isn't your best friend well I'm also not good at 
[02:54](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=174) math too which made me highly qualified to teach math with some memes and visual elements now with some special notes we can tell blender to manipulate these points individually in this case we want 
[03:04](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=184) to control how each blade of grass sprays in the breeze and to achieve this we need to control the rotation of each point based on the one before it essentially using the previous Point as 
[03:14](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=194) a period we'll use a note called offset point in curve which can give us the reference of a point along the grass this lets us reference the previous Point acting as the center of rotation 
[03:25](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=205) now if that isn't a previous point then we need to default it to the current Point using the switch node set to integer and add an index node now we'll use an evalate add index node set to 
[03:36](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=216) vector and grab the position node and plug it like this to get the position of the previous point and then add the vector math node set to substract and plug the current position and the 
[03:45](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=225) previous Point position like this now we have the arrow that we can use to do the rotation but before that we have to accumulate the field using the accumulate field node and also be sure 
[03:56](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=236) to set it to Vector too imagine it's like stacking those arrows belonging to each control point on top of each other now with a set position node put it over here and pluck the leading output into 
[04:07](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=247) the position input and then we can see that our grass Stacks up like this it's because the accumulate field node we initially gave every blade of grass the same ID to fix this we use the index 
[04:19](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=259) node and you evaluate on domain node set to spline and plug them like this to give each grass blade a unique ID now everything is at the center so we can add at the curve root node pluck the 
[04:31](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=271) root position to the offset of the set position node and now our grass is back to its original position then finally we can add the vector rotate note here set this to Al and now we can rotate the 
[04:45](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=285) grass in any direction we want oh that's the initial setup and next we will create a virtual wind but before that here's a few words of advice it might seem complex now but trust me 
[05:02](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=302) the more you play with geometry nose the more it will become second nature and you look back and say wow how did I ever struggle with this just keep practicing and soon you'll be a grass 
[05:16](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=316) professional now let's get this grass rain in the breeze we can use a note called a line outl direct Vector to control the rotation of each grass blade finger beit like pointing a finger in a 
[05:27](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=327) direction blender will automatically calculate the road ration for that direction set the Align M to c-axis and for the input Vector we'll use 1 0 0 this makes all the blades face the 
[05:38](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=338) x-axis but hey real grass isn't that uniform right the tip should bend more than the roots and here is where things get cool we'll grab a mix node set it to rotation then we'll plug this into the B 
[05:52](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=352) socket we'll grab the spine parameter noes which generates this nice gradient on the rout we want no rotation and on the tip we want the full effect of the rotation plug this to the mix node and 
[06:04](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=364) now you can see the sweet Bend but our grass is pretty stiff so let's add Randomness to it using the a popular noise texture node turn off normalize scale down the 0.5 and set the detail to 
[06:17](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=377) zero this creates a subtle natural level of Randomness then we use two math nodes set one to multiply and another to multiply add then connect them like this now for the grand finally let's animate 
[06:30](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=390) the grass to do this we'll animate the vector used by the noise texture node we'll use a combination of nodes like curves root Vector math scene time and combine xyc node to create a setup that 
[06:42](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=402) increases the x value over time and now you can hit play your grass is now swaying gently in the breeze it might seem a little bit slow so let's Crank It Up using a multiply node set to-5 then 
[06:55](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=415) plug it over here and now we got some nice looking wind but great there's more we can add even more Randomness to the rotation using the rotate rotation and an all to the rotation node this lets us 
[07:07](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=427) use the color generated by the noise texture to add some extra wubble to each grass blade pluck them like [Music] this and now that's some seriously 
[07:20](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=440) Dynamic grass and to add more controls we can duplicate this mix nose which we used earlier and place it over here this lets us adjust the strength of our noise texture giving the ultimate control over 
[07:31](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=451) the amount of Randomness in your grass so how is that you've gone from a BAL plane to a mini ecosystem with the power of geometry nodes all right we are now almost at the end let's make the 
[07:46](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=466) grass look a little less plastic and make it more like grass we've come a long way but shading is key don't worry because it's almost too easy first thing first let's jump into the 
[08:01](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=481) Shader editor and create a brand new Shader for our grass we will head back to Geometry notes and assign this new Shader over here back in the Shader editor we'll make a simple tune Shader 
[08:12](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=492) grab a diffuse bsdf Shader to RGB a mix node a coral ramp and a noise texture Now set the scale to 0.3 and I will use this normal node to replace the grass original normals 
[08:32](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=512) check the video description for the color codes and in the material properties set the shadow mode to none this means that our grass won't cast any Shadow but it can still receive them 
[08:43](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=523) from other objects creating a more stylized view now select the light and change it to sunlight and reduce the strength to 10 next let's head into the world Shader and set the enironment to 
[08:55](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=535) Black to remove all the effects inside on our grass shadow alternatively you can use this background Shader setup if you want to set the background color without affecting other shaders finally 
[09:06](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=546) in the render properties under color management set the real transform to standard to ensures our colors display correctly and that's pretty much it now this next part is optional but if you 
[09:18](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=558) want to make the grass a little bit more stunning here's an optional bonus step we use the geometry note to store some data about our grass then we can use that in the Shader we'll grab a stor 
[09:28](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=568) name attribute node and use it to store the output of the multiply ad node located after the noise texture this data will represent the wind affecting our blade then we'll add another 
[09:38](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=578) attribute to store a random value of each crass Blade Set this to spline and add a random value node make sure that both of these is set to vector and set the minimum values to 
[09:50](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=590) -1 then plug this at the end of the geometry node back in the Shader we use the add bu node to get the wind data then we'll use the map range node to modify the 
[10:04](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=604) data a little bit then we'll mix that with the original color of our grass and now our grass has a pleasing wind effect we'll do the same with the random attribute add a h saturation value node 
[10:17](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=617) and a separate XYZ node here reduce the factor and plug them together like this and now we have some variation making each blade ever so slightly different and that you have it you have created 
[10:28](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=628) some awesome look looking grass in blender that reacts to light sources making it look super realistic and stylized at the same time well congratulations if you have any 
[10:39](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=639) questions put them in the comments below and before you go check that subscribe button it might just turn into a rainbow if you haven't subscribed yet stay tuned for the next part big thanks to all my 
[10:49](https://www.youtube.com/watch?v=F7_btP0Vhzo&t=649) amazing patreon supporters now it's your turn to go further and Beyond and create some incredible grass scenes stay positive and happily blending [Music] 