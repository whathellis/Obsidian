---
URL: https://www.youtube.com/watch?v=tvKLXbhVBnw
thumbnail: https://i.ytimg.com/vi/tvKLXbhVBnw/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:53:19
published: 2021-11-13T11:00:14
duration: 427
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "7m 7s"]
# What Is 𝓖𝓸𝓸𝓬𝓱 Shading?
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155331.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=tvKLXbhVBnw
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/tvKLXbhVBnw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: An explanation and implementation of Amy Gooch's non-photorealistic effect for technical illustration.

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Code: https://github.com/GarrettGunnell/Gooch-Shading

References:
https://users.cs.northwestern.edu/~ago820/SIG98/gooch98.pdf

The opening line is from Short Truth by Yumi Zouma

Music:
Gold Falls Casino - HuniePop OST

Chapters:
00:00 Intro
01:22 Disclaimer
01:37 The Plan
02:45 The Implementation
06:15 Conclusion

Thanks for watching!

This video is dedicated to my friend, Alotryx.

also please subscribe haha please man please just subscribe dude please just like one sub I swear I'm not addicted please man please just one sub please

# Transcript
[00:03](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=3) hello everyone and welcome to a new video or a not so new video if you're watching this in the future i'd like to start off by showing you this sphere it's a beautiful sphere with 
[00:16](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=16) lighting and a cute specular highlight but it has an issue half of this sphere is completely black it is impossible to tell what detail exists there for all we know the answer 
[00:28](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=28) to life itself exists in that dark pitch-black recess of the sphere this poses a problem wouldn't you think while it looks realistic and is fine for video games in research papers the 
[00:42](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=42) reader should be able to see all the detail of a model this problem is something amy gooch seeked to solve where she and her colleagues devised a post-processing 
[00:53](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=53) effect called gooch shading you may now laugh but only once in this paltry programming installment we'll be going over an implementation of 
[01:05](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=65) the effect she proposed in 1998. uh oh we've got a disclaimer this video contains extensions of topics discussed in an earlier video making images look like ink drawings i 
[01:34](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=94) highly recommend you watch that video first and then you return formally gooch shading is a non-photorealistic effect and is mainly used for technical illustration it seeks 
[01:47](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=107) to emulate man-made technical drawings which tend to have very defined edge lines and non-realistic lighting to show the viewer complete detail gooch shading requires a model that has 
[02:00](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=120) been fong shaded meaning that it is diffusely lit and has specular highlighting with this fong shaded model we define two colors a warm color and a cool color the warm color will indicate 
[02:15](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=135) surfaces that are facing towards the light source and the cool color will indicate surfaces that are facing away we then map the model's lighting to this new lighting such that shading occurs 
[02:28](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=148) only in mid-tones and all details of a model will become completely visible while still maintaining viewer knowledge of lighting after this cool to warm shading we draw all the edges in black 
[02:41](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=161) to further accentuate the model's detail to begin let's start with a basic phong shader it's nothing special we just calculate the diffused lighting and then we calculate the specular highlight and 
[02:55](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=175) then we add them together gooch shading begins by hijacking this diffused lighting and replacing it with an equation that blends between our cool and warm colors this equation looks like 
[03:08](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=188) so the l.n is our traditional diffused lighting but it differs in that we don't clamp the result to 0 to 1 rather we take into account its full range of 
[03:20](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=200) negative one to one so we can get a complete gradient from our cool color to the warm color representing this in the code we have now inserted the gooch and we can take a 
[03:31](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=211) look at the sphere in unity while this looks pretty much like what we want it lacks creative control and it also doesn't represent what the model's color is 
[03:41](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=221) in the paper it goes over a more refined definition of the cool and warm colors that will also include the underlying model's color these two equations look like so 
[03:54](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=234) here we have k of blue and k of yellow which represent the saturation of our gooch colors on the right of the equation we have two parameters alpha and beta which will control how strong 
[04:08](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=248) the underlying color of the model is plugging these new colors back into the gooch equation with parameters provided by the paper we achieve the gradient that we are looking for 
[04:22](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=262) now we have to draw all the edges of the model black to accentuate the detail if you remember from my previous video making images look like ink drawings i went over an image effect version of 
[04:36](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=276) edge detection known as canny edge detection this was so i could use the effect on any image which is a major restriction because gooch shading is only for 3d 
[04:47](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=287) models we can use a much more competent method of edge detection that is commonly used in any game that has tune shader outlines such as manifold garden and borderlands 
[04:58](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=298) in unity rendered objects have their distance from the camera written to a texture known as the camera depth texture by sampling a pixel of that texture we know how far away it is from 
[05:11](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=311) the camera and consequently if we sample the neighbors of a pixel we know if there is any large difference in their depths if there's a large difference in depth then clearly there's an edge there 
[05:24](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=324) this method of edge detection is very simply called depth-based edge detection with this effect applied to our gooch model the effect is complete the gradient is clear we know which parts of 
[05:37](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=337) the surface are lit and which are unlit and edges and details are very clearly visualized and shown unfortunately i have no cool 3d models of my own to apply this to so i will 
[05:50](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=350) show you examples from the paper sorry here we have a fong shaded raptor foot its detail is mostly unclear as large portions of the model are completely black 
[06:02](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=362) when the gooch shading is applied the detail of the model becomes much clearer as you can see here on the bones of the toes which were previously black overall gooch shading is a very simple 
[06:20](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=380) and powerful effect that is commonly used for technical illustration but has been used in other contexts as well like team fortress 2 which used gooch shading for its illustrative rendering did i 
[06:33](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=393) make this video entirely because of the name yes this was a quick video to get myself back on schedule post game jam which if 
[06:42](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=402) you haven't seen my game jam video please go watch it now i'd also appreciate if you subscribed and checked out my other social media as well but i've got to go now i hope you have a 
[06:54](https://www.youtube.com/watch?v=tvKLXbhVBnw&t=414) great rest of your day and i'll see you next time you 