---
URL: https://youtu.be/FXuReln3XD0?si=e59WzrNO_-OopEnN
thumbnail: https://i.ytimg.com/vi/FXuReln3XD0/default.jpg
channel: "[[Lightning Boy Studio]]"
date: 
published: 2022-03-29T01:35:08
duration: 1675
tags:
  - video/3D/texture/shader
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "27m 55s"]
# Arcane Style Tutorial Part 1: Hair (Blender 3.0 / EEVEE)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716143433.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Arcane Style Tutorial Part 1: Hair (Blender 3.0 / EEVEE)" src="https://www.youtube.com/embed/FXuReln3XD0?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Video tutorial on how to replicate the stylized look of hair in the Arcane animated series.)
This tutorial was done using Blender 3.0

Check out Part 2 here : [[Arcane Style Tutorial Part 1 Hair (Blender 3.0  EEVEE)|Arcane Style Tutorial Part 1 Hair (Blender 3.0  EEVEE)]]
https://youtu.be/gG7ZoP3fd1w

Tidal Blades 2 Kickstarter :
https://www.kickstarter.com/projects/druidcitygames/tidal-blades-rise-of-the-unfolders-cypher-system-rpg-book

Our Twitter :
https://twitter.com/LightningBoySt1

Other credits :
Trailer Sound effects : Mark Donis [Pride Productions] - https://www.facebook.com/1MDonis/
Opening Logo Sound Mix : Les Productions Underground
# Transcript
[00:10](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=10) hey everyone david here from lightning boys studio today's tutorial will be the first in a series on how to make your own arcane style character in blender 3.0 first off 
[00:20](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=20) is going to be how to do stylized hair using a particle system and then in part 2 i want to explore some different ways you can paint textures and use camera mapping to really push your shots to the 
[00:32](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=32) next level so the tricky part about doing a tutorial like this is i don't work with fortis or railgame so i don't have a clue what their actual process is i just 
[00:41](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=41) spent way too much time analyzing their shots because i love animation and frankly their work is some of the best i've ever seen and so because i didn't have access to their shots i needed 
[00:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=51) something similar enough to our king and i could use for this tutorial and luckily i recently had to do a 30 second opening animation for a board 
[01:01](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=61) game project i'm working on and i think it fits perfectly for this purpose so let's watch it now and we'll discuss it after used to dream of flying over nibiri 
[01:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=74) [Music] i would glide past the glorious arenas wave to merchants on the floating docks it seemed so peaceful i felt 
[01:29](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=89) so safe but now that i'm here in nibiri i understand that piece came with a price a battle fought by tidal blades before 
[01:39](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=99) us [Music] this time the fight is ours [Music] 
[01:47](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=107) so the animation you just saw was for a board game called tidal blades which i've been working on with my wife for almost four years now and it's currently on kickstarter so if you want to check 
[01:57](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=117) it out please do it's very cool i'll leave the link in the video description but it's not going to be the topic of this video so when i started planning this animation i knew hair would be a 
[02:07](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=127) major challenge and it took me a lot of trial and error and but i think i finally managed to find the best way to do it so let's jump in blender and i'm going to show you 
[02:16](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=136) everything i learned all right so i'm going to be using this classic portrait of jinx as reference and let's analyze it for for a minute before we 
[02:25](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=145) start um so as you can see there are a couple of very fine strands of hair here and there but they've been very carefully placed and the hair is mostly made up of these larger strands of hair 
[02:38](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=158) that are almost flat but still get this kind of nice gradient on them a bit of specular and so we're going to look at how to make one of these strands and then we'll 
[02:50](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=170) be able to duplicate it and add these individual hair afterwards all right so let me start by creating a plane with shift a mesh plane 
[02:59](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=179) then i'm going to go to the particle properties click on the plus button and change this from emitter to hair so as you can see at first they're going 
[03:08](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=188) to be probably pointing up and we want them pointing down so i'm going to press rx and 180 to rotate them and i also don't want all those hair what i actually want is just one single 
[03:20](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=200) hair which is going to be called our parent hair and all the volume of our hair is going to be generated around that single hair so what i'm going to do is change this 
[03:28](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=208) number from a thousand to just one and as you can see i'm gonna be left with just one hair but it's on the side right now that i'd rather have it in the center so i'm gonna go uh in particle 
[03:40](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=220) edit mode in the top left i'm just gonna select all those points and delete them and i'm going to create a new hair in the center so if you go on the left to your toolbox you can choose add 
[03:52](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=232) and make sure to choose count of one just want to add one here and keys i'm going to set it to five so if i click in the center you see i'm going to create just one single hair and if i had 
[04:03](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=243) choosing like a bigger number you see it would have gotten more subdivided but i think five is enough for our needs all right so at this point let me go to the children's 
[04:13](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=253) section of the particle properties and changes from none to interpolated and i'm not sure you can see this quite well on your screen so let me go quickly to my 
[04:22](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=262) render settings under hair changes from strand to strip and then back to particle properties i can go to hair shape and change the diameter scale 
[04:33](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=273) so um as you can see i still only get one single hair which is my parent and all these are called the children and they're being generated around it so if 
[04:44](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=284) i switch back to object mode i can bump up this number to whatever i want and they're still going to be influenced by this single hair and the cool thing i 
[04:54](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=294) can do is also go under clumping and click use clump curve and then i can drag this little point in the top left and i can create 
[05:04](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=304) more of a triangular shape and it's it's really blocky at this point but i'm gonna show you in a minute how to fix that so to make this a bit smoother what you can do is go to 
[05:15](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=315) viewport display and change your strength steps to five um and if you want things to be even smoother i would go to render and 
[05:24](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=324) activate b spline now you can still change your clump curve if needed and um now it's still a bit too large and cubic so what you can do is adjust your plane because it's it's filling up 
[05:38](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=338) that whole space you could do it by scaling it but i don't suggest doing that because it's going to be messing up your values later on if those scaling values don't stay at 
[05:48](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=348) 1 1 1 so instead i would go in edit mode by pressing tab and scale the plane this way so it's so it's thinner so one thing to note about particle edit 
[05:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=358) mode is that sometimes when we switch back to object mode you notice that there's a small difference and the reason is that particle edit mode has its own viewport display uh settings 
[06:09](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=369) and under tool if you press n tool viewport display you'll see there's a path steps here and this needs to match exactly what you write on the viewport display here so that when you switch 
[06:20](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=380) back to object mode you get the same result another option that's good to know is trend lengths preserve strand lengths um personally i prefer to leave it 
[06:30](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=390) unchecked that way i can sort of um really stretch my hair uh it's kind of cool to look at when you check it because it's going to be preserving the the length of the hair overall but i 
[06:40](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=400) just find it a bit wonky sometimes to really get the shape you want so personally i tend to leave it unchecked okay so now that our strand has got a nice curve to it let's 
[06:49](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=409) go to the shader editor and add a new material so i'm going to press on new and then i'm going to delete the default principle bsdf 
[06:59](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=419) press shift a and type in air info node which is going to give us access to a couple of outputs that are really useful to control the look of this hair strand next i'm going to create a color ramp 
[07:13](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=433) and i'm going to connect intercept into it to show you what it does so basically intercept is going to create a gradient going from the root of our hair to the 
[07:22](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=442) tip and i can choose using color ramp i can choose any color to decide what kind of gradient is applied onto my hair 
[07:32](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=452) so right away it's going to look a bit nicer and then i want to break it up add a bit of a of this texture you see here so i'm going to make a nice texture by 
[07:43](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=463) pressing shift a nice texture i'm going to type in texture coordinate because i want to access this uv 
[07:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=471) output plug it into vector and that way i'm going to access the uvs of my plane and um then to mix it up i'm going to make a mix rgb 
[08:07](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=487) and so my original color ram is going to go in color one this noise is going to go into the factor and it's going to drive this color so 
[08:17](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=497) the black and white values of my noise is going to decide where this black appears and i'm going to create an extra color ramp 
[08:26](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=506) uh just after nice texture that way i can control the contrast of the color ramp as you can see and you can it doesn't have to be black 
[08:35](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=515) and white like you can change this to a bit of a darker value so you don't want to be 100 opaque and then you can play with the scaling here to uh give it the texture look you want 
[08:45](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=525) another thing i like to do with that hair info note is to use the intercept output to drive transparency that way i can make this tip of the hair look a bit less sharp and more like a 2d 
[08:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=538) 2d painted stroke so the way to do this is to create a transparent bsdf a mixed shader node and then we're going to plug this 
[09:11](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=551) transparent bsdf as the second shader input this whole thing here is going to go in the first shader and the factory is going to be our 
[09:19](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=559) intercept value and so you can plug this into material output now at first you're not going to see anything because we haven't activated 
[09:27](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=567) transparency in a material but if you go under settings blend mode and change this to alpha ash off a blend you can sort of get the a nicer softer finish here and if you want to control 
[09:40](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=580) it a bit better you can create a color ramp as always put it just after the intercept and that way you can sort of play with the setting and uh 
[09:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=591) maybe change it to b spline or whatever to hide the top emitter here you basically have two options either you can add 
[10:02](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=602) a transparency at the root this way with the pure white so the top will disappear this way it's going to be a bit nice or 
[10:13](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=613) you can just go in your hair settings and um you can disable from viewport display show emitter and render show emitter that way it will just never show up but i still like to add a bit of uh 
[10:27](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=627) fading in the top here again to keep that sort of um painted stroke look okay so i'm pretty happy with how this looks right now and let's say i want to start duplicating 
[10:35](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=635) those hair strands and create more layering like in our reference so i can press shift d and move these around and i can also 
[10:44](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=644) go in particle edit mode and start like moving those pieces of hair but what's missing is that we're not getting those drop shadows that makes you really see the difference um 
[10:54](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=654) between these different layers so how do we do that well what we'll need is a diffuse bsdf and before i start like mixing things together i'd like to organize uh our 
[11:06](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=666) setup a little bit because we already have 10 nodes and it's already kind of difficult to see where things uh how they are related so let me create a frame 
[11:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=674) and this one i'm going to call it um [Music] noise make it a little bit bigger 
[11:22](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=682) let's make one called transparency another one called gradient finally diffuse so 
[11:32](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=692) the three nodes here is our noise the three nodes here are for transparency and then you have the gradient here 
[11:43](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=703) this is going to be in their diffuse and this one's going to be left alone because it's kind of a compositing stack we're going to have multiple of these mixed nodes just stacked 
[11:53](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=713) one behind the other just to mix those different frames together so how do we mix this diffuse with the rest well i'm going to create another mix node here 
[12:02](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=722) and the diffuse is going to be deciding where this black color appears and the rest here is going to be the lighted portion of our shader so if i plug this output into the factor 
[12:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=734) you're going to see i get an error because i need the shader to rgb node i'll just put this quickly in the same frame and that way 
[12:23](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=743) if i switch back you're gonna see uh i do have a key light here so if i move here you're gonna see a bit of a of a difference now 
[12:33](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=753) the problem is uh right now it's inverted first um i need to change this all right so now you see you're getting like a darker 
[12:45](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=765) portion here where it's casting shadow but you'll agree it's much too dark right now so let me create a color ramp as always our most useful friend and uh 
[12:56](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=776) we're going to be crunching that white value here as much as we can okay so before we continue i just want to explain something quickly about how normals work on the hair particles in 
[13:06](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=786) blender by default they're going to look like something on the right they're not going to be actually generated as cylinders because that 
[13:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=794) would be too heavy if you have tens of thousands of them they're actually just planes but blender is simulating the normals to look like the cylinder and the normals would look something 
[13:26](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=806) like this where the ones on the side here are going to be pointing sideways and it's great if you're doing realistic work because you get this really like 3d look 
[13:34](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=814) but in our case we want to do stylized work and another option you can use is tangent normals instead and what it means is that each of these sort of rings here is going to be taking its 
[13:45](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=825) normals from the general curve of the hair so you see how they're all pointing in this direction here and what it does is it creates a nicer gradient that's that's much better especially if you 
[13:56](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=836) look from a bit further away it looks more like something you would paint uh because you're not going to be adding shadows on each individual hair if you 
[14:06](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=846) paint them you're just going to be painting this like one colored stroke and maybe there's going to be a gradient to your stroke itself but not actual shading on each hair so adding those 
[14:15](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=855) tangent normals on your hair is really simple go to your hair info node and plug the tangent normal output to the normal of your diffuse bsdf and right away you can see the difference in 
[14:26](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=866) your scene now there's still a couple of things that will affect the look of your shadows one is in the render settings um 
[14:33](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=873) if you go under shadows cascade size you're gonna see that you get different results if you play with these settings and also one big thing is on your key light 
[14:44](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=884) itself under shadows and i think i can show you better if it's like kind of sideways okay so you see here how you you still 
[14:52](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=892) get those very like thin strands of black if you play with the bias of your light you can sort of um get rid of most of them so it's going to be looking um 
[15:03](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=903) more 2d and of course you can sort of um smooth out this light here by playing with the angle to make it a bit softer 
[15:13](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=913) so at this point you might be thinking well this is cool and all but this this kind of looks like a piece of geometry i could have modeled and extruded along curve 
[15:24](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=924) so why did we bother making it using hair particle and the reason is there's just so many cool options we can use with hair like uh first thing is let's say i click on 
[15:34](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=934) this hair strand and press edit mode well i can add some subdivisions to this original plane and then i can customize sort of the creases i get on my so if i 
[15:46](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=946) look at it from this angle you can see i can create these creases and really customize where i get these uh these darker shadows you know 
[15:59](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=959) also like right now if i play with these settings they're all going to be affected the same but if instead of doing shift d i do ctrl c 
[16:08](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=968) ctrl v and move it then this one's going to be unique so i could let's say i want to do this small strand of hair i can just maybe put i don't know 
[16:20](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=980) five hair or six hair i don't know uh maybe scale this like this okay and let's say i don't want this uh piece uh that the edge ear to be so pointy 
[16:36](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=996) uh i can go to the uh roughness use roughness curve and i could uh play with this curve here 
[16:47](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1007) to break up the edge you know like this so this is not something you can easily do with geometry and and this is really cool 
[16:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1018) okay so here i went ahead and created a couple more of these uh single hair using the ctrl c control v method i talked to you about just one thing to point out is when you 
[17:07](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1027) do this by default they're going to also duplicate the material so they're not going to be linked to the original material 
[17:16](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1036) and so you kind of have to relink it so what you can do is just sort of select all of them and maybe now unselect one that you know you want 
[17:26](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1046) the material from reselect it and then ctrl l link materials and so now they're all going to be 
[17:37](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1057) linked to the same material and if you play with the transparency setting or whatever uh they're all going to be connected all right so at this point there's just 
[17:48](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1068) two things that i feel are missing and let me take a screenshot of this in photoshop the first thing is a soft specular highlight and we don't want to have something like too intense 
[17:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1078) with lots of lines like this like you might see in a more realistic um shader we just want to have a soft highlight that gives it just a bit more volume 
[18:08](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1088) and then the other thing is we're missing is this rim light here as you see on this hair and it cannot just light like the side of the hair it needs to light up the whole 
[18:19](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1099) strand and we're going to do that with a translucent effect okay so let's start by adding the specular um we're going to use a method that's very similar to what 
[18:29](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1109) we did with the diffuse except this time we're going to create a specular bsdf then we'll need the shutter to rgb like we did with the diffuse 
[18:39](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1119) and the color ramp and then let's put this in a frame just to uh again keep things organized um 
[18:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1131) put it in there all right and to add it to our like our current shader we're going to use a mix rgb uh so i just duplicated it with jfb 
[19:01](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1141) and we're going to change this to add because we just want to add the specular on top so color one is going to be our previous mix 
[19:10](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1150) then we're going to add this um like light blue color and what's going to be basically the mask telling where this light book color appears is this 
[19:22](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1162) specular that we created so it's going to go in the factor let's contrast this a bit and [Music] 
[19:31](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1171) all right and this goes back into shader one here so let's look at uh how it looks right now all right so 
[19:43](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1183) it's not looking right the reason we're seeing all these uh very thin line and the reason is we forgot to um connect the tangent normal into the 
[19:53](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1193) normal input of the specular bsdf so again let's look at the current preview all right so much better although um it looks a bit tricky right 
[20:07](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1207) now uh it's it's got a nice shine to it but i feel like it's a bit too perfect so one thing we can do is um 
[20:17](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1217) break it up using the um the noise texture that we made and what we're going to do is you see all these lines that we made with the noise there's like alternating bright and darker lines so 
[20:28](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1228) what we're going to do is we're going to offset this specular um vertically depending on these lines so uh if certain lines are brighter then it's going to offset vertically the specular 
[20:41](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1241) a bit upwards and then downwards and it's going to just break up the specular so it looks less perfect basically and the way we're going to do that is by 
[20:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1251) messing up the the normal input here with a vector math basically it's just vector math is a node that lets you um do operations on a purple input like 
[21:04](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1264) this um which has three vectors and then we're going to use the color ramp output of the noise color up here and the second 
[21:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1274) vector input and we're also going to be creating a map range node and it's just going to give us a bit more control to decide how much offset we want 
[21:26](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1286) and what map range does is let me just move these things okay so what map range does is it takes these 
[21:37](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1297) values which which are going from zero to one uh black to white and so from min to max and then it says two min to max so you can change 
[21:48](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1308) the values from zero to one to go to something some like another min and max value so you could say instead of going from zero to one let's go from zero to point six and 
[21:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1318) it's just going to scale those values accordingly so um as you can see now i can play with these uh if i set it to zero zero there's 
[22:07](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1327) going to be no offset and then if i play with these values a bit i can sort of just move it around so i just don't want to add too much of it just just a little bit 
[22:18](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1338) um like this and if you don't want to have too much specular you can either um reduce the 
[22:28](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1348) take a darker color that you add on top or you can change this white value on the color ramp of the of the specular and make it darker so 
[22:38](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1358) it's going to be less opaque so i think this looks pretty good uh for specular and next i'm going to show you how to add the uh the translucent effect for the nice trim light on the left here 
[22:52](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1372) okay so to make the rim light effect we're going to use a translucent bsdf and i know some of you are starting out or maybe confused about what actually is a bsdf shooter so i've set up a simple 
[23:03](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1383) scene here with three basic planes one with diffuse one with specular and one with translucent i'm i'm just gonna explain to you what it does so um 
[23:12](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1392) on this one i have a bsdf uh a diffuse bsdf and here i have a point light so if i move my point light you see uh this one is getting all the light information in my scene in this case i just have a 
[23:23](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1403) light and if i use the color ramp i can sort of crunch that information but if i move my camera uh the information is going to be the same because it's just getting the 
[23:33](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1413) diffuse information now on this one i have specular bsdf and so if i move my camera we can see it's a specular it's it's that light getting reflected in it like a mirror and um 
[23:47](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1427) if you by default i think the base color on the specular is white so you're going to pick up diffuse information also but if you bring that value down to something darker you're going to get 
[23:56](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1436) just a specular now the third one the translucent bsdf is not going to pick up any light from the front what's special about it is it's getting 
[24:05](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1445) light from behind so it's very useful for things like leaves in a tree and stuff like that and it's going to work great for us for hair because if you stack let me just show you 
[24:15](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1455) uh multiple of these um planes on one in front of one another you're sort of going to see the light getting um lost across that depth of plane so the 
[24:28](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1468) more planes you have and the less light is going to get true and this is great because like you see each of these planes have no depth technically but you can sort of see that 
[24:39](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1479) um through it using this translucent effect and this is exactly what we're going to be using to make the rem light on our hair okay so to add the last effect 
[24:50](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1490) translucency we're going to create the translucent bsdf a shader to rgb and a color ramp 
[25:00](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1500) let's plug this in plug this in this time let's not forget to connect our tangent normal coming from our hair info here i'm gonna create a frame 
[25:16](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1516) all right put this all into it um this time i don't think i'm going to be using a add mix i'm just going to be using a 
[25:25](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1525) standard mix node use the output of our color ramp into the factor and use some kind of like desaturated 
[25:38](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1538) purple like crunch the color ramp a bit and let's see how this looks okay so we're not seeing anything that's 
[25:48](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1548) normal as you remember um it's only going to be picking up light that's coming from behind so we could duplicate that q-lite and if 
[25:58](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1558) okay so if i make it coming from the back here um it's not picking up anything because it's not strong enough 
[26:11](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1571) but if i make the strength like something like then now it's going to be picking up the the rim light here and personally like it works with the 
[26:22](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1582) sunlight i really like using point lights for this because um well you have a couple more options like a custom distance so let's say you just 
[26:32](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1592) want to pick up a rim light at the top here but not at the bottom uh you can set up a distance of like i don't know one and then maybe that's too low 
[26:41](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1601) two yeah so you're only going to be picking up that that top part here and um other options you can play with is the well clip start you just want to keep it 
[26:51](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1611) low because if it's too high it's going to mess up your the look of it but bias is pretty nice if you bring it back up you're going to get like 
[27:00](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1620) further into the um the hair i guess because you're changing the bias of how shadows are casted and this is how it determines um how much 
[27:14](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1634) it goes into the different planes stacked on top of one another so um yeah it's pretty much uh best way i found to have a cold rim light effect 
[27:25](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1645) and create this this arcane style so that'll be it for this tutorial i hope you can take something from these tricks and apply them to your own characters next week we're going to 
[27:34](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1654) release a second part where i'm going to show you some of my favorite texture painting tricks and how to do camera mapping so hope to see you there and thanks 
[27:45](https://youtu.be/FXuReln3XD0?si=qTGf8EYvGQ2vsfsb&t=1665) again for watching you 