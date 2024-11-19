---
URL: https://www.youtube.com/watch?v=Z_-am00EXIc
thumbnail: https://i.ytimg.com/vi/Z_-am00EXIc/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T13:10:29
published: 2024-01-20T01:23:03
duration: 959
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "15m 59s"]
# The Strange Graphics Of LETHAL COMPANY
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722131042.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=Z_-am00EXIc
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/Z_-am00EXIc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: The first 500 people to use my link will get a 1 month free trial of Skillshare: https://skl.sh/acerola01241 ! 

Lethal Company has some very compelling visuals, but how much of it did the developer make themselves? And how does it all come together?

Topics covered: Frame capturing, fixed resolution rendering, edge detection, posterization, depth of field, bloom

Support me on Patreon!
https://www.patreon.com/acerola_t

Socials:
Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Github: https://github.com/GarrettGunnell/

References:
https://github.com/Unity-Technologies/Graphics/blob/ce1905322722287c1420a6d85de14158c1648a84/Packages/com.unity.render-pipelines.high-definition/Runtime/PostProcessing/Shaders/UberPost.compute

This series is largely inspired by Muhammad's "Behind The Pretty Frames" series of articles which you can read here: https://mamoniem.com/category/behind-the-pretty-frames/

Music:
Afternoon Break - Persona 3 OST
In A Moment's Time - Skullgirls OST
Junes Theme - Persona 4 OST
During The Test - Persona 3 OST
A New Frontier - VA-11 Hall-A OST
Those Who Dwell In The Shadows - VA-11 Hall-A OST
Every Day Is Night - VA-11 Hall-A OST
Your Love Is A Drug - VA-11 Hall-A OST
Underground Club - VA-11 Hall-A OST
Just Like This - Persona 3 OST
Like A Dream Come True - Persona 4 OST
Climactic Return - Danganronpa 2 OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=Z_-am00EXIc&t=0) hello everyone lethal company is a game praised by many for its horror comedy oh oh oh 
[00:28](https://www.youtube.com/watch?v=Z_-am00EXIc&t=28) man and of course its unique visual style surely a game that looks this interesting must have lots of proprietary Shader tricks involved but 
[00:38](https://www.youtube.com/watch?v=Z_-am00EXIc&t=38) no nearly all the Shader effects you see come prepackaged with the unity engine so today let's figure out how you could make the graphics of lethal company let's start with a simple visual 
[00:56](https://www.youtube.com/watch?v=Z_-am00EXIc&t=56) study of a Leal company screenshot to get some idea of what's going on you might hear a lot of words you're not familiar with but don't worry everything will be explained in detail later the 
[01:06](https://www.youtube.com/watch?v=Z_-am00EXIc&t=66) first thing you might notice is the dense fog everything a short distance from the camera begins to fade into a more homogeneous color obscuring details we know this isn't fake fog because of 
[01:16](https://www.youtube.com/watch?v=Z_-am00EXIc&t=76) these God rays in the shadow of the piping making this legitimate volumetric lighting and not just fake distance fog it's even more obvious if we look at these spotlights without the volumetric 
[01:25](https://www.youtube.com/watch?v=Z_-am00EXIc&t=85) light simulation then we wouldn't see these cones of light the next most obvious thing is that something strange is going on with the light surface interactions a point appears to be 
[01:34](https://www.youtube.com/watch?v=Z_-am00EXIc&t=94) either fully lit or fully in Shadow with no gradient or anything in between this could be a lot of different techniques but no matter what some quantization is being used here to reduce the amount of 
[01:44](https://www.youtube.com/watch?v=Z_-am00EXIc&t=104) values used to color objects we also have some Edge detection going on here but it seems to be that edges are only visible close to the camera you can see the edge here on the cliff but no edges 
[01:54](https://www.youtube.com/watch?v=Z_-am00EXIc&t=114) on the rocks in the distance then there's this blurry helmet obscuring parts of the screen this could potentially be a simple post-processing effect but that is to be determined next 
[02:02](https://www.youtube.com/watch?v=Z_-am00EXIc&t=122) we have the low resolution of the entire image it's clearly being upscaled from a lower resolution because everything is kind of low quality lastly we have every Gamer's favorite effect Bloom most 
[02:13](https://www.youtube.com/watch?v=Z_-am00EXIc&t=133) obviously on the Rocks here because the bloom bleeds onto the Shadows here's another example of the bloom blobs that's about everything we can also assume the usual color Corrections like 
[02:23](https://www.youtube.com/watch?v=Z_-am00EXIc&t=143) exposure and Gamma but it's hard to say how exactly those are being used without more information but a Rolla what about about those clouds up there oh that's just like a Skybox yoinked from Google 
[02:33](https://www.youtube.com/watch?v=Z_-am00EXIc&t=153) street view or something I don't know anyways we can Theory craft about these Shader effects all day if we want thinking about what order they are used in or whatever or we could just use this 
[02:43](https://www.youtube.com/watch?v=Z_-am00EXIc&t=163) handy dandy program to frame capture the game so that we can see all the details that go into how it was rendered the same method I used to get info about the Counterstrike 2 smoke grenades but first 
[02:53](https://www.youtube.com/watch?v=Z_-am00EXIc&t=173) something a little different this video is sponsored by skillshare skillshare is the largest online learning Community for creatives with thousands of classes led by actual industry professionals 
[03:04](https://www.youtube.com/watch?v=Z_-am00EXIc&t=184) across all disciplines like programming illustration business music culinary and many more skillshare is the perfect platform to get started with learning pretty much anything and they recently 
[03:15](https://www.youtube.com/watch?v=Z_-am00EXIc&t=195) made it even easier with learning paths which are curated classes meant to be taken in order to give you the proper path from beginner to intermediate to Advanced On Any Given topic skillshare 
[03:26](https://www.youtube.com/watch?v=Z_-am00EXIc&t=206) isn't just for beginners though the learning path I found most interesting was for helping Freelancers with price negotiations as well as building their personal brand which is something many 
[03:35](https://www.youtube.com/watch?v=Z_-am00EXIc&t=215) of my independent professional colleagues tend to neglect be sure to try out everything skillshare has to offer by following the link on screen or in the description the first 500 people 
[03:44](https://www.youtube.com/watch?v=Z_-am00EXIc&t=224) to use my link will also get a free 1-month trial thanks so much to skillshare for sponsoring this video now back to lethal company if you're unfamiliar with what a frame capture is 
[03:54](https://www.youtube.com/watch?v=Z_-am00EXIc&t=234) essentially this program captures all the graphics API calls that were made by the game for instance when the GPU is told to draw an object then the program will capture that and then we can 
[04:04](https://www.youtube.com/watch?v=Z_-am00EXIc&t=244) completely reconstruct the frame by executing those same exact API calls in order again this particular capture needs 16,000 API calls to draw the frame and we can see the details of each and 
[04:15](https://www.youtube.com/watch?v=Z_-am00EXIc&t=255) every one in addition Nvidia Insight does a full GPU memory dump so that we can use all the same assets like 3D models textures and decompiled shaders this is how I know lethal company is 
[04:26](https://www.youtube.com/watch?v=Z_-am00EXIc&t=266) made with unity because the names of the shaders in each pass follow un's Shader lab naming convention where the editor will sort the Shader into categories based on the slashes for instance this 
[04:36](https://www.youtube.com/watch?v=Z_-am00EXIc&t=276) Shader is in the hidden category so it won't show up in the unity editor and it's part of the hdrp shaders this means lethal company is using unity's highdef rendering pipeline the same rendering 
[04:47](https://www.youtube.com/watch?v=Z_-am00EXIc&t=287) backend used by the recently controversial City skylines 2 if you aren't chronically online City skylines 2 released with terrible performance issues even 40 series cards were 
[04:58](https://www.youtube.com/watch?v=Z_-am00EXIc&t=298) struggling to get real time from frame rates a big reason why the performance is so bad is because hdrp isn't really meant to have good performance its Shader effects are extremely expensive 
[05:08](https://www.youtube.com/watch?v=Z_-am00EXIc&t=308) and meant to give the best visuals possible hence the name lethal company runs very fast though on my mid-range PC it's clearing 100 FPS without any issues so why is it so much faster than City 
[05:20](https://www.youtube.com/watch?v=Z_-am00EXIc&t=320) skylines 2 well the reasons for that are endless but a big one is that lethal company is actually rendered at a very small resolution if we take a look at the view details in the profiler it's 
[05:31](https://www.youtube.com/watch?v=Z_-am00EXIc&t=331) 860 x 520 not 1920 x 1080 like it should be if it were rendering at my full native resolution 860 x 520 is a really strange number normally if a game is rendering at a lower Target resolution 
[05:44](https://www.youtube.com/watch?v=Z_-am00EXIc&t=344) then it's some sort of factor of the Native resolution for instance I'm at 1080p I would render it some smaller 16x9 resolution so that it cleanly upscales into my native resolution 
[05:54](https://www.youtube.com/watch?v=Z_-am00EXIc&t=354) lethal company doesn't do this it renders at a fixed 860 by 520 regardless of the Native resolution you're playing at meaning that the image gets warped depending on the monitor you play with 
[06:05](https://www.youtube.com/watch?v=Z_-am00EXIc&t=365) in our case the image is going to be warped horizontally to fill the space this is one of the main reasons why lethal company looks a bit strange it's also why the game is so pixelated and 
[06:14](https://www.youtube.com/watch?v=Z_-am00EXIc&t=374) low quality if you play at 1440p or 4K then this lowquality aesthetic is going to be significantly more pronounced but this strikes one mystery off the list the game looks low quality because it's 
[06:26](https://www.youtube.com/watch?v=Z_-am00EXIc&t=386) actually low quality it's not faked with a Shader effect this has the added benefit of making the entire game extremely cheap lowering the target resolution of expensive hdrp shaders 
[06:37](https://www.youtube.com/watch?v=Z_-am00EXIc&t=397) makes them way less expensive anyways let's take a look at this Frame from the beginning the frame starts with drawing all the objects in view annoyingly Unity renders games upside down for whatever 
[06:48](https://www.youtube.com/watch?v=Z_-am00EXIc&t=408) reason so I'll be turning it right side up for your viewing convenience you can thank me over on patreon as usual a huge thank you to all my current patrons without your support I wouldn't be able 
[06:58](https://www.youtube.com/watch?v=Z_-am00EXIc&t=418) to take the time to rotate the the video 180° you might be wondering why the objects have such strange colors instead of being drawn fully lit and colored like you're used to real-time rendering 
[07:08](https://www.youtube.com/watch?v=Z_-am00EXIc&t=428) has two main Tech trees forward and deferred forward rendering is how you would intuitively think a game is rendered when we draw an object then we do all the lighting and coloring 
[07:18](https://www.youtube.com/watch?v=Z_-am00EXIc&t=438) calculations immediately and write the output to the back buffer deferred rendering is a bit different instead when we draw an object we write all sorts of information about it to 
[07:27](https://www.youtube.com/watch?v=Z_-am00EXIc&t=447) something called the g-buffer you might think that stands for graphics buffer but no it stands for geometry buffer obviously this info we write is stuff like the normal vector or anything else 
[07:37](https://www.youtube.com/watch?v=Z_-am00EXIc&t=457) we could possibly want for later then during postprocessing we do all of our lighting calculations based on what was written in the g-buffer mostly everything in the Game Dev world has 
[07:47](https://www.youtube.com/watch?v=Z_-am00EXIc&t=467) used deferred although in reality it's some unethical Frankenstein monster of the two lethal company does not stray from the pack and also makes use of deferred rendering which is why we are 
[07:57](https://www.youtube.com/watch?v=Z_-am00EXIc&t=477) seeing the data that is being written into the G buffer here I would skip to the lighting pass so we can see the proper colors but there's one very important draw call that we don't want 
[08:06](https://www.youtube.com/watch?v=Z_-am00EXIc&t=486) to miss event 794 draws the helmet we see in the screenshot if we check out the model data in the frame debugger then we can confirm this is in fact the visor of the helmet the player model 
[08:17](https://www.youtube.com/watch?v=Z_-am00EXIc&t=497) wears and it's not faked with a Shader as a postprocess which answers one of our earlier questions and now we can move on before we can do lighting Unity needs to do all of its shadow mapping in 
[08:27](https://www.youtube.com/watch?v=Z_-am00EXIc&t=507) hdrp Fancy expensive lighting pre-calculations this takes about 8,000 API calls which means about half the frame time is spent on the fancy volumetric lighting we see in our 
[08:38](https://www.youtube.com/watch?v=Z_-am00EXIc&t=518) screenshots I'm not going to explain how the volumetric light works if you're interested though the logic is very similar to the techniques presented in my Counterstrike 2 smoke video If you 
[08:48](https://www.youtube.com/watch?v=Z_-am00EXIc&t=528) recall from that video this stuff is very expensive but this expense is clearly worth it as lethal company makes heavy use of volumetrics as a gameplay mechanic mainly for obscuring vision 
[08:58](https://www.youtube.com/watch?v=Z_-am00EXIc&t=538) both in in the dungeon and on the surface after Unity has finished pre-calculating the lighting then the Deferred lighting pass executes all of the objects in frame have their lighting 
[09:07](https://www.youtube.com/watch?v=Z_-am00EXIc&t=547) drawn then Unity draws the Sky Box in and then composits the frame with the volumetric fog this lighting Shader isn't anything proprietary either it is just hdp's default physically based lit 
[09:18](https://www.youtube.com/watch?v=Z_-am00EXIc&t=558) Shader so it ends up not being too different from a simple lambers diffuse that I've discussed in previous videos the frame at this point is pretty interesting this is what lethal company 
[09:27](https://www.youtube.com/watch?v=Z_-am00EXIc&t=567) would look like without any it stylistic effects this is surprisingly very useful information we know that the entire scene is drawn with realistic lighting first and then it gets stylized meaning 
[09:38](https://www.youtube.com/watch?v=Z_-am00EXIc&t=578) that at this point everything is post-processing which is my specialty how convenient this independent stylization is the first and only proprietary aspect of lethal company's 
[09:48](https://www.youtube.com/watch?v=Z_-am00EXIc&t=588) rendering which means the developer made it themselves and I have to figure out how it works great the name of this Shader is posterization filter and it was made with Shader graph unity's 
[09:58](https://www.youtube.com/watch?v=Z_-am00EXIc&t=598) node-based Shader editor the name gives us a pretty big hint of what's going on like I said earlier there is some obvious quantization going on and posterization is kind of just another 
[10:08](https://www.youtube.com/watch?v=Z_-am00EXIc&t=608) word for that if we take a look at a before and after though there's clearly more than just posterization we've got the edges in this past as well and if we take a look at the Shader assembly 
[10:17](https://www.youtube.com/watch?v=Z_-am00EXIc&t=617) there's a lot going on so we've got to figure out at least two things ourselves what's being posterized and how are edges being detected for the posterization it's going to be easier if 
[10:27](https://www.youtube.com/watch?v=Z_-am00EXIc&t=627) we swap to a different frame capture somehow even though we're not outside anymore this capture takes nearly 20,000 events to fully draw which is interesting this is because a ton of 
[10:38](https://www.youtube.com/watch?v=Z_-am00EXIc&t=638) time is wasted drawing things that aren't even in view which should probably be fixed but that's not really the point of this video so let's move on it took me a little bit to figure out 
[10:47](https://www.youtube.com/watch?v=Z_-am00EXIc&t=647) what's going on here because lethal company is pulling a dastardly trick normally when you posterize something you posterize the colors reducing the amount of allowed colors to a much 
[10:58](https://www.youtube.com/watch?v=Z_-am00EXIc&t=658) smaller amount the smaller amount of allowed values the more prominent the compression artifacts become resulting in these Blobs of color because there aren't enough colors to close the 
[11:07](https://www.youtube.com/watch?v=Z_-am00EXIc&t=667) gradients for some more info on why this is really useful and not bad actually you can check out these two videos of mine we see similar artifacts in our lethal company frame so you might assume 
[11:17](https://www.youtube.com/watch?v=Z_-am00EXIc&t=677) it's color data being quantized as usual but no if you take a closer look you can actually see color gradients so colors are not being compressed instead lethal company is quantizing the volum El 
[11:29](https://www.youtube.com/watch?v=Z_-am00EXIc&t=689) lighting data and applying it again that's right lethal company is making the most of its expensive Shader Effects by doubling up on their results first in a realistic way and then in a stylized 
[11:41](https://www.youtube.com/watch?v=Z_-am00EXIc&t=701) way that's why the floor here is noisy the volumetric light data is noisy so when it's quantized the noise gets exaggerated but a Rolla what about those weird squiggly lines on the wall that 
[11:52](https://www.youtube.com/watch?v=Z_-am00EXIc&t=712) kind of looks like posterization I thought that too but it's actually a second Edge detection when we take a peak and at the dreaded Shader assembly we can see that the Shader is doing two 
[12:02](https://www.youtube.com/watch?v=Z_-am00EXIc&t=722) neighborhood samples one of the depth buffer and one of the color buffer the simplest method of edge detection is by calculating the local maximum contrast of a pixel that is the largest 
[12:12](https://www.youtube.com/watch?v=Z_-am00EXIc&t=732) difference between neighboring pixels if this contrast value exceeds an arbitrary threshold then an edge exists there the contrast value is usually calculated with depth or normals which lethal 
[12:23](https://www.youtube.com/watch?v=Z_-am00EXIc&t=743) company is doing for one of the edge detections but it could technically be done with anything like color data the problem with that though is colors are three component vectors so we need to 
[12:33](https://www.youtube.com/watch?v=Z_-am00EXIc&t=753) reduce it to a single value either by only comparing one of the three components or calculating some value like luminance or saturation the answer to which method lethal company is using 
[12:43](https://www.youtube.com/watch?v=Z_-am00EXIc&t=763) is somewhere in the Shader assembly but I don't get paid nearly enough to interpret that for you beyond a basic level I'm just going to assume it's the luminance of the color because that's 
[12:52](https://www.youtube.com/watch?v=Z_-am00EXIc&t=772) what I would do beyond the light posterization and double edge detection there's not much else to the main stylistic path of lethal company but the effect that comes next might surprise 
[13:01](https://www.youtube.com/watch?v=Z_-am00EXIc&t=781) you a bit in case you forgot the black shapes on the border of the frame is the visor of the player character's helmet normally something this close to the camera or even your real life eye would 
[13:12](https://www.youtube.com/watch?v=Z_-am00EXIc&t=792) be out of focus but since our game camera is not a real camera or eyeball it's instead fully sharp like everything else in view what is a Shader effect we could use to simulate camera or eyeball 
[13:23](https://www.youtube.com/watch?v=Z_-am00EXIc&t=803) Focus that's right depth of field lethal company makes use of unities of absurdly expensive depth of field Shader to blur the helmet visor which is funny because this Shader effect is one of many things 
[13:35](https://www.youtube.com/watch?v=Z_-am00EXIc&t=815) that could be entirely responsible for city skylines 2 running so terribly the depth of field is calculated right after the posterization pass giving us the Blurred helmet visor and will also 
[13:46](https://www.youtube.com/watch?v=Z_-am00EXIc&t=826) slightly blur held items I think it's really funny that something so expensive is being used for something so easily faked but again lethal company gets away with it because of the very small render 
[13:57](https://www.youtube.com/watch?v=Z_-am00EXIc&t=837) resolution after depth of field we we have the onew combo of Shader effects all Gamers love to complain about bloom bloom is fairly straightforward you separate the bright pixels blur them and 
[14:07](https://www.youtube.com/watch?v=Z_-am00EXIc&t=847) then add it back to the original image but we don't only have Bloom here Unity is doing the right thing and condensing a whole lot of final tweaks into one Mega final pass called Uber post most of 
[14:19](https://www.youtube.com/watch?v=Z_-am00EXIc&t=859) the time we'd be out of luck with this pass like we were earlier with the posterization pass and would have to figure out what's going on ourselves but thankfully Unity actually has the Shader 
[14:28](https://www.youtube.com/watch?v=Z_-am00EXIc&t=868) code for all their shaders on GitHub which is an insanely valuable resource the Uber post compute Shader does a whole lot of effects in one big pass these being lens Distortion chromatic 
[14:39](https://www.youtube.com/watch?v=Z_-am00EXIc&t=879) aberration Bloom application vignetting color grading post exposure and Gamma correction lethal company is pretty clearly only using the bloom post exposure and maybe the color grading to 
[14:50](https://www.youtube.com/watch?v=Z_-am00EXIc&t=890) make it more saturated after this pass the UI is drawn and Gamma correction is applied before the frame is presented to the screen and we have success Yul drawn one frame of the game with all that 
[15:01](https://www.youtube.com/watch?v=Z_-am00EXIc&t=901) finished let's do a quick recap first all the objects in the scene are drawn and realistically liveit unity's atmospheric scattering simulation is composited with the image to create a 
[15:11](https://www.youtube.com/watch?v=Z_-am00EXIc&t=911) realistic fog the developer's custom posterization Shader is applied next drawing edges based on depth and some mystery color difference and then applying a second layer of volumetric 
[15:21](https://www.youtube.com/watch?v=Z_-am00EXIc&t=921) light but thresholded to create a posterization effect the helmet visor is blurred with unity's hdrp depth of field Shader and the frame finishes with Bloom as well as some final color Corrections 
[15:31](https://www.youtube.com/watch?v=Z_-am00EXIc&t=931) before being upscaled to fit the screen from its low fixed resolution giving it the pixelated aesthetic despite being an ultimately simple stylized rendering pipeline lethal company's visuals are 
[15:42](https://www.youtube.com/watch?v=Z_-am00EXIc&t=942) compelling and I hope it can serve as a point of inspiration for people that think these realistic effects can only be used for realistic Graphics or that they have to know Shader programming to 
[15:52](https://www.youtube.com/watch?v=Z_-am00EXIc&t=952) make an interesting looking game as usual thanks for watching I hope you have a great rest of your day and I'll see you next time 