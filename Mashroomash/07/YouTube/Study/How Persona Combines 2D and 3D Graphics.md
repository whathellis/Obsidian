---
URL: https://www.youtube.com/watch?v=dVWkPADNdJ4
thumbnail: https://i.ytimg.com/vi/dVWkPADNdJ4/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T13:09:20
published: 2024-02-29T10:56:41
duration: 1365
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "22m 45s"]
# How Persona Combines 2D and 3D Graphics
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722130948.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=dVWkPADNdJ4
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/dVWkPADNdJ4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: Get a free 30 day trial and 20% off an annual plan at
https://brilliant.org/acerola ! 

Persona 3 Reload is the official remake of my favorite game of all time and I'm very impressed with the visuals! Today we take a look at how much of it is shader work versus artist illustration and how it all gets put together.

Topics covered: Non photorealistic rendering, fresnel, ray traced vs screen space reflections, z prepass, shadow mapping, forward rendering, deferred shadows, screen space ambient occlusion, global illumination, transparency, 3d models as ui elements

Support me on Patreon!
https://www.patreon.com/acerola_t

Socials:
Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Github: https://github.com/GarrettGunnell/

This series is largely inspired by Muhammad's "Behind The Pretty Frames" series of articles which you can read here: https://mamoniem.com/category/behind-the-pretty-frames/

