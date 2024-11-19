---
URL: https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim
thumbnail: https://i.ytimg.com/vi/UQh0W4RD0zQ/default.jpg
channel: "[[Phoerens]]"
published: 2022-10-16T00:00:14
duration: 3061
tags:
  - video/3D/SubstancePainter
  - video/3D/playlist
done: false
cover: "[[Pasted image 20240715164101.jpg]]"
date: ""
playlist: "[[Phoerens]]"
---
[[Read it Later|Read it Later]] [time:: "51m 1s"]
[[./How to add details to your character Maya & Zbrush tutorial - Part 2|How to add details to your character Maya & Zbrush tutorial - Part 2]]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715164101.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="SUBSTANCE PAINTER TUTORIAL - How to TEXTURE a 3D character ! - Part 3" src="https://www.youtube.com/embed/UQh0W4RD0zQ?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: In this video i will show you how to setup your meshes coming from Maya and Zbrush, in order to texture them correctly inside Substance Painter; and how to import your maps inside of Maya in order to render the character using Redshift.)

Thanks for watching ! This is part 3 of the this charater tutorial, and will be the last. I hope you enjoy it, and hopefully I can learn you a thing or two ^^

These are the main topics of the video:
         .mesh exporting and naming, from zbrush & maya
         .substance painter project setup
         .mesh maps baking
         .different layers and masking modes in Painter
         .exporting the maps and importing them in Maya with redshift
         .seting up displacement
         .using subsurface scatering and cloth sheen

If you want to see part 1 & 2 : https://www.youtube.com/watch?v=KrirzdAyzGs&list=PLoQ4nMt6XaQII6MgLRFwQZTabl1eBPtnU

If you want to donwload good HDRI's : https://polyhaven.com/hdris

Concept made by Alex Braun
Music made by @TheFatRat


Chapters :
00:00 Setting up your meshes
03:32 Bake mesh maps
06:25 Texturing
30:45 Exporting the maps
33:19 Displacement setup
41:05 SSS & Cloth sheen
48:36 Render scene
50:27 Final render

▼ My ARTSTATION account (My big projects with multiple renders!):
https://www.artstation.com/phoerens


▼ My INSTAGRAM account where I post all my small & big projects!
https://www.instagram.com/phoerens_art/


