---
URL: https://www.youtube.com/watch?v=uO_B_aPlzho
thumbnail: https://i.ytimg.com/vi/uO_B_aPlzho/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:57:33
published: 2022-04-30T10:00:13
duration: 791
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "13m 11s"]
# Hacking The Graphics Of Melee
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155743.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=uO_B_aPlzho
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/uO_B_aPlzho" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: As a long time fan of Super Smash Brothers Melee, hacking the game's graphics has been on my to do list for a few years. In this video I analyze the game's graphics and describe the process of creating custom skins for Melee fighters. 

Support me on Patreon!
https://www.patreon.com/acerola_t

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Join My Discord Server! https://discord.gg/FxGQvbfm6Y

Skins:
https://ssbmtextures.com/characters/falco/itachi-falco/
https://ssbmtextures.com/characters/sheik/enron-sheik/
https://ssbmtextures.com/characters/captain-falcon/acerola-captain-falcon/

Resources:
https://youtu.be/qAIsq7M9paI
https://youtu.be/_RHDe3mUqB8

Music:
During The Test - Persona 3 OST
Afternoon Break - Persona 3 OST
Bad Bully - Kizumonogatari OST
New Game - WORLD OF HORROR OST
Iwatodai Dorm - Persona 3 OST
Sandgem Town (Day) - Pokemon Diamond OST


Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=uO_B_aPlzho&t=0) hello everyone super smash brothers melee is a game about action conflict overcoming your weaknesses and intense competition above all else super smash brothers melee is a game about family 
[00:14](https://www.youtube.com/watch?v=uO_B_aPlzho&t=14) what do i mean by that i don't know i just needed an intro for the video coming out a little over two decades ago melee's modding community has been 
[00:26](https://www.youtube.com/watch?v=uO_B_aPlzho&t=26) thriving for many years and has done an amazing job streamlining the modding process i initially thought it would be a major hassle to mod the textures of the game but due to the creation of a 
[00:38](https://www.youtube.com/watch?v=uO_B_aPlzho&t=38) super useful tool known as the dat texture wizard it's actually incredibly easy i got started with a very simple texture modification of falco i opened up his feather textures in photoshop and 
[00:51](https://www.youtube.com/watch?v=uO_B_aPlzho&t=51) hue shifted them to red to make sure i was doing it right with the texture wizard it's as simple as opening your legally obtained melee iso navigating to the falco costume you want to change and 
[01:03](https://www.youtube.com/watch?v=uO_B_aPlzho&t=63) then replacing the corresponding textures if we open the game and play with the corresponding falco costume we see that our man's is red now you may be asking yourself acerola why are there 
[01:16](https://www.youtube.com/watch?v=uO_B_aPlzho&t=76) weird blue streaks all over falco even though you changed the color of the texture to red and that's a great question the answer lies in the lighting model that melee uses melee uses what's 
[01:28](https://www.youtube.com/watch?v=uO_B_aPlzho&t=88) known as the blin phong lighting model which is very commonly used and also extremely basic it is composed of diffused lighting and specular highlights but melee gets a bit fancier 
[01:40](https://www.youtube.com/watch?v=uO_B_aPlzho&t=100) and has ambient lighting involved as well diffused light is obtained with the lambertian diffuse model which is the dot product of the surface normal in the direction of the light the resulting 
[01:52](https://www.youtube.com/watch?v=uO_B_aPlzho&t=112) value is multiplied with the color of the texture and we get very simple lighting the reason this works is because both of the vectors are normalized meaning their parts sum to 
[02:02](https://www.youtube.com/watch?v=uO_B_aPlzho&t=122) one the dot product of two normalized vectors is equal to the cosine of the angle between the two vectors which means that normals that point towards the light will be close to one and 
[02:14](https://www.youtube.com/watch?v=uO_B_aPlzho&t=134) normals that point away from the light will be close to or equal to zero this calculation is how we are able to see the textures of falco one thing to note is that melee limits the range of the 
[02:26](https://www.youtube.com/watch?v=uO_B_aPlzho&t=146) diffuse so that the characters are much more visible instead of zero to one it's probably more like 0.9 to 1. specular highlights are a bit more complicated as this would be the light that directly 
[02:39](https://www.youtube.com/watch?v=uO_B_aPlzho&t=159) reflects into our eyeballs in the real world the blinn fong model approximates this by calculating a vector that is halfway between the direction of the camera and the direction of the light 
[02:50](https://www.youtube.com/watch?v=uO_B_aPlzho&t=170) then we take the dot product in the same way as lamborghini diffuse the resulting value is then exponentially increased to control the intensity of the specular highlight and then it's added to the 
[03:02](https://www.youtube.com/watch?v=uO_B_aPlzho&t=182) color of the model instead of multiplied like the diffuse calculation melee uses a pretty low exponent which is why the highlights on falco are so large lastly melee gets fancy with the ambient 
[03:15](https://www.youtube.com/watch?v=uO_B_aPlzho&t=195) lighting and has a constant color associated with each stage this color is multiplied with the final output to filter it and make the model fit in with the stage lighting a bit more the 
[03:26](https://www.youtube.com/watch?v=uO_B_aPlzho&t=206) ambient light color of final destination is a dark pink coincidentally the dat texture wizard makes these material properties available to us the diffusion value 
[03:37](https://www.youtube.com/watch?v=uO_B_aPlzho&t=217) controls the maximum amount of light that is reflected off the model the ambience value controls how much ambient light is applied to the model the highlights color is the color of the 
[03:48](https://www.youtube.com/watch?v=uO_B_aPlzho&t=228) specular highlight in this case for falco it's blue which matches our observations and lastly there's a shininess value that controls how intense our specular highlights are if 
[03:59](https://www.youtube.com/watch?v=uO_B_aPlzho&t=239) you look out for the specular highlights you'll begin to notice just how shiny all the melee characters are especially captain falcon which in my opinion is a strange style choice anyways the red 
[04:12](https://www.youtube.com/watch?v=uO_B_aPlzho&t=252) falco skin is pretty boring so i went ahead and painted a sharingan over falco's eye textures which i think is super cool so cool in fact that i went ahead and changed falco's outfit to 
[04:24](https://www.youtube.com/watch?v=uO_B_aPlzho&t=264) match hitachi's color scheme the last change i made was removing the specular highlights which i think makes him look way better especially in motion now you may be asking yourself acerola 
[04:38](https://www.youtube.com/watch?v=uO_B_aPlzho&t=278) why didn't you put the really cool clouds on falco that are on the ikotsky robes and that's a great question the textures of melee characters are horribly warped and stretched even small 
[04:50](https://www.youtube.com/watch?v=uO_B_aPlzho&t=290) decals will be ruined as demonstrated here this problem isn't solvable with dat texture wizard instead we need to be able to change the actual model data in a program like blender extracting the 
[05:03](https://www.youtube.com/watch?v=uO_B_aPlzho&t=303) model data from melee requires a different tool called hsd raw i'm not going to go into specifics since biz already has a great in-depth tutorial on the process but the general workflow is 
[05:16](https://www.youtube.com/watch?v=uO_B_aPlzho&t=316) that we extract the dae and the smd data with hsd raw the dae contains all of the model data except for the rig and the smd file doesn't stand for suck my dick it stands for studio model data which 
[05:31](https://www.youtube.com/watch?v=uO_B_aPlzho&t=331) contains the correct rig data used for animating the model both of these files are imported into blender then we separate the dae from its useless skeleton and bind it to the smd rig as 
[05:44](https://www.youtube.com/watch?v=uO_B_aPlzho&t=344) you can see i have successfully imported sheik and the rig works great unfortunately the uvs on her chest got garbled in the process so we need to fix that uv coordinates are used to map 
[05:57](https://www.youtube.com/watch?v=uO_B_aPlzho&t=357) vertices of a model to a texture if i mirror the coordinates of her chest then the texture fits properly you may now be asking yourself acerola what the is that and that's a great 
[06:10](https://www.youtube.com/watch?v=uO_B_aPlzho&t=370) question it's a low poly version of chic every melee character has a low poly version of its model and is what the game uses for character shadows this is an optimization technique if you watched 
[06:22](https://www.youtube.com/watch?v=uO_B_aPlzho&t=382) my video on the graphics of pokemon legends arceus you would know that shadows are calculated by rendering the scene from every light's point of view this is very costly and the cost can be 
[06:34](https://www.youtube.com/watch?v=uO_B_aPlzho&t=394) reduced by using less geometry for those renders but we don't really care about the low poly model so we can just hide it now two weeks ago i attended genesis 8 which is the biggest smash tournament 
[06:47](https://www.youtube.com/watch?v=uO_B_aPlzho&t=407) of the year i got to meet tons of cool people including ludwig and i got to watch j mook's legendary run in real life over here oh oh oh that's a big grab that's one oh oh 
[07:13](https://www.youtube.com/watch?v=uO_B_aPlzho&t=433) i got super drunk at the after party and i was too nervous to say hi to atriak who tried to sponsor jay mook and get him to wear his enron hat merch but it unfortunately didn't work out he told 
[07:25](https://www.youtube.com/watch?v=uO_B_aPlzho&t=445) this story on stream and i had the wonderful idea to put an enron hat on chic to get familiar with modifying melee characters i could have pandered to the reddit and made a coffee cow joke 
[07:37](https://www.youtube.com/watch?v=uO_B_aPlzho&t=457) or turned sheik's hands into hot dogs but this seemed a bit more respectful the first thing i did was convert sheik's turban into a baseball cap which sounds problematic next i painted over 
[07:50](https://www.youtube.com/watch?v=uO_B_aPlzho&t=470) the turban texture so it has the same beige color as the real hat and i added the little enron logo it sounds pretty simple but it was still a good amount of work to get it looking decent since i 
[08:01](https://www.youtube.com/watch?v=uO_B_aPlzho&t=481) had to move her bangs around the brim of the hat all the desired modifications to the model have been made so now we have to get it back into melee we use the hsd raw program from earlier to overwrite 
[08:14](https://www.youtube.com/watch?v=uO_B_aPlzho&t=494) the model data and then we import the changed file into the legally obtained melee iso with the dat texture wizard if everything went okay then the game won't crash we now have an enron hat chic in 
[08:26](https://www.youtube.com/watch?v=uO_B_aPlzho&t=506) melee and i think it looks pretty alright now it's never my intention to leech exclusively i like to at least maintain artistic integrity so i started working 
[08:37](https://www.youtube.com/watch?v=uO_B_aPlzho&t=517) on a cool skin for my favorite character to watch captain falcon if you know anything about me you'd know i really like monochromatic or 2-bit color schemes which is heavily reflected in my 
[08:50](https://www.youtube.com/watch?v=uO_B_aPlzho&t=530) ludwig jam game the dating game in three dimensions these color schemes lend themselves well to tune shading and at the moment the gold standard for toon shaded skins in melee are the anna mele 
[09:02](https://www.youtube.com/watch?v=uO_B_aPlzho&t=542) line of skins these skins are characterized by a black outline and flat shading with defined hard shadows to show model detail without real lighting the part i am most interested 
[09:15](https://www.youtube.com/watch?v=uO_B_aPlzho&t=555) in is the black outline so let's start with that i imported captain falcon into blender using the same method as chic if you've watched my videos on gooch shading and ink shaders you might be 
[09:28](https://www.youtube.com/watch?v=uO_B_aPlzho&t=568) thinking that the outline is a shader effect but that is unfortunately not the case since at the moment shader injection for melee is impossible instead it's a much more clever trick 
[09:40](https://www.youtube.com/watch?v=uO_B_aPlzho&t=580) what we're going to do is duplicate the high poly model and join all of the objects together then we're going to add a solidify modifier to it so that captain falcon looks like big yoshi 
[09:53](https://www.youtube.com/watch?v=uO_B_aPlzho&t=593) lastly we invert the faces enable backface culling and change the material color to black and we have a fancy tune outline you may be wondering how this works and it's taking advantage of a 
[10:06](https://www.youtube.com/watch?v=uO_B_aPlzho&t=606) basic feature of all rendering engines in video games the backside of triangles are not rendered to save rendering time we can't see them so there's no reason to keep them since we inverted the faces 
[10:19](https://www.youtube.com/watch?v=uO_B_aPlzho&t=619) of the outline mesh all of the back sides of the triangles now face the camera except for the triangle faces that peek over the edges of the base model which gives us the tune outline 
[10:32](https://www.youtube.com/watch?v=uO_B_aPlzho&t=632) adding this outline causes a bit of a problem that i didn't need to mention with sheik because it didn't matter when you're importing a model back into melee the model needs to have the same number 
[10:43](https://www.youtube.com/watch?v=uO_B_aPlzho&t=643) of joint objects as the original and in this case we have just added one joint object thankfully this is an easy fix we can just join captain falcon's hands together since they use the same texture 
[10:57](https://www.youtube.com/watch?v=uO_B_aPlzho&t=657) and the number of objects matches again with the outline out of the way all that's left to do is texture painting since i don't need to make any changes to the model this is when i learned that 
[11:08](https://www.youtube.com/watch?v=uO_B_aPlzho&t=668) captain falcon was a terrible character to pick for this because my mans has 35 diffused textures that all need to be changed the color scheme i decided to use is one of my favorites which is 
[11:19](https://www.youtube.com/watch?v=uO_B_aPlzho&t=679) black and a sort of sickly off-white color which i used a long time ago on this background i made for a school assignment my first attempt involved going through each texture desaturating 
[11:31](https://www.youtube.com/watch?v=uO_B_aPlzho&t=691) it and then overlaying the off-white color the result wasn't that bad but i wanted a lot more contrast and i wanted the full range of black to the off-white color to be represented my next attempt 
[11:45](https://www.youtube.com/watch?v=uO_B_aPlzho&t=705) involved using a gradient map in photoshop to flatten the colors down and i think this looked much better i had to do a lot of repainting and curve correction on each texture to make sure 
[11:57](https://www.youtube.com/watch?v=uO_B_aPlzho&t=717) necessary detail was included but overall i think it looks much more stylized and interesting i imported the model back into hsd raw removed all the specular highlighting and ambient 
[12:10](https://www.youtube.com/watch?v=uO_B_aPlzho&t=730) lighting values and i was finished after exporting my legally obtained melee iso in the end i'm not super happy with how it looks i heavily underestimated how much the textures get stretched in the 
[12:24](https://www.youtube.com/watch?v=uO_B_aPlzho&t=744) game which makes the model look pretty gross i do think it looks nice when captain falcon is standing still though i think this falcon skin looks sort of like a newspaper cutout which is neat my 
[12:36](https://www.youtube.com/watch?v=uO_B_aPlzho&t=756) goal was to draw inspiration from animele but still look distinctly different and i think i succeeded but the shading of anna mele is ultimately superior if you would like to use any of 
[12:48](https://www.youtube.com/watch?v=uO_B_aPlzho&t=768) these skins the links are in the description additionally all the resources i used to learn how to do this are linked as well big thank you to shiggles for helping me with questions i 
[12:59](https://www.youtube.com/watch?v=uO_B_aPlzho&t=779) had as well as revealing the secrets of animele shading to me thanks for watching everyone i hope you have a great rest of your day and i'll see you next time 