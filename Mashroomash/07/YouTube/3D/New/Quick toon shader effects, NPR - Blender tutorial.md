---
URL: https://www.youtube.com/watch?v=faz3oSuDivE
thumbnail: https://i.ytimg.com/vi/faz3oSuDivE/default.jpg
channel: "[[Joey C-quel]]"
date: 2024-07-16T14:38:19
published: 2023-10-31T01:41:52
duration: 1883
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240716143845.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "31m 23s"]
# Quick toon shader effects, NPR - Blender tutorial
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716143845.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Quick toon shader effects, NPR - Blender tutorial" src="https://www.youtube.com/embed/faz3oSuDivE?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Cel shading, screentone, halftone, watercolor, outline, non photorealistic rendering. Wahoo)

🔗Links
Patreon: https://www.patreon.com/joeycarlino
Discord Server: https://discord.gg/dvmAZdwf5e
Gumroad Shop: https://gumroad.com/joeycarlino?a=844339507
Blender Market Shop: https://blendermarket.com/creators/joeycarlino
TikTok: https://www.tiktok.com/@joey_carlino
Instagram: https://www.instagram.com/robospunk/
Twitter: https://twitter.com/joey_carlino
Personal Email: JoeyCarlino@gmail.com
Busniness Email: JoeyCarlino@makrwatch.com

💰Support me by checking out these affiliate links:
https://linktr.ee/joeycarlinoaffiliate

🧠Things I Recommend (not affiliated)
Dotbow Blender Launcher: https://dotbow.github.io/Blender-Launcher/
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
 
