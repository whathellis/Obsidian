---
URL: https://www.youtube.com/watch?v=jJnwzkBre8Y
thumbnail: https://i.ytimg.com/vi/jJnwzkBre8Y/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:58:55
published: 2022-08-20T05:32:29
duration: 1570
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "26m 10s"]
# Fixing The Graphics Of FINAL FANTASY XIV
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155905.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=jJnwzkBre8Y
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/jJnwzkBre8Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: I've spent the past two months hard at work developing ReShade and GShade shaders to improve the graphics of Final Fantasy XIV. In this video I go over my creative and developmental process from start to finish explaining the decisions I made, the major issues I came across and the theory behind it all. Did I accomplish my goals of improving the visuals? Let me know!

Topics covered include fog, bloom, color correction, HDR injection, color blending, improved sharpness filtering, tone mapping, auto exposure, and screen space ambient occlusion (SSAO).

Download the shaders and presets here!
https://github.com/GarrettGunnell/AcerolaFX/wiki

Support me on Patreon! 
https://www.patreon.com/acerola_t

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Code: https://github.com/GarrettGunnell/AcerolaFX
Join My Discord Server! https://discord.gg/FxGQvbfm6Y

Music:
Joy - Persona 3
During The Test - Persona 3
Afternoon Break - Persona 3
This Mysterious Feeling - Persona 3
Fearful Experience - Persona 3
The Path Is Open - Persona 3
Sandgem Town (Day) - Pokemon Diamond/Pearl
Main Theme - Detective Conan
Muscle Blues - Persona 4
Like A Dream Come True - Persona 4
New Game - WORLD OF HORROR
Your Name, Please - Earthbound
Climax Return - Danganronpa

