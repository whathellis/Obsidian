---
URL: https://www.youtube.com/watch?v=UfSw6428bcc&t=606s
thumbnail: https://i.ytimg.com/vi/UfSw6428bcc/default.jpg
channel: "[[SouthernShotty]]"
date: 2024-07-02
published: 2024-02-21T01:00:31
duration: 716
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715174128.jpg]]"
---
[time:: "11m 56s"]
# EASIEST Way to Make Painterly Animations in Blender 3D (Procedural Shader)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715174128.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="EASIEST Way to Make Painterly Animations in Blender 3D (Procedural Shader)" src="https://www.youtube.com/embed/UfSw6428bcc?start=606&amp;feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
25% OFF PRODUCTS NOW
Dynamic VFX Pack (Free Sample Pack): https://blendermarket.com/products/blender-dynamic-vfx---elemental-asset-pack
FREE PAINTERLY MAPS: Crafty Asset Pack (Free Sample Pack): https://blendermarket.com/products/crafty-asset-pack
Patreon: https://www.patreon.com/southernshotty
Skillshare (affiliate link): https://www.skillshare.com/r/user/southernshotty
Tag me in your artwork on Instagram and Twitter @SouthernShotty
Instagram: https://www.instagram.com/southernshotty/
Twitter: https://twitter.com/SouthernShotty

