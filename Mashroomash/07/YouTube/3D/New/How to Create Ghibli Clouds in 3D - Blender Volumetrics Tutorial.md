---
URL: https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf
thumbnail: https://i.ytimg.com/vi/RgRPUlFBHH4/default.jpg
channel: "[[Lightning Boy Studio]]"
date: 2024-07-16T14:31:29
published: 2020-09-23T00:00:21
duration: 2843
tags:
  - video/3D/tutorial
done: false
cover: "[[Pasted image 20240716143207.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "47m 23s"]
# How to Create Ghibli Clouds in 3D - Blender Volumetrics Tutorial
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716143207.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="How to Create Ghibli Clouds in 3D - Blender Volumetrics Tutorial" src="https://www.youtube.com/embed/RgRPUlFBHH4?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: In this tutorial, David will show how to create volumetric clouds in the style of Ghibli films in Blender 2.9)

You can download a free Blender scene of this cloud on our Gumroad page :
https://lightningboystudio.gumroad.com/l/nPlSL

You can follow us on Twitter and Facebook :
https://twitter.com/LightningBoySt1
https://www.facebook.com/dinomancersproject/

If you want to see another take on how to make Ghibli style clouds in Blender, check out Kristof Dedene's video :
https://youtu.be/ZwhK51dSSbk

Check out our Ghibli tree tutorial here : 
https://youtu.be/DEgzuMmJtu8

You can watch our toon shader tutorial series here :
https://youtu.be/TpWI2rU8iF0

Curious to know more about our upcoming animation project "Dinomancers"? Check out our animation test here :
https://youtu.be/RDzCUMUEbu0

Cloud texture:
https://drive.google.com/file/d/1SelXRF9VYhksPys3MTYDsSHcQ1_VQT7Y/view?usp=sharing

Ghibli clouds reference images:
https://drive.google.com/file/d/1l8TD2FR6CeAnvZKP93YDxEWdBaWj-585/view?usp=sharing
https://drive.google.com/file/d/1dBOGF_RdogT_GgwI7y5GxtqXMB36u1vm/view?usp=sharing