✏ Comments and ideas for the next timelapses are appreciated :)
# Transcript
[00:00](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=0) Hey I'm Phoerens and in this video I will
explain my subtstance painter workflow, and i'll show you how I plug my maps in maya in
order to render my character. So if you are just interested in the texturing
process that's fine keep watching, but if you want to know how I modeled and sculpted
this lizard, I invite you to click on the link above, it will take you to the playlist
of the tutorial series and you can watch the 
[00:22](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=22) first two videos. So this is part 3, and will be the last one
of this series. Let's get started, so what do you need to
have in order to texture your character ? You need to have a model, best in tpose and symetrical,
and it has to have UV's. So I already did that in the previous videos. 
[00:40](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=40) Here i have this blank scene with just my
character mesh. You can see it is already in a pose, and it
has UVs. So all my meshes share the same UV space,
these are called UDIMS, and i applied the same shader to all of them. So in this scene I will plug my renders at
the end, and I will also do my final render 
[00:58](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=58) in it. However remember for painter it's best to
have a clean character in a tpose, because it will make the texturing process easier
in Substance painter. So I have another scene where i have my character
in a tpose, I put some props on the side, because for example the cape covered his shoulders
and I want to see everything on the body. 
[01:19](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=79) I also deleted my eyes because I won't texture
them in substance painter, i already applied a shader on it in redshift, it doesn't have
any maps applied to it, and I deleted one boot because the other side has the exact
same uv's so doing just one will result in having the texture applied to both of them
in the other scene with the pose. You can see i have the same UV's than on the
character with the pose. 
[01:44](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=104) A thing that I like to do is to rename my
meshes and end the names with underscore &quot;low&quot;. This is important in substance painter if
you want to properly bake your high poly details onto your low poly mesh. So what is baking ? Basicaly it's when you
have your mesh inside of painter, the one you will animate and use for renders, so i
won't have all the details you might have 
[02:09](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=129) added in zbrush. So to have these details and to use them for
texturing your character, you need to bake your high poly mesh coming from zbrush onto
your mesh in painter. However if you just bake your object with
everything, it will not always be correct and you wll have occluded areas where normaly
there should'nt be any. 
[02:31](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=151) So to prevent this you need to name your low
meshes ending with underscore low, and in zbrush you need to name the same meshes but
with underscore high, and then during the baking process Painter understands wich mesh
belongs to wich. So in zbzush i have the same meshes in the
same position, but they are just subdivided and thus have a lot more polygons, in order
to have all these details I added. 
[02:57](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=177) So I named them with the same names as in
maya, but instead of putting underscore low i put underscore high. So in maya I selected the whole character
and exported it in an fbx file, but with zbrush it's best to export in obj. However the obj format doesn't keep your mesh
names, so painter won't have access to them 
[03:17](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=197) during the baking process. So i exported every mesh in it's own obj,
and it's the file name that has the right name. So painter will use it's file name instead. Now in substance painter, i create a new project,
choose the template PBR - Metallic roughnes, 
[03:38](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=218) so these templates won't all have the same
attributes, and they will export your maps specificaly for the template your chose. So if you now you are going to render in keyshot,
it's good to take the keyshot template. However the PBR metallic roughness is a generic
one and works with most renders. I leave the resolution as it is, we can change
that later on, leave normalmap format on directX, 
[04:04](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=244) and I click use UV tile workflow because I
have UDIMS. So now I have my character, with it's shader
from maya assigned to it, and you can see it has it's 5 UV tiles. First i bake my high poly on my mesh. To do this go to edit, and click on bake mesh
maps. 
[04:30](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=270) I know i will export my maps in a 4K resolution,
so i will bake in 4K too. Next you can click use low poly mesh as high
poly mesh if you don't have a high poly mesh coming from zbush, but since i have them I
click on the icon and import all my high poly files. Leave the rest as it is, and below next to
&quot;match&quot;, choose &quot;by mesh name&quot;, so this way 
[04:53](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=293) he will only bake a high poly mesh that has
the same name as the low poly mesh but with underscore low. On the left you can see all the maps he will
generate, so I just unclick ID because i don't need it. One last thing, you also need to choose the
&quot;by mesh name&quot; independently for the ambient 
[05:11](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=311) occlusion, curvature and thickness maps, since
painter casts secondary rays to calculate them and you need to specify it for those
rays too. Once done, hit bake mesh maps. This can take some time depending on the resolution
you chose and on the number of UV tiles you have. 
[05:32](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=332) For me it took 9 minutes. And now you can see i have all the details
that i had in zbrush, but projected on my low poly mesh. And with these informations we can start texturing. I always start with creating folders for each
material, and in each folder I already create 
[06:32](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=392) a fill that will kind of have the base color
of the material. Now comes the masking process. First i click on the UV tile mask button on
the folder and choose on wich uv tile the folder will be applied. And to be more precise I applie a black mask
on the folder wich will hide everything, and 
[07:15](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=435) then I create a paint layer inside the black
mask, and fill with white the parts where I want the material to be shown. this is super handy because now I can put
whatever i want inside the folder, it will always just applie to the region I selected
in the mask of it's folder. Just remember, when you use masking options,
white is true and black is false. 
[07:41](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=461) So white will let your layers be seen. Once all my folders are created corectly,
i can start adding details inside of every folder. I begin with the wood material. I like to sometimes be in base color mode,
to just see the flat color without any lighting 
[08:23](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=503) or shadows. i first start with creating a fill layer,
that will contain my base color for the wood material. So this fill layer will just affect the color
so I just keep the color icon clicked. A fill layer can contain multiple fill layers,
so i create a new one inside it, and again 
[08:42](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=522) just choose the color. I then take a black and white map and plug
it in the color. This will repeat the texture map on my mesh
based on it's uvs. However you can notice the uv seems, so to
prevent that go on triplanar mode. You might need to modify the tiling of the
map. 
[09:14](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=554) i then create a level to have less contrast. So now i just ad more fill layers on top of
each other and tweak their opacity and blend mode to eventually have the black and white
details  I want. Once that done i ad a filter, and choose the
gradient filter. 
[10:14](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=614) With this i can choose which color will be
the black, white and grey values that are below. This allows to have a colored variation by
using black and white maps. So this is my base color for my wood. Now I create a brand new fill layer, choose
a lighter color, and assign a black mask to 
[11:09](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=669) it. In the black mask i ad a curvature generator,
wich will use sharp borders of my mesh to generate a mask. You can see my borders are white and the flat
zones are black inside the mask. this will let me have brighter borders on
the wood. 
[11:28](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=688) Again, masking is super handy and important,
because i just choose where my fill layer will be displayed on the mesh, and i can when
I want modifiy the color of the fill layer and tweak it as i want. So now i create another fill layer but this
time with a darker color, and again ad a black mask to it, and ad a dirt generator, to have
my dark color just inside the occulded areas 
[12:33](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=753) of my mesh. So remember, painter can only access to those
informations such as the edges and occluded areas of the mesh because we baked it. Wihtout baking the maps, you can't have access
to all these features and you miss the whole point of substance painters power. 
[12:50](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=770) Once the color values are fine, i modify the
roughness values. So the roughness values is how much the object
is reflective. 0 is reflective, and 1 is non reflective. So i activate the roughness option for all
the fill layers, and choose a right roughness value for them. 
[13:30](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=810) And since they have a black mask on them,
i can have different roughness values for each color and start to create these nice
details to make the materials more believable. Finaly i create a last fill layer that i name
color variation. Inside it i ad a map, and choose a blend mode
i like, and then lower the opacity. So that's it my wood is finished. 
[14:53](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=893) Before moving on to the next materials, I
will create a dirt material, that will be on top of everything els, and will be present
on some areas that I like. So same workflow as on the wood material,
i create a fill layer and in that fill I just ad multiple layers in order ot have the grey
values i like, and at the end I ad a color gradient filter to choose my colors. 
[17:22](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1042) On my dirt folder i ad a black mask, and a
dirt generator, so that my dirt will only be in the cavities. i also activate the height of my fill layer,
and slightly ad height value, so that the dirt is more like a layer on top everything. So I just hide it for now and will activate
it in the end. 
[18:28](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1108) I now move on to the other materials. I speed these parts up because the workflow
is the same, i basicaly do the exact same things over and over, until i have the desired
details i want. For my cloth pieces I won't ad the fabric
bump in painter, because even if i have a resolution of 4K on every UV set, it may not
be enough to show all the small cloth fibers. 
[18:52](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1132) i will ad them in maya directly. A nice generator is the UV border generator,
because it creates a mask around your UV shell borders. And since my cape is in one piece, it allows
me to have this nice worn effect on the edges of the cape. 
[20:58](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1258) So now for the lizard skin, I chose to first
ad bump information before adding the colors. So i create a fill layer, just activate it's
height values, and ad fill layer inside it. So it's way too strong, and i can choose to
lower it by simply change the opacity of the height value for my layer. I just combine different maps, and at the
end I ad an anchor point. 
[21:41](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1301) This is like a bookmark if you want, it just
remembers the things that are below it, so here it will keep the grey values from my
height. And i can use this anchor point in another
layer. So i create a layer, and in the color tab,
i go to anchor points and choose the one i just created. 
[22:00](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1320) I specifiy that I want the data from the height
channel, and now I get my height values inside my color. i then just change the fusion mode and the
opacity to have a nice color variation based on my height. So anchor points are super handy because if
i happen to modify my height, my color will 
[22:17](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1337) change accordingly because it takes the height
values that are referenced. Everyhting will just update. Now in order to ad small cartoon scales, i
create a fill layer, with a small value of height, and in it's black mask i created a
fill layer with this kind of dots map. I duplicate it, and decrease the tiling to
have a bigger map, thus bigger scales. 
[23:14](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1394) I do this to have more variation. So now every color layer i ad, i put it below
my scales, as they need to stay on top if i want the variation to be shown on every
color layer i may ad. To activate symetry, you may have to move
the symetry axe yourself, because it puts it in the midel of your scene, and thus not
in the middle of my character. 
[29:47](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1787) Now at the very end i make my dirt visible
again, and paint in a black mask where i want it to be. Now it's time to export my maps. Go to file, export textures and choose exr
format. It's a very good quality, with a losless color
range. 
[30:56](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1856) I set the size on 4K, and in the shader export
settings i unclick normal and emissive, since I won't need these maps. Once that done i have all my texture maps
for maya. However i also want black and white maps to
isolate some parts of my mesh, like the dirt, the cloth and the skin, so that i can modify
them independantly in maya. 
[31:34](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=1894) To do this i create a black fill layer, and
create a white fill layer where i want the white to be. I then export just the color into another
folder, and i do this for the different black and white masks I need. So in maya i open my blank scene with the
pose, and assigne a redshift material to my 
[33:33](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2013) whole character. I quickly create a dome light and put an HDRI
in it, to have a nice lighting during the shading part. You can download awesome hdris for free on
HDRI Haven, the link is in the comments. You can see my character is all smooth, so
we got to load the displacement on it. 
[33:54](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2034) I like to take a normal AOV, it helps me to
visualize the strenght of the normals. In order to have displacement on your model,
you need to activate it in each meshes shading properties, so I just check if every mesh
has it activated. You also want to activate tesselation, so
the mesh will be subdivided during render time. 
[34:50](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2090) So I already created and exported my displacement
maps from zbrush, I did that in the last video, wich is part 2. To have displacement I go in hypershade, create
a displacement shader, and import my displacement maps. So remember I have udims, so i just need to
import the first map, and i just need to specify 
[35:08](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2108) it's a udim map so that he understands that
there are more. I put it in the displacment node, and i plug
that into the displacement shader node. You can now see that i have all of my details
on my mesh. The difference is the most visible on the
wooden staff. That done, I also need to have my bump from
substance painter. 
[35:49](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2149) So i just create another displacement node,
and import my bump map from painter. Since it's an exr, i need to switch from srgb
to raw, otherwise he will put a color correction on my maps. At first it's always way too strong when it
comes from painter, so i just decrease the scale value intul i have the result i had
in painter. 
[36:44](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2204) So now i have my displacement from painter
but i have lost the one coming from zbrush, so to mix them and to keep both, i create
a displacement blender node, plug both maps, and I set the weight of the second map to
1, otherwise it isn't visible, and set it to additive mode, to have both maps. Now i import my metalnesss and roughness maps. 
[37:24](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2244) So i need to plug my roughness in the reflection
roughness slot, and not in the reflection weight like i just did here, I made a mistake
here sorry for that, and to have metalness i need to switch the fresnel type to metalness,
but the slot isn't visible so i need to hold the middle mouse buton while holding down
shift, and plug it directly on the metalness value. 
[37:59](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2279) Whe are not done yet with the displacement
becasue need to ad the cloth patern on my cape and the tissue from the staff. First I import my cloth mask, wich is a black
and white map, where only my cape is white and the rest is black. Then I take a cloth bump map, so you can get
these on the internet, or I bought these ones 
[38:53](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2333) on the artstation market. So again i create a displacement node, and
plug it into another slot in the displacement blender node, and I plug my mask map into
the displacement weight, so that will apply this displacement map only where there is
white on my mask, for instance only on the cape. 
[39:20](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2360) I plug my cloth bump into the displacement
node, and just modify the scale and also the repetition of my map to have a smaller pattern. Now i just do the exact same thing but with
another mask for just the tissue around the staff, and with another bump map. So now all my displacement is done, I can
move on to the rest. 
[41:26](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2486) Now I have put all my maps on my character
and you could say it's done. But actually to take my character to the next
level, I need to ad more specific attributes for some parts of my mesh, like for example
subsurface scatering on my skin, and sheen on my cloths. So basicaly subsurface scatering, or also
SSS, is when light goes into a surface, takes 
[41:50](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2510) a color, like red for the skin, and goes back
out. It ads so much more realism and makes your
characters more alive. So sss is not just on skin, it's also on all
types of organic things like plants, clay, platic, even marble. And the sheen is to fake all the tiny strings
you would have on a cloth, and that would 
[42:14](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2534) ad this nice rough spec on your cloths. So to ad this and to have better control on
my different materials, I will create a new redshift material for my skin, my dirt, my
cape and my tissue. I will then blend them together just like
i did with the displacement. So i create a material blend node, and plug
in my different materials. 
[42:55](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2575) And it's the output of my mixed material that
will go into the shader node. All my materials still have the same color,
roughness and metalness information, so i just plug them into every shader. Now i import all my masks, and plug them into
the blend color node of every material. So again, each material will only be showed
where there is white on my mask maps. 
[46:02](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2762) So now you see if I change something in my
skin material, it will only affect on my skin. So this alows me to change some minor details
for every material, for example i want the skin to be a bit more saturated, so I take
a color corrction node, and put it between the color node and the lizard skin material. Now I set my sss amount on 1, because skin
is a fully subsurface material. 
[46:36](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2796) I take a red color, because the light that
will pass trhrough the skin will take a redish color, because of the blood. i just need to change the radius, because
the radius determines wich distance the light can travel inside the mesh. A value of 1 can be fine if you have a biger
model, but since my model is small i need 
[46:54](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2814) to set the radius on a low value. Now I will aply some sheen on the cape. So I first make the cape a little more dark
with a color correction node. I then apply some sheen to it. So that's it, my lizard is done, now i can
render it with a nice lighting. 
[48:44](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2924) I took the time to make a nice looking render,
so i have this scene with a backdrop behind my character, so it's something a lot of people
do to have a smooth looking background and to not have pure black behind the character;
I have a 3 lighting setup, so it's very basic but it works well: so i have a light from
the top, a light on the side, and a rim light that's behind the character. 
[49:15](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=2955) I also added some dust particles with mash,
so I just modeled 4 different dust meshes, so you can see they are not detailed but they
are super small in the scene so it doesn't matter; and i just scattered them using mash,
wich is a scattering tool in maya. I also animated them slightly, so that during
my turn they slightly move. So this is my final render angle, you can
see the effect of my different lights, oh 
[50:11](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=3011) and i also added a point light in the middle
of the staff, to do a kind of magic lighting. So this was the last video of this little
series, I hope you found it usefull, let me know if you want some other tutorials, otherwise
I will just make some regular timelapses, and I try to publish every week a timelapse. So yeah thanks for watching and stay tuned. 
[50:46](https://youtu.be/UQh0W4RD0zQ?si=Blpz3pBqCkkIVLim&t=3046) Bye guys ! 