00:00 - Setup
01:29 - Cel shading color ramp
03:37 - Cel shading greater than
05:41 - Cel shading map range
09:44 - Screen tone
19:49 - more automatic cel shading
22:17 - Outline
24:55 - Watercolor
# Transcript
[00:00](https://www.youtube.com/watch?v=faz3oSuDivE&t=0) all right so on the main Channel I am already working on a video about tune shaders and things like that but uh just to go a little more in depth than making this one also so just make sure that you 
[00:12](https://www.youtube.com/watch?v=faz3oSuDivE&t=12) have a light in your scene I'm using 4.0 which means that screencast Keys is broken so you're just gonna have to try to follow along without that unfortunately and as always make sure 
[00:23](https://www.youtube.com/watch?v=faz3oSuDivE&t=23) that you're using node Wrangler because I you know I will be using that and pretty much everybody who is working in the Shader node editor is going to be using that all right so I'm just going 
[00:33](https://www.youtube.com/watch?v=faz3oSuDivE&t=33) to get rid of that camera for now and go to the shading tab right here I'll add in a Suzanne control 2 to add a subdivision surface modifier right here and I'll right click and shade smooth 
[00:47](https://www.youtube.com/watch?v=faz3oSuDivE&t=47) let's go to render view now over here and I'm just gonna set the world Shader right here to be a little lower maybe like point three something like that and the light that you use doesn't really 
[00:59](https://www.youtube.com/watch?v=faz3oSuDivE&t=59) matter to too much as long as you can actually see it influencing it right here I'm also going to make the background transparent just because I enjoy that more alright so uh let's add 
[01:09](https://www.youtube.com/watch?v=faz3oSuDivE&t=69) a new uh Shader right there a new material and uh don't worry about it looking different in in 4.0 um it's basically the same old principled Shader that you know all the 
[01:21](https://www.youtube.com/watch?v=faz3oSuDivE&t=81) options are just you know under these little drop downs now so don't worry about that basically the whole idea or the whole like workflow with tune shaders for the most part is gonna be 
[01:35](https://www.youtube.com/watch?v=faz3oSuDivE&t=95) using the Shader to RGB node right here and this only works in Eevee so make sure that you're using EV this doesn't work with cycles and then after this you can do anything you want to basically 
[01:48](https://www.youtube.com/watch?v=faz3oSuDivE&t=108) manipulate this color right here so commonly what you'll see is people use a color ramp like this and then you can just do whatever you want with these values you can turn it constant and it 
[02:01](https://www.youtube.com/watch?v=faz3oSuDivE&t=121) will immediately look kind of cell shaded where it's like solid colors like that you just have to move these around to get different results another thing you might have noticed is that it's a 
[02:13](https://www.youtube.com/watch?v=faz3oSuDivE&t=133) little it's supposed to be solid but we do still have some gradation right there there are a few things that you can do to try to fix that so and they're all gonna mostly have to do with your light 
[02:24](https://www.youtube.com/watch?v=faz3oSuDivE&t=144) so my light right now is an area light and if I go to the settings right here and just make the size zero it's gonna be a little better but another thing you can do is just turn off Shadow right 
[02:35](https://www.youtube.com/watch?v=faz3oSuDivE&t=155) here and it's not going to have as realistic like uh Shadows like like overhangs that would be casting Shadows like right here should be making the eye completely dark it's not going to do 
[02:50](https://www.youtube.com/watch?v=faz3oSuDivE&t=170) that when this is off but it will when it's on but when it's off it looks much cleaner so a lot of people like to do that I'm actually going to leave it on and I'm just going to change to a sun 
[03:01](https://www.youtube.com/watch?v=faz3oSuDivE&t=181) let's maybe make the strength five and I'll turn the angle all the way down the angle is is like the size of the light basically so if I turn it up a lot higher it's going to get softer like 
[03:11](https://www.youtube.com/watch?v=faz3oSuDivE&t=191) that so I'll just set it to zero and I'll pull it to the front a little just so we have a little more casting on the face but yeah so most of the tune shading things that you'll see in other 
[03:22](https://www.youtube.com/watch?v=faz3oSuDivE&t=202) videos are going to be using this method right here and you can change these to whatever colors you want so make it this a darker color and then we can push this way over here 
[03:33](https://www.youtube.com/watch?v=faz3oSuDivE&t=213) and maybe make another one in the middle that's a little lighter like this you turn the saturation down a little bit so now we have three colors right there it does in my opinion it looks pretty cool 
[03:45](https://www.youtube.com/watch?v=faz3oSuDivE&t=225) also even when you're not using constant just when you're like crunching the values a little more so you can you can get it pretty close and it's just like a little softer like that I still think 
[03:57](https://www.youtube.com/watch?v=faz3oSuDivE&t=237) that looks cool so yeah let's instead of using the color ramp you can also use a few other nodes so if you're just going for that hard cell shaded look you can use a math node and set that to greater 
[04:11](https://www.youtube.com/watch?v=faz3oSuDivE&t=251) than and that will basically be like the color ramp set to constant with only a black and white with you know two colors like that so you can do that also you could even use a few of these and 
[04:25](https://www.youtube.com/watch?v=faz3oSuDivE&t=265) add them together so the way that you would do that I haven't actually experimented with this but it should be pretty easy if you just get a mix color right here and just keep using these for 
[04:37](https://www.youtube.com/watch?v=faz3oSuDivE&t=277) the fact so if we have two of these you want to make sure that they're both using the um color like that into the value and I'll set this one to be a little higher so let's get two of these 
[04:48](https://www.youtube.com/watch?v=faz3oSuDivE&t=288) they're both going to be controlling the factor and then this one will be plugged into the second slot of the first one like that so now we can have three colors we'll make this one dark like 
[05:01](https://www.youtube.com/watch?v=faz3oSuDivE&t=301) that and I'll make this last one white this one would be like whatever middle color we want basically so we can do another thing let's make it blue this time just uh for some variety and then 
[05:13](https://www.youtube.com/watch?v=faz3oSuDivE&t=313) this one will do like dark blue like that so this is a way to make like basically uh if you were to turn this into a group you would be able to control all the colors from the outside 
[05:23](https://www.youtube.com/watch?v=faz3oSuDivE&t=323) whereas with the color ramp you don't have any inputs for the colors so you know we could group this up by selecting it all hitting Ctrl G and then you could you know take the group input use this 
[05:35](https://www.youtube.com/watch?v=faz3oSuDivE&t=335) for all the colors you know if you want probably makes sense to to name these instead of aab you could name them by pressing n or opening up this thing over here under group you could just change 
[05:47](https://www.youtube.com/watch?v=faz3oSuDivE&t=347) this to like color one two and three or whatever if you're planning on reusing it probably you know spend time making it a little cleaner and then we have uh these two thresholds so then from the 
[05:57](https://www.youtube.com/watch?v=faz3oSuDivE&t=357) outside you have three colors and you can change them all in here make it look them nicer like that there is a another way of doing this that gives you a little more control over like like if 
[06:11](https://www.youtube.com/watch?v=faz3oSuDivE&t=371) you don't want to be hard edged like that but you want it to be more like this you could instead use a map range and uh mostly you would just be using the from Min and the from Max so 
[06:22](https://www.youtube.com/watch?v=faz3oSuDivE&t=382) normally what I would do is just um crunch these numbers together this is basically gonna work just like the color ramp where these uh values are going to be like the position values right here 
[06:35](https://www.youtube.com/watch?v=faz3oSuDivE&t=395) that you're seeing so you know this one if we have it set to zero and one that would be like like this but if we set this to like 0.4 and 0.6 like that that would be the 
[06:47](https://www.youtube.com/watch?v=faz3oSuDivE&t=407) same as 0.4 oh that's 1.6 and this one would be 0.4 it's going to work the same exact way let's let's actually test it out because I'm curious so this should look exactly the same like that but you 
[07:02](https://www.youtube.com/watch?v=faz3oSuDivE&t=422) have the added benefit of being able to you know control all of these uh from a group just like this so just so that we can have one that's that's like hard Edge I'll do a hard Supply shade like 
[07:15](https://www.youtube.com/watch?v=faz3oSuDivE&t=435) that actually style shading is supposed to have one L I believe you could do the same thing where you have two like this except you can control how hard or soft they are basically what you want to do 
[07:26](https://www.youtube.com/watch?v=faz3oSuDivE&t=446) is just make sure that this first one right here you're just going to be looking at the from Max you want that to be the same as the from minimum for the next one so the way that I like to do 
[07:37](https://www.youtube.com/watch?v=faz3oSuDivE&t=457) this you could either use three value nodes like this it would be like the low the medium and the high so you would do this into the from minimum this into the from Maximum and then the next one 
[07:50](https://www.youtube.com/watch?v=faz3oSuDivE&t=470) they're gonna share this value like that and this is how you would control it and then you could do the same sort of setup with the mix color right here so this is going to be controlling the factor of 
[08:03](https://www.youtube.com/watch?v=faz3oSuDivE&t=483) this one this is going to be controlling the factor of the second one and then just like before we're just going to plug it into the second one right here if you wanted more you would basically 
[08:12](https://www.youtube.com/watch?v=faz3oSuDivE&t=492) just do the same thing like that just plug it into the second one and then you would have four colors but I'm not going to do that I think it's a little like this is fine we can we can just do this 
[08:23](https://www.youtube.com/watch?v=faz3oSuDivE&t=503) one I'll make this one green so that one I'll just copy paste this into each make this lighter and a little more desaturated and then this one completely like that so this one you have a little 
[08:36](https://www.youtube.com/watch?v=faz3oSuDivE&t=516) less control over like how close you want all the values so usually instead of setting it up with three values like this I'll use add I'll use add nodes so that's a math node just set to add like 
[08:50](https://www.youtube.com/watch?v=faz3oSuDivE&t=530) this so you can have basically you could add this in like that that would control the second one and this is for the second uh for the from minimum value also and then this you're adding it 
[09:04](https://www.youtube.com/watch?v=faz3oSuDivE&t=544) again so you would do it like this so everything is basically um relative to the first one and if you want you could even use the same value for both of these so uh let's just set this to point 
[09:14](https://www.youtube.com/watch?v=faz3oSuDivE&t=554) one just so it's quite a bit closer like that and then uh when we push this you can see all the colors are pretty close and we can kind of control the sharpness of it like how big the fall off is with 
[09:26](https://www.youtube.com/watch?v=faz3oSuDivE&t=566) this value right here so if we make it bigger you know it's going to get softer and if we make it smaller like point zero one then it's gonna look you know quite a bit uh sharper I think this 
[09:37](https://www.youtube.com/watch?v=faz3oSuDivE&t=577) would probably be better if we just set both of them like this so then we can have different values and we can actually see you know the middle value a little more like that set this 
[09:48](https://www.youtube.com/watch?v=faz3oSuDivE&t=588) to 0.01 so maybe the middle value is is soft like that you can come up some with you can come up with some pretty interesting results this way let's save this one and move on to a different one 
[09:59](https://www.youtube.com/watch?v=faz3oSuDivE&t=599) I can play around with with a half tone and Screen tone and stuff like that so this one I'll just call cell shading I'll just uh clear this out make a new one and I'll do the same thing where I 
[10:12](https://www.youtube.com/watch?v=faz3oSuDivE&t=612) bring a Shader to RGB everything is basically going to use that and we'll bring a math node set to greater than and this one I'll just do I'll do screen tone so it's going to be like little 
[10:23](https://www.youtube.com/watch?v=faz3oSuDivE&t=623) dots basically showing like the gradation instead of it being a hard line like this so for that you're going to want to use the voronoi texture that's going to be the easiest one to 
[10:33](https://www.youtube.com/watch?v=faz3oSuDivE&t=633) use and we can preview this with Ctrl shift left click like that and this is going to give us a bunch of little circles basically and if we turn it up you can see it's a little better looking 
[10:44](https://www.youtube.com/watch?v=faz3oSuDivE&t=644) and we can turn the randomness all the way down like that so it's more of like a grid of points if you want it to be more like kind of random stipply looking or a little messy 
[10:55](https://www.youtube.com/watch?v=faz3oSuDivE&t=655) then you can turn the randomness up and that would look good also so one of the challenges with creating a good screen tone Shader is um Can is figuring out which coordinates 
[11:06](https://www.youtube.com/watch?v=faz3oSuDivE&t=666) to use because right now you can see it's kind of stretched it's going to look kind of different well if we plug the distance in right here to the threshold and look at this we're kind of 
[11:16](https://www.youtube.com/watch?v=faz3oSuDivE&t=676) getting the effect but it it doesn't look very similar to how you would see in like a a normal like real comic book uh like screen tone or halftone effect so first of all one of the problems is 
[11:32](https://www.youtube.com/watch?v=faz3oSuDivE&t=692) the white uh circles normally it would be black circles obviously if you just like the look of this you can leave it that way but I'm going to bring in a mix node right here and plug this into the 
[11:45](https://www.youtube.com/watch?v=faz3oSuDivE&t=705) factor and basically instead of zero to one we want this to be one and zero and that's just going to flip the values around next I'm going to set this to a 2d because we're going to be treating it 
[11:54](https://www.youtube.com/watch?v=faz3oSuDivE&t=714) kind of like a 2d texture if we look at it from the top you can see it's already looking a little better but the coordinates that we're using I think by default these are the generated 
[12:04](https://www.youtube.com/watch?v=faz3oSuDivE&t=724) coordinates if you drag this out search for coordinate right here the generated one is the one that it uses by default so I would recommend using either camera window or there's a third one that's in 
[12:18](https://www.youtube.com/watch?v=faz3oSuDivE&t=738) a different node that we can use I think it's just called camera view or something like that but basically one of the main differences between well let's just talk about camera first and then 
[12:28](https://www.youtube.com/watch?v=faz3oSuDivE&t=748) I'll talk about window camera is going to kind of make it so so that it looks 2D from wherever you're looking as you can see it's kind of changing as I'm rotating it but if you focus on a single 
[12:42](https://www.youtube.com/watch?v=faz3oSuDivE&t=762) dot it's kind of staying in the same spot even when you move around like this but one difference is when you zoom in it actually gets bigger like that window is a little different because it's 
[12:54](https://www.youtube.com/watch?v=faz3oSuDivE&t=774) completely flat and when you zoom in it will not get bigger like no matter how far you zoom in the the texture is going to stay the same size but you can see it's kind of stretched out also that's 
[13:05](https://www.youtube.com/watch?v=faz3oSuDivE&t=785) because it's looking at the shape of the window right here and if we like push it you can see it stretches even more so I don't really like using window you could make it look good in renders basically 
[13:14](https://www.youtube.com/watch?v=faz3oSuDivE&t=794) by figuring out like the the ratio that you're rendering in so this is 16 by nine but you don't really need to know the actual ratio as long as you know the like the width and all that you could 
[13:27](https://www.youtube.com/watch?v=faz3oSuDivE&t=807) just I believe you could just uh multiply it so let's say you take a get a vector math node set to multiply let's set this to hold on and if you look through the camera this is what you're 
[13:40](https://www.youtube.com/watch?v=faz3oSuDivE&t=820) gonna see when you render so this is what you want to be like working working with basically let's see so you'd want this one to be a smaller number so you could do you could do 10 divided by 1920 
[13:52](https://www.youtube.com/watch?v=faz3oSuDivE&t=832) and then they should be circles like that and not squashed anymore but there's actually a better instead of using this one and having to do the math you can look for the camera data node 
[14:05](https://www.youtube.com/watch?v=faz3oSuDivE&t=845) right here and use the view Vector so this is going to give us the flatness it's going to give us the flatness of the window where when you zoom in it's the you know the texture is not going to 
[14:16](https://www.youtube.com/watch?v=faz3oSuDivE&t=856) change size but it's going to always be well it's not going to stretch and distort based on the shape of the window so it's kind of like camera mixed with window I think in a lot of cases camera 
[14:27](https://www.youtube.com/watch?v=faz3oSuDivE&t=867) actually looks a little better like if we instead of using the voranoi texture if we use the wave texture right here this is gonna give us lines instead so let's just plug this up into here turn 
[14:41](https://www.youtube.com/watch?v=faz3oSuDivE&t=881) it up a little more okay so to get different values you can also just tweak these values right here but as you can see with the camera data no The View Vector you can't really tell 
[14:52](https://www.youtube.com/watch?v=faz3oSuDivE&t=892) like you can't judge depth at all which is kind of that that's like normal that's what you would actually see in like 2D screen tone for the most part but if we use the camera one from the 
[15:04](https://www.youtube.com/watch?v=faz3oSuDivE&t=904) texture coordinate you can actually see it so if you want it to if you want it to conform a little more to your object then you might want to use camera even though it's not as accurate as like like 
[15:17](https://www.youtube.com/watch?v=faz3oSuDivE&t=917) close to the 2D effect I think in a lot of cases it looks a little better so we'll just be using that one moving forward just the camera camera coordinate right here but yeah the whole 
[15:27](https://www.youtube.com/watch?v=faz3oSuDivE&t=927) idea behind the screen tone or you know the half tone or the the lines like that is just doing this right here and then dialing in the values that you want like that you can also rotate it if you want 
[15:41](https://www.youtube.com/watch?v=faz3oSuDivE&t=941) like if you want to not be straight up and down but maybe 45 degrees you can either use a vector rotate or a mapping node and just plug it in in here and you would want this to be adjusting the Z 
[15:55](https://www.youtube.com/watch?v=faz3oSuDivE&t=955) rotation and this already is adjusting the Z rotation like that or you can set this to Euler and do it on whatever axis you want right there so I think this looks pretty good let's see we can also 
[16:07](https://www.youtube.com/watch?v=faz3oSuDivE&t=967) use this to kind of just to adjust existing colors so basically you would instead of using this directly in right there you would be using this to control like a mix Shader node or not a mixed 
[16:22](https://www.youtube.com/watch?v=faz3oSuDivE&t=982) Shader but a mix RGB so we can get a mixed color in there and we can put this in the factor right there so it's basically just going to be well I guess you could set this up a few different 
[16:34](https://www.youtube.com/watch?v=faz3oSuDivE&t=994) ways but one way is instead of the factor putting this in the uh the second slot and maybe changing this to multiply so then it's always going to make it's always going to be darker wait a sec 
[16:46](https://www.youtube.com/watch?v=faz3oSuDivE&t=1006) what's going on oh you know I forgot I gotta plug this in and now it should work okay so this is basically just going to be on top of you know whatever color you have going on there so you 
[16:58](https://www.youtube.com/watch?v=faz3oSuDivE&t=1018) could just make this whole thing like blue or whatever like that or you could you know mix with the cell shaded look that I did before with like a color ramp like this and then you can uh you know 
[17:12](https://www.youtube.com/watch?v=faz3oSuDivE&t=1032) crunch the values and use use whatever colors you want also so we could make this one a little lighter like that and then you know the factor is just going to control like how dark like that so if 
[17:24](https://www.youtube.com/watch?v=faz3oSuDivE&t=1044) you just want it completely black then this is what you're looking for and this should work the same with the wave texture right here let's just reset this so one is on the bottom it's not going 
[17:35](https://www.youtube.com/watch?v=faz3oSuDivE&t=1055) to make much of a difference but but you don't need to invert that one and this one is probably pretty cool looking when it's diagonal Also let's make this make this bigger though and let's mess with 
[17:46](https://www.youtube.com/watch?v=faz3oSuDivE&t=1066) these values a little that okay so you can get you know some cool effects like this there are other ways also of treating this like if you don't want it to be if you don't want these lines to 
[17:57](https://www.youtube.com/watch?v=faz3oSuDivE&t=1077) actually taper off and change size but you want them to be kind of like how do I say this well I'll just show you a different way name the screen tone one and I'll duplicate it so this one's 
[18:07](https://www.youtube.com/watch?v=faz3oSuDivE&t=1087) screen tone too so this one is going to be they're all going to be like consistent width but in like different steps kind of like when you're using um a color ramp set to constant so let's 
[18:18](https://www.youtube.com/watch?v=faz3oSuDivE&t=1098) just uh delete these for now and we'll start off with this one so so basically you want something to uh snap to values before it goes into the the grader then so if you want you could use this let's 
[18:32](https://www.youtube.com/watch?v=faz3oSuDivE&t=1112) see yeah and so all of these are going to be the con like a consistent width like that you can see just kind of stops right there and this is going to let's see where would it be well this is just 
[18:43](https://www.youtube.com/watch?v=faz3oSuDivE&t=1123) going to be zero and one so you would actually want this in here before you do this and now this this would be able to um like control where those are being placed but this is 
[18:55](https://www.youtube.com/watch?v=faz3oSuDivE&t=1135) only going to give you you know two dot sizes so if you want more than that then that's when you would bring in a color ramp or something like that so let's just use a color ramp plug this into the 
[19:09](https://www.youtube.com/watch?v=faz3oSuDivE&t=1149) threshold and set this to constant and basically you would just be using not this one my bad instead of the greater than that's what you want to do so we could uh bring in a mix right there but 
[19:20](https://www.youtube.com/watch?v=faz3oSuDivE&t=1160) you don't really need this I guess because you can you can change the values in here also sorry I'm kind of all over the place okay so you would basically just add however many steps as 
[19:30](https://www.youtube.com/watch?v=faz3oSuDivE&t=1170) you want in here and he would also want to flip this just so that we're dealing with a black black dots again okay so you can change the dot sizes and they're not going to have like Smooth 
[19:43](https://www.youtube.com/watch?v=faz3oSuDivE&t=1183) transitions in the same way as with the other one you can see it kind of like has a hard Edge right there and again this is going to look a little better if we turn Shadow off it's going to be a 
[19:53](https://www.youtube.com/watch?v=faz3oSuDivE&t=1193) little more clear the edges so yeah you can experiment with this experiment with this if that's actually what you want and this sorry this will also work just fine for the wave texture we can plug 
[20:05](https://www.youtube.com/watch?v=faz3oSuDivE&t=1205) this up here also and just so you can see everything that I have in here here's what it looks like all right so this is going to work the same way as well let's see another way you can do 
[20:15](https://www.youtube.com/watch?v=faz3oSuDivE&t=1215) kind of stepped let's do a cell shading and I'll duplicate this one so shading too so another way that you can do that let's I think I deleted the output material output okay another way you can 
[20:27](https://www.youtube.com/watch?v=faz3oSuDivE&t=1227) do this is just with a map range and I already showed this but this one's a little different you can set this to um stepped linear and that will immediately give you multiple steps but 
[20:38](https://www.youtube.com/watch?v=faz3oSuDivE&t=1238) you don't really have control or as much control as over their spacing you can't control how far apart or how big each band is you can only control like the steps right here and you can control I 
[20:51](https://www.youtube.com/watch?v=faz3oSuDivE&t=1251) think basically all of them are going to be evenly spaced apart so it's a little hard harder to control them individually but it does look pretty cool right out of the box you can also change this to 
[21:04](https://www.youtube.com/watch?v=faz3oSuDivE&t=1264) vector and that will basically take any colors in here and split those up into RG and B like this you can see we're getting a cool result it's basically just going to be changing the color of 
[21:18](https://www.youtube.com/watch?v=faz3oSuDivE&t=1278) the model right here typically I think it works best when this is just set to white like we have it because if you have it too dark then everything's just gonna turn black so I think having it 
[21:30](https://www.youtube.com/watch?v=faz3oSuDivE&t=1290) set to White works pretty well but just so that I can show you we can set this maybe to a noise texture and plug the color in here so this is what it's going to look like once it actually loads it's 
[21:43](https://www.youtube.com/watch?v=faz3oSuDivE&t=1303) just going to be colorful like that but then we put it through here and it's going to split it up into multiple multiple bands like that and you know the more steps we give it the more 
[21:55](https://www.youtube.com/watch?v=faz3oSuDivE&t=1315) accurate it's going to get the colors but if we have it pretty low then it will be mostly RGB right there which I think looks pretty cool if you're into that sort of thing if you want this is 
[22:08](https://www.youtube.com/watch?v=faz3oSuDivE&t=1328) just like an alternate way of doing it you could use a vector math node let's see Vector math node that's a snap and that's not science snap and that's going to be doing um the same thing as the map 
[22:21](https://www.youtube.com/watch?v=faz3oSuDivE&t=1341) range except you don't have the from minimum and stuff you only have the steps so the way this works is instead of saying how many steps you're saying like how many increments you want so if 
[22:36](https://www.youtube.com/watch?v=faz3oSuDivE&t=1356) you wanted two steps that would be one divided by two or point five yeah so you want four you would do 0.25 like that and it should be the same result but without any of the other control which 
[22:48](https://www.youtube.com/watch?v=faz3oSuDivE&t=1368) you don't have a whole lot of control over that anyway so maybe that's better for you let's see what else we have I guess another cool thing that you can do is um just like a fake outline it's not 
[22:59](https://www.youtube.com/watch?v=faz3oSuDivE&t=1379) a solid width outline like you would get for uh from freestyle a freestyle in here or if you do the inverted hole method or if you use the what is it if you do the grease pencil line art but 
[23:15](https://www.youtube.com/watch?v=faz3oSuDivE&t=1395) I'm going to show that in the main Channel video when I make it I'm not going to go into all that for this one so but anyway for the outline this one is is pretty simple it's again a Shader 
[23:26](https://www.youtube.com/watch?v=faz3oSuDivE&t=1406) to RGB you can use math nodes that's a greater than and a for an L node you can use fresnel or you can use layer weight I'm going to use layer weight you actually don't really need the Shader to 
[23:38](https://www.youtube.com/watch?v=faz3oSuDivE&t=1418) RGB in here but you will if you actually want to add it to one of your like you know the cell shaded things or any of the other effects that I have shown you can kind of add the outline just on top 
[23:50](https://www.youtube.com/watch?v=faz3oSuDivE&t=1430) of it so for that you will need the shaders RGB but for this you can just plug a fresnel into a greater than and you're just going to get this this effect right here to invert this instead 
[24:01](https://www.youtube.com/watch?v=faz3oSuDivE&t=1441) of the greater than you can use a less than if you want and it's just going to give you this black outline like that and it is going to change depending on the shape of your object so like I said 
[24:12](https://www.youtube.com/watch?v=faz3oSuDivE&t=1452) it's not even width all the way around but um it's still a pretty cool effect facing should work just as well it's a little different but maybe uh maybe it's 
[24:24](https://www.youtube.com/watch?v=faz3oSuDivE&t=1464) a little more consistent for your model so you might want to just play around with that both of these are basically just paying attention to like the viewing angle but yeah then you could 
[24:34](https://www.youtube.com/watch?v=faz3oSuDivE&t=1474) add this on top just like I was showing before so let's let's do that really quick okay so we have the color ramp set up right here and and you can do this a few ways you could multiply it you could 
[24:46](https://www.youtube.com/watch?v=faz3oSuDivE&t=1486) mix it I'm just going to use a mixed color just because I think that's probably the easiest to understand you just want to put this into the first the outline into the second and then you can 
[24:59](https://www.youtube.com/watch?v=faz3oSuDivE&t=1499) multiply it like that to get the dark outline or if you want you can put this in the factor and then the outline is just going to be whatever the second color is if you have this that's a mix 
[25:10](https://www.youtube.com/watch?v=faz3oSuDivE&t=1510) that is so a few different ways of doing it oh sorry this would actually be in the second one because I forgot we were using a less than for this but yeah this 
[25:19](https://www.youtube.com/watch?v=faz3oSuDivE&t=1519) would be the first color now in this case so you could set this to whatever color you want okay so we got the outline the next is kind of like a watercolor or something like that just 
[25:28](https://www.youtube.com/watch?v=faz3oSuDivE&t=1528) like painterly normals that's the idea just call this I'll call it painterly normals okay so the whole idea behind this is we're going to be changing the normal right here which is what's used 
[25:41](https://www.youtube.com/watch?v=faz3oSuDivE&t=1541) to figure out like the like the shading and the lighting so if you set this to shade shade flat this is this is showing the actual like normals of the faces right here if you change this to shade 
[25:55](https://www.youtube.com/watch?v=faz3oSuDivE&t=1555) smooth it's basically blending all of those flat values together so uh what we can do is take well we have a few options for the normal that we actually use but you can take the texture 
[26:07](https://www.youtube.com/watch?v=faz3oSuDivE&t=1567) coordinate you can use the normal from here or you can use a geometry node and you can use the normal from here and it'll make more sense um the difference between these when I 
[26:17](https://www.youtube.com/watch?v=faz3oSuDivE&t=1577) actually show you the other method we're going to use a voronoi texture and you just want to plug this into the vector and then instead of using the color you want to plug the position into the 
[26:27](https://www.youtube.com/watch?v=faz3oSuDivE&t=1587) normal right here so immediately you can kind of tell what's going on let's actually actually turn the metallic up a little bit and maybe let's turn the roughness down when you have some 
[26:38](https://www.youtube.com/watch?v=faz3oSuDivE&t=1598) Reflections it's a little easier to tell like what's going on it's basically making instead of it being smooth it's making it so like it's gonna make it so it looks like it's a shaded flat kind of 
[26:51](https://www.youtube.com/watch?v=faz3oSuDivE&t=1611) except it's gonna be the same as this voronoi pattern right here which I think is pretty cool and uh yeah so the voronoi when you use it like this the position it's basically just pixelating 
[27:02](https://www.youtube.com/watch?v=faz3oSuDivE&t=1622) the texture so if instead we're using a window so it's completely flat right here window looks like this by default it's just going to show you the same like it looks like a UV map basically 
[27:15](https://www.youtube.com/watch?v=faz3oSuDivE&t=1635) but if we use a position and turn the randomness down it's basically just pixelating it and you would just change the pixel size with the scale right here but then when we randomize it it looks a 
[27:28](https://www.youtube.com/watch?v=faz3oSuDivE&t=1648) little different so that's why we're getting this effect right here we're just pixelating the normals basically and then you can do whatever you want with this the main difference between 
[27:37](https://www.youtube.com/watch?v=faz3oSuDivE&t=1657) the texture coordinate and the geometry geometry coordinate is that when you rotate this one you can see um you know the the texture is staying put it's not really it's not really moving but if you 
[27:48](https://www.youtube.com/watch?v=faz3oSuDivE&t=1668) use the normal from the geometry it will uh change as you move it like that so it just kind of depends on on what you actually want but I think usually the texture coordinate one is the one that 
[28:03](https://www.youtube.com/watch?v=faz3oSuDivE&t=1683) people are going to want to use you can also distort this a little bit so if you want it to not be as like flat but actually look more like paint swatches you can use a noise texture right here 
[28:15](https://www.youtube.com/watch?v=faz3oSuDivE&t=1695) and there are a few ways of distorting with noise some people like to use a mix mix RGB set to linear light I believe it works the same way but I'm used to using geometry nodes so I always do it this 
[28:28](https://www.youtube.com/watch?v=faz3oSuDivE&t=1708) way I'm going to use the object coordinate for them we're going to use a Vector math nodes set to subtract subtract 0.5 basically is taking all of these values from the color that go from 
[28:38](https://www.youtube.com/watch?v=faz3oSuDivE&t=1718) zero to one and it's making them go from making them go from negative 0.5 to positive 0.5 so that the midpoint of all the values is zero and that just makes it so that when we distort it it's not 
[28:51](https://www.youtube.com/watch?v=faz3oSuDivE&t=1731) pushing everything only in One Direction and then we can set this to multiply or scale and now we just want to add it to this not that we want to add it to this Vector right here like that and this 
[29:04](https://www.youtube.com/watch?v=faz3oSuDivE&t=1744) will start to break it up and make it a little more random looking you can control the strength with strength with this uh scale right here so let's just set it to something really low and then 
[29:16](https://www.youtube.com/watch?v=faz3oSuDivE&t=1756) let's maybe make the scale a little lower the detail a little higher maybe like five you want to get really um grungy you can turn the roughness up a little and like 
[29:28](https://www.youtube.com/watch?v=faz3oSuDivE&t=1768) this turn it down I don't want it to splotchy but anyway you can get effects kind of like this so it looks a little more painterly now obviously if it's just 
[29:39](https://www.youtube.com/watch?v=faz3oSuDivE&t=1779) very reflective it doesn't really look like paint exactly so you can use this in combination with all the methods that I was showing before okay so I think if you just want it to look kind of like 
[29:49](https://www.youtube.com/watch?v=faz3oSuDivE&t=1789) watercolor or something like that like paint um then you can just use Shader to RGB with the color ramp but I think when you when you use the color ramp I think it 
[30:00](https://www.youtube.com/watch?v=faz3oSuDivE&t=1800) looks a little better when it's not set to constant and when you're just kind of crunching these a little closer or instead of using linear you can use B spline and basically it's not going to 
[30:10](https://www.youtube.com/watch?v=faz3oSuDivE&t=1810) be completely black where you put this stop right here it's gonna go a little past it so you can still crunch the values closer but it's a lot smoother looking so you can get results like this 
[30:22](https://www.youtube.com/watch?v=faz3oSuDivE&t=1822) let's just set this to be something like that I think that looks pretty cool let's make another one at the end make it a little orange this one we'll do completely White 
[30:34](https://www.youtube.com/watch?v=faz3oSuDivE&t=1834) okay so you can get some uh some cool results like this they are gonna have a hard Edge so if you want them to not have a hard Edge you can change the voranoi right here instead of F1 change 
[30:44](https://www.youtube.com/watch?v=faz3oSuDivE&t=1844) it to smooth F1 and then you have the smoothness meter right here like that so I think just a little bit like maybe halfway looks pretty good and it will still interact with the light so 
[30:57](https://www.youtube.com/watch?v=faz3oSuDivE&t=1857) let's just take a look at this move it around you can see that it will interact with the light which is pretty cool I think that's it if you want this file you can get it up on patreon that's 
[31:07](https://www.youtube.com/watch?v=faz3oSuDivE&t=1867) where I put it this will probably come out after the main Channel video about the same topic but if you sign up for patreon then you'll get it earlier so so yeah do that I guess I don't know have a 
[31:20](https://www.youtube.com/watch?v=faz3oSuDivE&t=1880) good one that's it bye 