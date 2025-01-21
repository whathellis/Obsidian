---
URL: https://www.youtube.com/watch?v=9dr-tRQzij4
thumbnail: https://i.ytimg.com/vi/9dr-tRQzij4/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T13:04:31
published: 2023-10-31T08:57:45
duration: 1731
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "28m 51s"]
# How Are Games Rendering Fur?
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722130509.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=9dr-tRQzij4
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/9dr-tRQzij4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: Get an exclusive @Surfshark deal! Enter promo code ACEROLA for an extra 3 months free at https://surfshark.deals/acerola 

It's easy to understand why fur is extremely problematic with its high density of objects and physical complexities, but somehow games have been rendering it for years! How could something so complex be so easily simplified?

Topics covered: Hair and its rendering complexities, shell texturing, half lambert, shell texturing applications, limitations of the technique, and overdraw

Code: https://github.com/GarrettGunnell/Shell-Texturing

Support me on Patreon!
https://www.patreon.com/acerola_t

Socials:
Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
TikTok: https://www.tiktok.com/@acerola_t
Discord: https://discord.gg/FxGQvbfm6Y

Resources:
https://hhoppe.com/fur.pdf
https://xbdev.net/misc_demos/demos/fur_course_notes/paper.pdf
https://thegamedev.guru/unity-gpu-performance/overdraw-optimization/
https://www.gamedev.net/forums/topic/655602-why-discard-pixel-take-a-noticeable-performance-hit/

