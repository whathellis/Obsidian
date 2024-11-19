---
URL: https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s
thumbnail: https://i.ytimg.com/vi/1ZvwhLRPM3M/default.jpg
channel: "[[Cartesian Caramel]]"
date: 2024-07-25
published: 2024-05-06T23:57:38
duration: 1413
tags:
  - video/3D/tutorial
done: false
cover: "[[Pasted image 20240715200119.jpg]]"
---
[time:: "23m 33s"]
# Blender 4.2 Portals using the Ray Portal node!
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715200119.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Blender 4.2 Portals using the Ray Portal node!" src="https://www.youtube.com/embed/1ZvwhLRPM3M?start=1&amp;feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
Description:: Testing new stuff in Blender 4.2
If you want to see more Blender related stuff:
Projects you can download: http://gumroad.com/bbbn19
Current projects of mine: https://twitter.com/Bbbn192

# Transcript
[00:00](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=0) [Music] all right we are now live hello everyone and welcome to today's very short live stream where I want to go over how I made these portals that work as you 
[00:11](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=11) would expect portal portals from the famous game so let me go over what these do specifically so we have one portal mesh right here and I can rotate and do whatever I want and then a secondary 
[00:25](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=25) portal where this empty is and then you know the orientation all that works as intended as we can see it's a little bit laggy because this is a dark scene uh I'm using Cycles in this case the ray 
[00:37](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=37) portal node only works in Cycles unfortunately maybe that'll change in the future I don't know it may be a while but how does this work well let's take a look at the Shader first to see 
[00:49](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=49) where the magic happens so let's go over all this so the main thing is we have the portal glow layer you know pretty self-explanatory and then there's the actual portal uh refraction not 
[01:03](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=63) refraction um I guess kind of refraction in a way it is moving the Rays and rotating them and all that cool stuff but those two layers equal that so let's go over the most important part which is 
[01:16](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=76) the actual oh let's show what's on the other side of the portal so with this we take the position and normal from the object the world space one just like that and then we apply the transform of 
[01:29](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=89) the portal relative to the other portal which that's the complicated bit that we'll get into a little bit later but we apply all those onto there and then it works which uh I wish it was as easy as 
[01:44](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=104) that but we need to do some more complicated math on the geometry node side because that's what spawns in the secondary portal and makes the link between them but that's the Shader side 
[01:55](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=115) so just remember that it's just applying a transform here and then a vector rotation there and then down here this adds just a little bit of warp to the portal cuz 
[02:05](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=125) without that we can see that just oh no warping but yeah okay now on the geometry node side now here this was a little bit complicated to figure out but and it could be simpler but there is a 
[02:19](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=139) crash with the switch node when it comes to matrices so I could not condense it so this kind of split where you kind of have to duplicate stuff is necessary unfortunately uh I will make a bug 
[02:29](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=149) report about that but at the moment uh this could be condensed but this is the only way that doesn't crash so in here in the object properties we have an object input in this case this empty so 
[02:42](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=162) that's like the Target location where the secondary portal will be I didn't want to make it so that there were just two objects and then you would make a link between them because then you would 
[02:52](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=172) have to apply the link to both objects going to both of them instead it's easier to have one object with one portal and it'll be the same on both sides cuz it's the same mesh and all 
[03:02](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=182) that good stuff so for convenience sake so over here sorry I'm just going to check the audio levels real quick we should be all good to go okay so how does this transformation 
[03:14](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=194) happen well the Matrix nodes were added to 4.2 just in time so the main thing let's go with portal one so here we find the difference the transform difference between uh the object the empty object 
[03:30](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=210) which is the top one here and the self object right here so with that with the self object we invert The Matrix then we multiply the two that basically offsets them then we separate them and then we 
[03:41](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=221) store them for use in the actual Shader so that's how it works but when you get to the other portal it gets a little bit more complicated but basically the same concept here it's inverted so we do the 
[03:56](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=236) uh self transform offsetting the empty transform I hope that makes sense here it's one way and here it's reversed but something needs to be done first so in this case we put the portal where the 
[04:10](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=250) empty is so again portal one portal two and then we set the instance transform again another new thing in 4.2 uh we set it to be the empty object set to relative this one set to relative 
[04:24](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=264) these two are set to original keep that in mind then I rotate by 180° so that it's facing back if you don't do that then it can mess up a little bit which I will demonstrate right here so if it's 
[04:36](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=276) just zero it can the mesh will be pointed the other way the portal will still work but the mesh will just look a little bit weird because it's not pointing towards you okay with all of 
[04:49](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=289) that and I there's probably a better way of doing this that's just why I found works and then lastly um I set a second portal mask so that we can make it orange so in this case that just sets 
[05:01](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=301) the value to one so that I can use as mask so it's orange okay and also another important thing the main thing if you don't have this it will not work you need to change the geomet geometry 
[05:14](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=314) to an instance so that you can set all of this data specifically on the instance domain you don't do that it will not work at all but yeah there's all that so again all this is happening 
[05:26](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=326) on the instance domain and there we go that's all the data that you need to make the relation between two portals work and it works pretty well and again on the Shader side we just have that 
[05:39](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=339) data going into here well actually it's this part this part's just warping not entirely necessary if you want to condense it actually speaking of that let me just show the most condensed 
[05:50](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=350) version of this possible the right here this is how you get a portal to work right here if we do that we can say wow it's working EXA exactly as intended a nice elegant setup it could be more 
[06:03](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=363) elegant but unfortunately we don't have the Matrix inputs in the Shader editor unfortunate but it's what we have to do but it's rather clean it's not too bad oh another thing with the normal I 
[06:16](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=376) offset it by a little bit just to present uh prevent uh Z fighting so in this case I do have the portals being a little more 3D just to give it a little bit of depth with the warping effects 
[06:29](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=389) and Theiss but even if this were just a flat plane uh just to avoid Z fighting you offset it by the normal by just a little bit cuz that bad things happen if you don't 
[06:39](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=399) do that yeah that is the effect in all of its Glory so I guess I could go over the portal like the actual emission effect right here so here uh the U map let's 
[06:54](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=414) take a look at that real quick it's just that oh also I have the portal Textures in here as a nice little Atlas let me go over to the render results so that we can see 
[07:05](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=425) this uh I wanted to get one well this is just a circle it's not stretched but the image is making it look uh stretched so let's go back over to the Shader Editor to go through even more of 
[07:17](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=437) this so we have that and then I animate it by just pushing it in a certain direction making this look very very purple and then I offset it random per object wow that is very very bright I 
[07:29](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=449) apologize for that uh and then to make it seamless I pingpong uh the X the yeah the x axis and then after that it's just the noise so here we can see that the mo the 
[07:42](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=462) noise is doing that if I were to not use the seamless part we would see that there is a seam right there so there we go once again it's just moving as it should and then we use that to warp the 
[07:55](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=475) distance from the center again the UV map is centered right here so that does that and then again linear light just warps it does what it should and then we set that gradient and 
[08:08](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=488) then I use my little special linear light falloff uh just the logarithm style and all that good stuff here's the inal so if you want to take a look at it uh we have all that which just makes the 
[08:20](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=500) emission very crisp it always works very well and then we just have that emission and then we add it to that so that's that and also I switch between the ray portal 
[08:32](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=512) and a transparent node just so that the outside is actually just regularly transparent and not being portal you could make it more efficient by just switching the vectors but I wanted this 
[08:43](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=523) to be a cleaner node setup while sacrificing just a hint of performance to have another transparent node but yes that is that and uh it's working pretty well again performance uh on the stream 
[09:00](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=540) is not that great because again this is in uh Cycles not Eevee if I do this we can see you know it's pretty good pretty good then up here uh just the Shader is a bit different I'm still experimenting 
[09:15](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=555) with these different uh textures and such I guess yeah I could experiment a bit more with them here so in this case I just swapped out the uh the noise texture with the boroi and that's how I 
[09:25](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=565) did that again this is the most elegant version that I've that I have so far and it should be pretty good yeah we can do a bit more if you have any questions please ask them now 
[09:38](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=578) oh wow uh 10 minutes not bad not bad just for going over the effect I do like this because you can just turn up the uh the noise and then it looks really really 
[09:52](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=592) cool and also since it's all one plane one Shader one mesh all that good stuff you know the portal surface does not need to be solid like with a material assignment that was in a previous 
[10:04](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=604) version but with this version you could just make it as weird and wacky as you want which is what you want this one I was taking inspiration from uh the Ratchet and Clank game which they have 
[10:16](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=616) portals as well and theirs are a lot more fancy because they do some weird loading stuff where it can load up a completely different scene and then portal into that but anyway it's getting 
[10:28](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=628) a bit ahead ah head of ourselves and also I guess I should go over all the other features like again you could just scale these a ton it works out pretty 
[10:38](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=638) well there you go cool stuff like look at that it's amazing it works that well oh and there's even some recursion happening causing some weird stuff to happen that's cool a raise or lower this 
[10:54](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=654) one should see that's almost correct yeah you go like I I did not think that we would get this um this technology inside of uh Cycles any or blender anytime soon now 
[11:09](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=669) in theory this should be possible to do in Eevee especially the newer version of Eevee because they like render targets exist in other game engines like or game renderers I guess you could say like 
[11:24](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=684) ratch and Clank has one portal obviously has one that was out how many years ago many many many many years ago um yeah it's kind of the render Target type of fact yeah see what else can I go over I 
[11:41](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=701) think that's pretty much everything yeah here you can also scale the portals and they will work as intended making the world over here look small the world over here look big which 
[11:53](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=713) is really cool I want to try if I have time A lot of um camera going through portal effects because it could look really really cool uh and that's something I should mention if you want 
[12:05](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=725) an object to go through the portal this is something that I haven't really automated just yet I've done some tests but I still need to figure it out in its entirety here if you want a object to go 
[12:18](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=738) through the portal the problem is that you need two objects two real objects so here you would need to make a match ideally you would just do that with geometry nodes have an object uh well 
[12:31](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=751) put that object into like a collection and then geometry notes would be like okay get that object apply the transform so that it's there I've tried it but I haven't gotten the best of a seamless 
[12:45](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=765) version yet there's always been a little stuff going on but I will figure it out it shouldn't be too difficult I just don't it's getting a little bit late and I was like okay let's get this done 
[12:56](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=776) before we okay uh another thing that I should probably show off is the dimensional Cube which I believe I posted today uh this one it is still working 
[13:11](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=791) good I did this all in the same blend file which in hindsight was not the best idea looks like one part is missing Ah that's why one of the shaders I turned into an actual portal Shader 
[13:26](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=806) that is funny oh I can fix that really really so just going rotate well I don't even think a rot is needed this case no actually it is there we go let's just there good 
[13:45](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=825) that puts that over there so it's techn technically the same one over there but anyway so the way this one works is by using the local geometry space and then moving that a bit so how do I explain 
[13:59](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=839) this in the best way possible so this cube right here imagines that it's still right here as we can see from this it gets the local position and no matter where I move it it still thinks it's at 
[14:13](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=853) 0000 0 essentially and then the incoming this is still in uh Global space but then it gets converted into local space or object space using a vector transform node kind of it does the position 
[14:26](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=866) rotation and scale thing all inside one node it's unfortunately all the parts aren't exposed so I couldn't use this in the other setup but it's not that much of 
[14:36](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=876) convenience and then you scale by negative 1 this uh scale by negative 1 probably should have been before then coming but it doesn't really make a difference in this case so that's how 
[14:47](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=887) that works let me over a little bit to make it a little bit cleaner but that's how it works all of these still imagine that they're at 0000 or a a small offset from there as 
[15:01](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=901) in this case I just move it over by 9 M I'm just going to go and hide the other inputs using controll H just to make it look a little bit cleaner so here once again this room is projecting to that 
[15:15](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=915) room this one is projecting to Green this one's also projecting to Green because it's the same material let's go and uh swap that out really quickly there we go if we move the ad we can 
[15:26](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=926) just see that moves over the space that it's looking at so again this plane still thinks it's here and then I just slide it over to there yeah that's how that works I hope that was okay because 
[15:39](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=939) um it was a little bit fast also this first one is a cube and this was just because I was testing with a cube uh starting out as we can see here it still works which is very very funny so right 
[15:54](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=954) here whoops let me going control two this cube is looking over to here it's clipping through the the roof so I can go and make so that that is not 
[16:06](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=966) an issue there we go this side's looking there and then that one's looking there I can scale it up and then see the portal world go and z and then we're back so there we 
[16:23](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=983) go any questions because I think uh I think I went over everything let's go over to portal again there's so many things I want to test out with this node I'm trying to figure out Parallax 
[16:36](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=996) mapping using it got somewhere but unfortunately it can't self Shadow so it's not using yet but I'm getting there I am getting there okay I need to create something 
[16:50](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1010) like that in Unreal Engine 5 well good news that's probably I definitely possible using render targets I would imagine someone's done a tutorial for that in the past 
[17:00](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1020) asked will you share the blend file uh potentially I'm not sure if it'll be free or paid on Gum Road we'll see may not sure yet again this is very experimental this node is only is under 
[17:13](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1033) a week old in blender 4.2 so there's still a lot that I want to learn before I feel comfortable sharing the file that's why these breakdowns are here just in case and again with the geometry 
[17:26](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1046) node side this part it's good it's self explanatory but it could be even more efficient by using a switch node to make this all in one go rather than alternative but unfortunately there's a 
[17:38](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1058) little crash that happens with the Matrix nodes in the The Matrix sockets in the switch node so unfortunately that cannot be done just yet today I spent three hours fig 
[17:54](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1074) figuring out your flash lightning project it's amazing ah nice uh with that you can probably use the particle system that I made for the Sparks oh no wait the the lightning yeah 
[18:06](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1086) I forgot that that has the points that are attached to an Armature or to a moving deforming mesh which is always very annoying to uh to do in blender I wish we had a node to do that but 
[18:21](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1101) unfortunately uh it wasn't really a thought that people would want to distribute points on moving faces with a determined Point count so we had to do it ourselves which is annoying but once 
[18:34](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1114) you make it once you don't have to make it again you can make it an asset put it in your asset library and the only downside is people who view your videos don't have access to those node groups 
[18:44](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1124) so they're basically stuck nowhere then they need to go and spend 3 hours making it eventually eventually we'll probably have node groups to do all that like assets that blender has made but it'll 
[18:57](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1137) be a while before node groups are good enough but we're getting there The Matrix nodes are a good a good um step in that direction finally getting finally getting lower to what blender 
[19:12](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1152) actually uses versus just you know weird layers of filters between the actual Cod for lack of a better term yeah that's the effect I think I may end the stream right about now just because that's 
[19:27](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1167) basically everything I don't think there's anything else to go over um I guess I could just play around with these a little bit let's go and make a cube so in this case it will be 
[19:39](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1179) a oh interesting I thought this would work lawlessly interesting huh why is it not oh no that's why 
[19:53](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1193) because the UV Maps I forgot let's go and put this right in here so now this should show that's portaling a 3D space into there but it it's freaking out a little bit because the planes are 
[20:06](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1206) clipping through each other so let's just go and do that so now this is portaling a 3D space rather than a 2d space kind of like I forgot what that game was where it had this kind of 
[20:18](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1218) projection technology then in theory I should be able to also scale space like that causing it to look very very very weird ah okay non-uniform scaling seems to 
[20:31](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1231) make it freak out a bit more which is actually interesting maybe that's a result of the um oh no wait maybe maybe I need to actually apply a 
[20:45](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1245) matrix transform to the incoming Direction well anyway if you just make it scale normally on all axes you should be perfectly fine yeah pretty PR cool 
[20:59](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1259) [Music] stuff that's so weird so where was the human mesh let's go back over to oh okay uh that's funny since that's in the portal World we're 
[21:15](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1275) seeing that freak out let's go and move that up and let's go and move this portal up it's so weird also here's a little turret model that I made a while 
[21:33](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1293) back let's go control Z hopefully I have enough undo steps to add in no I have like one no one undo step before I could get the portals back into place oh that's a shame okay let me go and open 
[21:49](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1309) up the file once again remove all the changes that I made just to get back to Baseline so that we can end the stream in style okay let me get the chat back up okay so 
[22:03](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1323) that's the effect again uh very noisy because again this is Cycles trying to denoise one sample which is not [Music] fun 
[22:16](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1336) okay all right I believe that's it thank you all for watching uh more portal projects will be coming in the future because well this is a lot of fun lots of cool stuff I really like the lighting 
[22:28](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1348) here as well I've been playing around with different uh um color spaces I found that filmic looks the best with this kind of blue and orange I'm interested in Kronos because it seems to 
[22:41](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1361) have the like um desaturation with high values without uh making them look Des super desaturated like agx but for the moment I'm still using filmic just because it 
[22:55](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1375) feels I'm more familiar but yeah that is the portal effect and how it was done I hope it was understandable even with the new Matrix nodes I know that not many people uh 
[23:08](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1388) know about that and know how they work but they're just a location rotation in scale and then there's nodes where you can invert that uh offset it with a multiply Matrix node and a lot of other 
[23:21](https://www.youtube.com/watch?v=1ZvwhLRPM3M&t=1s&t=1401) cool stuff but thank you all for watching and I will see you next time have a good one 