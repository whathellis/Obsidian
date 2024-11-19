---
URL: https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR
thumbnail: https://i.ytimg.com/vi/gG7ZoP3fd1w/default.jpg
channel: "[[Lightning Boy Studio]]"
date: 
published: 2022-04-08T02:08:22
duration: 2395
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715193118.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "39m 55s"]
# Arcane Tutorial Part 2 : Deep Dive Into the Arcane Look and Camera Projections (Blender 3.0 / EEVEE)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715193118.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Arcane Tutorial Part 2 : Deep Dive Into the Arcane Look and Camera Projections (Blender 3.0 / EEVEE)" src="https://www.youtube.com/embed/gG7ZoP3fd1w?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Part 2 of our series on how to replicate the stylized look of the Arcane animated series in Blender.)
This tutorial was done using Blender 3.0 and the EEVEE rendering engine.

Watch Part 1 here : [[./Arcane Style Tutorial Part 1 Hair (Blender 3.0  EEVEE)|Arcane Style Tutorial Part 1 Hair (Blender 3.0  EEVEE)]]
https://youtu.be/FXuReln3XD0

To purchase the Lightning Boy Shader check out our Gumroad page : https://lightningboystudio.gumroad.com/#aYbiH

Tidal Blades 2 Kickstarter :
https://www.kickstarter.com/projects/druidcitygames/tidal-blades-rise-of-the-unfolders-cypher-system-rpg-book

Our Twitter :
https://twitter.com/LightningBoySt1

Other credits :
Trailer Sound effects : Mark Donis [Pride Productions] - https://www.facebook.com/1MDonis/
Opening Logo Sound Mix : Les Productions Underground
Arcane Cogs Reference: Magali Vidal - https://www.artstation.com/artwork/Vy8bR5

