---
URL: https://www.youtube.com/watch?v=E9-LRRDVmo8
thumbnail: https://i.ytimg.com/vi/E9-LRRDVmo8/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:51:34
published: 2021-10-30T10:00:02
duration: 529
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "8m 49s"]
# Making an Inktober Shader
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155238.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=E9-LRRDVmo8
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/E9-LRRDVmo8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: In this Halloween special, we look at an effect I wrote that makes videos games look like ink drawings for Inktober.

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Code: https://github.com/GarrettGunnell/Inktober-Ink-Shader

References:
https://en.wikipedia.org/wiki/Canny_edge_detector

Music:
This Is Halloween - Kingdom Hearts 2 OST

Chapters:
00:00 Intro
00:26 The Plan
01:13 Edge Detection
05:09 Stippling
06:34 Improvements
07:58 Conclusion

Thanks for watching!

This video is dedicated to my friend, Alotryx.

also please subscribe haha please man please just subscribe dude please just like one sub I swear I'm not addicted please man please just one sub please

# Transcript
[00:11](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=11) hey everyone and welcome to a new video or a not so new video if you're watching this in the future today we're going to be looking at how i made this picture look like this with an inktober inspired 
[00:23](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=23) post-processing shader in unity since this effect is of my own creation and not an implementation of someone else's work i kind of needed to have a general idea of how i wanted it to work 
[00:37](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=37) the plan here was to try and detect the edges of an image and separate them so that the image looks like a sketch then i wanted to layer these edges on top of a stippled render of the original 
[00:49](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=49) image and this would ideally make the image look like an ink drawing that was sketched and then shaded to illustrate this an individual shader passes the first pass is edge detection the second 
[01:02](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=62) pass is stippling the third pass will combine these two buffers and then the fourth pass will color it all so with a plan figured out let's look at finding the image edges 
[01:14](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=74) edge detection is a very difficult task in the context of image effects and you may ask yourself acerola what do you mean the edge is right there and you're right it's very obvious for 
[01:27](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=87) us as humans what is an edge and what isn't but image effects operate on a per pixel basis so to get a real judgment of what an edge looks like to a computer we need to zoom all the way in 
[01:40](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=100) once again even looking at just these 6 pixels the edge is obvious but this is rarely what images actually look like what if the pixels looked like this instead is this an edge or not and 
[01:51](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=111) that's a hard question to answer and precisely why edge detection is a non-trivial task when i was starting i tried to make my own little edge detector using contrast 
[02:02](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=122) thresholding essentially if the contrast between two pixels exceeded a given threshold then i would say that's an edge and this didn't work at all or at least not well enough to be actually 
[02:13](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=133) useful so i started researching real world edge detection algorithms and i came across one known as the canny edge detector canny edge detection is a five pass effect which are as follows one we 
[02:26](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=146) blur the image to smooth it and remove any noise two we find the intensity gradient of the image three is magnitude thresholding four is double thresholding 
[02:38](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=158) and five is edge tracking by hysteresis and there's a lot of really complicated words here but i promise the concepts are really simple we're going to completely ignore the first pass because 
[02:50](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=170) i didn't want to blur my images as video game renders don't have the problem that it is trying to solve so my implementation is a 4 pass effect finding the intensity gradient of an 
[03:02](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=182) image is a really fancy way of saying that it is calculating the change in intensity of an image where there is a high change in intensity there could be an edge such as a shift from black to 
[03:13](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=193) white this works by convolving two matrices around a pixel then taking the magnitude of these two values the matrices you use depend on the implementation so i personally used the 
[03:25](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=205) sobel operator which is the industry standard applying this to our example image makes it look like so the white areas are where there is a high change in 
[03:34](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=214) intensity the next pass which is magnitude thresholding keeps every pixel that has the largest or equivalent gradient magnitude compared to its neighbors and 
[03:45](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=225) this thins a lot of the potential edges down and makes it look like this which i think actually looks really cool the next pass is a double thresholding that is parameterized by the programmer 
[03:56](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=236) and optimal thresholds are kind of unique to individual images so you have to play around with it a bit the way it works is we have a high threshold value and a low threshold value if the 
[04:07](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=247) intensity of a pixel is higher than the high threshold then it is marked as a strong edge if the intensity is between the two values it is a weak edge and if the intensity of a pixel is lower than 
[04:20](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=260) the low threshold it's removed entirely the final pass which is edge tracking by hysteresis takes the weak and strong edge pixels from before and it removes every weak edge pixel that is not 
[04:32](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=272) surrounded by at least one strong edge pixel and that's it we now have an image with everything except the detected edges removed obviously it's not perfect and 
[04:43](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=283) it kind of reminds me of that scene from spongebob where he draws like a really complicated face and then erases all of it and then we get a perfect circle but the next thing i wanted to do with 
[04:54](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=294) the edges was blur them a bit so that it looks like the ink is bleeding into the background this is a simple pass i just had every pixel become a weighted average of its neighbors so that it 
[05:04](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=304) slightly blurs the whole image but maintains the strong edge lines [Music] with our linebuffer complete we can now look into stippling i'm not going to 
[05:15](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=315) make this very complicated but there's a lot of really cool intricate ways to stimple images with stuff like voronoi diagrams but i'm going to keep it simple and use blue noise dithering blue noise 
[05:27](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=327) in the context of computer graphics refers to any noise with a few low frequency components and no concentrated spikes in energy basically it's like equally distributed 
[05:38](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=338) noise and it visually looks like this as a texture i'm a busy boy so i didn't want to write my own script for generating blue noise so i used one of the many free blue noise textures on the 
[05:48](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=348) internet the way the stippling works is that we sample the blue noise and then we sample the luminance of the image and if the luminance is above that noise value then 
[05:58](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=358) we keep it otherwise we discard it and when applied to the image it looks like so now we can combine our two effects drum roll please 
[06:11](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=371) and it looks like the blur i put on the lines contrasts heavily with the stippling the lines are too thick and the stippling feels way 
[06:24](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=384) too dense anyways thank you guys for watching i gotta go now and i hope i see you next time okay just kidding we'll fix the effect 
[06:36](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=396) fixing the lines is easy all we have to do is remove the blur pass and thin the lines down a bit i actually had a pass that was thickening the lines that i didn't mention earlier so i'll just 
[06:47](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=407) remove that too next i want to make the stippling a lower resolution this can be achieved by multiplying the uv coordinates of the pixel by a decimal so that when it 
[06:58](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=418) samples the blue noise texture it functionally enlarges the noise as it tiles across the image to demonstrate here is normal uv coordinates for sampling and here is uv coordinates 
[07:08](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=428) multiplied by 0.5 the stipple effect becomes much lower resolution and in my opinion it looks a bit more organic there's one last change i want to make which i came up with while i was at work 
[07:20](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=440) i want to modify the line width based on the luminance of the image at that point so brighter edges have thinner lines and darker edges have thicker lines with this change to the effect i think it 
[07:31](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=451) makes the lines look much more interesting with that the effect is complete i think all that's left is to color it i went into photoshop and i made a simple paper 
[07:41](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=461) and ink texture i took an off-white color for the paper and i applied a little bit of noise to it and i did the same thing for the ink but with a really dark warmer color 
[07:51](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=471) sampling these textures accordingly makes renders now look like this which i think gives off the vibe of paper and ink overall i'm pretty happy with how this 
[08:02](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=482) effect turned out it is written as a post-processing shader so it can be used for both video games and as a general image effect to show you how it would look in a video game i applied it to one 
[08:13](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=493) of my old screenshots from cyberpunk 2077 and i think it looks pretty good please let me know what you think in the comments anyways i've got something special 
[08:23](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=503) planned for the next video so be sure to subscribe so you know when that video comes out also check out my twitter for project updates but i've gotta go now so have a great rest of your day and i'll 
[08:34](https://www.youtube.com/watch?v=E9-LRRDVmo8&t=514) see you next time you 