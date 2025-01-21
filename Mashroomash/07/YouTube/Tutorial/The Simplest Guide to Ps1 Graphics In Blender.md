---
URL: https://www.youtube.com/watch?v=390peMdni7s
thumbnail: https://i.ytimg.com/vi/390peMdni7s/default.jpg
channel: "[[SunnyIsOnline]]"
date: 2024-07-16T17:37:36
published: 2024-01-31T09:17:19
duration: 974
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240716173746.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "16m 14s"]
# The Simplest Guide to Ps1 Graphics In Blender
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716173746.jpg]]
````
````col-md
flexGrow=1
===
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/390peMdni7s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
(Description:: Both beginners and intermediates can struggle with finding out how to replicate the Psx and Ps1 render styles in Blender because a lot of that information is hidden away to sell addons and plugins, so I figured I'd make a video running through everything you need to know for this PSX style in Blender.)

My Socials! 😁 - https://linktr.ee/sunnyisonline

Links from the video!!!:
Gimp Download Link - https://www.gimp.org/downloads/
The Models Resource - https://www.models-resource.com/
Vertex Wobble Addon - https://lucasroedel.gumroad.com/l/psx_snapping
PSX Efx - https://blendermarket.com/products/dripspsxefx---lofi-playstation-1-effects
After Effects Dithering Tutorial - https://www.youtube.com/watch?v=w1Eu_FG_yxE&t=

00:00 - Pre-Requisites
00:38 - Modeling
03:15 - Texturing
06:36 - Vertex Colors
08:08 - Fake Lighting
09:42 - Vertex Wobble
12:31 - Important Settings
14:33 - Compositing the Finished Render
15:51 - Outro
# Transcript
[00:07](https://www.youtube.com/watch?v=390peMdni7s&t=7) like any other style the ps1's aesthetic is born of limitation the PS1 has a few quirks in the hardware that make it very unique and produce the classic look we all know and love I'm going to run you 
[00:17](https://www.youtube.com/watch?v=390peMdni7s&t=17) through everything here step by step so if you already have models or you just want a composite feel free to skip around these sections but if you're just starting off I'm going to be making this 
[00:26](https://www.youtube.com/watch?v=390peMdni7s&t=26) little crate here as well as running through a small scene I made just just to show off the different ways you can stylistically reach with this PS1 Hardware look let's 
[00:36](https://www.youtube.com/watch?v=390peMdni7s&t=36) begin low poly modeling is probably not as difficult as you think because in reality what we are doing is making these low poly models so that our textures can do all the heavy lifting 
[00:47](https://www.youtube.com/watch?v=390peMdni7s&t=47) for us because the PS1 had very very limited Hardware meaning that rendering a bunch of polygons at once was not really a possibility so you can see we have this character here this is the 
[00:58](https://www.youtube.com/watch?v=390peMdni7s&t=58) main character from the original sign Silent Hill and he's got quite a bit of detail you know he he looks pretty good especially for the time but if we come into the non-textured view yeah it's 
[01:09](https://www.youtube.com/watch?v=390peMdni7s&t=69) it's kind of a mess if you showed this to your boss as a 3D artist they would probably kill you but the texture really brings it all together and makes it look really nice so you're basically just 
[01:19](https://www.youtube.com/watch?v=390peMdni7s&t=79) going to be modeling entirely for performance so for example I have this crate you may model if you're making a game this is probably something you would create as an asset it's fairly low 
[01:30](https://www.youtube.com/watch?v=390peMdni7s&t=90) This would run really well on a game engine but if we're going for the PS1 style we want to minimize as much as we can so our crate would actually look a little more like this just a cube 
[01:43](https://www.youtube.com/watch?v=390peMdni7s&t=103) because we are going to let the texturing do all that heavy lifting for us we don't need any of this indentation because there's not going to be any actual light hitting our Cube it's it's 
[01:53](https://www.youtube.com/watch?v=390peMdni7s&t=113) just going to be the texture the other thing to focus on is how characters are approached especially deformation because in a lot of modern models they will tell you make sure you add extra 
[02:03](https://www.youtube.com/watch?v=390peMdni7s&t=123) geometry to where your arms are going to bend but in these older models we can see that here at the knee we just have one band so if we were to actually Bend this character's leg or bend it up looks 
[02:17](https://www.youtube.com/watch?v=390peMdni7s&t=137) pretty nice and then we do this and it crushes down this is not how a human being's Body Works but because of the hardware they couldn't do anything about that so even though I would love it if 
[02:28](https://www.youtube.com/watch?v=390peMdni7s&t=148) this model deformed correct irly if I'm going for the PS1 style if I move her leg up here you can see that it crushes down into a tiny little toothpick and that is completely by intention I could 
[02:40](https://www.youtube.com/watch?v=390peMdni7s&t=160) add edge Loops very very easily but because this is how the model worked we are staying completely faithful to the hardware and that's going to add authenticity to the render when it 
[02:50](https://www.youtube.com/watch?v=390peMdni7s&t=170) finally comes out I'm going to link in the description where I got this model it's a website called the models resource and they actually have models from basically any PS1 game just stored 
[03:01](https://www.youtube.com/watch?v=390peMdni7s&t=181) in here for you to download for you to look at you can look at the texture sheets you can look at the characters and you can completely see how they work and base your work off of them but since 
[03:10](https://www.youtube.com/watch?v=390peMdni7s&t=190) we have a nice model let's move on to texturing our beautiful beautiful crate so the first thing we're going to do is actually find a crate texture so if I look up crate texture obviously do not 
[03:22](https://www.youtube.com/watch?v=390peMdni7s&t=202) go on Google and steal someone else's texture if you're making a game you should make your own I'm just doing this for tutorial sake so we're going to save this crate image it looks like I've 
[03:32](https://www.youtube.com/watch?v=390peMdni7s&t=212) actually already saved this before which is pretty cool and we are going to open up so now that we have our crate on here we are going to first completely downscale this image so for these older 
[03:44](https://www.youtube.com/watch?v=390peMdni7s&t=224) textures I would recommend sticking around the texture resolution of 120 to 240 so because this is a prop I'm going to go with a really really low texture size so we're going to come to image 
[03:56](https://www.youtube.com/watch?v=390peMdni7s&t=236) come to scale image and we are going to take the size of our image all the way down to 120 pixels which is incredibly small but since this in an actual game would probably be a background asset 
[04:09](https://www.youtube.com/watch?v=390peMdni7s&t=249) nobody's really going to notice so once we get that in and we Zoom you can see that it already looks pretty PSX this is a very low res image but there's one more thing we can do to further compress 
[04:21](https://www.youtube.com/watch?v=390peMdni7s&t=261) the image that they would also do back in the day and that is coming to image going to mode coming to indexed and basically just crushing down the amount of colors in the image alog 
[04:33](https://www.youtube.com/watch?v=390peMdni7s&t=273) together cuz right now all of these Browns are fading together very nicely but that takes up a lot of storage there are a lot of different colors in this image so what this does is make sure 
[04:43](https://www.youtube.com/watch?v=390peMdni7s&t=283) that there are only a maximum of eight colors in this image for objects with a lot of colors you can bump this up to around 16 but I would stick to eight especially if it's a background asset 
[04:53](https://www.youtube.com/watch?v=390peMdni7s&t=293) and we're going to turn on dithering so this is basically a way of blending different colors together efficiently so if you have a model that has flat shading kind of like the asterid model I 
[05:04](https://www.youtube.com/watch?v=390peMdni7s&t=304) was showing you earlier I would not do dithering I would set this To None because it's going to kind of up the model and add a little bit of like weird Speckles and it doesn't look too 
[05:13](https://www.youtube.com/watch?v=390peMdni7s&t=313) great but for a model like this if we press convert you can see that the dithering adds this really nice retro style shading to it that looks just absolutely incredible I I love how this 
[05:24](https://www.youtube.com/watch?v=390peMdni7s&t=324) comes out so now we are going to export As and we're going to head back over to blender so now that we're in blender we're going to unwrap this model not before adding seams on every side 
[05:36](https://www.youtube.com/watch?v=390peMdni7s&t=336) because every side's going to be the same and then the way we're going to unwrap this is just selecting each side and pressing unwrap so that every single side is unwrapped exactly the 
[05:47](https://www.youtube.com/watch?v=390peMdni7s&t=347) same so now that we've done that we're going to come to shading add a new material I'll call it crate and we're going to add an image texture and we are going to find our 
[06:02](https://www.youtube.com/watch?v=390peMdni7s&t=362) crate so the next thing we'll do is that if you want to go for the N64 style the N64 would blend together colors kind of like this that's why a lot of people complain that the N64 looks blurry in 
[06:15](https://www.youtube.com/watch?v=390peMdni7s&t=375) some ways and that is because of this linear option basically it's just lightly blending all the colors which looks really good on highres images but on this low reses image it looks kind of 
[06:25](https://www.youtube.com/watch?v=390peMdni7s&t=385) Muddy so the PS1 would actually use closest and there we can see it's a lot crisper but you can see the pixels a lot better personally I prefer it for this kind of style and it looks very nice but 
[06:37](https://www.youtube.com/watch?v=390peMdni7s&t=397) this is not the only texturing technique that they would use back then so fun fact Crash Bandicoot was actually not made with an image texture but rather something called vertex colors which are 
[06:48](https://www.youtube.com/watch?v=390peMdni7s&t=408) kind of obsolete nowadays so doing them in blender it it feels a little hidden away but regardless they're still here so if you want to add a Vertex color you would come over here to color attributes 
[07:00](https://www.youtube.com/watch?v=390peMdni7s&t=420) and press plus and press okay and then come to the shading tab We'll add a new material which we'll call vert color and you are going to add this node color attribute and then plug that in and 
[07:15](https://www.youtube.com/watch?v=390peMdni7s&t=435) select our One Singular vertex color option here so what a Vertex color basically is is instead of storing an image it will store a color value in each vertex and then it will form a 
[07:28](https://www.youtube.com/watch?v=390peMdni7s&t=448) gradient between each of the vertices and whatever color they were respectively chosen so if we come into vertex paint up here and we select the color let's do something a crate would 
[07:40](https://www.youtube.com/watch?v=390peMdni7s&t=460) be let's do like a let's do a brown over here let's do orange there we go you can see that as I color in it's forming a very smooth gradient between the colors of each corner and this is using a lot 
[07:53](https://www.youtube.com/watch?v=390peMdni7s&t=473) less storage than an image texture would use so if you want to take that approach to modeling your character and texturing them you absolutely can you just have to take it into account when you're 
[08:03](https://www.youtube.com/watch?v=390peMdni7s&t=483) modeling them because then you might end up having weird gradients that look kind of silly but the most important thing we can do with this is we can actually fake lighting lighting is very very intense 
[08:14](https://www.youtube.com/watch?v=390peMdni7s&t=494) on the PS1 console so a lot of games opted to just not use it alog together and fake it using vertex colors and the way we can do that is come into the shading tab we're going to add a new 
[08:24](https://www.youtube.com/watch?v=390peMdni7s&t=504) color attribute to this object we're going to add our color attribute node and then we we going to mix this with our original image so we're going to set a mix node to color plug both into a and 
[08:36](https://www.youtube.com/watch?v=390peMdni7s&t=516) b and set it to multiply and then I usually set the factor to one and it's a completely Black Cube now but it will not be for long cuz we're going to come to vertex paint and let's say that for 
[08:48](https://www.youtube.com/watch?v=390peMdni7s&t=528) example our light was hitting this crate from above we're going to put this crate in a room where there are overhead lights so oops that's orange we are going to paint this white light on the 
[08:59](https://www.youtube.com/watch?v=390peMdni7s&t=539) top corners of our crate and now it looks like there's a shadow on the bottom of the crate and we're doing that with no image texturing or anything so we could even fake a shadow coming from 
[09:11](https://www.youtube.com/watch?v=390peMdni7s&t=551) the back over here by adding black here and now we could comfortably tuck this into a corner and it would kind of look like it's actually being shaded by the environment when really we're just 
[09:22](https://www.youtube.com/watch?v=390peMdni7s&t=562) assigning colors to this object personally I like doing this for rooms it kind of adds a convincing ambient occlusion when if you come in here we're going to be having ambient occlusion 
[09:31](https://www.youtube.com/watch?v=390peMdni7s&t=571) screen space Reflections motion blur and Bloom off at all times so if you want to convincingly fake this Shadow you can completely do that with vertex colors so the next thing we are going to do is 
[09:43](https://www.youtube.com/watch?v=390peMdni7s&t=583) something called vertex snapping so I'm not sure the actual term for it but basically the PS1 could not calculate the position of vertices if they weren't a whole number so there are no decimal 
[09:55](https://www.youtube.com/watch?v=390peMdni7s&t=595) places for the position of vertices like if we come into n our end menu over here and we move this verticy we can see that the Z is at 1. 12253 but on the PS1 it would be one and 
[10:08](https://www.youtube.com/watch?v=390peMdni7s&t=608) two and three so we need to simulate that within our camera view without having that Hardware present which seems like it would be really difficult but luckily there is a wonderful wonderful 
[10:21](https://www.youtube.com/watch?v=390peMdni7s&t=621) free plugin for blender that I'm going to link in the description that lets you do this for an entire scene incredibly incred L easily so I'm going to set up my camera and you should too and we are 
[10:33](https://www.youtube.com/watch?v=390peMdni7s&t=633) going to open up the menu for this add-on so basically what this add-on does is it's only like three buttons but we're going to add a grid I'd say a good size for the grid is usually around 200 
[10:45](https://www.youtube.com/watch?v=390peMdni7s&t=645) but the size of the grid can go all the way up to 46 I'm not sure why it starts breaking after that but 406 is the max so we're going to add this grid and we're going 
[10:55](https://www.youtube.com/watch?v=390peMdni7s&t=655) to position it right over our scene so in this case case it's just a cube so we're going to put it right over our Cube doesn't have to be exact and then we're going to click on our Cube and 
[11:05](https://www.youtube.com/watch?v=390peMdni7s&t=665) we're going to add modifier and our PC is going to lag a little bit so basically what's now happening to this object is that it is constantly snapping to each of the 
[11:16](https://www.youtube.com/watch?v=390peMdni7s&t=676) vertices on this camera's grid so it's shaking and wobbling around a bit and if we were to move this in our camera scene it would look like this all the time this effect is very very convincing on 
[11:27](https://www.youtube.com/watch?v=390peMdni7s&t=687) characters specifically because you can notice each of the vertices on a rounded object moving a little easier than on this Cube object but there is still one problem which is that when we move the 
[11:37](https://www.youtube.com/watch?v=390peMdni7s&t=697) camera nothing happens whereas if we were on a PS1 it would still continue vertex wobbling while the camera moves so we are going to do something very very interesting so in order to make the 
[11:49](https://www.youtube.com/watch?v=390peMdni7s&t=709) vertices wobble with the camera what we're going to do is Select our grid press contrl a and all transforms just so that the object is completely centered then we're going to come to 
[11:59](https://www.youtube.com/watch?v=390peMdni7s&t=719) object constraint add a damped track and set it to the camera and now we're going to set that to X I find that X is usually the best for this and now if we move around the camera the entire grid 
[12:12](https://www.youtube.com/watch?v=390peMdni7s&t=732) will track to the camera so if we move around we can see that the vertices still wobble even in the camera view which is just absolutely rad and if we're to move the Box around it 
[12:24](https://www.youtube.com/watch?v=390peMdni7s&t=744) continues wobbling which looks really really cool and you can do this with an entire scene just going through and adding the modifier on everything there are a few more settings we can change so 
[12:33](https://www.youtube.com/watch?v=390peMdni7s&t=753) we can come into color management and set this to standard I find that it looks a lot better for these renders and then we'll come into film and we'll set this filter size to zero and this 
[12:43](https://www.youtube.com/watch?v=390peMdni7s&t=763) basically removes a lot of blenders anti-aliasing giving us those kind of sharp Jagged edges which are a little hard to see here but oh yeah you can see it up here pixelated edges that fall off 
[12:56](https://www.youtube.com/watch?v=390peMdni7s&t=776) really hard and then if we come into our format section now we're going to set our frame rate to something just anywhere below 30 personally just for the stylized look I really like the look 
[13:07](https://www.youtube.com/watch?v=390peMdni7s&t=787) of 12 frames per second but if you want accuracy I would set it somewhere from 24 to 30 cuz that's usually what those consoles would run at so now that we've set up everything we need to for the 
[13:19](https://www.youtube.com/watch?v=390peMdni7s&t=799) actual style and I've even put together this tiny little rotating animation which I'm actually going to set to linear now we can head into the compositing Tab and do some really 
[13:30](https://www.youtube.com/watch?v=390peMdni7s&t=810) simple effects so if you want a pixelated low resolution effect just come over to the resolution Tab and i' divide everything by four so we have this completely 480p render and if we 
[13:43](https://www.youtube.com/watch?v=390peMdni7s&t=823) click render you can see it's really small and when we zoom in it's very pixelated but if you want to keep your image 1080p but still have this pixelated effect you will come into the 
[13:54](https://www.youtube.com/watch?v=390peMdni7s&t=834) compositing tab and we are going to add a scale a pixelate and another scale node and we're going to set the first scale to 0.25 on both axes and then set the 
[14:09](https://www.youtube.com/watch?v=390peMdni7s&t=849) second scale node to four and now when we render it is a full 1080p image but it's still really pixelated because of the compositing and if you were to render the entire animation the entire 
[14:22](https://www.youtube.com/watch?v=390peMdni7s&t=862) animation would be low res like that which is really really cool but at least personally I am going to use the method of dividing a resolution by four just because I really like the low reses look 
[14:32](https://www.youtube.com/watch?v=390peMdni7s&t=872) so right before we render we actually arrive at a bit of a Crossroads so the final effects we need are we are going to dither the entire scene and there are two ways to do this either you can buy 
[14:44](https://www.youtube.com/watch?v=390peMdni7s&t=884) this $18 blender plugin which includes a lot of things it includes a lot of neat features for the PSX style like texture wobble and vertex wobbling and you can even Crush down all the colors in the 
[14:57](https://www.youtube.com/watch?v=390peMdni7s&t=897) scene it is an incred incredibly impressive add-on especially for the price it is super super underrated and absolutely worth the $18 so if you're going to be doing a lot of PSX style 
[15:09](https://www.youtube.com/watch?v=390peMdni7s&t=909) renders I highly encourage you to buy this add-on cuz it is just incredible the other path is you can always just not do the dithering which is completely normal a lot of the current uh PS1 
[15:19](https://www.youtube.com/watch?v=390peMdni7s&t=919) modding climate is just trying to remove the dithering cuz people don't like it and they think it makes their image unclear so if you want to Veer away from it a little bit stylistic you can do 
[15:29](https://www.youtube.com/watch?v=390peMdni7s&t=929) without the dithering and be completely fine but if you want to do the dithering for mostly free as long as you have a copy of After Effects and if you don't have a copy you can get a copy I'm I'm 
[15:41](https://www.youtube.com/watch?v=390peMdni7s&t=941) not going to go into that that's not my job but if you have a copy of After Effects this wonderful tutorial will show you how to dither your entire scene and it looks absolutely beautiful thank 
[15:51](https://www.youtube.com/watch?v=390peMdni7s&t=951) you so much for watching and I hope to see your PSX style renders at me on Twitter once you create them cuz I would love to see them and if you want critiques I will give out critiques 
[16:01](https://www.youtube.com/watch?v=390peMdni7s&t=961) thank you all for watching and goodbye 