Chapters:
0:00​​ Intro
0:57 Arcane Shots Analysis
4:50 Making an Arcane Style Default Cube
15:56 How to Bake Texture in EEVEE
22:05 Character Shading/Texturing
32:58 Texturing the Character's Head
34:05 Lighting Tricks
37:34 Eye Specular
37:51 Character Camera Mapping
39:00 Environment Camera Mapping
# Transcript
[00:10](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=10) everyone it's david from moneyboy studio and this is part two of our tutorial series on how to make an arcane style and blender now last tutorial we explored how to do stylized hair using 
[00:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=19) particles and today we're going to take a deeper look into what makes arcane so unique from how to paint textures set up the shading and make the most out of camera mapping and finally i'm going to 
[00:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=30) show you how i used all these techniques to create my own character and animated shots for the opening of my project title blades alright so that's a tall order but 
[00:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=40) as with anything new and difficult i tried to break it down in small steps so i want to start with some observations pinpoint what are the challenges exactly we need to overcome and then we're going 
[00:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=52) to find solutions for each of them so just grab a seat and let's get started so the first observation i want to make is about backgrounds and the fact that if they all look so beautiful is because 
[01:05](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=65) they are literally painted from the camera in almost every shot and if you have experience in 3d it might be quite obvious already but i still want to point it out because it's 
[01:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=76) an important part of of arcane in general so let's take this room as an example you can see this best on the small chest here pay close attention to this last 
[01:25](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=85) bolt you see how this part is very flat it's pointing this way well if we switch to a shot of the same chest a little later look how the bolt is different you don't 
[01:35](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=95) have this flat edge here anymore it's sort of round and the highlights are much thinner and higher res so that means it was literally redrawn from the camera for this close-up shot 
[01:46](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=106) and a good way to tell if something is camera projected is usually true to shadows notice how you can see these painted strokes here and this dash of orange in 
[01:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=114) the transition now compare with the shadow projected from the chest here and you'll see the difference so camera projections is something we're going to learn how to make in just a few minutes 
[02:03](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=123) but for now uh there's a couple more things i want you to look at so the second observation i want to make is about their shader and i'm putting this in quotation marks in my mind because i 
[02:14](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=134) don't believe they do have a perfect shader for every situation i think almost everything you see in this show is artfully assembled and compositing and if in a particular instance 
[02:25](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=145) something is going to be better defined by a 3d light like on the arm of this character then they're going to use lights and if they feel like the base texture is going to work better as is 
[02:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=156) you're just gonna color correct it so it feels like it's lighting but it's actually a texture and this piece of metal here is a good example because the right side is in the shadows you might 
[02:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=165) expect it to be from the lighting but if you actually look at the texture on art station you'll see it's part of the texture itself the next observation i want to make is about specular now many 
[02:56](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=176) of the characters in arcane would have this very iconic three-point highlight in the eyes and it doesn't always move the same sometimes it will follow perfectly the eye movement sometimes 
[03:06](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=186) only partially or it might wiggle a bit to show emotion so it's clear it's just drawn on another layer and they animate it by hand but even on other shiny surfaces they 
[03:17](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=197) never shy out of painting the specular instead of letting the 3d lights decide where it would go see this creature which is by the way one of the cutest and coolest thing i 
[03:28](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=208) have seen on this show but that's beside the point um check out these little painted specular here and there they just stay in place when the creature moves 
[03:38](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=218) sometimes they sort of disappear when it turns its head because it's not in the same angle but they don't move like you would expect such a highlight to do and and that's fine it's in fact one reason 
[03:49](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=229) you can barely feel these are 3d animated characters okay so the final observation honestly blew my mind when i noticed it and it's something i'm quite sure not 
[03:59](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=239) many of you realize because they do it so seamlessly that you almost can't see it so i want you to pay very close attention to the shadow projected on her 
[04:08](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=248) arm here just at the end of the shot you can see the arm rotate a bit just before she jumps and check out how the shadow actually follows the arm like if it was part of 
[04:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=259) the texture now if the shadow was 3d you would expect it to be staying the same place like this not move as if part of the arm in fact you can even see a shadow pop in and out of existence on 
[04:31](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=271) the shirt right here and still the arm shadow isn't affected so i'm almost 100 sure this is projected and it's hard to see because it's so well done but if you really look for it you're going to see 
[04:42](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=282) some small details that you that were clearly painted over to add some higher details here and there all right so now that we know what we're 
[04:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=292) trying to achieve how about we do fun little projects just to get warmed up i'm going to call it um our arcane style default cue and i'm going to use it to demonstrate a couple of camera 
[05:01](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=301) projections tricks so i went ahead and created a simple cube with a couple of bevels and subdivisions to break up the shape i've also imported an image with these gears 
[05:09](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=309) i found them on the art station were made by our texture artists who worked on the show and we're going to use them as reference to paint the cube in the same style i'm using a square resolution 
[05:18](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=318) for my camera of 4096 and i also changed my color management settings from filmic to standard just to make sure that whatever i project or render is going to look the 
[05:28](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=328) same on screen something i always do when i do stylized work so i'm going to do a viewport render save this as cube render and i'm going 
[05:37](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=337) to bring this in photoshop to do a quick paint over so i'm going to speed things up a bit here because there's a lot of things we want to cover but let me walk you through 
[05:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=345) my thought process while i'm painting here i'm using the lasso tool so i'm only painting on one face at once and what i'm trying is just to create some slight variation between each face so 
[05:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=354) they look a bit more 3d i try to always start with bigger shapes at first and then slowly add in the smaller details as you can see i'm also picking up with the 
[06:05](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=365) color picker colors from the gears and i'm not just using brown colors but also green blue hues to give it a bit of variation next you're going to see i'm going to 
[06:13](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=373) add some highlights on the edges and it's something they do on every prop and every character in arcane is really part of the style and i'm not just gonna add them on the edges but also on the 
[06:23](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=383) surface itself and notice how the angle of the scratches is different on every side and i'm doing this on purpose to give it more treatiness even without lighting here 
[06:33](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=393) i'm adding some darker scratches as well and you're gonna notice i'm not just using darker colors but also lighter colors just to highlight the side of and give those cavities a bit more volume so 
[06:43](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=403) i'm using photoshop here because um well i'm a full-time illustrator and this is the tool i like to use most for painting but you don't have to use photoshop you can use any painting app that you like i 
[06:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=414) know many artists we use clip studio paint so anyway here i'm sort of roughing up the edges a bit so they're not so perfect and arcane is a gritty 
[07:04](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=424) world and i kind of want to give this impression this cube has been dropped on the floor a few times or bumped over and i want to say don't get discouraged 
[07:12](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=432) if this is difficult for you to make this cube this is perfectly normal and that's why i chose a simple object to start with you want to fail faster you want to try different things in a row 
[07:22](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=442) it's okay if it's not perfect but you're going to improve more rapidly it's going to be more fun overall okay and here you're going to see i'm 
[07:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=449) going to start painting something simple on the ground um just so that it's not a flat color and i'm using a darker color on the left 
[07:39](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=459) to give the impression it's casting shadow and notice how i'm using a slightly darker color very close to the to the cube it's sort of um faking occlusion i guess but in a more 
[07:50](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=470) painterly way and here i'm doing a quick jump back in blender just to have some reference for lighting so what i'm doing is i'm creating a plane and i'm in setting another face here which i'm 
[07:59](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=479) deleting so that i have this larger plane with hole in it and it's going to cast a sort of light in the center and i want to use this as reference to add a bit of lighting uh to our camera 
[08:13](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=493) projection so i'm not quite sure what i'm looking for i'm just moving it around trying to find some interesting angle for shadows and how it falls on the cube 
[08:21](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=501) and i'm pretty happy with this so i'm going to do a viewport render i'm gonna save this and bring this back in photoshop okay so back in photoshop and i just 
[08:34](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=514) copied and pasted the lighting on top and and i encourage you to play with blending modes here i'm using it in color dodge and playing with the levels 
[08:43](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=523) of my render to get a nice lighting effect and i'm copying this light again over my cube which is on a different layer and again playing with the levels to find 
[08:53](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=533) something i find interesting now i'm also going to want to paint some orange on the side of this lighted section here and i don't know if you remember the 
[09:03](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=543) reference with powder and the chest but this is what i'm trying to emulate i'm using an orange color and a new layer i'm just painting it on the side here to give 
[09:13](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=553) the light some bleeding effect um so it looks a bit more interesting and finally i'm just going to paint out 
[09:22](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=562) those gears which i don't really need anymore and i'm going to save this so we can start projecting it back onto our cube and floor in the 3d scene okay so back in blender and i'm mostly done with 
[09:33](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=573) photoshop so i'm going to bring the speed back to normal speed and blender so you can better follow so here still i'm looking at the cube and floor from a camera i'm going to 
[09:42](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=582) select both at once then press u and project from view so what it did is it created some uv mapping for us as if projected from the camera as you can see here in the uv 
[09:53](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=593) editor and now i'm going to go in the material properties i'm going to switch the principal bsdf for an emission shader 
[10:03](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=603) and then i'm going to click on this little yellow dot pick image texture and open the image we exported from photoshop now we need to apply the material on our 
[10:12](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=612) plane as well and as you can see it's going to look a bit weird at first and whenever things look weird like this after camera projections it's usually because there's 
[10:21](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=621) not enough subdivision and as you can see i'm gonna add a couple more uh four or five i'm gonna press u again then project from view and it's gonna fix everything it's going to look just like 
[10:32](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=632) we did like the painting we did in photoshop now if i look around in the scene you're going to notice that things don't look as good when i'm not looking from the 
[10:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=640) camera and it's because we're using the same texture for the floor and the cube and we need to do an alternate texture just for the floor that doesn't have the cube in it so here i'm just going to um 
[10:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=651) copy the texture we did and sort of erase the cube as best i can and paint the lighting behind it that way we can use that texture to apply on the material for our 
[11:02](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=662) floor okay and now this is exported i'm back in blender back at normal speed and i'm going to create 
[11:11](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=671) actually rename this material to q and i'm going to create a copy for the floor and name this one floor and i'm going to change the image texture for the one we just made so as 
[11:21](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=681) you can see it mostly fixed the problem we had but we still have a couple of problems notice the weird lighted bits on each of those 
[11:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=689) edges here um this is because the camera is projecting here and stops at the edge here let me jump back in camera view and show you actually in the uv editor you can see it pretty well and this matches 
[11:41](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=701) what we see from the camera and what we need is for the texture not to repeat when it goes outside the uv square so i'm going to go in the shader editor and i'm going to change this repeat 
[11:53](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=713) option to x10 and it works because i have a brown color and my world color is brown too so it's just extending that brown color on all sides and it works so i'm pretty happy with this 
[12:06](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=726) but let's say we have a camera move and we at some point are going to see behind the cube and so a camera moves and then boom you see 
[12:17](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=737) here how this looks weird um this is because i'm going to select the faces here and you're going to see the reason they look weird is because they're picking their color information from the 
[12:28](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=748) front of the cube that we painted and this is not what we want what we want is for this to be textured differently there's a few ways to fix this and one of them is to do a second 
[12:37](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=757) camera projection so let me just move this gear here i'm going to rename my camera to camera projection one and then i'm going to duplicate it with shift d and call it projection two 
[12:49](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=769) um so i'm gonna jump in my camera and go in my scene settings and change the camera to the second camera that we just made and that way if i move it first you have 
[13:01](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=781) to go and view uh lock camera to view and then i can move it on the side here we're going to be able to do a second camera projection and fix this bit here so what i'm going to do 
[13:13](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=793) is select my cube and we don't want to overwrite the original uv mapping done from the first camera projection so we're going to go in the object data properties under uv 
[13:24](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=804) maps and we're going to create a new one with the plus button i'm going to rename it uv map 2. so you see if i select my faces go back to the first uv map gonna have my original and if i click on 
[13:35](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=815) the second one then select my faces and press u project from view if i switch between the two you can see i now have two different uv sets and by default images are going to use 
[13:48](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=828) the first one the one called uv map but i can use this vector input here to plug in a different uv set if i want to and that's what we're going to do so i'm going to go in the 
[14:01](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=841) i'm actually going to do a render so view viewport render image i'm going to bring this back in photoshop and i'm going to paint over the bits that we don't like 
[14:10](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=850) okay so back in photoshop creating a new layer i'm selecting this face and filling it up with a flat sort of gradient color and then i'm using some larger brushes at first to break up the 
[14:20](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=860) shape and then i'm using the lasso tool to do a nice sharp selection paint a bit on it and use a smaller brush to give it a bit of volume now to export all we need is the new layer we painted so i'm 
[14:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=870) going to hide the one underneath i'm going to save this as a transparent jpg and bring it back in blender okay so now i'm back in blender and what we want to do first is create a new 
[14:41](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=881) image texture so i'm going to do shift a type in image texture i'm going to click on open and pick the new transparent jpg that we made in photoshop and as i explained earlier we need a different uv 
[14:53](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=893) set for this image i'm going to type in uv map i'm going to pick the uv map 2 that we made with the second camera and i'm going to connect the uv output to the vector so that we're using this uv 
[15:04](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=904) map for this image and if i switch to the uv editor you're going to see i really need to use this second uv map otherwise the new thing we painted it's just not going to be aligned properly 
[15:13](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=913) with the cube so let's go back to the shader editor and now we need to mix this new image on top of the other one so i'm going to need a 
[15:22](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=922) mix rgb and i'm going to use the first one as color one the second one as color two and then we're gonna use the alpha uh to 
[15:32](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=932) tell it where this new color is gonna appear and if i plug this into the emission you're gonna see the result uh actually if i switch back you're to see the difference now this doesn't work and 
[15:42](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=942) now with the new projection we have fixed this face and the back and here's how it looks i encourage you to try this simple cube it's a good exercise and you can add a bit of sharpen here i'd use 
[15:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=952) the unsharp mask and after effects helps you see the texture is a tiny bit better okay so i'm going to go back in the scene because there's one last thing i want to show you it's a really awesome 
[16:02](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=962) technique i just discovered a couple months back and i've been using it non-stop ever since so you remember when i told you that doing the second camera projection was 
[16:12](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=972) one way to add the texture in the back so let me show you the other way i'm gonna go in edit mode i'm gonna select these edges on the side here to unwrap the cube so i'm just ctrl shift clicking 
[16:24](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=984) to select whole lines and i'm trying to sort of unfold this cube so once they are all selected i'm gonna mark them as seams so i'm gonna press u 
[16:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=996) and mark c now go to your object data properties create a new uv set i'm going to call it unwrapped and select all your faces press u and then unwrap i'm going to go to the uv 
[16:48](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1008) editor and if everything worked correctly you should see this cross shape here i'm going to just resize it place it in the center like this 
[16:56](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1016) and now that you've got this check this out let's go to the shader editor and i'm going to create a new image and uh i'm gonna click new and then make sure that alpha is enabled click on the 
[17:08](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1028) color and bring down the alpha value to zero uh rename it to i don't know bake texture and then you're gonna change the 
[17:17](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1037) resolution to 4096. and the reason we're calling this big texture is because we're gonna bake all this information onto our unwrapped cube 
[17:26](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1046) so for this i'm gonna need a new camera i'm gonna call it um bake camera then i'm going to go to my scene properties and i'm going to change the active 
[17:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1056) camera to this new camera and move it um this way then i'm going to hide a couple things the floor go to my render 
[17:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1065) settings change film to transparent and just frame this nicely like this and now i'm ready so i'm gonna go in my texture paint mode 
[17:59](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1079) go to tool make sure your baked texture is selected and then go all the way down to a weirdly hidden section called options external and 
[18:09](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1089) change this resolution to 4096 just like our camera output settings and this is going to take a render and bring it into the image editor of your choice you can change this into your preference 
[18:20](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1100) settings into file paths i have photoshop here and click quick edit so it's automatically bringing this image in photoshop and i'm just going to save it not do anything 
[18:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1109) else then you want to go back in blender and click the button apply and that's all you need to do now to see the result you'll need to plug the right uv set so i'm going to duplicate this 
[18:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1120) one change it to unwrapped and plug it into the vector like we did before and if i plug the result here you're gonna see that we baked the result of our render onto the unwrapped 
[18:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1132) cube um so you see this part here didn't uh quite render that's okay we can just plug back the original projection do quick edit 
[19:05](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1145) do a quick save in photoshop go back click apply and then do this on this other side as well quick edit save go back in blender apply and then if you plug in the result 
[19:18](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1158) of this image you can see we baked all that information onto our unwrapped cube now i don't know if you understand the implications of this but this literally means we can now bake stuff in eevee 
[19:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1169) which i always thought was impossible we're going to see later in this tutorial how to make the best use of this technique to build textures for a character but first let me just show you 
[19:39](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1179) how to fix this common problem you might encounter which is those thin black lines here i'm gonna save our image as a jpg and then we're gonna open it in 
[19:48](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1188) photoshop and you're gonna see you're gonna have a single layer over transparency i'm gonna duplicate it and put it on there apply a gaussian 
[19:58](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1198) blur on it and i'm gonna duplicate it a bunch of times and that way it can create a very quick and dirty bleed effect but it's to fix those black lines if you save this 
[20:07](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1207) and then go back in blender so here i'm going to use the shortcut alt r to refresh and as you can see the thin line is gone and i can just start like painting over i'm in paint mode so 
[20:20](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1220) i can just use my brush and fix whatever i need this is like a standard texture on an unwrapped model but because we painted it at first from the 
[20:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1229) camera it's got this nice uh 2d feel to it so i mean you can go ahead and fix anything you find that's wrong like this darker line here you can fill up the 
[20:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1240) darker sections that had just no projections in the beginning um i mean blender is not bad to uh as a painting program i just find that 
[20:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1252) it's sometimes lacking some of the textured brush that i really like in photoshop but to do this kind of fix it's really nice to just be able to rotate around your model and fix it so i 
[21:03](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1263) like to switch between the two and you can really use the two at any time like for instance i could um go in quick edit and open photoshop whoops okay so this 
[21:14](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1274) is too far off this is because i was not inside my camera so just go back in the camera that's why we need to make sure that the um resolution of our scene matches the screen grab and we're inside 
[21:24](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1284) the camera otherwise you might get some weird framing like this so i'm gonna go in quick edit and now it's going to be fraying properly and i can just paint whatever i'm going to do a new layer and 
[21:35](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1295) this is important i'm going to paint some stuff whatever i want and and then 
[21:42](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1302) this is the key point is i'm going to delete the underlying layer so i'm just going to keep this let's save this and when i go back in blender and apply 
[21:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1311) it's just going to apply the new changes i did so it's not going to screw up anything it's just going to add this a painted layer on top then i can continue painting in blender it's just super 
[22:01](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1321) quick and intuitive and i cannot believe this option is so well hidden and i just learned about this now alright so let's say you're ready for the next step and want to do your own character what you 
[22:11](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1331) see here is dust she's one of the main characters in the board game title blades and i did a short animation with her for the opening video for the kickstarter 
[22:21](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1341) which you see here so this is the scene with just the character model and i want to focus on shading and texturing in this tutorial 
[22:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1349) so i'm not going to spend much time on modeling i can show you the topology here to be honest i i wouldn't say my sculpt is as good as any of the characters that you see on the show 
[22:39](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1359) arcane i did my best with the limited time i had and you can look it up on art station but their sculpts are 
[22:48](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1368) really really good check out the clothes all the nicely sculpted wrinkles this is how they get all the nice rim lights on their characters so back to my own 
[22:59](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1379) blender scene i'm gonna switch in rendered view to show you the textures now this is rendered in real time in blender eevee and you can see it lags a little mostly because i have the hair 
[23:08](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1388) enabled there's like thousands of them if i turn it off it's going to be much more responsive and all my lights are dynamic so i can move around the rim light and they're 
[23:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1396) all casting shadows and whatnot this was done using the lightning boy shader which is really well suited to do this kind of stylized work inside blender and i'm going to show you how that works now 
[23:25](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1405) before we do any complex shading of course we're going to need a base texture for a character and this is a step that can be really daunting so i'm going to give you a tip 
[23:35](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1415) remember earlier when we baked the result of our two camera projections onto our cube right i told you this is amazing because you normally cannot bake in eevee well we can use this to our 
[23:46](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1426) advantage uh we can create a basic shader and then bake that result onto a texture and then start from there to add more details and use our cool 
[23:58](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1438) brushes but at least we'll add a base and this project is the first time i used this technique and honestly it worked really well so let me walk you through my process first step is base 
[24:07](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1447) colors so you don't need any shader you can delete that and just create an image texture i'm gonna make it pretty big here because i want this to encompass the whole body so i'm gonna make it 8k 
[24:18](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1458) and we call this dust body texture i'm just going to make this a light gray and plug it into the material output and just to make sure this is clear you do need a uv mapping done on your character 
[24:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1470) for this to work so make sure to unwrap your model i'm not going to show you how to do that here but it needs to be all lined up onto the same uv square here for this to work so here to start adding 
[24:41](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1481) some different colors onto our model we're going to go in an edit mode and start doing some selections i'm going to use the shortcut l for select linked it's going to select everything that's 
[24:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1491) connected together so now i've selected the pens here and if i go to texture paint press n to open the tool settings and just make sure i'm painting in the 
[25:00](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1500) right texture and choose a color now you also need the paint bucket i'm going to press t and click on fill here and then i'm going to pick the teal 
[25:10](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1510) color from my image reference if you don't have any image reference then you can just choose the color you want and i'm going to click on the pens now 
[25:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1519) at this point if everything turns the same color it's because you forgot to activate the paint mask option like i did so you need to go at the top 
[25:28](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1528) right next to the texture paint mode and click on this little button called paint mask and that way if you use the fill um tool again it's only going to be filling that 
[25:37](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1537) color inside your selection and here i'm going to speed things up because it's going to be a bit repetitive but if you do that with every part of your character that has a different color 
[25:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1545) eventually you're going to end up with something that looks like this just something nice and flat next step is going to be adding a bit of shading occlusion specular stuff like that that 
[25:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1554) we can bake on top of our flat colors to serve as a better base for the texture and to do this i'm going to start using the lightning boy shader and i know not every one of you is using it 
[26:05](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1565) so just to make sure you're not confused about what i'm doing let me just explain what it is if you've watched the previous hair tutorial you'll be familiar with the setup of having bsdfs 
[26:14](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1574) followed by shader to rgb nodes and color ramps and all of that stacked on top of each other using rgb mix nodes with the lightning boy shader you have a built-in layer stack 
[26:27](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1587) and if you want to create more layers you have a new menu where you can create those pre-built custom nodes that you can plug in as new layers and if you want to change the setting of these 
[26:38](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1598) nodes you just press h on any node and it's going to open up some options which kind of replace the color ramp but are a bit more intuitive okay so here i'm going to start using the lighting boy 
[26:47](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1607) shader and you do need to have it enabled under your preferences add-ons to see the same options as i'm as i'm seeing and my goal here is not to force you to buy this shader if you want to 
[26:57](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1617) encourage us it's super appreciated but please stick around if you don't because i'm going to do my best to really teach you the logic of what i'm doing so that if 
[27:06](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1626) you want to recreate this with basic nodes uh you are able to so here i created the basic landing by shooter with just one layer which is my flat colors and here i'm connecting the 
[27:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1636) key light in the second layer to add shadows on top of it by default the key light node wants to add illumination but here i want shadows so i'm inverting it and using a darker color and just 
[27:27](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1647) playing with the settings a bit for a base texture like this i don't want the shadows to be too strong so that's why i'm using an opacity of about 0.5 and here i'm going to move my light the 
[27:37](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1657) one that's connected to the key light node called character i'm going to rotate it forward so i don't have as many shadows and here i'm just continuing to add more layers i'm going 
[27:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1665) to do a specular on layer 3 and remember we're not doing the shader for the character we're only creating a base texture and using the shader to help us make that first base texture 
[27:57](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1677) okay so here i don't want to use a pure white color for your specular and just dropping the opacity is not going to cut it so i'm going to create a rgb curve i'm going to connect the original flat 
[28:08](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1688) colors into it and use that as the color for the specular and that way you should get much nicer results when you play with these shader settings 
[28:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1699) it's important to remember that you're going to eventually project all these details from a specific camera onto your texture so make sure to jump in your camera once in a while and adjust the 
[28:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1710) lights from there it's not as important for diffuse but specular is going to change based on the angle you're looking at it so make sure to adjust it based on that camera and this is where the offset 
[28:39](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1719) setting on the specular can be really useful because you can sort of move the specular around exactly where you need it and one last thing that can help to really get those nice details in 
[28:49](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1729) there before you bake this is ambient occlusion so here i'm creating a screen space ambient occlusion and putting it in layer four and again here i'm playing with the settings softness range max 
[29:00](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1740) distance just to you know tweak this to your liking and before i show you how to bake this remember you don't have to use the same material for every piece on your character like here i was finding 
[29:12](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1752) that arm was a bit too shiny so i just made a duplicate material made it unique and of course you can always rename your materials if you want to keep track of 
[29:21](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1761) what is what and then once you have done that you can go into edit mode and select your pieces assign them the new material and you can change 
[29:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1770) the material um so like here i'm gonna tweak the specular a bit to make it softer a bit bigger a bit more transparent so it looks like actual skin so let's say i'm happy with this how do 
[29:43](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1783) i do to bake it well i do the same as i did with the cube first you need an image texture onto which to put the baked information so remember you need to click alpha and 
[29:52](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1792) drop it down to zero so it's completely transparent what's going to create some issues this time is we have a specular in there and specular is going to move around as we project from different 
[30:02](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1802) directions around our model and what's going to happen is we're going to have speculars all over the place so here's what i'm going to do i'm going to create a color note this is a lining boy 
[30:12](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1812) specific node and i'm going to plug the color into the color and alpha into alpha mask so basically this turns this image into a new layer i can use 
[30:24](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1824) and i'm going to create a fifth layer and connect that layer into it so basically what we did is we created the transparent image and we added it as a new layer on top of everything and 
[30:35](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1835) because it's transparent it shouldn't affect anything at this point everything should look exactly the same now let's see what happens when we bake this 
[30:43](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1843) i'm going to go in texture paint and you want to make sure to not leave this at fill it really needs to be in draw mode and then i'm going to unclick the paint 
[30:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1854) mask option which we don't need anymore and i'm going to click on n to open up the tool settings make sure to click on your baked texture not your 
[31:06](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1866) flat colors and then i'm going to go down at the very bottom the uh option edit under external 
[31:15](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1875) and then i'm going to change this to 4k because 8000 is probably going to crash blender and i'm going to click on quick edit and just like with our cube it's going 
[31:25](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1885) to bring a render into photoshop we're just going to save it go back in blender and i'm gonna press apply and uh wait a bit for it to um project it back 
[31:39](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1899) okay and now a little challenge can you guess what's uh different when i move my camera you see how the specular is not moving anymore 
[31:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1911) and the reason is we're not looking at the specular we're looking at the baked texture and wherever this is black this is where 
[32:00](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1920) nothing has been projected yet but since we're using this as a layer on top of everything else where there's no texture you're just seeing the original shader underneath 
[32:09](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1929) so this is pretty neat and all that's left to do is to project from all the other directions okay so i'm gonna skip ahead a bit and here you can see the final bake texture 
[32:20](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1940) once i'm done reprojecting from all directions you can see it's not perfect especially when different pieces of geometry intersect you really need to come in and fix those 
[32:30](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1950) sometimes it's easier to do in photoshop you can also do it in blender and you can see there's also a couple of assets that i decided to hide for this projection such as the swords the 
[32:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1960) hanging capes the shield too these were all projected separately onto their own texture so the process is completely the same here you can see i did some kind of basic lighting i just reprojected that 
[32:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1971) onto it and now i'm refining the details in photoshop just to add a bit more scratches and definition for the head same process but i wanted to have a lot of resolution because i knew i had this 
[33:03](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1983) close-up shot at the end so i used the 8k textures just for the head first i just set up a basic lighting like for the other assets then i projected this from the front and did a pretty good 
[33:14](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=1994) pass just in photoshop and here you can see i drew the eyes and the eyelashes and the pursing uh but just because it was too weird not having them in there to evaluate if the texture was working 
[33:24](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2004) correctly but they're not part of the projection and as you can see after i first projected it there was still a bunch of stuff that didn't work under the chin so i fixed all that and a lot 
[33:34](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2014) of the work was just adding details that i didn't see from the front and here's an example of something that i find super useful in photoshop i wanted to paint some tattoos on her neck and i 
[33:44](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2024) just didn't like the result i was getting blender it was a bit too soft so what i did is i basically just sketched them in in blender and then i read the projection from photoshop and i used 
[33:54](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2034) vector curves to really draw them in uh super sharp and then i painted inside the selection using like soft gradients and here you can see the result when it's projected back 
[34:06](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2046) now as far as lighting goes as we took note in our observations we don't necessarily want to shade the character the same depending on the shot sometimes you might want a rim light but other 
[34:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2056) times maybe you just want to use the base texture with some color adjustment so let's look at how to do that with the lining boy shader so let's start with a shader with just our base color as layer 
[34:26](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2066) one so if you just want to do a color adjustment usually rgb curves will give you the most control the quickest way to add this adjustment is to press tab on the lining boy shader node that will 
[34:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2076) give you access to rgb curves that applies on top of all your layers or you can create a rgb curves node from the default blender nodes and then you can place it after your image texture so 
[34:45](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2085) what's cool with the rgb curves is you can not only play with the contrast but if you go in the individual color channels you can also affect the general color balance now 
[34:55](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2095) this is going to affect the whole texture so let's say you want to adjust something but just at the bottom of your character or just the shoulder so how do you do that well with the lighting boy 
[35:04](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2104) shader you can create gradients and it makes this very easy for this purpose so here i'm adding a spherical gradient in layer two and by default it's going to be just a pure color but then if i do a 
[35:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2116) rgb curves and modify my original image texture with it you can see this is going to limit where the color correction appears and this is 
[35:25](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2125) very similar when you think about it to just compositing in real time this is something you would do um in nuke or in after effects but here i'm just doing it in eevee and it's so 
[35:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2136) much fun because i don't have to worry about puzz mats and stuff like that i'm just literally editing the material of my object so what else can you do well you can create a key light if you want 
[35:47](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2147) to add shadows now if you just use a darker shadow on top of your texture you're going to realize that it starts to look a bit 3d so for this what i like to do is to create a custom shadow 
[35:58](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2158) texture in photoshop and what i'm looking for when i paint this shadow is i'm trying to pick not the darkest color but one of the darker color 
[36:07](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2167) and i'm painting using the blend mode called darken and what darken does is it's only going to affect the colors that are lighter than the color i'm painting with 
[36:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2179) and here's why this is important because we already have some kind of shadows painted in our texture we don't need to make these sections even darker what we need is for everything else to be as 
[36:31](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2191) dark as the shadow that is painted in the texture so let me show you how that how that looks in the scene so here i've connected the new image into the color of the key light and as 
[36:40](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2200) you can see instead of just darkening everything the shadows blend a bit more seamlessly with the original texture and here's a shot from arcane that shows 
[36:51](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2211) weld what i mean now look at this section on the cheeks here the darker red section uh this is coming from a light because you see it fade away as he raises his 
[37:00](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2220) head and if you skip a little later there's a place where there's barely any lighting on the face and you can see that the color that they chose is really exactly the same one as the darkest one 
[37:09](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2229) under the eyes here and that's why it blends so seamlessly now what if you want to add a very bright section of light on your character not just a darker shadow well it's going to be even 
[37:19](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2239) simpler you can just use a key light note if you want and uh choose a super bright color i mean here again you could create an alternate texture if you want 
[37:29](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2249) and make it brighter and connect it into the color but it really depends on what's your intention now let's talk about uh specular you can see here that this two-point 
[37:38](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2258) highlight is painted and i exported it as a separate jpg that way i can use it as a standalone layer and i can even plug in the texture coordinate and mapping node to translate it if i need 
[37:50](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2270) to move it okay so time is running out and i want to show you one last thing you can do with camera mapping here's an example where despite all my best efforts 
[38:00](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2280) applying the technique i just showed you i just couldn't get the lighting i was looking for but here's the beauty about reprojecting details is that you can always just create a new layer on top of 
[38:10](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2290) everything your lighting your shadows as we saw you only need to create a new transparent image use a color node to connect it as a layer on top one thing i didn't mention 
[38:20](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2300) so far is if you have bloom enabled you should turn it off before doing the projection and once that done you can just go in texture paint mode make sure to select 
[38:27](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2307) the right texture and find the quick edit button at the very bottom this is really no different than when we were baking or shader onto our texture in fact it's almost easier now because we 
[38:37](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2317) already have an animated camera so we can just project from there just don't forget to turn off the underlying render when you're done and so that way you only project the new 
[38:47](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2327) changes and it can work even if the character is moving a lot you just need to animate the opacity of that layer if necessary 
[38:56](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2336) and if you do it carefully and choose your frames right it's going to be pretty seamless and you know what this whole establishing shot is made of multiple 
[39:05](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2345) projections that i animate the opacity of one after the other as i get closer to that mountain so as you can see there's really no limits to what you can do with this kind of projections and i 
[39:16](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2356) hope it gives you ideas for your own projects all right so that's it for this tutorial i hope you learned a few things and thought that was interesting um if you do try to make the arcane style 
[39:26](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2366) default cube or even your own character please share your work with us on twitter we always love to see that if titleblade seems like something that might interest you i encourage you to 
[39:36](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2376) visit the kickstarter page it's currently in the last few days the campaign but i think you can still pledge if you miss it and of course if you like 
[39:42](https://youtu.be/gG7ZoP3fd1w?si=f_gzD4_-lmIuY4CR&t=2382) the laneway shader you can also check it out on our gumball page so thanks again for watching and i'll see you next time 