Opening Logo Sound Mix : Les Productions Underground
# Transcript
[00:06](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=6) [Music] hey everyone i'm david from lining board studio and today we're going to look at how to make jubilee inspired painterly clouds in 
[00:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=16) blender 2.9 so there's a few ways we could do this we could look at our previous tutorial how we did trees and 
[00:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=26) apply the same technique so cast some particles apply custom normals but the problem is we're never going to get those very fluffy edges like you see on clouds so what i'm going 
[00:36](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=36) to do today is show you an entirely new technique that's based on volumetrics but that's actually way more powerful and customizable 
[00:44](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=44) so i hope you guys are excited and without further delay let's get started alright let's do this before we start just make sure to activate the node wrangler and you can 
[00:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=56) go to edit preferences add-ons type in node wrangler make sure this is uh activated that way we have all the same shortcuts as i do in the node 
[01:05](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=65) editor will be much easier for you to follow along um so first thing i'm going to do is make a basic volumetric object 
[01:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=74) and we're not actually going to use it for a cloud but we're going to use some of the same principles and so i think it's going to be useful 
[01:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=82) for me to show you some of the issues i have with the default volumetrics in blender that way you'll better appreciate all the differences once we make our own 
[01:32](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=92) upgraded version for this tutorial so the way it works is you click on this cube go to material and then replace the principle bnd vsdf by a principal volume 
[01:46](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=106) now you can extend your timeline and press shift f3 a bunch of times until you you see a node and make sure to plug your volume 
[01:54](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=114) into volume not surface now if you hold down z you can change this to render and if you grab your light and move it closer you'll notice that you start seeing this 
[02:06](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=126) this volume um so first thing that bothers me a bit is how it flickers really weirdly as you move the camera around so even if you go to your render settings 
[02:17](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=137) um volumetrics and bump up this to like just two pixels it's going to look better when you do your render but as you move around in your scene i find it kind of annoying 
[02:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=148) especially as uh so on our dyno masters project we work just in eevee and we like to really um get a sense of what this scene is going to look like as we press play 
[02:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=160) and i just don't like that it's flickering all the time so small detail but it's going to be fixed in our in our own version 
[02:47](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=167) now one thing one thing volumetrics are really good at is to render uh three-dimensionally uh noise textures or gradient textures so let's say i were to create a i don't know a must grave 
[03:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=181) texture and plug it into my density you'll see that i get this 3d texture in my scene so pretty cool now 
[03:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=194) it mounts on it might sound useful to be able to fill up an object with a volume but it's not actually that powerful and i can demonstrate it 
[03:24](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=204) by just creating a uv sphere and applying the same material to it you notice that it still has this cube shape and the reason is it doesn't 
[03:35](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=215) actually look at the surface of your mesh just at the bounding box so it makes it really hard to sculpt anything that has a precise shape you have to use a bunch of gradient 
[03:47](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=227) textures and vector curves to shape your things and you cannot even use textures because you don't have uvs so makes it a bit difficult to escape to sculpt a good-looking cloud 
[04:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=240) and but for me like the final nail in the coffin of this principle volume is you cannot use a shader to rgb node with it so that 
[04:10](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=250) means there's no way to make a two or three tone shader and get that very nice toon shaded look um so if you don't mind i'm just gonna ditch this and 
[04:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=262) start over with uh with something better so um what i'm gonna do is create a diffuse bsdf so press shift a type in diffuse bsdf and then i'm also going to create a 
[04:36](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=276) transparent vsdn so uh and i'm going to mix the two using an image texture i made so press shift a image texture and i'm going to open and 
[04:49](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=289) pick that cloud texture there so if you want to see it i just press shift f10 twice and you can see the cloud texture so it looks like this i painted this earlier in photoshop 
[05:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=301) you can paint your own or you can use this one i will link it in the video description and and so we use this alpha to drive where things appear transparent 
[05:12](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=312) and where you see the diffuse so we're going to mix these two together using ctrl shift right click so that's one of the things that node wrangler adds as a shortcut 
[05:20](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=320) and then we're going to plug the alpha in the factor here and the mix shader in your material output surface and you won't see transparency right away 
[05:31](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=331) because you need to activate and you need to change the blend mode from opaque to alpha hashed and shadow mode to alpha hashed and now 
[05:42](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=342) if i move on my light you'll see that there is actually transparency but it still looks wrong and the reason is we're using uvs from a cube 
[05:50](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=350) but we need to project it from the front so let me go in front of you here and go in edit mode with tab press u and then project from view and then we'll go 
[06:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=361) in the uv editor so press shift f10 and then press on l and uv pack island so it's gonna fill up that uv space nicely and you can go back to the shade 
[06:15](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=375) editor pressing shift f3 so now you see we we have our cloud texture applied to the cube on on both sides of these surfaces because it's projecting it from the 
[06:25](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=385) front and you have this nice fuzzy edge like we want but the problem is we're we're not filling the cube like it doesn't look like a tree cloud 
[06:34](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=394) and the reason is it can only using the diffuse bsdf plugin surface you can only apply your textures to surfaces so we need a surface 
[06:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=405) inside so that you see you see the cloud and one way we could do this is just by stacking a lot of planes right next to each other so i'm going to delete the the one the back here so just 
[06:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=416) press tab click on tree to access the faces and then delete those faces so you only have the one in the front and i'm gonna go in my modifier panel 
[07:08](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=428) and add an array and i'm gonna change this to fixed length i can add a length of 2. and unclick relative offset click on constant offset instead and 
[07:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=442) type in just like 0.5 and y for now so as you can see i have a bunch of planes that have been generated like inside inside my cube 
[07:35](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=455) and as i lower this value it's going to reduce the distance between the plane so the more i add the more it's starting to look like 
[07:47](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=467) a 3d shape and it's still retaining that very fuzzy edge at the top because each of these planes have the imitate the image texture applied 
[07:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=476) onto it so we're getting somewhere now there's still obviously a lot of issues like it still doesn't look like cloud it's way too blocky and this is way too flat so let's address the 
[08:08](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=488) flatness of the front first we're going to make a custom normal map for it and it's going to be very different from how we did it in the ghibli tree 
[08:19](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=499) tutorial this time we're going to use an image texture and we're going to use metal balls to generate it so press shift a metal 
[08:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=508) ball and so you get this ball here and i don't know if you've ever used metal balls uh honestly i don't use metal balls very 
[08:35](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=515) often myself but they are actually very useful for the kind of thing we're gonna do here so uh what metal balls do so if i duplicate this one 
[08:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=525) and just move it up and scale it down is that they will always merge with each other and so right now it looks very low resolution but you can reduce this maybe to uh 
[08:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=536) 0.02 so now you have this um this sphere and as you approach it closer it's going to merge with this one so let's keep this scene uh handy at the top i'm gonna open up a 
[09:13](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=553) new viewport here and i'm going to um [Music] okay so what is that this okay so i'm gonna jump in top view 
[09:25](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=565) and just try to frame nicely onto it and then i'm gonna move my camera where my viewport is so to do this you do control alt and zero on the numpad and it's gonna 
[09:36](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=576) just jump your rendering camera at the same place now i want to change my format to something square so let's just go to the output 
[09:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=585) properties of here uh and change this to 1000 should be enough and then i'm going to uh just scale make sure that the big one is filling up 
[10:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=601) the square as much as you can and now the trick uh so that we were able to render a normal map is gonna we're gonna click on this 
[10:11](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=611) little arrow here and you see there's a button called matcap and if you click on it there's actually a material that looks like a normal map 
[10:19](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=619) in the screen space so that's that's really useful because like it's always going to be pointing the the pink color is always going to be pointing the top 
[10:29](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=629) in the bottom right and the green and top left and it's it's just it's just exactly what we need uh to render a normal map so i'm going to jump back in my camera by pressing 
[10:37](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=637) 0 on the numpad and we're going to sculpt sort of a more complex shape for the front of our cloud so i'm gonna make a bunch of these these 
[10:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=648) spheres here and uh to make it a bit faster i'm going to duplicate a bunch three or four and then if you select all four at once 
[11:08](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=668) and click on your pivot point you can change it to active element so if i duplicate this with shift d now i have four more and if i pick my big sphere 
[11:20](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=680) last so it's going to be my active element the pivot is going to be at the center of uh of my sphere so now as i rotate they're always going to be uh staring 
[11:33](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=693) near the surface you see so makes it uh a bit easier to duplicate a bunch so i just need to unselect the big one shift d and then select the big one back 
[11:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=705) up rotate them shift d select the big one rotate and uh maybe one last time okay so i'm just going to move them a 
[12:07](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=727) bit uh try to not go uh outside of your your sphere here and uh you can move them a bit down with uh by pressing g for grab and then z to 
[12:20](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=740) lock it in the uh the z z-axis as you move them so they will sync in the uh the shape of your um your sphere and uh what you want to look for is to 
[12:33](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=753) create sort of uh an overlap at the top here so you want the spheres in the middle to be able to get 
[12:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=765) uh light from the top so make sure that they're not too faded inside your your your surface because you want as much green as possible here so that they will get nice 
[12:57](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=777) lighting so i'm going to sink these ones inside a bit so this is pretty good this one i'm going to sink in just a bit more 
[13:09](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=789) and if you want to merge things together you can just like duplicate one again make it pretty large and just like move it up and down so you can fill up this space a bit 
[13:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=806) so this is almost done [Music] i would say all right i think this should be perfect so 
[13:43](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=823) just unclick your overlays and then maybe i could even uh change the resolution to 0.01 so it's renders even a bit smoother and then go to view 
[13:57](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=837) viewport render image and then image save as and let's call this cloud normal map so we can jump back to your share editor with shift f3 
[14:13](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=853) you need to click on your cloud all right we won't really need those metal balls anymore i'm just going to put them in a collection for now 
[14:23](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=863) so select all of them press m new collection call it normal map baking so maybe the first normal map you do won't look right and you want to go 
[14:36](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=876) back to it change stuff a bit and uh until you get the perfect mix um like i did practice a lot just to find the right mix so i'm doing this in front of you but 
[14:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=888) there's a lot of trial and error behind it um so i'm going to import in another image texture so shift a image texture and let's open 
[15:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=900) our cloud normal map and we'll need a normal map node so shift a normal map and let's plug the color into the color of the normal map and make sure to change the color space 
[15:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=914) to non-color otherwise it won't work and then all you need to do is plug this normal map into the normal of your diffuse so right away you should see that you 
[15:24](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=924) have this uh volume that's appeared on your sphere and it's it's still flat it's not a displacement it's just a normal map so we're faking normals over our flat plane 
[15:36](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=936) um i think i'm going to change this light to a sunlight change the strength to one okay so it's going to be a bit softer so nice we got some volume now it still 
[15:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=948) looks a bit 3d uh tree like you i'm sure you'll agree so we're gonna try to break this shape up a bit 
[15:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=956) so instead of being very perfect spheres it's gonna look a bit more fuzzy like the edges of our clap so let's make so shift a nice texture and we're going to click on this 
[16:11](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=971) image here of our normal map and press ctrl t so that's another shortcut the node wrangler adds and what it does is it it brings out the texture coordinates for this image 
[16:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=982) and we'll be able to then mix the texture coordinates with our nose texture to to break it up a bit so just ctrl shift right click it's going to add a mix node 
[16:31](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=991) and bring the factory to something just a bit lower than one and then bump up the scale quite a bit so as you can see we're mixing a noise 
[16:42](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1002) texture with our our sphere normal map and the more we increase it the more it's going to be distorted so 
[16:53](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1013) that way we were able to get a more organic look so i'd say that's much better now um let's add some colors to this um i think it might be a good moment to 
[17:09](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1029) import um our image reference so let's bring in this image from uh a jubilee movie and i really like this cloud 
[17:23](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1043) so let's let's see if we can match this look as close as possible um i'm actually going to change the color of my world setting here so 
[17:34](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1054) that it's also blue that way it's going to match the blue all right and 
[17:45](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1065) oh yeah i'm going to change the color management settings uh to um so you won't be able to see it but if you go to your render properties the 
[17:56](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1076) very bottom there's a color management panel and changed it from filmic to standard that will be easier for you to pick colors 
[18:05](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1085) from an image otherwise there's going to be a bit of a difference so let's go back to object and all right so we're gonna start adding more and more nodes so let's make a 
[18:19](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1099) frame maybe so we keep things organized um i'm gonna call this one normal map let's bump up this label size put this in all right so this is our 
[18:35](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1115) normal map so we don't forget and now we're gonna add a shader to rgb so remember that's the thing we couldn't do if we were using a real like a volumetric shader 
[18:47](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1127) but now we can because we're using a diffuse so shader to rgb and then create a color ramp and put it after the shader to rgb so now we can remap the colors the black 
[19:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1140) and white colors to new colors so the white color is going to be this kind of yellow and the black color is going to be 
[19:10](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1150) kind of blue and we're going to move these two closer together get more of a toon shaded look right and then i'm going to add another 
[19:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1162) handle and it's going to be a darker color so we get those uh darker occluded parts let's pick the darker blue 
[19:33](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1173) and i'm actually going to duplicate this one and actually it's not the same color i need to pick it okay so just move it closer so you really get 
[19:43](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1183) that that dark blue but just at the very very end and we're gonna pick it up using ambient occlusion so let's go to ambient occlusion here 
[19:54](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1194) activate it and let's enter maybe like one and five so let me zoom in a bit so you see now it's picking up this this edge here because of our normal map 
[20:07](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1207) so it's like the surface thinks it's facing very far away from the light at this point so it's picking up the darkest color you can find so 
[20:17](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1217) it gives it a bit of a watercolor feel to it and as we put more of these this cloud piece together uh they're going to also cast occlusion 
[20:29](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1229) onto each other so it's going to look nice all right so i think we're getting somewhere all right um so now if you remember we still have a problem of this looking 
[20:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1248) really blocky so let's try to slowly sculpt this into more of a shape a cloud shape so for this we're going to be using a gradient texture so shift a 
[21:03](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1263) gradient texture and we're going to change this to spherical so it's going to be a spherical gradient in 3d space and if i click ctrl t here 
[21:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1276) i can access the texture coordinates and let me just demonstrate what it looks like right now so i'm not going to use my cloud texture for now just plug 
[21:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1288) the factor into the mixing factor of our mix shader so as you can see there is this shape here and it's actually um a sphere so i can move it back and forth 
[21:43](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1303) and it's appearing inside my cube and i can move it around and if i want to center it the best way is like you could just move it with location and scale but the easiest is 
[21:55](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1315) just to use the object location instead so it's going to be nicely centered great so now we're going to be mixing these two so 
[22:08](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1328) maybe let's create a new frame again just to keep things tidy so let's call this one round shape and make it 50 put it in there okay and we're gonna mix our grainy 
[22:23](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1343) texture with this cloud texture that we had so ctrl shift right click it's going to bring your mix node change it to multiply you can click on 
[22:32](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1352) multiplier just press u bump the factor to one and this is what we're going to plug into our mix shader now to tell where the transparency appears 
[22:41](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1361) so all right so from the front as you can see we still have our our cloud texture but as we move around we now have a rounder shape 
[22:52](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1372) so still not perfect but but we're getting there now uh if you look closely uh it's it's gotten a bit more fuzzy because our our sphere has 
[23:03](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1383) faded out the edges so what i want to do is just add a color ramp right after the multiply and i'm going to crunch back up those those edges just a bit 
[23:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1406) all right all right so um [Music] now uh let's break up this even more using another noise texture so 
[23:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1428) i'm going to press shift a nice texture press ctrl t again and we'll call this we'll put this into a frame it's going to be called noise 
[24:11](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1451) okay and we're going to be mixing the noise with the gradient texture the spherical gradient texture so ctrl shift right click mix these two together 
[24:27](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1467) change this to multiply from the factor to one and now it probably won't look very very different now my scene is starting to lag just a bit so 
[24:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1480) make sure that this is not too low like if your computer is not very fast just you can put a big bit of a higher value here and still it's still going to look good 
[25:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1500) all right um so you won't see the noise right away you need to press shift a type in color ramp and we're good slide this color around 
[25:09](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1509) between the noise texture and the multiply node um and that way we can crunch crunch it and now we start into the former cloud 
[25:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1522) so as you see from back here starting to look a lot nicer and you can change the scale to something bigger or smaller uh now there's still a bit of an issue here 
[25:34](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1534) like we're what we want is to break up the round shape in the back but i think you'll agree that the front really look good like we don't want to break it up 
[25:42](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1542) and create those weird holes in it so we need to restrict the noise to only be applied in the back none in the front so what i will do is add a um 
[25:57](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1557) another gradient texture but this one will keep it in linear so it's just going to be oh sorry okay so i just want to put in the frame okay um i'm going to press ctrl t 
[26:15](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1575) look sometimes if you're in a frame they might appear somewhere very far when you're seen happens and um okay and let's just 
[26:27](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1587) plug this directly into our mix shader here just so we we can see what's going on so um i'm gonna use object coordinates here 
[26:41](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1601) okay so as you can see it's not properly aligned we need to rotate it uh with rotation z so i'm gonna change this to 90 degrees so it's sitting in the front and i'm going to 
[26:54](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1614) change the scaling to 0.2 so it's a bit more faded so we have this section here that's all white and so we're going to be adding it 
[27:06](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1626) to our noise so that it's all broken up in the back and it's a hundred percent white in the front so let's mix these two the color ramp and 
[27:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1636) the gradient texture with ctrl shift right click and it's going to bring up this mix node but this time we're going to put it in add 
[27:27](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1647) so we're adding this one on top of the noise and if we want to see just how this one is looking i'm gonna plug in the mix shader 
[27:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1668) it's not working okay oh yeah okay it's because my color ramp is not crunchy anymore so add it yeah all right i was confused for a moment 
[27:59](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1679) um so there you have it so this is perfectly like filled up and it's being broken up in the back so this is what we wanna um this is what we wanna multiply with our 
[28:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1694) original round shape i know it's getting confusing like maybe let me zoom back a bit here because i know some of you are trying to do this as i do it so 
[28:22](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1702) let me just show you the overall picture so you have your normal map it's being plugged in diffuse vsdf and then using a shared rgb we color it then to add transparency we need to tell 
[28:38](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1718) where it's transparent so um this should go here okay and so we have our cloud texture and it's being multiplied by a bunch of stuff 
[28:51](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1731) uh our round shape and then our noise texture that is limited to just be in the back and then we're crunching it just a bit here with the color ramp so let's see how it looks 
[29:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1754) all right um it shouldn't actually be affecting the front which is a little weird maybe i should add another color ramp here 
[29:34](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1774) that way i can crunch the value yeah okay so with this cover ramp we'll be able to crunch the values of our of our linear gradient here to make sure 
[29:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1788) that it's not being lost all right so the cool thing now is that using this like if i play with this location value i can sort of uh 
[29:58](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1798) randomize just the edge of my cloud if i look at a bit from the back here you can see that i can really change how it looks in the back and if i change the scaling it's gonna 
[30:11](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1811) add the scale here can make it very fine or very big so pretty cool right um okay so 
[30:27](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1827) let's say you're you're ready to build your cloud so you can um put this into a new collection so press m new collection we call it uh i don't know cloud piece and you can 
[30:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1840) hide it and then if you press shift a collection instance you can make a new cloud piece and so this is a collection instance if you've watched our previous 
[30:51](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1851) jubilee tree tutorial you'll be familiar with this basically what it lets you do is you can just make a bunch of these and they all point back 
[30:59](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1859) to the original one so if you change the original one you're going to update and it's a bit uh faster to calculate and stuff so okay so one of the issues you might 
[31:10](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1870) encounter as you add more of these is you'll see some weird lines or artifacts appearing and so don't panic there's a way to fix it just press 
[31:20](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1880) n go to view and change the clip start to something a bit higher so just like just point one is enough it's because since we have those planes stacked up 
[31:30](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1890) very close to each other it's just messing up with the clipping plane so um so that should fix it now as you build your cloud you can always like rotate these 
[31:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1900) to make some some variation to it so i'm just going to uh just try to recreate that that cloud very quickly okay maybe change the light angle 
[32:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1920) so it's facing more to this side i want to show you how we can achieve this darker region on the left here so let me uh duplicate a bunch of these 
[32:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1948) okay so a few things you can do uh first if ever you want to reduce the strength of your normal map you can do it uh just go to uh normal map here and 
[32:38](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1958) change the strength leave it update okay so you can change the strength here so it's not that strong so sometimes it looks a bit blobby so you can reduce it a bit um 
[32:52](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1972) you can obviously continue to break it down a bit more if you want to okay if you want you can try increasing the distance of your ambient occlusion 
[33:12](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=1992) so this this goes further and um and if it if it doesn't go far enough you can play with your color ramp here and make this one go a bit further still 
[33:27](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2007) okay i'm gonna play with these values a bit if you break it up just a bit more okay let me bring one in front here okay uh i might adjust my colors just a 
[34:30](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2070) bit um so the first blue here i think i'm gonna make it a bit lighter maybe less saturated 
[35:02](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2102) okay and so there's a few other things you can do to tweak the look um if you create a light like a point light and then um 
[35:21](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2121) go to your light settings deactivate shadows uh i think i'm gonna lower my settings just a bit from my cube still here maybe point 
[35:33](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2133) okay so you have your point light so if you move it somewhere you'll be able to um to fill up the darker portions and can increase the light size or the 
[35:52](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2152) radius maybe that's too much so you can sort of sometimes you want these areas to all be filled up and vertically you can duplicate one and put 
[36:13](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2173) the negative value it's going to suck out the light from it so something something you can play with and finally a technique i find even more useful 
[36:24](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2184) is to go back into your material and we're going to add a a gradient texture so gradient 
[36:38](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2198) change this to spherical press ctrl t and this will be let's create a frame and we call it uh extra light so we'll add the kind of a light but using 
[36:57](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2217) an empty so let's create an empty here plain axis oh move it to the top collection okay and then change this to object but this one 
[37:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2234) this time pick the empty instead of leaving it empty to use the object settings from your object and we're gonna just after this color 
[37:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2246) ramp here we're going to be adding a mix rgb use the factor from this as the mixing factor and let's just pick this this blue color 
[37:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2260) here so now if i move this notice that i get this this color appearing it's because there's an actual 
[37:50](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2270) spherical gradient in my 3d sphere and the position is determined by the position of this empty so i can move it around but i can also scale it 
[38:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2281) to make it softer so what you can do is put it here to try to get those like you see how this is very soft here in the blue 
[38:12](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2292) in the blue shadow so you can sort of use this to to achieve this this effect um make it nicer blue here 
[38:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2308) and then you could duplicate it again and create another mix node duplicate all of this again and use this as the mixing factor and so in the front what you could do is 
[38:46](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2326) add a a lighter color just make sure to change the empty location to the other one so now you can add more light from this 
[38:58](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2338) side and it can be a very like a very soft gradient it's it's nice to uh blend things together 
[39:07](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2347) using these empty and since it's not an actual light it's just a spherical gradient uh going to give you that softer look because it's not concerned with the 
[39:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2356) surface of your object just it's just its position in 3d space so um so all of this is still like editable you can change the 
[39:30](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2370) angle of your your light and like it's it's not going to be perfect i can't i can make it i cannot make a very good looking cloud in in two minutes 
[39:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2380) but with enough enough time i think you could make a very nice looking cloud and possibly less time that it would take you to uh to paint it but um 
[39:51](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2391) but it also also has the advantages of being in full 3d so you can just find a nice angle and uh it looks nice and it has a very uh 
[40:03](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2403) nice fuzzy edge that you couldn't get with pure geometry now there's there's one last thing that i'd like to show you and it's um 
[40:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2416) [Music] it's to how to add variation to your cloud piece so let's say i i duplicate this one on this side here and because right now they all look the 
[40:28](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2428) same right it's all the same the same blob but what would be nice if is if we were able to make all of them a bit different so i'm going to um 
[40:40](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2440) use a similar technique to what we did in the ghibli tree tutorial and it's using the uh so in object properties viewport display you have this thing 
[40:50](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2450) called color and we can access this color in the note editor even though it's a color it's it's um it's a collection instance because 
[41:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2460) collection instance don't even have a material i couldn't even apply another material to this one but i can access its color here so um so let's just pick the cube 
[41:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2474) and then i'm going to add a object info node and you see this this color info is output is what we need so we're going to instead of using just 
[41:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2486) one color we're going to be using the red channel to do something the green for something else and the blue for another parameter so 
[41:37](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2497) i'm going to use a separate rgb because we need to separate the colors so now i'll need a combine x y z because we're going to be put plugging these into 
[41:50](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2510) vector inputs and so i need to convert one value into three so what i would like to do is affect this um at first this uh offset of my noise 
[42:05](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2525) so in the in the y input here so so and this is the uh the noise and confuse it with the linear green texture like we have on top so let's plug the red in 
[42:21](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2541) y and then this into the location and then i'm going to duplicate this one now use the green color but this time i'm going to be plugging it into x y and z and plug this into 
[42:39](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2559) scale and finally what i'm going to do is add a power node here 
[43:00](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2580) and i'm gonna use the b color into it okay so let's see how it looks so now so if i if i pick this collection instance i can play with its red color in 
[43:16](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2596) viewport display object properties to offset this value so i can make all of these sides of the clouds a bit different then i can play with the green value to 
[43:30](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2610) make this either very large blobs or i could enter a big value to make a very fine detail okay and finally my last setting 
[43:48](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2628) is going to be my dissolve operator so you see how it's dissolving my my noise texture the problem is we still have that linear gradient that's telling this part to 
[44:01](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2641) always stay full so we need to address that for it to work properly so let's click on the cube and so what we could do to make it go 
[44:13](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2653) away is just to offset it maybe in the uh in the x direction you see so if i if i were to go in the x minus here 
[44:23](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2663) it would just disappear so by default my color is going to be one so i need to and i wanted to as i increase my value 
[44:35](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2675) i actually want this this value to go into negatives so i'm going to add a math node and this one's going to be multiply and we'll multiply by -1 
[44:47](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2687) so that way as you increase the value it's actually going to be a negative value it's going to work but the problem is by default my blue is going to be 1. so if i add 
[44:58](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2698) i i invert it to minus 1 it's going to feed minus 1 into here so i actually need to do something else here i need to add 1 so that even though 
[45:12](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2712) i start from 1 i make it minus 1 i need to add back 1 so that it's now zero i don't know if that was clear but hopefully it is um so let's 
[45:26](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2726) add another combine x y z and i think we said it's the x value that we need so let's just go back here import display and let's change this 
[45:44](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2744) back to one one one okay so if i move this value to something higher than one i can fade it away so i can start making those 
[45:55](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2755) really nice puffy cloud there's really no limit to what kind of cloud you can do with these uh three settings so it's pretty nice so you can combine them 
[46:10](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2770) to add those uh like fading away puffy clouds on the side and stuff um that's pretty much it i hope you uh enjoyed the tutorial and learned 
[46:21](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2781) something sorry if it ended up a bit long-winded it's always difficult to make something that's both technical and artistic at the same time 
[46:31](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2791) but as you can see here the depth of what you can do is really impressive so hope you give it a try it's not the easiest technique to master so don't get discouraged keep practicing 
[46:42](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2802) and i'm sure you'll get there oh and also you guys need to check out this other tutorial it's made by a guy named christoph he released it yesterday 
[46:50](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2810) and he's also found a really cool way to make ghibli clouds so if that's something you like don't miss it we'll put the link in the video description 
[46:57](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2817) i'm looking forward to do more tutorials for you and i'll see you next time hey thanks for watching did you know also developing an animated series called 
[47:06](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2826) dino answers we also have a six part tutorial series on how to make a full featured toon shader and blender so if you like our work make sure to 
[47:14](https://youtu.be/RgRPUlFBHH4?si=A6tMIRC1LjobGJsf&t=2834) check them out and subscribe to our channel all right take care 