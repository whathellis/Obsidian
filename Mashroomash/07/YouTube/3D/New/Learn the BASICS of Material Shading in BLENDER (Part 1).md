---
URL: https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5
thumbnail: https://i.ytimg.com/vi/Wg244y2f9Fw/default.jpg
channel: "[[Brandon 3D]]"
published: 2022-04-18T19:45:01
duration: 1746
tags:
  - video/3D/texture/node
done: false
cover: "[[Pasted image 20240711164913.jpg]]"
date: ""
q-data:
  leech-count: 1
  due-at: 2024-07-26T18:00:00.000Z
---
[[Read it Later|Read it Later]] [time:: "29m 6s"]
[[./Blender PBR Material Shading (Material Series Part 2)|Blender PBR Material Shading (Material Series Part 2)]]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240711164913.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Learn the BASICS of Material Shading in BLENDER (Part 1)" src="https://www.youtube.com/embed/Wg244y2f9Fw?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
Blender Material Texture Shading Introduction Tutorial:

(Description:: Blender material nodes are used for material shading. They can be confusing, so this is a basic Blender materials tutorial for absolute beginners. We will cover adding materials to objects, the Principled BSDF shader, the Color Ramp, mix shaders, transparent materials and more. I have some Blender shading tips at the end of the video that will save you time. In part two, I'm going to cover PBR materials in Blender which are photorealistic texture materials you can add to objects.)

Materials are what make an object in Blender look the way they do. Blender materials have three channels: surface, volume and displacement. Using a variety of nodes, you can mix and match textures and map your materials to your object. Before you start watching other Blender tutorials on material shading, watch this so you understand the basics. THANK YOU!

These are some of my FAVORITE products related to Blender and digital art. Using these links to purchase may pay me a small commission at no extra cost to you: 

BLENDER MARKET FAVORITES: 

❤️ My favorite Blender add-ons: 
https://brandonsdrawings.com/best-blender-addons

❤️ Favorite Blender courses on Udemy: 
https://brandonsdrawings.com/blender-udemy-courses

❤️ Favorite gifts for digital artists:
https://brandonsdrawings.com/products-for-digital-artists

My Amazon list for digital artists: 
https://a.co/9774wiw

As an Amazon Associate, I earn from qualifying purchase. 

Get more Blender and 3D content on my website (and subscribe to my e-mail list) at: https://brandonsdrawings.com

Instagram:                  https://www.instagram.com/brandonsdrawingsart/
Facebook:                   https://www.facebook.com/brandonsdrawingsart
Twitter:                        https://twitter.com/brandons_art
ArtStation:                  https://www.artstation.com/brandonsdrawings



Timestamps:
0:35 Basics of Adding Materials in Blender
3:51 Nodes in the Blender Shader Editor
9:09 Principled BSDF Shader in Blender
12:56 Mix Shader in Blender
14:32 Color Ramp Node in Blender
15:33 Texture Nodes in Blender
18:35 Mix RGB Node inn Blender
19:55 Mapping Textures in Blender
21:39 Math Node in Blender
22:05 Transparency Shading in Blender
22:56 Volume Shading in Blender
25:43 Shading Tips in Blender

# Transcript
[00:00](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=0) this is part one of a two-part blender tutorial covering the very basics of setting up materials and shading in blender i'll give a thorough overview of how to add materials how basic material 
[00:10](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=10) nodes work and we'll cover some of the more common nodes you'll use in part two we will get into pbr texture materials which are super realistic materials i'll save some quick but valuable tips for 
[00:20](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=20) the end if nodes are confusing i promise this should demystify a lot of it for you let's go a quick note i will be doing everything in cycles these materials will work in ev2 but sometimes 
[00:33](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=33) the settings are a little bit off between the two render engines we start with materials at the material properties panel with an object selected this panel displays materials assigned 
[00:43](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=43) to the object this is a default material that's assigned objects can have more than one material assigned to them in these material slots pressing the plus icon adds a new material slot but 
[00:54](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=54) there's no material in the second slot yet we can either use this drop down box to choose a material already in our blender scene or we can press new to create a new one let's do that 
[01:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=64) with the new material selected a few tabs get added below we have preview surface volume displacement settings and a few more by default there will be nothing in the 
[01:15](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=75) displacement nothing in the volume but under surface we have a whole bunch of settings and preview is just the preview of the material you can choose different shapes 
[01:23](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=83) to have the material previewed on but these three the surface volume and displacement are the three channels a material can have surface is everything on the outside 
[01:33](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=93) surface of the object like paint wood metal etc it's what you're going to use the most volume is how you want the three-dimensional space inside the 
[01:42](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=102) object to be filled you'd use this if you wanted to make smoke or fog inside of an object you'd also use it for liquids clouds things like that displacement is physical movement or 
[01:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=113) displacement of the mesh an example of when you use this is if you had a brick wall and you wanted it so detailed that the mesh actually popped outwards on the bricks and sunk in where the mortar was 
[02:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=124) there are other ways to fake this look and we'll get into that in part two but that's what displacement is let's look at surface for now everything on this panel is basically a summary of 
[02:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=134) what's actually been created using nodes in the shader editor for simple materials you can handle all the settings right here but once they get more complex you'll want to jump 
[02:24](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=144) over to the nodes at the top it says surface and then it says principled bsdf the principled bsdf is the default shader for materials in blender it is a very versatile shader 
[02:35](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=155) that can create many of the things you want to make what is a shader by the way a shader is a calculation of how to output materials and how those materials will interact 
[02:45](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=165) with light in your scene if we click the name of the shader we can choose from a long list of other shaders we aren't going to cover them all and you won't use very many of them this shader 
[02:55](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=175) doesn't have many options but the principled bsdf has a lot more settings because it can do a lot more stuff remember how we added the second material while the first material is the 
[03:05](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=185) material currently assigned to the plane by default when a material is placed in the first slot it gets assigned to the entire object to change materials we can go into edit mode select the portion of 
[03:16](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=196) the mesh we want to assign the second material to select the material and then press assign we could select different parts of the mesh and assign different 
[03:24](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=204) materials to different parts in this way we can select the material slot and press minus to remove the slot the removed material will still be available to add to objects later until 
[03:36](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=216) we close blender we can double click on the material in the slot or down here and rename it i'll rename it to subscribe just as a little reminder for you to subscribe and turn on 
[03:47](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=227) notifications so you don't miss future tutorials this is as far as we're going to go right here we are now heading over to the shader editor the best way to get there is to change to the shading 
[03:57](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=237) workspace at the top before we go any further there is an add-on in blender called nodewrangler that you want to have turned on pretty much all the time go to edit preferences 
[04:07](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=247) add-ons and search for nodewrangler check the box next to it to activate it this add-on enables a lot of things you can do with the nodes it should really just be incorporated into blender by 
[04:17](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=257) default but for technical reasons it's not if your workspace isn't exactly like mine don't worry the important things are you should have a 3d viewport set to 
[04:27](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=267) material preview mode and you should have this big area known as the shader editor the properties panel should be over here on the side let's just cover a few basic things about the shader editor 
[04:37](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=277) in the top left we see a drop down box that says object this means the shader editor is set to work on object materials which is what we want but we can change this to work on shading of 
[04:48](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=288) the world which is the background of the scene the sky etc this is how you could add an hdr image to light your scene or to serve as a background up here we have some of the same 
[04:59](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=299) controls from the materials panel it shows our material slots and the materials assigned to them now let's talk about nodes we have the principled bsdf node 
[05:10](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=310) assigned to this material this large node is the principled bsdf with all the same options we saw in the materials panel but you will always have this material output node as well you can 
[05:20](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=320) select a node and press g to move it around or just click and drag it many of the same shortcuts of blender work in the shader editor if i have a node selected shift d duplicates it 
[05:31](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=331) shift a is how we add a new node and x deletes a node the material output node is the final output of whatever information your nodes create it has three channels i mentioned these earlier 
[05:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=344) the principled bsdf is a surface shader so it's plugged into the surface input of this final output node all information in node editors flows from the left to the right so you put 
[05:55](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=355) information into the nodes on the left side the nodes do something with that information and put out new information on the right because the material output node is the final output where all the 
[06:06](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=366) nodes end it only has inputs on the left side these dots for inputs and outputs are called sockets the principled bsdf node has a whole bunch of input sockets on the left but only one output socket 
[06:18](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=378) on the right you'll notice the sockets are different colors a green socket represents complete shader information if a node has a green output on it it is considered a shader meaning it can be an 
[06:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=389) end product that can be plugged into the final output node you'll often hear node and shader used interchangeably but technically only some nodes the nodes with green outputs are actually shaders 
[06:41](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=401) yellow sockets indicate color information so this base color for example we could plug any sort of color information into this and the socket will recognize it as color this could be 
[06:52](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=412) a color image the gray sockets are value inputs these could be numerical values of any kind but often range between 0 and 1. many of these settings on the bsdf have 
[07:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=424) values that range from 0 to 1 0 means there's none of the effect and one is the effect is turned all the way up let's look at roughness as an example roughness is how rough a material 
[07:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=434) surface surfaces and it affects the reflection of light zero would be a completely smooth surface which is unrealistic for most materials one would be very rough you can actually 
[07:24](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=444) click this value and type in a value higher than one if you want to these gray sockets can also accept black and white or gray scale values why are black and white or gray scale images important 
[07:35](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=455) well it's unlikely that you'll want a material to be exactly the same roughness everywhere so these zero to one values allow us to map values to different areas of the material using 
[07:46](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=466) black and white or gray scale coloring here's an example of a roughness map that can be plugged into this socket zero is represented by black one is represented by white and everything in 
[07:56](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=476) between is represented by a shade of gray the darker the gray the closer it is to zero so the lower the effect will be in that part of the material and the lighter it is the closer it is to one so 
[08:07](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=487) the effect will be stronger there this image plugged into this roughness socket would use grayscale data to map out roughness values over the object so that's what the gray sockets are they're 
[08:17](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=497) value inputs that can also be mapped with grayscale images this concept will be important in both procedural and pbr texturing that we cover in part two the last color here is purple purple sockets 
[08:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=509) deal with vector information which is information that either tells blender where to map something or where to move something it's hard to explain but you'll see this mostly with normal maps 
[08:39](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=519) and material mapping which we will cover soon for the most part you usually plug outputs into light colored input sockets so green always needs to go to green purple into purple etc this is not 100 
[08:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=533) always the case with yellows and grays sometimes you have a black and white output that you're going to use in a color socket and vice versa but yellows are looking for color information and 
[09:03](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=543) grays won't recognize color information other than black white and grayscale so the principled bsdf shader in blender has a lot of settings probably more than any other because it does a lot of 
[09:15](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=555) things this was only added to blender a few years ago and before you actually had to combine a lot of nodes to be able to do what this node can do by itself it's important enough to go over a lot 
[09:25](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=565) of these settings i'll be honest some of them i've never used and i'm not going to be able to adequately explain but base color is pretty self-explanatory it's the starting color of the material 
[09:35](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=575) without any effects like reflectiveness or roughness added to it the next three are for subsurface scattering which is what happens to light that penetrates the surface and scatters underneath it 
[09:45](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=585) the best example of this is human skin when light hits skin some of it goes through and scatters underneath giving it a pinkish hue the subsurface scattering settings can replicate this 
[09:55](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=595) effect metallic i'll try to explain this as best i can materials that are truly metal have a reflective property but also have their own color so it's 
[10:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=604) different than say a glass mirror there are two basic workflows for shading that you'll see and they are a metalness workflow and a specular workflow some artists choose to use the metallic input 
[10:16](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=616) and sum the specular depending on the material and their personal preferences these are different from each other but are both ways of giving a material reflective properties 
[10:25](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=625) roughness we kind of covered but it's how rough the surface is on a very tiny nearly microscopic level and affects the reflection paper has a high roughness value on a microscopic level it is not 
[10:37](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=637) smooth and that roughness will make it not reflect light as well most glass will have a very low roughness and even at the microscopic level is very smooth antistropic sheen and clear coat are 
[10:49](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=649) some advanced characteristics you can give a material that we aren't going to cover right now transmission is how much light is allowed to pass through the material rather than be reflected off of 
[10:58](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=658) it emission is light that the material actually emits from itself you can give the emitted light its own color and strength you can actually use this to have objects like your scene or for a 
[11:09](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=669) variety of effects if you're emitting light from a material it's usually going to drown out any other settings you have up here so this is usually used by itself there's also an emission shader 
[11:19](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=679) that only does a mission if you want to use that instead alpha is transparency whenever you see the word alpha in pretty much any graphic software it's referring to the 
[11:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=689) transparent quality one is no transparency a little backwards it seems and zero is full transparency that's just how alpha values work of course this and all other settings can be 
[11:40](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=700) mapped to an object so you could have parts of your material transparent and parts not transparent you would use a grayscale map to do this the normal input is for a normal map 
[11:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=713) normal maps are a way to fake depth and shadows in your material without actually changing the geometry of the mesh they are very useful here's an image of a surface with no normal map 
[12:03](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=723) and here's an image with the normal map no difference in the actual mesh just using normal data to fake the look of depth and height alright so let's look at some other node 
[12:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=734) options in the blender shader editor to add a node in the shader editor you press shift a and you get this menu the nodes are all categorized into groups and there are quite a few of them often 
[12:25](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=745) you'll know what node you're looking for and can search for it by name in the search field you'll see a category called shader remember a shader is a node with a 
[12:34](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=754) finished output ready to be plugged into the output node some of them are for surfaces some are for volume you can also go over here in the shader properties and see the options for 
[12:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=764) different shaders most of them are very simple don't have a lot of inputs or are designed to do one very specific thing like the glass shader the principal bsdf is so useful that it's almost always 
[12:55](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=775) what you start with the mix shader can be added to combine two shaders together i will duplicate this shader and show you how to mix two shaders i'll give one a red base color 
[13:06](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=786) and one a blue base color for demonstration to connect sockets you can drag the output socket of one node over to the input socket of another and when it's 
[13:15](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=795) connected this line will appear to show the path of the information there are a few ways to disconnect a shader and one of them is to just click the output connection drag it off and let go i've 
[13:26](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=806) got a faster way as one of my tips at the end of this video by the way i would love to get a like on this video if you made it this far it really helps and is really really appreciated thank you so 
[13:36](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=816) much if you drag and drop a node onto a connection blender will insert it for you between the two nodes if it can meaning if there are appropriate sockets to plug into so back to the mix shader 
[13:47](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=827) it has two green inputs for you to connect two shaders you want to combine the factor which you will see a lot is how you want the shaders combined with this setup turning it all the way to 
[13:57](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=837) zero will be one hundred percent the top shader turning it all the way to 1 will be 100 the bottom shader putting it somewhere in the middle will be a faded combination of both shaders but you 
[14:08](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=848) notice the factor shader has a gray input node this means we can map this factor if we plugged in a grayscale map or a node that maps values from 0 to 1 we would tell blender to put the top 
[14:20](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=860) shader where there is black and the bottom shader where there is white and to mix the two together where there is gray i'm going to leave these two shaders connected and we are going to 
[14:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=869) look at a few other important nodes that come into play we'll press shift a and in the search bar type in color and choose the color ramp node you will use this node a lot 
[14:40](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=880) it's a gradient node it defaults with two gradient points a black on the far left and a white on the far right with a completely smooth and linear transition between there are different settings to 
[14:50](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=890) choose for how the gradient is interpolated that means how it transitions or fades from one point to the other it also has a factor input on the left and on the right it has both a 
[15:00](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=900) color output and an alpha output the color ramp can generate color information you can select one of these points and choose a color this can be used for all sorts of gradients in your 
[15:10](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=910) materials you can click the plus icon to add a control point this could allow you to add a new color to the gradient or just use it for more control 
[15:19](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=919) the color ramp is often used as a factor input and this is one of those times where you will actually plug a yellow color output into a gray input socket if your colors are all going to be 
[15:30](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=930) grayscale we will see the color ramp again soon one category of material nodes in blender is texture nodes shift a to add a node and find the category labeled 
[15:40](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=940) texture these are a bunch of different ways to procedurally generate black and white or gray scale textures that can later be combined and tweaked to get procedural 
[15:49](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=949) looks that you want we'll look at the musgrave texture first which is commonly used to add procedural grunge effects i'll plug the height output into the color input of the principled vsdf just 
[16:00](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=960) to show you what it looks like since musgrave is outputting black and white color it's okay to plug it into the color input socket so long as we understand we are only getting black and 
[16:08](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=968) white out of it this is the basic musgrave texture pattern there are different types of musk grave you can choose from where it says 3d you can choose other 
[16:17](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=977) dimensions i almost always leave it at 3d although 2d would work since the plane we're using is a 2d object choosing 4d adds a w value down here and whenever you see the w value in shading 
[16:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=989) it's an animation factor it can make the texture move over time change the w and the texture moves you can keyframe this value to have the texture be animated which is awesome the other settings also 
[16:41](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1001) adjust the look of the muskrat scale and detail are probably the most helpful a very very common use of the color ramp that we looked at before is to add it after a texture node so let's do that 
[16:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1013) shift a and we find the color ramp under converter for nodes you use repeatedly i've got some tips to add them to the editor faster at the end of this video so let's drop the color ramp in between 
[17:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1024) the musgrave texture and the principle shader notice this now has a gray socket into a gray socket on the left and a yellow socket into a yellow socket on the right it's almost like it was meant 
[17:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1034) to be the color ramp now acts as a gradient control for the transitioning between black and white areas in the texture node if we move the white closer to the 
[17:23](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1043) black it shortens the transitional fade between black and white on the texture moving the black up will remove some of the white another trick is to select the white then use the color selector here 
[17:34](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1054) darken the white and it subdues the texture pattern everywhere and lastly since the color ramp does output rgb colors we can change the colors to actually output a colored texture if we 
[17:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1064) want i'll quickly show you some other texture nodes and we'll move on veronica varonoi boronoi is a useful texture that you can get a lot of cool 
[17:54](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1074) looks out of the brick texture allows you to make procedural bricks or blocky textures lots of settings on this one the wave texture allows you to add bands 
[18:06](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1086) or rings here's the really interesting part these textures can be used as inputs for other textures i could plug the voronoi into the wave scale and get this 
[18:17](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1097) i could plug the must grave into the scale and get this or plug the voronoi into the musgrave and get something like this there are endless combinations of these 
[18:27](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1107) you can use to get different effects and there are countless blender tutorials out there that show you different ways to play around with all of this another way to mix and combine texturing 
[18:37](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1117) effects or colors is using the mix rgb node the mix rgb node in blender acts just like the mix shader we looked at earlier but instead of being for shader outputs it's for color including 
[18:47](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1127) grayscale color values i'll add a mix rgb node i'll plug a musgrave texture into one yellow socket and a varonoi texture into another again we have this factor setting that controls how much of 
[19:00](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1140) each one we get for this one we also have a lot of different blending modes if you've used other graphics software like photoshop or whatever you've probably seen these before they are 
[19:08](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1148) different formulas for how to blend colors together not going to go into a lot of detail here but the default mix might give you a very different effect than add or multiply and depending on 
[19:19](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1159) what you're going for you may use different blend modes for demonstration i'm going to add a wave texture and plug it into the factor to control how these two textures are mixed together 
[19:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1169) you see the bands from the wave texture have separated where the musgrave and voronoi show up of course adding a color ramp in here can give us even more control 
[19:38](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1178) or we could add color to this we've used one texture node as a map for how to combine two other texture nodes and this is a very simple setup there are endless combinations on how you can 
[19:49](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1189) mix and match textures to get all sorts of procedural effects and again there are tons of tutorials on different ways to do it so now let's talk about mapping textures 
[19:58](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1198) onto an object with this simple texture it isn't that big of a deal but it will be with a more complicated one and when we get into pbr texturing in part two to add a texture mapping setup to this we 
[20:08](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1208) actually have to add two nodes the first is a mapping node this node's purple vector output will plug into the purple vector input here and we immediately notice that the 
[20:18](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1218) entire texture disappears this node is a control node with all the mapping controls but it doesn't even know where to start without the help of another node the texture coordinate node 
[20:29](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1229) the texture coordinate node has a bunch of different ways that the texture can be told how to be mapped in blender different uses may require different outputs here generally for procedural 
[20:38](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1238) things object is going to be your best bet but you see this has adjusted the material based on the size of the object so an alternative could be the generated which is kind of just like the default 
[20:49](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1249) when we get to pbr stuff where we will actually be using images that may need to be placed on very specific parts of a mesh as well as multiple images which need to be placed in the exact same way 
[20:59](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1259) we will use uv so this mapping node gives us all sorts of controls on where this texture is mapped on the object we can change the location along all three axes this is 
[21:09](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1269) only a two dimensional object so some of this isn't as important we can rotate the material and we can scale the material along each of these three axes 
[21:19](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1279) one main point on nodes we should mention here is an output can go into many inputs but an input can only have one connection going into it often we'll use 
[21:31](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1291) the same mapping setup and feed it into multiple different nodes but if we try to feed two nodes into one input it's not going to work another node you will see used a lot is 
[21:40](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1300) the math node i hate math but this node isn't too bad it could be plugged in between two other nodes and then it can run a simple math formula on the data before it gets to the second node 
[21:51](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1311) remember black and white values have values of 0 and 1 respectively well maybe you want to amplify those values by multiplying them or maybe you want to take two values and add them together 
[22:02](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1322) the math node does this and a lot more sometimes in blender you want a material to be transparent or translucent there are both transparent and translucent shaders in blender that can be combined 
[22:12](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1332) with other shaders or used by themselves more often i find the glass shader useful on this you'll see an ior setting whenever you see ior it means index of 
[22:23](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1343) refraction which is one of the terms i cover in my blender terminology video that i recommend beginners check out different materials reflect light at different angles your regular glass has 
[22:34](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1354) an ior of 1.45 which is the default value for this node other materials like plastic water thicker or thinner glass will have different iors so the glass shader can actually be used for more 
[22:46](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1366) than just glass the roughness value can be adjusted and this is a good demonstration of what roughness does higher is less reflective while lower is more reflective 
[22:56](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1376) everything we've covered so far has dealt with the surface channel of materials but volume is something you might want to use as well there are only a handful of volume shaders and i'll 
[23:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1384) need a three-dimensional object to demonstrate this so i'll add a cube and give it a new material i'll delete the principled shader because i don't want this object to have a surface i just 
[23:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1394) want it to have volume the object turns black until you plug something into the volume channel volume absorption means the volume will absorb light as it passes through an 
[23:23](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1403) object this is kind of what happens when you're looking into a pond and light starts to disappear as it gets deeper volume scatter is more like what you see with fog and every scene is better with 
[23:33](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1413) a little fog in it with volume scatter light hits the volume and bounces around this can be very demanding on a computer to calculate so if your computer struggles with blender volume shading 
[23:43](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1423) might not work for you at the moment there's also the principled volume shader which combines the two in the most realistic way possible and it's probably the one to use most of the time 
[23:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1433) it also hasn't been around forever and before you had to mix a scatter and absorption node together to get what this node can do by itself we plug the volume into the volume channel and we 
[24:02](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1442) get this some pretty dense fock we can slide the density down to reduce the fog but notice it's a very uniform fog throughout the object using texture nodes color ramps and 
[24:13](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1453) other things we can tweak the density value to get really cool effects i'll add a noise texture which we didn't really cover but it's similar to the musgrave texture node this one has a 
[24:22](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1462) factor output which can plug into the density input of the volume shader it might be difficult to see but as we adjust the scale of this noise texture there are sort of noisy pockets of fog 
[24:34](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1474) that we can adjust the size of we could add a color ramp between these two to adjust the fog similarly to how we adjusted things with the surface material 
[24:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1484) we can change the color of the volume which might make this easier to see we can have the fog give off its own light which isn't really realistic but it can create a cool effect 
[24:54](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1494) there are a lot of other things to play around with here too and i should point out we see a new color socket here these blue sockets are for attribute inputs which is as of this recording a fairly 
[25:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1504) new feature in blender that i haven't fully wrapped my head around yet they're useful in geometry nodes which are an entirely different use of nodes that this video is not getting into what you 
[25:14](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1514) could do with this object is to make it huge and have it encompass your entire scene to add fog to it but remember volume is very demanding when you're rendering so use it with caution and 
[25:23](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1523) don't go crazier than you need to with it since we are using a noise texture to control the fog density here we could change it to 4d which gives us that w value we discussed before we could use 
[25:34](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1534) that along with keyframes to animate the density of the fog hard to see in preview mode but it could look something like this when rendered out 
[25:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1544) i promised some helpful tips at the end of part one so here we go when you find yourself adding the same node to a lot of materials like the color ramp for example you can speed this up two ways 
[25:54](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1554) press shift a to add a material find the node you want and right click it you can either add a shortcut for the node by doing this you'll be prompted to press a key to create a shortcut but how 
[26:05](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1565) many keys do you have on your keyboard some useless trivia the standard keyboard actually has 101 keys on it i didn't count them i googled it what i prefer is to add nodes to my quick 
[26:16](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1576) favorites menu right click the node and choose add to quick favorites now in the shader editor you can press q and a short menu of your favorite nodes appear 
[26:26](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1586) with the node wrangler add-on enabled you can do so many things and here are just a few of them make sure you remember to turn on the node wrangler add-on 
[26:35](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1595) if you want to disconnect a node connection press control and then right click on your mouse with those pressed just cut through the connections you want to disconnect and they're gone you 
[26:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1604) can do this across multiple connections at once in blender it's often useful to see what one single node in your node tree is contributing you can do this as long as 
[26:54](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1614) node wrangler is turned on hold down control shift on your keyboard and then click on a node it connects that node into this viewer node and then into the final output so you can control shift 
[27:05](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1625) click around to see what your nodes all look like by themselves when you're done ctrl shift click the final shader and it'll go back to normal when you have a texture node in your 
[27:15](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1635) editor and want to connect it to a mapping and texture coordinate node you can save a lot of time by selecting the node and pressing ctrl t it automatically sets up the connection for 
[27:25](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1645) you here are a few ways to organize your nodes you can drag with your mouse to select several nodes and then press ctrl j and it will frame these nodes you can 
[27:36](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1656) click the frame and drag the entire frame around you can still move nodes around within the frame and the frame will adjust its size as needed press in on your keyboard 
[27:44](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1664) to open up a sidebar in the shader editor here you can label the frame let's give it a nice name that you should remember you can check color and give it a color 
[27:53](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1673) background under properties you can increase the size of the label up to 64 font this is a great way to organize large node trees you can also create node groups let's 
[28:04](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1684) say we wanted this node and this node to be condensed into one single node select them and press ctrl g whoa what just happened blender created a node group with a group input then the two nodes 
[28:16](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1696) and then a group output press tab to go back to our node tree here the two nodes have been combined into one node group we can again name the group give it a color and pressing 
[28:26](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1706) tab while it's selected will take us back into the node group if we had a value inside the node group that we wanted controlled without having to tab into the node group we can connect the 
[28:37](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1717) empty socket on the group input into the value we want to control now tab out and we see we can control that strength value right here from the group node 
[28:46](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1726) super useful to stay organized in part two of this blender tutorial i'm going to cover pbr textures which use images to create super realistic materials i'll have more quick tips at 
[28:57](https://www.youtube.com/watch?v=Wg244y2f9Fw&list=WL&index=5&t=1737) the end of part two as well my name is brandon and i'm a blender artist thank you thank you thank you for all your support and i'll see you in part two stay creative 