Some tutorials I liked with their own painterly approaches:
[[../../3D/Don't have/Turning 3D Models into Masterpieces A Blender Tutorial|Turning 3D Models into Masterpieces A Blender Tutorial]]
```NiftyLinks
url: https://www.youtube.com/watch?v=6uaJ0L4E390
title: Turning 3D Models into Masterpieces: A Blender Tutorial
description: In this video, I introduce my Blender Live Paint Filter, an incredible tool that can turn your 3D scenes into stunning paintings in Blender. I'll share the s...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/6uaJ0L4E390/maxresdefault.jpg
```
[[./Painting brush strokes with Geometry Nodes in Blender|Painting brush strokes with Geometry Nodes in Blender]]
```NiftyLinks
url: https://www.youtube.com/watch?v=MgZsVBVZ3Nc
title: Painting brush strokes with Geometry Nodes in Blender
description: Turn on CC for subtitles.A breakdown and demonstration on how to use the Geometry Nodes paint-over tool "Curve Painter" that was put together to help you cre...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/MgZsVBVZ3Nc/maxresdefault.jpg
```
[[./Making 3D animation look painterly (it's easier than you think)|Making 3D animation look painterly (it's easier than you think)]]
```NiftyLinks
url: https://www.youtube.com/watch?v=s8N00rjil_4
title: Making 3D animation look painterly (it's easier than you think)
description: In this video, I'll go over a surprisingly simple way to make your stylized 3D renders feel like a painting. I do it by painting over Object Space Normal Map...
favicon: https://www.youtube.com/s/desktop/86d8f362/img/favicon_144x144.jpg
image: https://i.ytimg.com/vi/s8N00rjil_4/maxresdefault.jpg
```

(Description:: We'll guide you through the process of setting up procedural shaders in Blender, showing you how to manipulate nodes to achieve a dynamic, painterly effect that automatically applies across your entire animation. This method not only simplifies the creation process but also allows for incredible flexibility in adjusting the style and colors of your animation on the fly.)
# Transcript
[00:00](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=0) today we're going to be looking at how to create this procedural painterly effect now a painterly style is something that is normally very manually labor intensive so we're going to be 
[00:07](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=7) looking at some effects and shaders we can use to speed up the process and make it quick and easy let's dive [Music] in great so start off by grabbing our 
[00:18](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=18) object and we're going to go ahead and add two material slots on the second one we're going to go ahead and call this one outline and the first one here we're going to go ahead and call this one 
[00:29](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=29) painter great so starting with the bsdf node on our painterly material we're going to go ahead and add a Veron texture now if you're using node wrang layer add-on which is included with 
[00:40](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=40) blender for free you'll be able to use the same keyboard shortcuts as me so if I control shift click here down to the position you'll see that we're getting a faceted look so let's go ahead and add a 
[00:50](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=50) texture coordinate here and then we're going to go ahead and pipe the normal there into the vector and you can see how this is giving us a faceted look similar to kind of a painterly look ever 
[01:00](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=60) they're very harsh and sharp edges so we're going to go ahead and roughen those edges up to give it more of a pain early look so I'm going to go ahead here and plug this directly into the normal 
[01:10](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=70) my bsdf here so you can see how it's starting to affect our material already so let's look at how we can roughen this up so what we're going to do is create a mix color node here so let's go ahead 
[01:22](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=82) grab a mix color and what we want to do is plug our normal here into the a value and then we will plug that result here into our Vector now what this Factor will allow us to do is mix that between 
[01:36](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=96) those two add a noise texture here plug the factor into B grab our object coordinates here and plug that into the vector of the noise texture now if we look at what the noise texture is doing 
[01:48](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=108) we can see with those object coordinates it's going ahead and splashing noise all across our object now you can tweak these settings here to alter the look but I'm going to leave these by default 
[01:57](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=117) let's go ahead and look at how that's affecting our Veron text texture there you can see that by turning this up and down we're losing our faceted look with sharp edges and getting more kind of 
[02:06](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=126) pain early splotches perfect you can decide how much you want to put in there .15 and then I'm going to adjust my Veron texture here I'm going to do a scale of about four I'm going to add one 
[02:18](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=138) to the detail and you can see how that's changing the look there I'm going to leave roughness at 0.5 and the rest of these at their default settings we can see how it is starting to affect our 
[02:30](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=150) model perfect let's go ahead and actually add some brush Strokes in here I've included one of these materials in the crafty asset sample pack which is on sale at blender market right now with 
[02:42](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=162) their winter sale you can unpack the file and you'll get these diffuse maps and normal maps and if you want project files like the one from this video additional materials or casual tutorials 
[02:53](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=173) check out my patreon so what we're going to do is grab this paintbrush normal map which as I said will be included for for free and we're going to go ahead and drag that into our Shader here and we're 
[03:04](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=184) going to grab the object coordinates here we're going to drag that down into the vector now if you hold shift and slice with the right Mouse button you can go ahead and create a reroute node 
[03:16](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=196) there and just keep things a bit more organized now what I'm going to do is hit shift a and look for a mapping node drag that on over here and this will allow us to easily control the scale 
[03:26](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=206) let's go ahead here and take a look at our map you you can see how we're getting these kind of brush stroke lines all across so what we can do is drag this scale out here and add a value node 
[03:37](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=217) and then now we can just uniformly scale our texture up and down now we're going to do two things with this brush normal map one we're going to mix it into our texture to add some kind of brush lines 
[03:48](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=228) to the edges here and then we're also going to mix it into the overall normal map so that we kind of have a brush texture overlaid our faceted foni texture look so what we're going to do 
[04:00](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=240) is go ahead and drag this mix node here by shift and put another one there and change the modes of both of these to linear light and that will just get us a better blend so let's go ahead change 
[04:14](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=254) this one to linear light as well and then what we're going to do is grab the color from here and mix it into the bottom there and if you take a look at the position here you can see that with 
[04:25](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=265) this Factor here and mixing in these kind of small brush chokes to the edges there so I'm going to leave my factor to 0.15 which is about 15% great so let's go ahead and look at how that's 
[04:36](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=276) affecting our overall model here you can see that we're starting to get more of a painterly look I'm going to go ahead and choose a color makes it a bit easier to see perfect you can see how we're 
[04:46](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=286) starting to achieve that painterly look but let's go ahead and mix the brush into the normals a bit more making it a little bit easier to see so first of all drag the color of our brush out into a 
[04:56](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=296) normal map and plug that into the color and and then plug this directly into our model so you can get a good view of it and you can see here that it doesn't look great as is and that's because when 
[05:06](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=306) you drag in by default it sets the color space to srgb since this is a normal map we want it set to non-color and you can see how that's already looking better now you may notice that we're getting 
[05:16](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=316) these kind of swirls here and that has to do to the fact that we're using the object and it's just having a hard time of knowing where the UV coordinates are something we can do to improve that is 
[05:25](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=325) come here on the image and go from Flat to box and that will box projected over now you may notice some harsh lines here up the blending there and you'll see that now we're getting a much more 
[05:35](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=335) natural brush stroke overall now I really want to crank up this brush stroke effect bump this up to something like five and you can see that now I'm really starting to get that brush 
[05:44](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=344) pattern so what we can do is duplicate this mix note here and just drag that over there and bump this down to the bottom one and we'll switch this back to mix that means it won't use any fancy 
[05:55](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=355) blending modes it's just going to mix directly between the two now what we can do is take the position note here mix this here and I'm going to set my factor to something like 0.5 and you can see 
[06:05](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=365) that now we're getting a mixture of that faceted look and the brushes and you can go ahead and adjust that either way so maybe something like. 3 might give you a pretty natural look between the 
[06:16](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=376) [Music] two now if you remember before I said you could download that material and it have all the maps so we'll go ahead here and drag in the paintbrush diffuse up 
[06:26](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=386) here I'm just going to move this up here we'll leave this one Sr R GB and we want this to have the same mapping as our normal grab that same vector and move that up there ahead and reroute that 
[06:36](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=396) just to keep that a bit more organized likewise we will change this to box and blend to match the settings that we have down here now if I take a look at this we can see how we're getting that 
[06:46](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=406) brushstroke effect over everything perfect so what we can do here is we can duplicate this mix node here and let's go ahead and mix this with our Veron texture so we also have this color 
[06:58](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=418) socket here that we can use to kind of feed into our color mixer here so let choose multiply here and we'll drag this there I'm going to view this so we can see what we're looking at here and drag 
[07:11](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=431) this paint diffuse here on the bottom and we'll drag the color from Veron texture here on the top and turn this facture up and I'm going to set this around something like 7 which will 
[07:21](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=441) equate to about 70% perfect so you can see the look we're starting to get there and if you want you can add a color ramp in between these and that will convert the Veron texture to a grayscale effect 
[07:34](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=454) so you can see how we are getting a nice kind of mixture of colors there on the grayc value so let's look at how we can plug that into our base color so let's go ahead put this back here and what 
[07:44](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=464) we're going to do is yet again duplicate this color node and this time we are going to plug the output of here into the factor and then we'll unplug that into our base color now what's going to 
[07:56](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=476) happen is this grayscale color value is going to determine the colors between a and b and I grab kind of a nice warm color and let's grab a kind of cool color to complement this maybe something 
[08:09](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=489) like a nice kind of dark purple perfect you can see that now we're introducing that so right there we're starting to get good mixed colors now if you wanted to use an image map that You' already 
[08:19](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=499) painted you could plug these into the a or the B values and mix color in on top of it as well drag this multiply node off here into space which will allow us to search and we're going to look for 
[08:30](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=510) color ramp and you want to choose the one where it's plugged into Factor perfect now what we can do grab that color there and plug that into the roughness and now you can see that we're 
[08:40](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=520) getting some variation and roughness across our [Music] object so we'll go over here to the modifier panel add modifier and search 
[08:50](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=530) for displacement now you'll see that it's going to break your model at first and we'll fix that in a second but we're going to click new texture here and just call thist painterly we'll come down 
[09:00](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=540) here to the texture panel so we're change image or movie to Veron there play with these if you want but I'm just going to go ahead leave them by default come over here to our displacement 
[09:11](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=551) modifier and we just need to lower the strength down to something really small I suggest something like 045 and you can see how that is giving our model a kind of hand painted look so 
[09:22](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=562) this is how we're going to get our outline effect go ahead search for solidify and we're going to set this to something thing really small like 015 you can adjust this base on your model 
[09:34](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=574) and then we're going to come down here to the normals we're going to click flip perfect and then we're going to come down here to materials and do material offset one now that's going to apply the 
[09:43](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=583) outline modifier that or material that we have to the flipped normals there now so you should be in your outline material here and just add a light path node and we're going to add a geometry 
[09:57](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=597) node and you'll notice here on the geometry node that we have back facing now what we're going to do is add a transparent bsdf and then we'll go ahead and add two mix shaders so what we're 
[10:07](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=607) going to do is we're going to go ahead we're going to grab this transparent bsdf we're going to plug this into the bottom of the first mix Shader you're going to grab your bsdf your principal 
[10:17](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=617) bsdf and you're going to plug that into the top of that first mix Shader and then you're going to use the is Shadow Ray for the factor now we're going to do the mix Shader we're going to grab this 
[10:28](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=628) mix Shader plug it in into the top of the second one and then we're going to grab the transparent bsdf and plug this into the bottom of this one and then now we can call on back facing and Cycles 
[10:37](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=637) using this geometry note so we'll go ahead grab that top one and plug it into the factor there and then if we grab this Shader and put it there now if you want to enhance that effect you can go 
[10:45](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=645) ahead and increase the thickness here and that will make it thicker we're just going to go ahead and leave ours thin there a little tip here if you want to clean it up grab your nodes and hit 
[10:55](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=655) controll H and it will just shrink it down to the ones that are being used and then you don't have so much mess so first of all here I'm going to set my reference down to something like 0.1 and 
[11:05](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=665) then I'm going to choose kind of a clay material color that we have there so this is just matching the kind of color after that we're going to go ahead and add a noise texture here and just take a 
[11:16](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=676) look at how it looks on our object there I'm going to bump mine up to a scale of about 10 and then leave all the other settings to default next I'm going to add a color ramp and just drag that over 
[11:29](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=689) here and just crunch this down and then we can take this value and we'll plug it into our Alpha here and plug this mix Shader in here and now you can see how that is controlling the alpha of our 
[11:40](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=700) outline there so you can drag this in to have less outline and you can adjust the scale there to kind of adjust kind of the messiness there there's already a couple other great painterly effects out 
[11:49](https://www.youtube.com/watch?v=UfSw6428bcc&t=606s&t=709) there though they were a bit labor intensive so I'm going to link those tutorials below as well for additional resources 