arrow in thumbnail drawn by thlurp

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=0) hello everyone final fantasy 14 is in my opinion the best mmo on the market at the moment it has thousands of hours for both casual gamers and hardcore gamers alike with 
[00:12](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=12) the only downside being that you have to play through a realm reborn but what about the graphics final fantasy 14 is built on an engine that was released in 2010 
[00:23](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=23) it's written in directx 11 which makes it quite outdated and the visuals reflect this very often the developers have made numerous improvements to the engine over the years but the game is 
[00:34](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=34) still plagued with low contrast colors low resolution textures poor lighting and really bad shadow acne now do i think the game looks bad not at all i've taken plenty of great pictures with the 
[00:46](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=46) in-game photo mode but the game can definitely look a lot better which is why i have spent the past month making the gameplay go from this to this and the game's photo mode to go 
[00:57](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=57) from this to this but where did i start okay so before you gatekeep me and comment ace rolla you're just trend chasing because asmingold is playing 
[01:14](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=74) final fantasy 14. i have 2 000 hours in the game and i'm a saint of the firmament anyways with the subtle flexing out of the way how do we even start with fixing up final fantasy 
[01:27](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=87) reshade is a generic post-processing injector for games reshade works by intercepting all of the graphics api calls that the game makes then it takes what would be the final render of the 
[01:39](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=99) game and applies any shaders we want to it before presenting the new image to the screen for you to see reshade gives us more than just the color info of the game render though it also provides us 
[01:51](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=111) with the depth information of the scene which is extremely important for many post-processing effects but for final fantasy 14 we will be using g shade which is a version of reshade made 
[02:02](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=122) specifically for final fantasy vanilla reshade disables the depth information for any multiplayer game to prevent exploitation but g-shade doesn't do this which is very useful since otherwise 
[02:15](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=135) this video would not be nearly as cool the first effect i wrote was simple screen space fog just to see if everything was working properly the most basic distance fog works by taking the 
[02:26](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=146) pixel's depth value linearizing it and then multiplying it by the camera's far plane to get the distance of that pixel from the camera an important thing to remember and a limitation of g shade is 
[02:38](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=158) that we have no access to the game camera's properties meaning we don't actually know what the camera's far plane is so we just have to use our own this also means that any image effects 
[02:49](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=169) that require the camera transformation matrices are not possible such as temporal anti-aliasing and motion blur i'll be using a far plane of 1000 since that's fairly standard but you can 
[03:02](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=182) customize it if you want moving on we calculate a fog factor from this distance however we want and linearly interpolate between the pixel's color and the fog color if everything has gone 
[03:14](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=194) right then fog will now be in the game as i've explained in other videos fog is very useful for both weather effects and conveying distance final fantasy already uses fog on distant objects but we can 
[03:30](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=210) make a scene a bit more gloomy with our fog effect if we so desire unfortunately though the fog color can never always match the game's environment so this effect isn't going to be used for 
[03:41](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=221) gameplay and i will keep it disabled now that we know g shade works just fine we can move on to the meat and potatoes of post-processing color correction to start we are going to simulate camera 
[03:54](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=234) exposure by multiplying our pixels with any number the higher the number the brighter the image after this we are going to white balance our pixels in order to make the colors cooler or 
[04:05](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=245) warmer and tint which colors the pixels are balanced towards next we will control the contrast of our image by modifying the slope of the color based on a defined linear midpoint 
[04:17](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=257) then we can make the pixels brighter or darker by adding or subtracting a brightness value afterwards we are going to filter the colors by multiplying them with any other color we desire and 
[04:28](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=268) lastly we will control the saturation of the image by linearly interpolating between the luminance of the pixel and the normal pixel color this color corrector is an improvement on my 
[04:39](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=279) original color corrector from previous videos as it allows you to customize the contrast brightness and saturation of each individual color channel rather than operating on just the entire color 
[04:52](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=292) this enables you to do some really powerful adjustments like more visually interesting monochromatics and selective desaturation to name a few after implementing the color correction i got 
[05:04](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=304) started on my favorite post-processing effect bloom you might be saying to yourself but acerola the game already has bloom as demonstrated in my elden ring video 
[05:16](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=316) bloom works by filtering the image so that only bright pixels remain then we blur those pixels and add them back to the original image to make it look like bright pixels are overwhelming the 
[05:28](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=328) camera lens i have upgraded the bloom shader from the previous video to give you the ability to color correct the bloomed pixels before adding it back to the image so you can make bloom 
[05:38](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=338) highlights brighter or warmer or whatever you'd like to make the bloom match the scene a bit more our bloom implementation isn't quite finished bloomed pixels are often pushed beyond 
[05:50](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=350) the normal maximum color value in a low dynamic range color space this means that bright areas of the image are going to completely lose their detail as all of the colors are clamped to white to 
[06:01](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=361) fix this we need to convert those high range bloomed pixels into the low range values using a tone mapping operator so that the image detail is preserved the tone mapping shader i implemented allows 
[06:14](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=374) you to choose between several different operators but for my gameplay preset i've decided to go with narkowicz aces it makes the colors look all nice and vibrant oh wait a second it appears i'm 
[06:27](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=387) being handed something by production okay well it appears this isn't tone mapped at all if we try to output which pixels exceed one we'll see that none of them do even 
[06:41](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=401) the areas that very obviously should this means that we're trying to tone map a render that has already been clamped to one which is kind of pointless unfortunately this is just how g shade 
[06:53](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=413) works the effects we have written so far are ping-ponged with the g-shade backbuffer which is the texture that will be presented to the screen when everything is done for example our bloom 
[07:04](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=424) effect takes the back buffer info and then writes new information to the g-shaped backbuffer then our color correction effect takes that buffer information and does its thing on it 
[07:16](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=436) writing the new color information to that buffer lastly we try to tone map what we assume is a high dynamic range buffer and then it gets presented to the screen for you to see the issue here is 
[07:28](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=448) that the g shade back buffer is a low dynamic range texture meaning it only allows 8 bits per color channel so every time we write information to it all of our color channel values get clamped 
[07:41](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=461) down to 0 to 1 rather than maintaining those accurate high dynamic range values for us this means that high dynamic range effects are impossible in g shade after realizing this i packed up my bags 
[07:56](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=476) gave up on the project and went to taco bell for dinner arriving at the taco bell drive-thru the line was long and so i had plenty of time to reflect on all the mistakes i've 
[08:06](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=486) made in my life how i got here you know the works but after several depressing minutes i had an idea what if it was actually possible to get g-shaped to support high 
[08:18](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=498) dynamic range currently are shaders right to the g-shade back buffer but what if they wrote to a different buffer instead if i create a high dynamic range buffer and 
[08:29](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=509) include it in all of my shaders then my shaders can now read from and write to this new hdr buffer in order for this to work we need two more shader effects one effect that transfers the contents of 
[08:42](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=522) the back buffer to our new injected buffer and one effect that transfers the contents of the new buffer to the g-shaped buffer so that we can actually see what our shaders have done to it the 
[08:52](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=532) trade-off here is twofold first the overhead of transferring the contents of the buffer is going to add about .6 milliseconds of render time to our shader pipeline which is not 
[09:04](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=544) insignificant secondly my shader effects are incompatible with other g shade shaders since my shaders read and write to an entirely different buffer there are workarounds for this but it's 
[09:15](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=555) honestly not worth the effort regardless why would you want to use other people's shaders anyways in exchange for these trade-offs is a completely legitimate hdr rendering pipeline for final fantasy 
[09:27](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=567) 14 and one of the main reasons why my shaders are so powerful as far as i'm aware my shaders are the first to do this for g shade but if i'm wrong please let me know in the comments with our new 
[09:39](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=579) injected hdr buffer our image is now properly tone mapped no more clipping occurs and the detail is preserved the last effect i implemented for my g shade preset is sharpness final fantasy 
[09:54](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=594) suffers heavily from low quality textures and with the low contrast visuals a lot of detail is lost thankfully sharpness fixes this my sharpness filter works by applying this 
[10:06](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=606) convolution matrix to each pixel what is a matrix convolution i don't know man google it or something this accentuates edge lines by increasing the contrast between pixels causing the illusion of 
[10:19](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=619) higher detail the sharpness causes distant objects to get really noisy and yucky looking though so we are going to use the same logic as our fog effect to filter the sharpness based on depth so 
[10:30](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=630) that only objects close to the camera are sharpened with every effect finished i spent a lot of time tuning each effect to look good for gameplay and ended up with this as a 
[10:43](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=643) final result we're finished wait why is the video so much longer hello everyone fixing the graphics of final 
[10:52](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=652) fantasy xiv was a video by youtuber ace rolla in which he attempted to improve the visuals of final fantasy utilizing g-shade and his own custom shaders unfortunately he failed and he paid the 
[11:07](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=667) ultimate price the gameplay preset suffered from several unacceptable issues it was too bright in some areas too dark and others rendering the game unplayable quite often additionally the 
[11:19](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=679) extra bloom just generally looks bad there's weird haloing on hair and random bloom blobs will appear and disappear on terrain ruining everything lastly the amateur sharpness filter causes way too 
[11:32](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=692) many artifacts and sometimes makes characters look absolutely awful this is quite frankly embarrassing so today we're fixing the graphics of fixing the graphics of final fantasy xiv 
[11:49](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=709) okay so the biggest problem of my gameplay shaders i made was that you couldn't really play the game with them well you could but sometimes you'd be blinded and sometimes you couldn't see 
[12:01](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=721) anything at all i wonder if there's a post-processing effect that addresses this exact problem auto exposure is a shooting mode on a camera where the camera decides what the 
[12:11](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=731) exposure should be based on the lighting conditions of the photo if the scene is too bright then the exposure will be lowered but if the scene is too dark then the exposure will be increased 
[12:22](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=742) obviously the game camera is not a real physical camera so we need to simulate this behavior of auto exposure ourselves our first objective when implementing auto exposure is determining the average 
[12:34](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=754) luminance of the image there's two ways we could go about this we could progressively down sample the image to a one by one pixel averaging the luminances along the way and then using 
[12:45](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=765) that pixel as the average luminance this would be very fast but the resulting auto exposure will be very sensitive to even the mildest changes in scene lighting instead we're going to create a 
[12:58](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=778) luminance histogram which is the distribution of the luminance across the image with a histogram we could calculate a better average luminance to use by controlling how extreme values 
[13:10](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=790) influence that average consider a histogram of 256 bins where the first bin is the minimum allowed luminance and the last bin is the maximum allowed luminance if we create an array with 
[13:23](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=803) size 256 and have that memory shared between thread groups of 256 we can divide up our image into 16 by 16 chunks to be processed by each group of 
[13:36](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=816) threads each thread within a group will take its corresponding pixel calculate its position in the luminance histogram and then add one to that bucket in the shared array then when each group has 
[13:48](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=828) finished calculating its local luminance distribution it writes that distribution information to another texture where x is the histogram at that chunk and y is the histogram data this texture ends up 
[14:01](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=841) looking like this as you can see each slice of the texture is an individual histogram for a small portion of the image next we need to flatten this texture into a single 
[14:12](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=852) histogram this can be done by summing up each row of the 2d histogram and writing that sum to the corresponding bucket in the 1d histogram the result is a 1 by 256 texture that contains the luminance 
[14:27](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=867) distribution of our game render with this we can calculate an average luminance of the screen and then scale the camera exposure with auto exposure the game becomes playable now when the 
[14:39](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=879) game gets too dark the auto exposure will make the game brighter and when the game gets too bright the auto exposure will make the game darker in terms of the post-processing pipeline auto 
[14:50](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=890) exposure usually goes right before tone mapping okay so with that problem out of the way now we have to tackle the bloom dilemma i spent a long time trying to find bloom settings that would always 
[15:02](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=902) look good but too often the bloom would ruin the visuals even though sometimes it would look really good so i decided to disable the effect entirely and only use it for g posing the only time the 
[15:13](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=913) bloom always looked good was when the entire screen was bloomed but this is no different than an additive blend with a lot of extra steps so i went ahead and implemented photoshop blend modes and 
[15:24](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=924) replaced the bloom with a mild color dodge this way we accentuate the game's existing bloom rather than trying to add onto it the last issue the gameplay shaders had was that the sharpness 
[15:36](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=936) looked awful this is the result of me being really lazy and using a very simple sharpness filter it turns out the modern world has much more sophisticated ways of sharpening images to avoid these 
[15:49](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=949) exact issues contrast adaptive sharpness is an effect invented by timothy lotz the same guy who made fxaa so that's cool the technique provides sharpness without artifacts by only sharpening 
[16:02](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=962) parts of the image that are low in contrast while leaving high contrast pixels alone but the trade-off is that it's a bit more expensive than our amateur sharpness filter we start by 
[16:12](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=972) sampling our pixel and its neighbors we find the minimum pixel value and the maximum pixel value we use this minimum and maximum to calculate an amplitude that controls how much sharpening occurs 
[16:25](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=985) by taking the minimum of the minimum value and 2 minus the maximum value and then we multiply that by the reciprocal of the maximum this amplitude then scales our user-defined sharpness value 
[16:38](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=998) which in the sample provided by amd is an interpolation between negative one over nine and negative one over six this is the part that makes the technique contrast adaptive since high differences 
[16:50](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1010) in minimum and maximum color values will result in an amplitude close to zero preventing any sharpening from occurring lastly we multiply the sharpness amount with each sampled pixel sum the results 
[17:03](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1023) and divide by one plus four times the sharpness value to obtain our new sharpened pixel the result is a sharpened image without any gross artifacts that my initial sharpness 
[17:14](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1034) filter had making it look much better while still bringing out the detail of final fantasy's textures with all of the problems of my gameplay shaders solved i went back to the lab to 
[17:26](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1046) fine-tune each effects parameters to create our new finished gameplay shaders no more unplayable game areas no more bloom artifacts and no more sharpness artifacts these gameplay shaders are 
[17:42](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1062) almost perfect i'd say why is the video still so much longer hello everyone it turns out making gameplay shaders is hard youtuber ace rolla demonstrated this in his video 
[17:55](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1075) fixing the graphics of fixing the graphics of final fantasy xiv in which he valiantly attempted to fix the shaders but ultimately failed and he paid the ultimate price you might 
[18:07](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1087) be asking acerola what's wrong with the shaders they look fine wrong while the shaders do look good in most circumstances our tone mapping has a really tough time dealing with very 
[18:19](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1099) bright lights in very dark areas resulting in what i call mega bloom this mega bloom looks absolutely terrible and needs to be fixed that's 
[18:34](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1114) right today we're fixing the graphics of fixing the graphics of fixing the graphics of final fantasy 14. as i mentioned earlier our tone mapper is the issue more specifically it's our 
[18:47](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1127) auto exposure and our tone mapper not playing together very well when scenes are dark the auto exposure is going to make lights very bright and the narkowicz ace's tone mapper tends to 
[18:58](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1138) over saturate bright colors resulting in our mega bloom to fix this we are going to throw away the narkwick's tone mapper and instead create our own filmic curve using the hable tone mapper curve 
[19:10](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1150) formula after hours of fine tuning my curve looks like this which is kind of just a really fancy logarithmic curve when we compare this with the narkowicz aces curve we see why mega bloom occurs 
[19:23](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1163) the difference in brightness between mid-tones is quite substantial and my curve brings those colors down much more preventing the mega bloom from occurring we now have a new problem and it's that 
[19:34](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1174) our shaders look very boring without the vibrancy and saturation that narco x aces gives us for free to fix this we need to turn to our color corrector to bring those interesting colors back 
[19:46](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1186) increasing the exposure makes our colors bright enough to make it through our new tone mapping curve base final fantasy 14 is very yellow to counteract this we wipe balance towards cooler tones and 
[19:58](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1198) tint until it looks good we're getting funky with the contrast and increasing the contrast of the red and green color channels by a small amount and the blue color channel by a large amount 
[20:08](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1208) increasing the brightness of red colors by a small amount green colors by a medium amount and blue colors by a large amount result in an overall brighter image with accentuated blues lastly we 
[20:20](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1220) desaturate red and blue colors a tiny bit to achieve what i feel is a more realistic looking color space after fixing the color correction a small adjustment to the auto exposure settings 
[20:31](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1231) finishes everything up the conversion to the new tone mapper is a success no more mega bloom this means we're finished right not quite the shaders are still missing 
[20:45](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1245) something something that would make them truly go the distance i used this opportunity to implement a shader technique i had been procrastinating for a long time screen space ambient 
[20:55](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1255) occlusion but before we learn about that what even is ambient occlusion ambient occlusion is the occlusion of ambient light for example this ball is being lit by a directional light source we can see 
[21:09](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1269) the entire ball because of all the ambient light that is bouncing off the ground and back onto the ball but the part of the ball that is close to the ground and on the opposite side of the 
[21:19](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1279) light is darker because it is getting less ambient light this is ambient occlusion screen space ambient occlusion seeks to simulate this to get more realistic lighting and it does it 
[21:31](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1291) entirely from just the depth buffer well technically it does it from the depth buffer and the screen space normals but richey doesn't give us the screen space normals of the scene so we need to 
[21:42](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1302) calculate them in place using the depth buffer but acerola how do you get the normal vectors from just the depth values that's a great question since we know 
[21:53](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1313) the distance of each pixel from the camera we can construct a view space position of each pixel where the x and y-coordinates are the pixels positioned in the image and the z-coordinate is the 
[22:04](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1324) view space depth of the pixel then to get that pixel's normal vector we need two more vectors one that is the center pixel's position minus the top neighbor pixel's position and another that is the 
[22:17](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1337) center pixel's position minus the right neighbor pixel's position lastly we take the cross product of these two vectors to obtain the view space normal vector one thing to note is that we have not 
[22:29](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1349) reconstructed the normals from final fantasy 14 textures rather we have reconstructed the normal vectors of the triangles of the models which gives us the flat shading appearance alright so 
[22:41](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1361) in the interest of keeping this video concise i'm going to go over how ssao works in the abstract sense thankfully screen space ambient occlusion is conceptually pretty simple consider a 
[22:54](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1374) point on the surface of an object if we want to figure out how visible this point is then we just need to determine how many nearby objects there are to possibly obscure it to figure this out 
[23:05](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1385) we want to project a hemisphere kernel tangential to that point which is a fancy way of saying in the direction of the surface normal which we calculated earlier then we want to randomly sample 
[23:17](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1397) depth values in this hemisphere to find any objects that may be obscuring the point you might be saying to yourself wow this sounds like a computational nightmare yes the version of ssao i 
[23:29](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1409) implemented for my shaders was xe gtao from intel the most modern publicly available ambient occlusion technique the ssao makes a substantial difference as you can see here it also makes a 
[23:42](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1422) substantial difference in your gpu's lifespan as it basically doubles the performance cost of my shaders with it enabled at max settings finally after 100 plus hours of 
[23:54](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1434) development and hundreds of thousands of gil in discounted teleports the gameplay preset is finished as one final review let's go over each shader pass from start to finish we first apply ssao 
[24:08](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1448) since it affects the scene lighting next we apply a mild color dodge blend to accentuate highlights in bloom then we apply our main color correction adjustments of temperature tint contrast 
[24:20](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1460) brightness saturation and exposure this puts our colors into hdr so we need to apply auto exposure and then our custom tone mapping curve to preserve the image detail next we apply a special color 
[24:33](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1473) blend created by myself to increase the image contrast and crush mid-tones lastly we sharpen the image to improve texture detail and gamma correct the image to bring out shadows a bit more if 
[24:45](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1485) you're thinking to yourself wow this looks terrible and i could do better that's great it turns out each shader effect i wrote is completely customizable every single aspect of each 
[24:56](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1496) effect can be fine-tuned to your liking giving you the power to create the preset that looks best for you you can move around the effects to change the order of operations clone them to double 
[25:08](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1508) up on certain effects or disable effects you don't like conveniently there's also a user guide that explains how each effect works and what each setting does written by myself there's a lot more 
[25:20](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1520) effects available for use that i didn't mention in this video such as dithering a crt effect depth of field and a useful tool for lining up rule of thirds compositions if you would like to 
[25:32](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1532) download the shaders and presets the link is in the description along with an album of gameplay and gpos comparisons for your viewing pleasure i have written an installation guide for those of you 
[25:43](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1543) who haven't used g-shade before as well if you take any pictures with the shaders please use the tag hashtag acerola fx on any posts because i'd absolutely love to see them i asked if 
[25:55](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1555) anyone wanted to take pictures with my shaders in several gpo's discords and got no response anyways that's all i've got for you today thanks so much for watching and 
[26:06](https://www.youtube.com/watch?v=jJnwzkBre8Y&t=1566) i'll see you next time 