Music:
Afternoon Break - Persona 3 OST
This Mysterious Feeling - Persona 3 OST
Midori Eyes - Paradise Killer OST
During The Test - Persona 3 OST
Junes Theme - Persona 4 OST
Every Day Is Night - VA-11 Hall-A OST
Underground Club - VA-11 Hall-A OST
Those Who Dwell In The Shadows - VA-11 Hall-A OST
Your Love Is A Drug - VA-11 Hall-A OST
GO!GO!STYLE - Paradise Killer OST
Joy - Persona 3 OST
Sandgem Town - Pokemon Diamond OST
Like A Dream Come True - Persona 4 OST
Layer Cake - Persona 5 OST
Prof. Omochao - Sonic Adventure 2 OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=9dr-tRQzij4&t=0) this video has been sponsored by surf shark hello everyone if you've ever thought about hair for even a moment you could easily conclude that it's probably hard to render when even movies are 
[00:10](https://www.youtube.com/watch?v=9dr-tRQzij4&t=10) struggling to get good hair CGI that means it must be even harder for us to render hair in video games so what's the big deal what makes hair so difficult to model and how are video games solving 
[00:20](https://www.youtube.com/watch?v=9dr-tRQzij4&t=20) this problem hair and other similar materials are kind of unique in that conceptually they get very complicated very quickly I feel like most topics are only truly 
[00:35](https://www.youtube.com/watch?v=9dr-tRQzij4&t=35) complex in one or two aspects and a lot of worries can be easily discarded or simplified for instance the smoke rendering for my Counter-Strike video requires an understanding of complex 
[00:46](https://www.youtube.com/watch?v=9dr-tRQzij4&t=46) light physics but since it's all done as a post-processing effect I don't have to worry about triangle count or other mesh optimization issues because the smoke has no mesh in my video about rendering 
[00:56](https://www.youtube.com/watch?v=9dr-tRQzij4&t=56) millions of grass blades I had to understand complex GPU coing algorithms in order to reduce the triangle count and geometric burden on the GPU as much as possible but I didn't need to do much 
[01:07](https://www.youtube.com/watch?v=9dr-tRQzij4&t=67) more to make it look like grass so I didn't have to worry about complex lighting or physics this is what makes hair so problematic it's geometrically complex which is the first thing you 
[01:18](https://www.youtube.com/watch?v=9dr-tRQzij4&t=78) would notice about it probably how could you even begin to efficiently render a full head of human hair the average person has 80 to 120,000 strands of hair on their head so how would you model 
[01:29](https://www.youtube.com/watch?v=9dr-tRQzij4&t=89) that each strand has to be composed of multiple segments because otherwise it geometrically can't curve so you're looking at a few hundred, triangles dedicated to just the hair of one person 
[01:40](https://www.youtube.com/watch?v=9dr-tRQzij4&t=100) this would maybe be okay for a game with a protagonist that has a beautiful head of hair but gets eite into a universe where everyone is bald and is trying to kill them for having hair and it plays 
[01:51](https://www.youtube.com/watch?v=9dr-tRQzij4&t=111) like vampire survivors unfortunately your game probably has many people with hair that can be on screen at the same time and the cost of that High Fidelity Hair hair is going to get very expensive 
[02:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=122) very quickly we are also ignoring the hairy needs of nonhumans for instance a cat has around a 130,000 strands of hair per square in of their body which means they require the expense of one full 
[02:13](https://www.youtube.com/watch?v=9dr-tRQzij4&t=133) human head of hair per square inch but let's imagine the scenario where you are able to afford this insane geometric overhead of realistic hair after all we could render millions of grass blades so 
[02:24](https://www.youtube.com/watch?v=9dr-tRQzij4&t=144) we could reasonably afford fancy hair if we really wanted it unfortunately the trials and tribulation do not stop at the geometric level like with the grass in fact we are met with a much more 
[02:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=154) terrifying opponent hair lighting models hair is transparent which immediately raises tons of red flags because now you have to do subsurface scattering since rays will transmit light through the 
[02:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=165) hair Illuminating the volume underneath this means we have to do similar algorithms as the ones demonstrated in the Smoke video which is really bad because hair is composed of hundreds of 
[02:55](https://www.youtube.com/watch?v=9dr-tRQzij4&t=175) thousands of strands so in order to get accurate simulated interactions we you would have to do at least tens of thousands of transmissive operations to get a convincing output for just one 
[03:05](https://www.youtube.com/watch?v=9dr-tRQzij4&t=185) pixel This is complicated even further by the nature of hair itself smoke is easy because the transmission of light is consistent but hair is not consistent it changes Behavior depending on how old 
[03:16](https://www.youtube.com/watch?v=9dr-tRQzij4&t=196) or young it is meaning that it is spatially different as you go along the strand of hair This is complicated further by Common outside influences on hair that radically change appearance 
[03:25](https://www.youtube.com/watch?v=9dr-tRQzij4&t=205) such as moisture shampoos grease or bleach this is then complic ated even further when you consider everyone's hair is radically different and the way it interacts with those outside 
[03:35](https://www.youtube.com/watch?v=9dr-tRQzij4&t=215) influences is different too so we're already looking at a lighting model that needs an insane amount of parameters to encapsulate the full extent of possible human hair types and the way those hair 
[03:44](https://www.youtube.com/watch?v=9dr-tRQzij4&t=224) types interact with common natural phenomena this is made even worse because we as humans are much more familiar with hair and what it looks like so we are able to spot a 
[03:53](https://www.youtube.com/watch?v=9dr-tRQzij4&t=233) regularities much easier and identify when the hair just doesn't look right after all hair is a major contri contributing factor to The Uncanny Valley and a sort of perceptual 
[04:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=242) bottleneck when it comes to making games look more realistic aside from the lighting problems there are also inherent Hardware problems with rendering hair because hair is often 
[04:11](https://www.youtube.com/watch?v=9dr-tRQzij4&t=251) thinner than a pixel on your monitor how can you render something that is smaller than a pixel but don't worry let's imagine a scenario where gpus can handle infinite triangles and Ray tracing 
[04:22](https://www.youtube.com/watch?v=9dr-tRQzij4&t=262) Hardware has advanced 1,000 years to be able to handle hair light interactions in real time and monitors they now have infinite resolution somehow and games can also somehow render infinite 
[04:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=274) resolution in real time unfortunately we still have one more major problem hair has to move otherwise it's not very useful since hair moves that means hundreds of thousands of objects now 
[04:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=285) need to interact with each other at real-time rates and this is not simple interaction it's actually insanely complicated physics because the way hair moves is also dependent on the hair type 
[04:55](https://www.youtube.com/watch?v=9dr-tRQzij4&t=295) and other contributing forces such as static electricity random clumping of hair grease and other General volumetric physical phenomena this all comes together to inform us that realtime High 
[05:05](https://www.youtube.com/watch?v=9dr-tRQzij4&t=305) Fidelity Hair implies a great geometry burden light interactions that are as complicated as it gets and physics Tech you will only ever see in science fiction and remember that this is all 
[05:15](https://www.youtube.com/watch?v=9dr-tRQzij4&t=315) for just one instance of hair in the scene we would need to do this for every character with hair that is visible also don't forget that for a cat it is 200x the cost of whatever it is for a human 
[05:25](https://www.youtube.com/watch?v=9dr-tRQzij4&t=325) each one of these categories is complex enough to have its own hour-long video but today we'll be looking at a tried andrue solution to the geometry dilemma a method games have been using for 
[05:35](https://www.youtube.com/watch?v=9dr-tRQzij4&t=335) decades to fake fur grass and other similar materials it's way simpler than you think and it's still being used in games today but first something entirely different this video has been sponsored 
[05:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=345) by surf shark surf shark is a popular VPN service dedicated to keeping your internet browsing activities private and your data secure a VPN works by acting as a middleman between you and your 
[05:56](https://www.youtube.com/watch?v=9dr-tRQzij4&t=356) desired destination keeping you private from the death destination as they believe they are talking to the VPN this provides a number of benefits such as preventing your ISP from throttling your 
[06:06](https://www.youtube.com/watch?v=9dr-tRQzij4&t=366) internet connection as well as obscuring your personal data such as where you're browsing from in fact you can make use of Sur sharks servers around the world to pretend like you're using the 
[06:15](https://www.youtube.com/watch?v=9dr-tRQzij4&t=375) internet from another country this allows you to get around Geor restrictions enabling you to watch movies and shows that are available in other countries but not your own surf 
[06:24](https://www.youtube.com/watch?v=9dr-tRQzij4&t=384) shark does everything you've heard about vpns before and more offering services for data breach alerts antivirus and a search engine that keeps you private but the best part about surf shark is their 
[06:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=394) 30-day money back guarantee try out surf shark today risk-free and get three extra months on your subscription when you use promo code Ace Rolla or click the link in the description thank you so 
[06:44](https://www.youtube.com/watch?v=9dr-tRQzij4&t=404) much to Surf shark for sponsoring this video now let's learn about shell texturing question for a flat field of grass would you rather render 20 million triangles or 32 triangles surely we 
[06:56](https://www.youtube.com/watch?v=9dr-tRQzij4&t=416) can't visualize millions of grass blades with only a few squares or can we we start by rendering a single [Music] quad if we want to represent a dense 
[07:10](https://www.youtube.com/watch?v=9dr-tRQzij4&t=430) grass field on this flat plane then we should think of it like the ground that Grass Grows out of to visualize this as texture data let's imagine that a green pixel means grass is growing out of that 
[07:20](https://www.youtube.com/watch?v=9dr-tRQzij4&t=440) spot and a black pixel means no grass is present grass probably doesn't have much of a visible pattern to how it grows so we can model it easily with white noise which is just random numbers while the 
[07:32](https://www.youtube.com/watch?v=9dr-tRQzij4&t=452) CPU can make use of complex State machines to produce uniformly distributed random numbers we don't have that sort of privilege on the GPU instead we make use of hashing functions 
[07:42](https://www.youtube.com/watch?v=9dr-tRQzij4&t=462) to take a seed number and Shuffle it around so much that it results in a number that feels random ideally seeds that are close in value will have wildly different outputs and overall the 
[07:52](https://www.youtube.com/watch?v=9dr-tRQzij4&t=472) outputs should be as uniform as possible because otherwise it won't feel very random if there's a general Trend to the RNG hashing functions range from simple to complex you can find a bunch of them 
[08:03](https://www.youtube.com/watch?v=9dr-tRQzij4&t=483) on Shader toy so whichever one looks good to you will probably work just fine for General random number needs with a hashing function in hand we compute a seed from the UV coordinates remember 
[08:13](https://www.youtube.com/watch?v=9dr-tRQzij4&t=493) that for a square the UV coordinates range from 0 to 1 from the top left to the bottom right pushing the seed through the hashing function gives us a random number between 0 and 1 and if the 
[08:23](https://www.youtube.com/watch?v=9dr-tRQzij4&t=503) value is greater than zero let's interpret that as the presence of a blade of grass back in unity we see that our plane is entirely green at first you might think every number was greater 
[08:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=514) than zero but no our plane is technically composed of one really big blade of grass because the square only has one seed value possible from the UVS in order to get more Blades of grass we 
[08:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=525) multiply the UVS by a density value which will be the width and height of the field for example a density of 100 means 100x 100 Blades of grass with a higher density we see a few black pixels 
[08:56](https://www.youtube.com/watch?v=9dr-tRQzij4&t=536) but obviously the majority of values are greater than zero so we end up with a mostly green square but this makes sense because this Square represents the ground and where all the grass is 
[09:06](https://www.youtube.com/watch?v=9dr-tRQzij4&t=546) growing out of so we draw another square but this one is going to be a little bit above the ground since the UV coordinates of this Square are the same as the initial Square the random numbers 
[09:16](https://www.youtube.com/watch?v=9dr-tRQzij4&t=556) are going to be exactly the same but now when we do our grass presence check we compare the random number to our new Square's height instead of zero since this square is a bit taller more pixels 
[09:26](https://www.youtube.com/watch?v=9dr-tRQzij4&t=566) are black indicating that the grass in that spot was not tall enough but the majority of the square is still green so we should draw a third square and repeat this process again with the new height 
[09:37](https://www.youtube.com/watch?v=9dr-tRQzij4&t=577) and then we should repeat the process again until we have some arbitrary number of squares like 16 for example at this point there are barely any green pixels on the top layer indicating that 
[09:47](https://www.youtube.com/watch?v=9dr-tRQzij4&t=587) most of the grass isn't freakishly tall but now the most pressing matter is that these empty pixels are blocking our view we can't see our Grass at all it turns out we can get rid of pixels we don't 
[09:58](https://www.youtube.com/watch?v=9dr-tRQzij4&t=598) want by just telling all the pixel Shader to discard its work when certain conditions are met for example if there's no grass then discard the work this gets rid of those pixels but now we 
[10:07](https://www.youtube.com/watch?v=9dr-tRQzij4&t=607) see that it's a formless green blob to get some easy lighting we can multiply the color of the grass by the height of the square which gives the impression that less light is reaching the depths 
[10:16](https://www.youtube.com/watch?v=9dr-tRQzij4&t=616) of the grass with our low IQ lighting we finally see the fruits of our labor 16 squares that stack on top of each other to create the illusion of a cohesive volume of Blades of grass since it's 
[10:26](https://www.youtube.com/watch?v=9dr-tRQzij4&t=626) entirely driven by texture data we can make the f as large as we want and have no performance concerns since it's not real geometry like with my higher Fidelity grass but we still get the same 
[10:36](https://www.youtube.com/watch?v=9dr-tRQzij4&t=636) result of a visually dense field for a fraction of the cost this technique of visualizing complex volumes with simpler geometric slices is called shell texturing and has been used in games for 
[10:47](https://www.youtube.com/watch?v=9dr-tRQzij4&t=647) many years the most iconic example is perhaps Viva Pata which used shell texturing for their entire style okay I promis this was not all aoy to get you to watch a fifth video about grass but 
[10:58](https://www.youtube.com/watch?v=9dr-tRQzij4&t=658) grass in her are pretty similar if you think about it so let's convert our grass field into something that looks a bit more like hair now when I say hair I specifically mean fur because in the 
[11:08](https://www.youtube.com/watch?v=9dr-tRQzij4&t=668) current day we can actually more than afford decent geometry for good-looking hair on people but for Animals it's a different story when it comes to Shell texturing fur is probably the number one 
[11:18](https://www.youtube.com/watch?v=9dr-tRQzij4&t=678) use case and you've definitely seen it many times over in lots of games the most popular example probably being C from Dark Souls we can translate our shell textured grass from a plane to any 
[11:29](https://www.youtube.com/watch?v=9dr-tRQzij4&t=689) arbitrary mesh by extruding the shell out from the normal of the base vertex essentially for something like a sphere we just draw a bunch of spheres on top of each other and then in the vertex 
[11:38](https://www.youtube.com/watch?v=9dr-tRQzij4&t=698) Shader extrude the shells outwards from the normals based on our desired distance this is all it takes to finish the effect we now effectively have a green furry ball that we can change to 
[11:48](https://www.youtube.com/watch?v=9dr-tRQzij4&t=708) another color to look more like hair the sheer density of the strands and visual noise gives an illusion of complexity when in reality the mesh is simple obviously hair isn't very square like 
[11:59](https://www.youtube.com/watch?v=9dr-tRQzij4&t=719) this so let's try and make it look more like thin strands it's easier to visualize differences on the flat plane so let's go back to grass for a moment the first thing we'd like to do is have 
[12:08](https://www.youtube.com/watch?v=9dr-tRQzij4&t=728) longer blades this is as easy as increasing the distance that the shells span across but it immediately reveals a critical flaw of shell texturing if we increase this distance too much then it 
[12:18](https://www.youtube.com/watch?v=9dr-tRQzij4&t=738) becomes very obvious that it's just a bunch of quads and not actual Blades of grass we have a few options here we could simply not increase the distance and live with the length we've got which 
[12:28](https://www.youtube.com/watch?v=9dr-tRQzij4&t=748) is what a Pata does we could increase the distance and call it the style of our game and pretend it's intentional which is what Dark Souls does or we could just add more shelves to fill in 
[12:38](https://www.youtube.com/watch?v=9dr-tRQzij4&t=758) the new gaps it's 2023 and not 2006 so we can afford a few more shelves than just 16 with 32 shells we can get longer Blades of grass for essentially the same price and we can take it to the extreme 
[12:50](https://www.youtube.com/watch?v=9dr-tRQzij4&t=770) with something like 256 shells which makes it look entirely solid at this number of shells we do have several performance concerns but we'll talk about that later the important part is 
[13:01](https://www.youtube.com/watch?v=9dr-tRQzij4&t=781) that we can have much longer Blades of grass now without any obvious discontinuities but it still looks like something out of cube world to get something more strand-like we take the 
[13:10](https://www.youtube.com/watch?v=9dr-tRQzij4&t=790) fractional part of our multiplied UV coordinates to operate in the local space that our grass blade occupies the origin of this space is in the bottom right which is kind of awkward so we 
[13:19](https://www.youtube.com/watch?v=9dr-tRQzij4&t=799) translate it to the center and we can now identify how far away a pixel of the grass blade is horizontally from its local Center by calculating the magnitude of the trans ated local 
[13:29](https://www.youtube.com/watch?v=9dr-tRQzij4&t=809) position now all we have to do is check if this distance is greater than our desired thickness and if it is we discard the pixel giving a cylindrical grass instead of cuboid grass ideally we 
[13:40](https://www.youtube.com/watch?v=9dr-tRQzij4&t=820) want the thickness to taper off as height increases so we can combine our discard checks into one by multiplying our thickness with the grass height minus the Shell's height different 
[13:49](https://www.youtube.com/watch?v=9dr-tRQzij4&t=829) thicknesses have very different appearances but now when we swap back to the sphere the tapered strands of hair look much more convincing than the rectangular hair from earlier we can 
[13:57](https://www.youtube.com/watch?v=9dr-tRQzij4&t=837) finish up the lighting by applying some shading to the whole body with the classic lambers and diffuse as described in my video on water this is a pretty harsh lighting model without any ambient 
[14:07](https://www.youtube.com/watch?v=9dr-tRQzij4&t=847) light so I tried out valves half Lambert which is a non-physically based model that makes use of the full range of the dot product for shading instead of the clamped dot product which we multiply 
[14:17](https://www.youtube.com/watch?v=9dr-tRQzij4&t=857) by5 and add .5 to translate the range from negative - 1 to1 to 0 to 1 the half Lambert breaks the laws of physics because it doesn't follow Lambert's cosign law but in my opinion it looks 
[14:27](https://www.youtube.com/watch?v=9dr-tRQzij4&t=867) more pleasant here and if we aren't going to have some crazy realistic looking hair we should do what looks good instead of what is technically correct I also like to clamp the dot 
[14:35](https://www.youtube.com/watch?v=9dr-tRQzij4&t=875) product in the half Lambert resulting in formless midtone Shadows especially when we remove the fake ambient occlusion on our shells to make the sphere look like a sort of stylized Dand Lion at this 
[14:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=885) point we have really basic solutions to the geometry problem and the lighting problem of hair but remember that hair also moves around so let's look at a really basic solution to the physics 
[14:55](https://www.youtube.com/watch?v=9dr-tRQzij4&t=895) problem let me preface this by telling you UPF front I'm not a physics expert nor have I done much physics programming so this information I'm about to give you is complete that I put 
[15:05](https://www.youtube.com/watch?v=9dr-tRQzij4&t=905) together without doing much reading on the subject mainly because there isn't much reading on the subject available we want to do our physics after we have extruded our shells in the vertex Shader 
[15:13](https://www.youtube.com/watch?v=9dr-tRQzij4&t=913) currently our hair sticks straight out and doesn't droop at all in reality gravity should be pulling these long strands downward a more sophisticated simulation might treat the shells as 
[15:23](https://www.youtube.com/watch?v=9dr-tRQzij4&t=923) discret segments of Springs and apply related physics while keeping track of velocity and acceleration but we're not very smart around here so let's just Define a default directional Vector that 
[15:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=934) the hair will Point towards while at rest to represent the pole of gravity this default Vector will Point downwards all we need to do now is add this directional Vector to our vertex 
[15:43](https://www.youtube.com/watch?v=9dr-tRQzij4&t=943) position multiplied by the strength of the displacement while this is working just fine it's not what we want we want the displacement to only affect the tips of the hair which we can do by 
[15:52](https://www.youtube.com/watch?v=9dr-tRQzij4&t=952) multiplying the displacement by the normalized height of our shells when the height is zero at the base of the hair the displacement is canceled out but towards the tip of the hair the height 
[16:00](https://www.youtube.com/watch?v=9dr-tRQzij4&t=960) is one and we get a full displacement our hair now droops instead of fully displaces which is great unfortunately if we move the ball around it doesn't respond to the movement ideally when we 
[16:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=972) move left the hair follows behind pointing to the right and the opposite for the other directions only the CPU knows what buttons we are pressing which means we need to have the CPU update our 
[16:21](https://www.youtube.com/watch?v=9dr-tRQzij4&t=981) displacement Vector each frame but a roller didn't you say that we should avoid moving data between the CPU and GPU at all costs I certainly have said that a lot and it's still true but in 
[16:33](https://www.youtube.com/watch?v=9dr-tRQzij4&t=993) reality some amount of data is moved from the CPU to the GPU every frame to update variables that must be updated such as the current frame time the camera data and any other variables that 
[16:44](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1004) change from frame to frame what we want to avoid is mass data transfer and that includes updating Shader variables we only want to update what we absolutely have to but updating a single 
[16:54](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1014) directional Vector is not going to break the bank on the CPU whichever dire we are moving we set our hair displacement Vector to the opposite direction and now our hair responds to our movement 
[17:04](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1024) obviously this looks ridiculous we want the hair to transition between these directions instead of instantly snapping to fix this we want our directional Vector to be defined in the larger scope 
[17:14](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1034) so that it maintains State over time then we subtract the direction we are moving from our Vector each frame and normalize it before passing it into the Shader this way the direction the hair 
[17:25](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1045) points changes over time instead of instantly because it takes time for our subtractions to result in the complete opposite direction this finishes our hair physics although you'd be hard 
[17:35](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1055) pressed to call this physics it's more like rudimentary State blending but it kind of gets the job done with minimal resources also this finishes our hair in general with shell texturing as a 
[17:46](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1066) solution to the geometry problem very simple non-photorealistic lighting as a solution to the lighting problem and the worst physics you have ever seen as a solution to the physics problem we have 
[17:55](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1075) created what's actually an incredibly versatile piece piece of tech that games are still using today just telling you it's versatile is pretty boring though so let's take a closer look at some 
[18:05](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1085) examples since shell texturing creates the illusion of dense geometry from simple geometry it's ideal for materials like hair fur grass rugs Moss hay or maybe even something low scope like the 
[18:17](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1097) bristles on a toothbrush I mentioned earlier that Viva Pata uses this technique for the fur on their animals which gives the iconic pinata look since the strands are rectangular and look 
[18:27](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1107) like paper strips they also use shell texturing for the Short Grass which honestly looks more like a rug than grass but the intent is clear Viva Pinata is from 2006 though so let's look 
[18:38](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1118) at a more modern example with genin impact regardless of your opinion on the game you have to admit genin impact is filled with beautiful environment art and also serves as a great reference for 
[18:48](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1128) how simple tried andrue techniques still have their place in the modern era like Parallax mapping billboarding and even shell texturing genin impact makes use of shell texture string for moss on 
[18:59](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1139) trees and rocks as well as the straw that makes up the roofs of some houses and whatever this is supposed to be there's probably more examples in the game but it shows that this technique 
[19:09](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1149) works for more than just hair and fur the last big example is CF from Dark Souls unfortunately CF is where this technique begins to fall apart while shell texturing is an amazing solution 
[19:20](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1160) when it works it turns out there's a lot of scenarios where it doesn't work so let's take a closer look at some of the big drawbacks of this Tech shell texturing is an illusion an attempt at 
[19:30](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1170) tricking you into seeing more than there is because shell texturing involves what's basically a layer cake of meshes if at any point we are allowed to look parallel to the layers then the illusion 
[19:40](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1180) is instantly broken and the effect falls apart this is why Si looks so weird these strange artifacts on the body are the gaps in the shells we can see a similar effect on our own shell textured 
[19:51](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1191) sphere and when we look at the grass from the ground's perspective then we can easily see through the entire grass field this is also why I know for certain that gench and impact is using 
[20:00](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1200) shell texturing because we can see through the gaps in the Moss when we Jank the camera enough so how do we fix this critical visual bug we don't take it from genin Impact and Dark Souls 
[20:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1212) these aren't amateur Productions if they didn't fix it you don't have to either the unfortunate reality is that there isn't really a good way to fix it otherwise they would one tried and- true 
[20:22](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1222) fix is known as fin meshes which are artist authored additions to models that extrude from the mesh in order to C the camera when shells are viewed at parallel angles but this wouldn't 
[20:32](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1232) actually fix C because the issue there is that the distance between the shells is too large fin meshes also wouldn't work for gench and impacts Moss because where do you put the fin there's no way 
[20:42](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1242) to cover all the discrepancies and at a point you'll have so many thin meshes that you ended up with a high fidelity Moss mesh which is what we were trying to avoid in the first place the problem 
[20:51](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1251) then isn't shell texturing but the camera if the camera is locked in some regard such as not being a able to rotate then the player will never be able to break the illusion this sounds 
[21:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1262) like a joke but it's really not plenty of games have fixed camera angles or limit the camera in some way in fact this is how Viva Pinata gets away with it as their camera does not go low 
[21:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1272) enough to allow the player to break the visuals Viva Pinata makes use of the other best solution which is to keep it as simple as possible this grass here is so short that there isn't any room to 
[21:23](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1283) see between the layers at all you can see here how much of a difference the distance between shells makes when it comes to grazing angles lastly Viva Pata and genin impact make use of the last 
[21:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1294) example solution which is avoiding realistic lighting our shell textured ball looks way cooler and way more fluffy and stylized when we erase the occlusion between strands this also 
[21:44](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1304) allows us to lower the shell count because now there won't be any cascading gradients creating obvious discontinuities in the mesh this is how gench gets away with such few shell 
[21:53](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1313) counts on their Moss you can only see the gaps when you really try hard to see them because other otherwise it's a formless fluffy blob from any other point of view if you try to have 
[22:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1322) realistic lighting without also tanking the cost of more shells you'll get C from Dark Souls where the lighting betrays itself and only serves to accentuate the broken illusion speaking 
[22:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1332) of more shells our technique has one more villain that few people ever actually talk about one important topic we've glossed over this whole time is how our Shader is even discarding pixels 
[22:23](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1343) if each shell is its own object and can discard its own work then how does the GP you know which pixel to draw normally when we tell the GPU to draw an object its vertex Shader is executed to 
[22:34](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1354) finalize its position and then the object is rostered to the screen and then its fragment Shader is executed for every pixel that was rostered and then its distance from the camera is stored 
[22:45](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1365) in the zbuffer when we next tell the GPU to draw an object its vertex Shader is executed and it is rostered to the screen but now before we execute the fragment Shader we test the distance 
[22:55](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1375) from the camera with what is currently in the Z buffer and if the object is behind what has already been drawn then we can discard the pixel and not waste any more work but if the object is in 
[23:05](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1385) front of what has already been drawn then we execute the fragment Shader and overwrite the pixel that has already been filled in this is called overdraw and it's clearly not good because we 
[23:15](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1395) have effectively wasted computational power on what was already drawn there it would have been better to draw this object first and then the original object so we could have skipped that 
[23:24](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1404) work um Mr R I don't really see what the big deal is with overriding a few pixels monitors are composed of millions of pixels so it would probably be bad to do something a million times only to throw 
[23:37](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1417) that all away to do it again another million times especially if that work involves really complex lighting calculations Unity is smart most of the time and knows this is bad and tries his 
[23:48](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1428) best to draw objects front to back to reduce overdraw as much as possible sometimes it breaks and ruins your day as demonstrated by The Game Dev Guru in his performance analysis of the forest 
[23:59](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1439) demonstrating the dangers of overdraw so what does this have to do with our shell texturing unfortunately our clipping means our shell texturing causes immense amount of overdraw the outer shell is 
[24:09](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1449) drawn first and its pixels are clipped which will be most of the pixels since it's the top layer since nothing got written to the zbuffer then the next Shell's fragment Shader will be executed 
[24:18](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1458) and so on and so forth until a pixel is filled in or every shell has been drawn this means a pixel could be checked once or twice but the worst case is every shell clips that pixel and executing 256 
[24:30](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1470) fragment shaders for one pixel is pretty bad for my ball of 256 shells you can see that when it's far from the camera the performance impact of overdraw is insignificant since such few pixels are 
[24:41](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1481) rostered and being overwritten but when the ball covers the camera our frame time increases a considerable amount since most pixels are being rendered to potentially hundreds of times this is 
[24:52](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1492) why it's absolutely critical to make the most out of as few shells as possible such as this fluffy fur break down that makes use of High Fidelity textures to make just four shells look really good 
[25:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1502) but honestly if you're not going too crazy on anything else you might be able to get away with decent shell counts on a lot of objects in the scene if you're looking to innovate on something like 
[25:11](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1511) Viva pinata's style since memory bandwith on gpus has increased immensely since then now I know what you're saying gee this has been a lot of words describing something that breaks the 
[25:21](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1521) moment you look at it slightly wrong and also makes it worse for everyone when you try to fix its issues why are you waiting wasting my time with this shell texturing is an archaic Graphics 
[25:31](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1531) technique that mimics complex geometry using simple shells bypassing the cost of rendering extremely high triangle counts it is ideal for imitating materials like fur carpet grass moss and 
[25:42](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1542) other shrubs the list goes on you've seen this in games like Dark Souls genin impact Viva Pata and tons of others additionally it has extremely high mileage for its performance cost 
[25:53](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1553) relative to Artistic potential shell texturing is not perfect though and suffers from from major aliasing artifacts when you look at it the wrong way because in reality it's just an 
[26:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1562) illusion the technique also scales poorly because of overdraw so you can't use too many shells since you can't use too many shells you're limited to simpler lighting to avoid making the 
[26:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1572) artifacts worse if you play a shell texturing strengths then you will reap the rewards and if you're an indie developer looking to improve your stylized Graphics then it is absolutely 
[26:21](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1581) something you should look into none of this matters compared to the most important Boon of shell texturing though it's simp Simplicity shell texturing is very few lines of code it makes for an 
[26:31](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1591) excellent beginner graphics project but the true educational value of shell texturing is where it can go it is like the first upgrade in the tech tree that leads to tons of other discoveries like 
[26:41](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1601) maybe trying to programmatically generate bin meshes or improving the lighting model or making the physics not terrible or fixing the aliasing problem with some anti-aliasing or maybe you can 
[26:51](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1611) use shell texturing to visualize generic volumetric functions or even something as simple as making it work with textured data instead of white noise the extensions are endless and it's a 
[27:01](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1621) genuine stepping stone that has real world industry applications unlike many other beginner projects my old Graphics coworker Rory's main portfolio project that got him the job involved shell 
[27:12](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1632) texturing because of all this I'm excited to announce the ace Rolla furry challenge I want you to learn and Implement shell texturing then I want you to improve it in some regard you can 
[27:23](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1643) do this in whatever environment you want but for Unity I have fully annotated my shell texturing repo that explains every single line of code to make this hurdle as easy as possible when it comes to 
[27:33](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1653) referencing it and implementing the effect yourself you can also join my Discord server for some discussion channels and some beginner resources if you're new to shaders post your 
[27:42](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1662) Creations on Twitter with the # a Rola furry Challenge and tell us a bit about what you learned and what you improved your deadline is Sunday November 19th and we'll go over submissions in next 
[27:52](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1672) month's video as an added incentive if there are at least 100 submissions I will eat these really hot peppers on stream when the next video releases also given my content style you may think I 
[28:02](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1682) might prefer a post submission but no I value sincere expression of self more than anything and would prefer you take the subject matter very seriously first before trying to be funny as a 
[28:13](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1693) last reminder this code is freely available and fully annotated in the description below but if you just want to play with a furry ball then a build is up over on my patreon where you can 
[28:22](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1702) also vote on the next next video topic since I am choosing the topic for next month for the 100K subscriber special as usual a huge thank you to all of my current patrons without your support I 
[28:33](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1713) wouldn't be able to enlist viewers to do Mass amounts of Free Labor also I'm live right now over on Twitch if you have any questions about the video or the challenge come ask away anyways that's 
[28:43](https://www.youtube.com/watch?v=9dr-tRQzij4&t=1723) all from me I hope you have a great rest of your day and I'll see you next time don't forget to check out surf shark and get 3 months free with your subscription 