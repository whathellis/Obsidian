---
URL: https://www.youtube.com/watch?v=gg40RWiaHRY
thumbnail: https://i.ytimg.com/vi/gg40RWiaHRY/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T13:05:59
published: 2024-06-30T23:38:36
duration: 1098
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "18m 18s"]
# I Tried Turning Games Into Text
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722130612.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=gg40RWiaHRY
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/gg40RWiaHRY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: To try everything Brilliant has to offer for free for a full 30 days, visit https://brilliant.org/Acerola/ you’ll also get 20% off an annual premium subscription! 

ASCII art has been a staple of the internet since its inception -- but today I'm wondering if we could make a shader that turns games into ASCII art, and if we can, would it even look good?

Support me on Patreon!
https://www.patreon.com/acerola_t

Download my ReShade shader pack!
https://github.com/GarrettGunnell/AcerolaFX/releases

Socials:
Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Unity Code (lacking some features compared to ReShade): https://github.com/GarrettGunnell/Post-Processing/tree/main/Assets/ASCII
ReShade Code: https://github.com/GarrettGunnell/AcerolaFX/blob/main/Shaders/AcerolaFX_ASCII.fx

Music:
Afternoon Break - Persona 3 OST
In A Moment's Time - Skullgirls OST
Junes Theme - Persona 4 OST
During The Test - Persona 3 OST
Midori Eyes - Paradise Killer OST
Police Station - Persona OST
With Renewed Hope, We Continue Forward - VA-11 Hall-A OST
Neon District - VA-11 Hall-A OST
Sandgem Town - Pokemon Diamond OST
Like A Dream Come True - Persona 4 OST
Color Your Night - Persona 3 OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=gg40RWiaHRY&t=0) hello everyone back in the Golden Era of gaming the 2000s if you wanted help with a game you would consult game facts these guides had a culture of fancy artistic headers composed of only text a 
[00:13](https://www.youtube.com/watch?v=gg40RWiaHRY&t=13) graphic design technique known as asy art if you're around my age these game facts guides may have been your first introduction to asy Art but the technique goes all the way back to 1966 
[00:24](https://www.youtube.com/watch?v=gg40RWiaHRY&t=24) and even further back to 1867 if you include typewriters but what I'm thinking about is the future could we render a game as ASI art and if we did would it even look good would it even be 
[00:36](https://www.youtube.com/watch?v=gg40RWiaHRY&t=36) playable so today we'll be turning characters into characters as far as I'm aware there aren't any games that use an asy art Shader for its main art Direction but 
[00:53](https://www.youtube.com/watch?v=gg40RWiaHRY&t=53) some games have basic ASI art shaders available in their photo mode such as returnal ral's ASI art Shader is is what inspired me because quite frankly it doesn't look very good while it does 
[01:04](https://www.youtube.com/watch?v=gg40RWiaHRY&t=64) accomplish the simple task of converting the image to text so much detail is lost that everything becomes formless blobs requiring your brain to fill in a lot of information that is now absent to 
[01:15](https://www.youtube.com/watch?v=gg40RWiaHRY&t=75) mitigate this loss of detail the Shader uses the underlying image to color the overlaid text characters which helps a bit to separate the shapes from each other but I think it looks kind of ugly 
[01:25](https://www.youtube.com/watch?v=gg40RWiaHRY&t=85) and deviates too far from the traditionally monochromatic style of asy art unfortunately this loss of detail is a requirement for the Shader so we must rely on the characters alone to 
[01:36](https://www.youtube.com/watch?v=gg40RWiaHRY&t=96) communicate as much detail as possible if we compare the returnal asy Shader to some real asy art we can see one pretty big difference which is defined Contour constructed with slashes underscores and 
[01:48](https://www.youtube.com/watch?v=gg40RWiaHRY&t=108) vertical bars to communicate Edge flow and visual boundaries if Ral had these Edge lines then the formless blob dilemma would be solved but is it possible to make a Shader that draws 
[01:58](https://www.youtube.com/watch?v=gg40RWiaHRY&t=118) edges with the proper asy characters I didn't really feel like doing any research on this topic because I already know how to solve the problem so I don't need to do any research which means 
[02:08](https://www.youtube.com/watch?v=gg40RWiaHRY&t=128) today is an ace Rolla invention the Shader I showed at the beginning of the video features exactly what we need asky edges that follow the image contour and it's actually a fairly simple solution 
[02:20](https://www.youtube.com/watch?v=gg40RWiaHRY&t=140) but first a word from our sponsor this video has been sponsored by brilliant brilliant is the best way to learn math data science and computer science interactively brilliant offers thousands 
[02:32](https://www.youtube.com/watch?v=gg40RWiaHRY&t=152) of lessons from basic to Advanced so if you're just getting started learning math or are brushing up on your linear algebra for graphics programming brilliant has something for you even if 
[02:41](https://www.youtube.com/watch?v=gg40RWiaHRY&t=161) you don't know where to start that's not a problem brilliant customizes its content to fit what you need just take a quick quiz when you sign up and Brilliant will match you with lessons 
[02:50](https://www.youtube.com/watch?v=gg40RWiaHRY&t=170) that fit your interests and your level of expertise I personally use brilliant whenever I need a quick and accessible refresher on math concepts that I haven't worked with in a while such as 
[03:00](https://www.youtube.com/watch?v=gg40RWiaHRY&t=180) complex numbers or some aspect of calculus I appreciate that brilliant makes it easy to find lessons on topics you're looking for which some search engines have been making that harder 
[03:09](https://www.youtube.com/watch?v=gg40RWiaHRY&t=189) recently be sure to try out everything brilliant has to offer with a free 30-day trial and 20% off an annual plan when you visit brilliant.org slasa or click the link in the 
[03:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=201) description thanks so much to brilliant for sponsoring this video I recommend watching in full screen because these asky renders do not downscale properly and might look bad in the smaller 
[03:31](https://www.youtube.com/watch?v=gg40RWiaHRY&t=211) YouTube video player before we get to the fancy edges we need to recreate the basic returnal asy Shader which forms the foundation of the effect so how does rnal convert this base image into text 
[03:43](https://www.youtube.com/watch?v=gg40RWiaHRY&t=223) first we need to decide on the size of our text characters or the area that they will take up in order to conserve as much image detail as we can we want our characters to be as small as 
[03:53](https://www.youtube.com/watch?v=gg40RWiaHRY&t=233) possible but just big enough to be legible for some reason returnal uses 10x10 characters which is pretty strange for reasons that'll make more sense later I chose to go with 8x8 characters 
[04:04](https://www.youtube.com/watch?v=gg40RWiaHRY&t=244) because it's a pleasant power of two and it's what I found to be the smallest possible resolution for legible text now that we know the size of our characters the idea is that the pixels of the image 
[04:14](https://www.youtube.com/watch?v=gg40RWiaHRY&t=254) are going to be replaced with text as you can see though the pixels aren't the same size as the letters a pixel is 1x one but our text is 8x8 so we need to modify the pixels to match the size of 
[04:26](https://www.youtube.com/watch?v=gg40RWiaHRY&t=266) the characters we could super sample the image and increase the size of the image by eight times but in a game context we'd go right back to square one as the render gets downscaled to fit your 
[04:36](https://www.youtube.com/watch?v=gg40RWiaHRY&t=276) monitor unfortunately this means we need to downscale the image and Destroy enough image detail to create pixels that are the same size as the text this is pretty easy we just divide the 
[04:47](https://www.youtube.com/watch?v=gg40RWiaHRY&t=287) dimensions of the image by the resolution of the text in our case we divide by eight which as you can see results in a lot of lost detail once we upscale back the pixels are now 
[04:56](https://www.youtube.com/watch?v=gg40RWiaHRY&t=296) equivalent in size to the asy characters now we just need need to establish a relationship between pixel and asy character this could be any possible relation but the simplest and best 
[05:07](https://www.youtube.com/watch?v=gg40RWiaHRY&t=307) option for us here is relating the luminance or brightness of the pixel to a specific character desaturating the image gives us the luminance but this brings up another problem there's a lot 
[05:17](https://www.youtube.com/watch?v=gg40RWiaHRY&t=317) of different possible luminance values way more than there are asky characters so to make our lives easier we want to reduce or quantize the luminance to a smaller set of possible values this will 
[05:28](https://www.youtube.com/watch?v=gg40RWiaHRY&t=328) also let us control how many asky characters there are I wanted 10 so we need to take all the possible luminance values and translate them to one of 10 values since luminance is already a 
[05:38](https://www.youtube.com/watch?v=gg40RWiaHRY&t=338) value between 0 and 1 we can quantize it down to 10 possible outputs by multiplying by 10 taking the floor and dividing by 10 now our image is composed of only 10 luminous values and it's 
[05:50](https://www.youtube.com/watch?v=gg40RWiaHRY&t=350) ready to be replaced with asy characters to do this we need a texture that contains the text we want our text to communicate luminance so a dark pixel should be a tiny letter or symbol and a 
[06:00](https://www.youtube.com/watch?v=gg40RWiaHRY&t=360) bright pixel should be a large letter or symbol this is the asy texture I created for my effect a near black pixel is represented with a space which is why you see only nine characters now to 
[06:11](https://www.youtube.com/watch?v=gg40RWiaHRY&t=371) replace the pixels with the corresponding asy character we use the luminance as the coordinate for where to start in the texture we take the pixel screen position mod by 8 to put it in 
[06:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=381) the 8x8 range of the asy character size and add the luminance to the horizontal texture coordinate to get the proper character that's really all there is to the basic asy Shader to make it look 
[06:32](https://www.youtube.com/watch?v=gg40RWiaHRY&t=392) more like returnal all we do is multiply by the downscaled color data while it certainly looks cool already it's kind of just a glorified half toning Shader even though it's technically all text to 
[06:44](https://www.youtube.com/watch?v=gg40RWiaHRY&t=404) fix this I wanted to try adding those Edge lines but how do we even start with something like that before we try to solve the edge problem let's clarify what exactly we need just edges alone 
[06:55](https://www.youtube.com/watch?v=gg40RWiaHRY&t=415) won't satisfy the needs of the asy Shader we also need to draw the edge with the prop symbol that conforms to the Contour for example a flat Edge should be drawn with an underscore a 
[07:05](https://www.youtube.com/watch?v=gg40RWiaHRY&t=425) vertical Edge should be drawn with a vertical bar and for angled edges we should use the corresponding slash this means we don't just need Edge data we also need to know the angle of the edge 
[07:14](https://www.youtube.com/watch?v=gg40RWiaHRY&t=434) which makes things a bit more complicated I've presented numerous Edge detection methods in my previous videos already so as a quick recap here are our options for detecting edges on images 
[07:25](https://www.youtube.com/watch?v=gg40RWiaHRY&t=445) alone we have the soo filter The canny Edge detector and the difference of gas I in a games context where we have more data to work with we have Edge detection through depth and normal difference and 
[07:35](https://www.youtube.com/watch?v=gg40RWiaHRY&t=455) the inverse whole method this is not a comprehensive list of all Edge detection methods just the ones I've talked about before thankfully the one we need is already present because only one of 
[07:45](https://www.youtube.com/watch?v=gg40RWiaHRY&t=465) these also gives us the direction of the edge the soble filter that's because the soo filter isn't really an edge detector it's an approximation of the image gradient when you hear gradient you 
[07:56](https://www.youtube.com/watch?v=gg40RWiaHRY&t=476) might think of a blend between two colors but in Vector Cal calculus the gradient of a function is a vector field where each Vector points in the direction of greatest change the soo 
[08:06](https://www.youtube.com/watch?v=gg40RWiaHRY&t=486) filter when convolved with our image gives us this gradient Vector for each pixel as you can see there is only change detected along the border of our circle with no change on the flat color 
[08:16](https://www.youtube.com/watch?v=gg40RWiaHRY&t=496) areas since these are vectors in two-dimensional space we can get the angle of the vector with the wonderful a tan 2 function giving us an angle between pi and Pi which we can convert 
[08:27](https://www.youtube.com/watch?v=gg40RWiaHRY&t=507) to 0 to 1 for Simplicity we now have the same problem we had earlier with the luminance there's a lot more angle values than there are Edge asky characters so we again want to reduce 
[08:36](https://www.youtube.com/watch?v=gg40RWiaHRY&t=516) the possible angle results to four values then we downscale the image to the size of the asy characters like before and use the quantized angle as the texture coordinate for the edge asy 
[08:47](https://www.youtube.com/watch?v=gg40RWiaHRY&t=527) texture and we have amazing asy edges it works kind of the edges may be lackluster but the proof of concept is there the edges follow the Contour of the original original image 
[09:00](https://www.youtube.com/watch?v=gg40RWiaHRY&t=540) unfortunately we can hardly call these edges though there's just too many gaps and holes in the edge line which is unacceptable for a simple Circle example our Shader should be able to draw a 
[09:10](https://www.youtube.com/watch?v=gg40RWiaHRY&t=550) circle just fine using the GPU to downscale and upscale the quantized angle buffer results in poorly conserved edges ideally we'd like a little more control over the output to keep the 
[09:20](https://www.youtube.com/watch?v=gg40RWiaHRY&t=560) downscaled edges as cohesive as possible to get that control we can use a handy dandy compute Shader as a quick review compute shaders are CPU programs for generic computation the work is executed 
[09:32](https://www.youtube.com/watch?v=gg40RWiaHRY&t=572) in groups and you the programmer get to decide on how many groups are dispatched and how large the groups are an ideal group size is 8x8 for 64 total threads coincidentally the same size as our asy 
[09:45](https://www.youtube.com/watch?v=gg40RWiaHRY&t=585) text then we simply dispatch enough groups to cover the full resolution Edge data and our compute Shader will decide if a tile should be counted as an edge in the downscaled output or not I did 
[09:55](https://www.youtube.com/watch?v=gg40RWiaHRY&t=595) this by having each thread determine which kind of edge its pixel is writing that to group shared memory then the first thread of the group would scan the group shared memory using the identified 
[10:05](https://www.youtube.com/watch?v=gg40RWiaHRY&t=605) Edge as an index for another array adding to that spot in the array and then afterwards find the max value in that array and using that as the edge that fills the downscaled pixel 
[10:14](https://www.youtube.com/watch?v=gg40RWiaHRY&t=614) basically we're constructing a local histogram of the edge data to figure out which kind of edge is most common in the 8x8 tile and using that as the simplified Edge output I added a 
[10:25](https://www.youtube.com/watch?v=gg40RWiaHRY&t=625) threshold parameter so that the tile needs a certain amount of edge pixels within it to to be counted as an edge and the result is a downscaled edge buffer that has far more cohesive Edge 
[10:34](https://www.youtube.com/watch?v=gg40RWiaHRY&t=634) lines than the original GPU downscale the circle is pretty much perfectly converted into edges that follow the Contour but what about a more complicated picture a yeah that looks 
[10:46](https://www.youtube.com/watch?v=gg40RWiaHRY&t=646) pretty bad this is because our Soo filter isn't actually Edge detecting to convert the soo filter into an edge detector we have to threshold the magnitude of the gradient essentially if 
[10:56](https://www.youtube.com/watch?v=gg40RWiaHRY&t=656) a high change is detected then it's an edge otherwise it's not this fixes the render but the problem with this is that the edges look like complete ass the soo filter is not meant to produce 
[11:06](https://www.youtube.com/watch?v=gg40RWiaHRY&t=666) aesthetically pleasing edges it's meant to extract features for data analysis we can fix this by adding another pre-processing step to our effect with a simple difference of gaussians we can 
[11:16](https://www.youtube.com/watch?v=gg40RWiaHRY&t=676) extract highfrequency details of the image in a way that looks more pleasant and then run the solo filter on that for Edge Direction data as you can see the difference of gaussian's edge lines look 
[11:26](https://www.youtube.com/watch?v=gg40RWiaHRY&t=686) far better than the soo filter edges in another video of mine I demonstrated how the difference of gaussians can be used for a wide variety of different art styles just by itself but here it takes 
[11:37](https://www.youtube.com/watch?v=gg40RWiaHRY&t=697) a back seat as a simple pre-processing step to improve the visuals and reliability of the asy Shader now all we have to do is layer the edges on top of the base asy pass and the ace Rolla asy 
[11:49](https://www.youtube.com/watch?v=gg40RWiaHRY&t=709) Shader is all finished this is about as far as we can take the asy Shader from a pure image processing standpoint but these few example renders show The Promise of the 
[11:59](https://www.youtube.com/watch?v=gg40RWiaHRY&t=719) effect static images are kind of boring though I wanted to see the effect in motion so I implemented what we have so far as a reshade Shader so we can use the effect on some games thankfully we 
[12:10](https://www.youtube.com/watch?v=gg40RWiaHRY&t=730) can make the effect look even cooler in a 3D context over in Final Fantasy 14 the effect looks exactly the same cuz it would be weird if it didn't but we can see that in motion the edges stay 
[12:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=741) visually cohesive over time and it looks surprisingly really good in a 3D context we can make the edges even more reliable by checking for substantial differences in depth and normal values on 
[12:33](https://www.youtube.com/watch?v=gg40RWiaHRY&t=753) neighboring pixels which will add some more EDG lines that the difference of gaussians fails to capture this makes the clothing of my character look a lot better so it's definitely worth the 
[12:42](https://www.youtube.com/watch?v=gg40RWiaHRY&t=762) extra Edge detection step one significant issue with the Shader though is that the high contrast causes eye fatigue pretty quickly staring at this effect for a while just does not feel 
[12:51](https://www.youtube.com/watch?v=gg40RWiaHRY&t=771) good especially when you're walking around and trying to actually parse the visual information because of this the asy Shader is probably best left as a photo mode effect like how returnal uses 
[13:02](https://www.youtube.com/watch?v=gg40RWiaHRY&t=782) it but there are some things we can do to remedy the eye fatigue the color of the asky letters and the background can be easily controlled instead of using black and white we can use a lower 
[13:11](https://www.youtube.com/watch?v=gg40RWiaHRY&t=791) contrast color combo another idea I had was to fade the Letters Out based on depth which I think looks pretty good and could make it more useful for an actual game the last option I added was 
[13:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=801) for not drawing edges after a certain distance which has a sort of depth of field effect at this point I was satisfied with the effect and did didn't need anything more it also runs pretty 
[13:31](https://www.youtube.com/watch?v=gg40RWiaHRY&t=811) fast already so we don't need to do any real optimizing so now we can experiment with the Shader and see what effects it looks good with as well as where the Shader looks good and where it looks bad 
[13:41](https://www.youtube.com/watch?v=gg40RWiaHRY&t=821) we've looked at Final Fantasy A lot so let's look at something a bit more modern Elden ring and see how the asy Shader handles some more complex visuals because asy art is a computer thing it's 
[13:51](https://www.youtube.com/watch?v=gg40RWiaHRY&t=831) probably best combined with other effects that evoke Tech Aesthetics you could go the Retro route with color quantization to try and improve the colored asy art from returnal then layer 
[14:01](https://www.youtube.com/watch?v=gg40RWiaHRY&t=841) a CRT filter on top and we already have a trendy indie game filter that would go crazy on Reddit you could keep it minimalist and try to make the game look like it's printed in the command prompt 
[14:11](https://www.youtube.com/watch?v=gg40RWiaHRY&t=851) which really is just the Basse asy Shader already with different colors I wanted to go the Epic neon cyberpunk route though because the asy Shader is just asking to be bloomed I didn't want 
[14:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=861) it to look like it's glowing I wanted it to look burnt so I added some tone mapping to increase the contrast sharpened it to make it crispier and then color burn the image I really like 
[14:32](https://www.youtube.com/watch?v=gg40RWiaHRY&t=872) how this looks and it makes me think of DSX for some reason with some creative Framing and vignettes you can make the game look even more novel this would look pretty cool for like a 
[14:40](https://www.youtube.com/watch?v=gg40RWiaHRY&t=880) point-and-click adventure game the Shader looks pretty nice on people The Edge detection makes hair look really cool and I particularly love how eyes look with the Shader applied but when 
[14:49](https://www.youtube.com/watch?v=gg40RWiaHRY&t=889) does the Shader not work you've probably noticed that all my example photos have been close-ups or very zoomed in this is because the effect looks best at at this close distance when you zoom out the asy 
[15:01](https://www.youtube.com/watch?v=gg40RWiaHRY&t=901) characters get a lot noisier and everything jumbles together stuff like faces at this distance are impossible to convert to asy because remember we are losing this much detail no matter what 
[15:12](https://www.youtube.com/watch?v=gg40RWiaHRY&t=912) but the edges do help identify separate shapes so with the depth fallof I mentioned earlier the game isn't entirely unplayable if you were to further separate entities with flat 
[15:22](https://www.youtube.com/watch?v=gg40RWiaHRY&t=922) colors you could probably create some cool Tron or super hot like visuals just how unplayable does this make ELD in ring though can I defeat Moog with the asy Shader on so I can finally play the 
[15:33](https://www.youtube.com/watch?v=gg40RWiaHRY&t=933) DLC unfortunately it draws over the UI so I have to do this without UI for [Applause] dearest 
[16:55](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1015) Micha you must abide alone a while welcome honored guest to the birthplace of our dasty also if you'd like to support the 
[17:21](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1041) Channel vote on future video topics and help me continue creating free resources for game development and Shader programming you can do that over on my patreon as usual a huge thank you to all 
[17:31](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1051) my current patrons without your support I wouldn't be able to speedrun Elden ring on a new character in time for the DLC release well that was easy the asy Shader was no burden at all in the end 
[17:43](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1063) this is the kind of Shader that you have to design entirely around due to its heavy restriction on image detail and it isn't like a CRT filter where you can kind of just slap it on and call it a 
[17:52](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1072) day it still makes for a really cool photo mode effect though and you can see some more images and videos of it over on my Twitter page if you'd like to play with it yourself the re-shade Shader 
[18:02](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1082) pack and source code are available in the description entirely for free as always anyways that's all from me I hope you have a great rest of your day and I'll see you next time 
[18:12](https://www.youtube.com/watch?v=gg40RWiaHRY&t=1092) [Music] 