Music:
Afternoon Break - Persona 3 OST
Afternoon Break - Persona 3 Reload OST
In A Moment's Time - Skullgirls OST
Junes Theme - Persona 4 OST
During The Test - Persona 3 OST
During The Test - Persona 3 Reload OST
A New Frontier - VA-11 Hall-A OST
Those Who Dwell In The Shadows - VA-11 Hall-A OST
Every Day Is Night - VA-11 Hall-A OST
Underground Club - VA-11 Hall-A OST
Like A Dream Come True - Persona 4 OST
Layer Cake - Persona 5 OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:12](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=12) hello everyone Persona 5 walked so Persona 3 reload could run with improved character models stylistic lighting Ray tracing and of course its beautiful user interface and VFX like just look at 
[00:26](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=26) [Music] this you're on our [Music] own each individual menu is a piece of 
[00:47](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=47) art to be admired which has me wondering how much of this is artist authored how much credit goes to Graphics programming and lastly how could we make it all ourselves 
[01:05](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=65) just like last time with lethal company we'll be using Invidia insight to analyze every aspect of persona 3's rendering from start to finish typically the user interface is drawn last so 
[01:15](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=75) let's do a general overview of the game's rendering up to when the UI would be drawn obviously Persona 3 isn't seeking to be a realistic game so we refer to its visuals as 
[01:26](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=86) non-photorealistic rendering instead of physically based rendering but just because Persona 3 isn't physically based doesn't mean it isn't following its principles in fact most of the time NPR 
[01:36](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=96) is underneath the umbrella of PBR because it's no different than stylized art and other mediums as an illustrator or painter you learn to draw from reality first in order to learn the 
[01:47](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=107) rules everything abides by as well as develop an understanding of anatomy and where things should generally go only after you've learned the rules can you properly break them and simplify to your 
[01:57](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=117) desired level of stylization it's the same with non-photorealistic rendering stuff like tune shading is usually a simplification of physically based rendering these techniques are invented 
[02:07](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=127) by those who know the rules and how to break them to get desired results with that in mind let's take a look at the game but first something a little different this video has been sponsored 
[02:17](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=137) by brilliant brilliant is the best way to learn math data science and computer science interactively brilliant offers thousands of lessons from basic to Advanced so if you're just getting 
[02:27](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=147) started learning math or are brushing up on your linear algebra for graphics programming brilliant has something for you even if you don't know where to start that's no problem brilliant 
[02:36](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=156) customizes his content to fit what you need just take a quick quiz when you sign up and Brilliant will match you with lessons that fit your interests and your level of expertise I personally use 
[02:46](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=166) brilliant whenever I need a quick and accessible refresher on math concepts I haven't worked with in a while such as complex numbers or some aspect of calculus I appreciate that brilliant 
[02:56](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=176) makes it easy to find lessons on topics I'm looking for be sure to try out everything brilliant has to offer with a free 30-day trial and 20% off an annual plan when you visit brilliant.org slace 
[03:08](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=188) Rola or click the link in the description thanks so much to brilliant for sponsoring this video here in the dorm room we walk underneath a light source to see how the light interacts 
[03:18](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=198) with the protagonist immediately you can tell the difference the light source makes compared to when the protagonist is only in ambient light it also clearly shows us which details are mostly artist 
[03:28](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=208) authored and which are driven by Shader in physically based rendering all of the detail comes from lighting calculations in the Shader because that's how the real world works we see things because 
[03:37](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=217) light bounced off of it and into our eyes we use the normal Vector a vector orthogonal to the surface at any given point to determine how lit a pixel should be which is where shadows and 
[03:48](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=228) thus detail comes from these normals are stored in each pixel of something called a normal map which is a texture that gives us highly detailed 3D models by allowing the lighting calculations to 
[03:58](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=238) operate per pixel instead of per vertex this is combined with something called an albo map which stores the color information of a 3D model without regard to any sort of shading we take the 
[04:09](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=249) direction of the light source and the normal Vector calculate the dot product and then multiply it with the albo to get the diffused lighting which is added to the ambient light the dot product is 
[04:19](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=259) like an exposure value for the albo a DOT product of zero reduces the resulting color to black meaning in that case the pixel was facing away from the light source and was thus in Shadow I 
[04:30](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=270) have a Shader here that does exactly that given these two textures you can see that the parts of the sphere pointing away from the light are shaded and on a per pixel level the normal map 
[04:39](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=279) drives all of the finer details while this is cool and physically correct it also looks very harsh and ugly the solution is to add more lights because again that's how it works in the real 
[04:50](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=290) world but having all these details dependent on the position and direction of existing light sources can be frustrating and the more light sources you add the more expensive everything 
[05:00](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=300) gets this is where Persona 3 Breaks the Rules details like clothing wrinkles are not driven by some complex normal map but rather just painted onto the character so that they are always 
[05:10](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=310) present and are unaffected by poor light conditions we can see the clothing wrinkle Shadows don't change when the protagonist is under the light instead the light source serves to cast physical 
[05:20](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=320) shadows and brighten the character where the light hits Persona 3 makes use of another PBR concept known as frenel which is where this slight Rim lighting comes from frenel is something you 
[05:31](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=331) observe every day it is the phenomenon in which the strength of a reflection is dependent on the viewing angle this is easily observed with water when you're at a lake and you look straight down at 
[05:41](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=341) the water you can see through it just fine but very quickly as you go towards the horizon the water surface becomes more mirrorlike as the strength of the reflection increases towards the grazing 
[05:51](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=351) angles it is also observed in hallways with shiny floors or right here on the protagonist shoulders and hair where the angle of inci Ence is greatest you can see that the reflection on the shoulders 
[06:02](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=362) disappears when you look down at them other than that there isn't much else the lights in Persona 3 reload are doing but we've still got more to look at the game has very nice edges on its 
[06:12](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=372) character models these aren't painted on like the clothing wrinkles because you can see the edges change dynamically with the animations so there's some sort of edge detection Shader technique at 
[06:21](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=381) play we also have a very tasteful amount of Bloom which is responsible for the light looking so soft then there's this weird sort of line effect on Shadows whether or not this is an intentional 
[06:32](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=392) comic book- like effect or a Shader artifact is unknown lastly we have Ray tracing if you have terrible frame drops while playing this game it's because you don't have a 20 series or better GPU 
[06:43](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=403) with Ray tracing hardware and should disable Reflections in the graphics settings if you disable Reflections the game swaps to screen space Reflections instead of Ray traced the difference in 
[06:53](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=413) quality is very obvious in the tardus lobby though with Ray tracing enabled the reflection of the clock is always visible regardless of camera angle whereas with the shitty screen space 
[07:03](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=423) Reflections the clock gets cut off once it's no longer on screen but you can tell that this area was designed for screen space Reflections the default camera view is very conveniently placed 
[07:14](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=434) such that you can't see the clock cut off this means the ray tracing was probably an afterthought in the design process which is unfortunate now that we have a general idea of what's going on 
[07:24](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=444) let's hop into the frame capture to see how it all gets put together let's start by taking a capture here in the protagonist room where we can get close to the camera there's actually a 
[07:32](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=452) graphics bug in view but I'll point it out later unlike lethal company Persona 3 reload is made with Unreal Engine and is also a AAA production so we can expect a more sophisticated and concise 
[07:44](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=464) render unfortunately because it's a AAA production a lot of information is absent like the names of the shaders and textures that information is what made it really easy to tell what was going on 
[07:54](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=474) with lethal company but without it I have to try a bit harder with my eyes to decipher for the techniques at play instead of taking the easy route with metadata this Frame capture contains 
[08:05](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=485) 7,612 events and starts out with something called a z prepass a z prepass also known as a depth prepass is a common Graphics programming technique used to avoid something known as 
[08:17](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=497) overdraw overdraw is what happens when a pixel gets written to multiple times during a frame render imagine we drew a rectangle that covers the screen that's all well and good but now imagine we 
[08:27](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=507) drew another rectangle on top of it for some reason we'd now have one full instance of overdraw and wasted all of that work we did to draw the first rectangle because we can't see it 
[08:37](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=517) anymore this doesn't sound like that big of a deal until you run some numbers a 1920x 1080 monitor contains a little over 2 million pixels so we wasted 2 million instances of our Shader you can 
[08:49](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=529) then imagine why it would be very unoptimal to do some complex calculations like Ray tracing only to throw it away and do it again on top of it when that first instance of work is 
[08:59](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=539) is already costing you a lot of your performance budget any bit of overdraw could be enough to end your career a number of solutions exist such as deferred rendering which I explained in 
[09:09](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=549) the lethal company video draws all the objects on screen and then does the complex lighting calculations as a postprocessing effect ensuring that there is no overdraw another solution is 
[09:19](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=559) the Z prepass where we draw all the objects in view to the depth buffer first allowing shaders to stop what they're doing if the pixel they are about to write to is behind the pixel 
[09:28](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=568) that already exists in the depth buffer avoiding the complex calculations and saving you from wasting work at the cost of doubling up on your vertex shaders Persona 3 reload chooses the route of 
[09:39](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=579) the Z prass which must have you wondering if deferred rendering is a solution to overdraw and Persona 3 is using a different solution does that mean Persona 3 is making use of forward 
[09:50](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=590) rendering instead of deferred Persona 3 is forward rendered meaning it does all of its light calculations immediately when the object is drawn but we we still have to do one thing before the lighting 
[10:01](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=601) stage can execute the next stage of persona 3's rendering is a technique known as Shadow mapping you might not have ever thought about it before but Shadows are often the most expensive 
[10:11](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=611) part of a render pipeline it's a very non-trivial problem and there's a reason a lot of older games have completely fake Shadows but a Rolla couldn't you just look at the pixel's point in space 
[10:22](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=622) and then draw a line between that point and the light source to see if there are any objects in between that the line collides with thus casting a shadow on that pixel yeah you could do that that's 
[10:33](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=633) called Ray tracing hopefully this demonstrates how intuitive convenient conceptually simple and absolutely accurate Ray tracing is for just one of its many use cases but unfortunately Ray 
[10:46](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=646) tracing is expensive so we have to devise another solution since we want to know if another object is in between the light source and the pixel we are drawing but 
[10:56](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=656) we are unable to actually know about all of the object around the pixel then we have to do it cleverly with texture data if we do the same thing as the Zep repass from earlier but from the 
[11:06](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=666) perspective of the light source instead of the camera we can write the distance of each object from the light source to something called a shadow map then when we're rendering a pixel we check if it's 
[11:16](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=676) behind an object in the shadow map and if it is it's in Shadow this method while clever has many drawbacks for instance we need to do this Shadow mapping process for every single light 
[11:27](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=687) source that we want to be able the cast Shadows which gets extremely expensive the more complex your scenes are this is why foliage and video games never cast Shadows really because imagine how 
[11:38](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=698) expensive it would be to render all of your grass multiple times for every light source it's just not possible another issue is that the quality of our shadows is limited by the texture 
[11:49](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=709) resolution of the Shadow Maps the higher resolution they are the more accurate the shadow information and the better the Shadows look but the memory cost and bandwidth quickly becomes a bottle neck 
[11:59](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=719) despite these problems Shadow mapping is used by pretty much every game because it's cheaper than Ray tracing and the only alternative is just faking your shadows with a mesh or the infamous 
[12:09](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=729) Circle drop shadow you can see Persona 3 reload filling in its shadow Maps here to prepare for the forward lighting pass for whatever reason it wastes time rendering a shadow map for the light 
[12:20](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=740) that's in the hallway on the other side of the door this is probably a bug but it barely renders anything at all so it doesn't matter that much with the shadow mapping finished the lighting stage is 
[12:30](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=750) ready to execute like I said earlier Persona 3 is forward rendered so lighting is done at the same time the object is drawn in the last video I mentioned that in the real world games 
[12:41](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=761) are usually a weird combo of forward and deferred which is true here as well Persona 3 is writing out a lot more information than just lighting results for future effects unfortunately it's 
[12:52](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=772) kind of impossible to know what this data represents without extensive investigation but the obvious stuff is the normal which we can see are very simple and serve to accentuate the 
[13:02](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=782) overall shape of the model instead of juice out more detail also because of the Z prepass we don't have to worry about wasting work on pixels that are behind other pixels the edges of the 
[13:12](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=792) protagonist are drawn before anything else we can see that there is a whole 3D model here for these edges so Persona 3 must be using some variant of the inverse hole technique which is where 
[13:23](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=803) you discard pixels that are facing towards the camera so the edges are only drawn on borders and the player model under is still visible there is a discard instruction in the Shader 
[13:32](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=812) assembly so it's certainly doing something in that ballpark but how exactly the discard is determined is buried underneath a lot of logic after that it's business as usual every object 
[13:42](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=822) in view is drawn with lighting but you'll notice there aren't any cast Shadows this means we're looking at the diffuse light only right now and they decided they want to do Shadows later 
[13:51](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=831) after all the objects have been drawn the game draws the player again into a mask so that presumably future effects can operate on only the the player or on everything except the player since the 
[14:01](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=841) Bas lighting is done and all the objects have been drawn we move on to postprocessing the first post-processing effects are going to be those that mess with the lighting of the scene because 
[14:11](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=851) it's making adjustments to what exists physically in space generally this means effects like screen space Global illumination or screen space ambient occlusion which Persona 3 reload is 
[14:21](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=861) doing here in this case it is ambient occlusion Persona 3 is approximating the absence of ambient light in places where light would be hard to reach despite being used for realism in games quite 
[14:33](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=873) often it is actually not realistic in the slightest which is why it works great for our stylized game we can also see a very strange pattern to the ambient occlusion which looks 
[14:42](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=882) suspiciously similar to that weird line pattern we saw earlier in our visual study we'll know why it looks like this when we learn how we approximate ambient occlusion to begin with for each pixel 
[14:53](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=893) we want to do a number of samples in a hemisphere around that point in space to check how many many samples intersect with another object in the depth buffer if there are a lot of intersecting 
[15:03](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=903) points then that means it's probably hard for light to get to that spot so it's probably going to be a little darker while the logic is admittedly simple the results are pretty nice the 
[15:13](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=913) more samples you do the more you get a perfect approximation if this confuses you please take a moment to review integral calculus and then come back unfortunately it's very expensive to do 
[15:24](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=924) even a small amount of samples so you want to try as hard as you can to get a decent distribution of directions in your small sample pool for a better approximation generally this means your 
[15:34](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=934) distribution is uniformly random and so the result is visibly noisy this is then usually solved with something like a basic D noiser or if you combine it with temporal anti-aliasing you get perfect D 
[15:45](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=945) noising for free Persona 3 doesn't use random numbers for their ssao they use dither noise which is why we see a dither pattern in the ambient term this is because the developers know the noise 
[15:57](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=957) is going to be visible no matter what and having white noise on the characters would be ugly so they opted to go with the stylized dither noise to turn what would normally be a con of ssao into a 
[16:08](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=968) pro and adding a little spice to the visuals of the game the ssao gets multiplied with the additive lighting buffer to add more interesting shading and the frame continues on next up is 
[16:19](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=979) the hard Shadows Persona 3 uses the shadow maps of each light source we made earlier to create a shadow mask for the scene there's one pass for each light source but there's only two lights the 
[16:29](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=989) sun outside and the light in the room it's interesting to note that the game creates these Shadows with inverted shading logic instead of darkening the areas in Shadow everything that isn't in 
[16:39](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=999) the shadow mask gets brighter giving the scene its much needed brightness adjustments instead of making everything even darker except for these window spots that's not the only thing that's 
[16:49](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1009) going to brighten up the room though as the next portion of the frame uses Ray tracing for indirect lighting which gives us Global illumination and Reflections on the GL vossy surfaces 
[16:59](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1019) most people would probably never notice that the bedst stand and laptop screen are reflective for some reason the wood material is reflective as well these Reflections are composited with the 
[17:10](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1030) lighting buffer and the scene is further illuminated giving us pretty much the finished scene lighting to put into perspective how expensive the ray tracing is just for this very simple 
[17:20](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1040) adjustment it took longer to calculate these Reflections then it took to do everything else we have covered in this video so far this is because I am playing on a 1660 a GPU without Ray 
[17:30](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1050) tracing Hardware so my GPU is quite literally not built for this if I did have a 20 series or better it would be way faster with all that lighting finished it's time to draw all the 
[17:40](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1060) transparent objects in the scene but a Rolla I thought we were doing postprocessing right now this is AAA Graphics programming we do whatever we want wherever we want whenever we want 
[17:51](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1071) take your sensitive ass back to unity's built-in rendering pipeline the transparent objects include the actual window pains themselves these secondary drapes and the Shadows on the 
[18:03](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1083) protagonist's face that's right these cool stylized Shadows on the character models are fake and are actual meshes so the artists can have absolute control over them while you could use some 
[18:14](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1094) sophisticated techniques like screens space Shadows to get a similar look this mesh approach is very cheap and easy and pretty common especially in the VR chat space as post-processing effects are too 
[18:26](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1106) expensive for VR so the mesh ends up having to do a lot of the heavy lifting this is also where the graphics bug appears the transparency on the window in the back is all messed up and noisy 
[18:36](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1116) for some reason after the transparent objects are drawn we go back to postprocessing the next pass is a coloriz on the protagonist using the mask we generated earlier to do some 
[18:46](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1126) color Corrections and sharpen details which exaggerates the borders of the Shadows making them look a bit cooler and more illustrative the frame then finishes with anti-aliasing and some 
[18:57](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1137) final color Corrections to smooth out the crispy edges and make the room look cooler since this scene is in the morning time we missed the bloom because nothing in view here is bright enough 
[19:07](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1147) apparently but it would probably be applied on these same passes anyways just like in Lethal company with its final Uber post pass now that the game is all rendered it's finally time for 
[19:17](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1157) the cool user interface no not this UI this UI despite appearances you might think this is being drawn after the game is rendered but it's not it just uses the render from when the game was paused 
[19:29](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1169) in order to not waste resources because of this optimization the frame capture is only 376 events instead of being an additional 3,000 events to the previous 7,600 it's very difficult to account for 
[19:43](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1183) my own perceptual biases now so I'm not sure if it's obvious to everyone that this is a 3D model in the background but the frame starts with the Z prepass of the 3D model then its edges and lighting 
[19:54](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1194) get drawn just like the last capture but since there's no lights then all all of the Shadow mapping and related passes get skipped and it's finished essentially we swapped out the old game 
[20:03](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1203) scene for this new scene that contains a floating model of the player and yeah it is the same model as the one used in game just with different textures and as coloring is the result of a screen space 
[20:14](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1214) mask for the water background texture after the new scene is finished drawing the UI gets assembled the two water costic effects are rendered to separate buffers and blurred a bit since 
[20:25](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1225) everything is transparent we draw from back to front so that elements are Blended on top of the previous elements first we draw the background image which is the original render from when we 
[20:34](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1234) paused except it's posterized meaning the values of the image were reduced to a smaller amount of values and then mapped to this dark blue to White gradient then the image is Warped with a 
[20:44](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1244) wave to make it look like it's being seen through water and it's tinted heavily towards light blue the two cosics from earlier get Blended on top and a transparent dark blue gradient is 
[20:54](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1254) drawn to add some depth to the water another gradient is drawn upwards towards a lighter blue and this cool white shape is drawn on top text indicating this is the main menu gets 
[21:04](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1264) drawn and the 3D model from earlier finally comes back lastly a bunch of cool little confetti particles are Blended to add some visual flare and all the buttons are 
[21:13](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1273) drawn it's the same process for all the different menus in Persona 3 they are each a different pose of the same 3D model this one is probably my favorite but what about the Battle UI 
[21:26](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1286) it's the same deal clever Reus of the same models with different shaders applied to the simple geometry to create stylized UI elements this is a wonderful demonstration of how proper use of 
[21:37](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1297) different camera angles and poses can make the same asset look new and interesting rather than come off as cheap and repetitive but what about the allout attack finisher cards 
[21:47](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1307) unfortunately this is not God's greatest gift to stylized shaders it is a very clever Switcheroo from 3D to a drawn jpg so out of everything this is the only thing that is entirely artist authored 
[21:59](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1319) in the end Persona 3 reload demonstrates how the fundamentals of physically based rendering can still be used in stylized contexts as well as how to reuse assets the right way with this much of an 
[22:11](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1331) improvement on the visuals of Persona 5 and the experiments with Ray tracing I'm very excited to see what Atlas has in store for Persona 6 by the way the theme announcement for my first ever game Jam 
[22:22](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1342) event is going to be announced live on the channel here in a few minutes so come check that out also if you'd like to support the channel you can help me out over on patreon as usual a huge 
[22:33](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1353) thank you to all my existing patrons without your support I wouldn't be able to play Persona 3 reload for 3 days straight while saying I'm working that's all for me I hope you have a great rest 
[22:42](https://www.youtube.com/watch?v=dVWkPADNdJ4&t=1362) of your day and I'll see you next time 