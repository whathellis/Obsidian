---
URL: https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26
thumbnail: https://i.ytimg.com/vi/Yx2JNbv8Kpg/default.jpg
channel: "[[FlippedNormals Marketplace]]"
published: 2020-10-30T22:44:39
duration: 517
tags:
  - video/3D/texture/UV
done: false
cover: "[[Pasted image 20240712202358.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "8m 37s"]

`````col
````col-md
flexGrow=1
===
![[Pasted image 20240712202358.jpg]]
````
````col-md
flexGrow=1
===
<iframe src="https://www.youtube.com/embed/Yx2JNbv8Kpg?list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````

(Description:: Enjoy this free chapter from our FlippedNormals Exclusive - UV Mapping for Games) https://flippednormals.com/downloads/uv-mapping-for-games/

Early Bird Special - Get the full course at 25% OFF until November 6th

▶ SUBSCRIBE | http://www.youtube.com/channel/UCvd6HxqYVWvfvfaF2Ereb9Q?sub_confirmation=1

▶ MARKETPLACE | https://flippednormals.com/

▷Instagram | https://www.instagram.com/flippednormals
▷Twitter | https://twitter.com/flippednormals
▷Facebook | https://www.facebook.com/flippednormals

# Transcript
[00:04](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=4) video games are complex understatement of the century right perhaps one of the most complex topics that is a universal bottleneck 
[00:13](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=13) for beginners and experts alike is the concept of uvs now i'm not talking about solar uvs although game developers could stand to 
[00:22](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=22) get a few more of those i'm of course referring to uv mapping a technique used within the digital space to project 2d images onto 3d models 
[00:34](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=34) that may not mean much to you as of right now so before i get into explaining what uv maps are let's first look at why they exist to help us form an understanding 
[00:45](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=45) you are likely aware that to hold and represent visual data within games we use images depending on the type of game we are making we often call these images 
[00:56](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=56) something different such as sprites for 2d games and textures for 3d games at the end of the day they are all simply image containers 
[01:06](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=66) which hold pixel color data that we use to display artwork let's start with how we use and display these images within a completely 2d game 
[01:17](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=77) in a two-dimensional space the only dimensions we are concerned with are the width and the height our x and y dimensions or directions respectively well we know that digital images are 
[01:30](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=90) two-dimensional right so since our image is already in the same dimensional space there is very little we need to do in order to actually prepare it 
[01:41](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=101) simply importing the images and setting them up as sprites within your chosen application is most often as much as it takes so if we extrapolate that knowledge a 
[01:51](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=111) little bit for 3d games it would make sense to utilize images in the same dimensional space right except what exactly is a 3d image 
[02:02](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=122) here lies the real reason why uv mapping is used and for many working in 3d is a necessary evil 3d images do not exist at least not yet 
[02:12](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=132) nor in the capacity that could be usable for games and due to the nature of using 2d images to store our textured data we are inadvertently limited by the 
[02:22](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=142) dimensions of said resources to circumvent this limitation the process of uv mapping was developed to be what i will call a translator between our 2d textures 
[02:34](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=154) and our 3d models in most instances creating a 3d model requires the development of polygonal faces to represent the surface of the asset we are making 
[02:46](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=166) in a modeling application these polygons would exist in what is referred to as the geometric space which i'll just call 3d space in order 
[02:56](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=176) to use textures on 3d models we need to bring one dimension into the other because it is much easier to lose a dimension than add one 
[03:05](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=185) we opt for bringing our 3d model into a 2d environment this environment is called the texture space separate from the 3d space and it is where we will be able to 
[03:16](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=196) visualize both our 2d and 3d assets together this environment allows us to bring in our textures and position the polygons of our models 
[03:27](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=207) to capture the image data essentially we're mapping coordinates between 2d pixels and 3d space all done via our texture space translator 
[03:38](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=218) now i know you're probably thinking wow that's pretty complex and you're right it is complex however in your day-to-day life you simply won't be interacting with uv mapping in this 
[03:48](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=228) way all major modeling applications already have their own implementations on how to tackle this obstacle in more elegant ways 
[03:55](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=235) by interfacing it as a uv editor fundamentally it is all using this underlying theory of translating between texture space and 3d space like i've mentioned in a 
[04:07](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=247) two-dimensional plane we refer to these dimensions as x and y however when we operate in 3d we also use x and y with the addition of our third dimension 
[04:18](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=258) z now normally this is fine as the 2d x and y dimensions can be easily translated to 3d coordinates but the x and y dimensions of the texture space 
[04:30](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=270) are not directly corresponding to coordinates in 3d space but rather represent coordinates on the polygonal faces of our models so in order to avoid 
[04:41](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=281) further confusion by using x and y naming conventions in our texture space it was decided that we would instead refer to the horizontal 
[04:50](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=290) and vertical dimensions as u and v respectively that's where the term uv map actually comes from now this has been why uv mapping exists but how does it actually work we'll be 
[05:05](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=305) looking at this question in much more depth over the rest of the series but essentially the process of uv mapping is what allows artists to unwrap their models and provide them textures 
[05:18](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=318) again that may not be an immediately satisfying answer so let's unpack what unwrapping a model means let's first look at origami the art of 
[05:27](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=327) paper folding it may not look like it but origami and uv mapping are actually incredibly similar albeit in the reverse order 
[05:37](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=337) for sake of argument origami starts in a two-dimensional space as a flat piece of paper the process that then proceeds to unfold or rather fold is the transformation 
[05:49](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=349) from a 2d item the one that exists within the 3d space now obviously the paper exists within the 3d space the entire time however the concept remains the same 
[06:00](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=360) with 3d models we already have our paper folded into our design but we need to find a way to take our paper and flatten it back out 
[06:08](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=368) to a two-dimensional item modeling applications provide us the ability to insert what are called seams you have probably heard this term before likely relating to seeing a texture 
[06:19](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=379) misaligned on a model where you can see the seam line what seams allow us to do is non-destructively tell our application where to make cuts along the faces on 
[06:29](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=389) our model to better unwrap it in its attempt to flatten a 3d model into a 2d space origami may be difficult to picture here 
[06:38](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=398) so we can also think of inserting seams as the seam lines of a shirt in order to flatten out a model we may need to entirely cut off various areas of our model from other 
[06:49](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=409) parts much like how the fabric for a shirt is in separate pieces before it is stitched together at the seam lines 
[06:57](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=417) now there is no right or wrong way to add seams as we will learn in the series however there are certainly better methods and rules of thumb that artists follow 
[07:07](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=427) to maximize their space since games often have a very finite amount of space available for us on rap as we unwrap more and more parts of a model 
[07:17](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=437) the more crowded our texture space will become here is where film and games begin to differ a little unwrapping for films is more oriented 
[07:26](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=446) towards making texturing far easier for the artist as there really is no limit to the amount of textures they can use since everything is not rendered in real 
[07:34](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=454) time the optimization here is that an artist that can texture quicker is an artist that can work faster because of this uv unwraps of models can look rather 
[07:45](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=465) spacious and somewhat easy to identify even at a sheer glance for games this is simply not the case as they need to be rendered at 30 to 60 
[07:54](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=474) frames per second in real time with potentially multiple players and possibly thousands of other textured assets 
[08:02](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=482) therefore there are incredibly harsher limitations as uv maps are intended to be optimized for performance instead this will be where the focus of this 
[08:12](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=492) series lies and understanding how we can unwrap uv maps with a game oriented mindset in the next video we will have our first hands-on look 
[08:22](https://www.youtube.com/watch?v=Yx2JNbv8Kpg&list=PL-EipzbshMbQkXb7hS0D6tKV5yfzH_6hS&index=26&t=502) at unwrapping a simple 3d object to see what it looks like in a real-time modeling application 