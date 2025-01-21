---
URL: https://www.youtube.com/watch?v=1jWNeLujtV8
thumbnail: https://i.ytimg.com/vi/1jWNeLujtV8/default.jpg
channel: "[[Tawan Sunflower]]"
date: 
published: 2023-12-29T04:07:52
duration: 748
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715180627.jpg]]"
q-data:
  leech-count: 1
  due-at: 2024-07-24T18:00:00.000Z
---
[[Read it Later|Read it Later]] [time:: "12m 28s"]
# Make 3D Renders Look Like Paintings | Blender Tutorial
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715180627.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Make 3D Renders Look Like Paintings | Blender Tutorial" src="https://www.youtube.com/embed/1jWNeLujtV8?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Today I will show you how to make any render looks like a painting!)
________________________________
👇Parts👇

00:00 - Introduction
00:57 - Part 1 : Geometry | Aligning Instances to the Camera
02:36 - Storing Attributes and Final Touches
04:25 - Part 2 : The Shader Magic | Brush Texture
05:19 - Setting up the Transparency
05:54 - Fixing the Normals
06:26 - Removing Brush Shadows
07:00 - Part 3 : The Secret Techniques
07:19 - Fixing the Rotation
08:27 - Color Randomization
10:03 - Using Toon Shader
10:48 - Finishing the Geometry Nodes
11:08 - Using the Setup on Other Objects
11:51 - The End


________________________________________________
📙Links📙

fjsmu - https://twitter.com/fjsmu

________________________________________________
❤️ SUPPORT THE CHANNEL ❤️

Patreon: https://www.patreon.com/TawanSunflower
Gumroad (Free Tutorial Files): https://tawansunflower.gumroad.com/

________________________________________________
💬Socials💬

Linktree: https://linktr.ee/tawansunflower
Twitter: https://twitter.com/himawari_hito

# Transcript
[00:00](https://www.youtube.com/watch?v=1jWNeLujtV8&t=0) you have probably known about blender the all-in-one software it does re effects drawing re editing coding you name it but the best thing that blender can do is 3D Blender exhales at photo 
[00:11](https://www.youtube.com/watch?v=1jWNeLujtV8&t=11) realistic rendering capturing every Reflections bump scratches with perfection although sometimes we don't want to replicate reality entirely now take again at these scenes they are made 
[00:24](https://www.youtube.com/watch?v=1jWNeLujtV8&t=24) in 3D but how all the liners the colors and the effects just make them look like 2D illustrations it just looks very hard to do in 3D back then I have no idea how these scenes were created but today I 
[00:39](https://www.youtube.com/watch?v=1jWNeLujtV8&t=39) want to challenge myself to recreate this illustration in 3D most specifically I want to figure out how to recreate those breathtaking brush drugs that just make you question reality it's 
[00:50](https://www.youtube.com/watch?v=1jWNeLujtV8&t=50) just looks perfect in its own [Music] way so I think you all know the most important step by now let's start off by 
[01:05](https://www.youtube.com/watch?v=1jWNeLujtV8&t=65) deleting this Cube and add a different Cube by pressing shift a mesh and Q people have been asking me a lot why I do this it's 
[01:15](https://www.youtube.com/watch?v=1jWNeLujtV8&t=75) um it's it's because um anyways let's dive into the geometry note here I will click new and we should be able to do the magic first I would add distribute points on faces note this 
[01:29](https://www.youtube.com/watch?v=1jWNeLujtV8&t=89) redistribute points on top of our Cube and next I will add an instance on points node this will replace the points with an instance but because we don't have an instance object yet the whole 
[01:39](https://www.youtube.com/watch?v=1jWNeLujtV8&t=99) thing just disappear so I search for GD and plug the mesh into the instance now you can see a lot of Grid or planes in your wheel Port as you can see it's too big so I reduce the size a little bit 
[01:52](https://www.youtube.com/watch?v=1jWNeLujtV8&t=112) right now the planes are not facing the camera so we had to add something to the rotation I will add an object info note this this will allow us to get information about all the object in the 
[02:02](https://www.youtube.com/watch?v=1jWNeLujtV8&t=122) scene and I want to get the location of our camera so I select the camera from this drop down and choose relative next I will add a position node and grab two more nodes which are vector MTH and 
[02:13](https://www.youtube.com/watch?v=1jWNeLujtV8&t=133) align all the to Vector set the vector map to subtract let's connect them up set the Align all the to Vector to c-axis and then pluck the rotation and 
[02:25](https://www.youtube.com/watch?v=1jWNeLujtV8&t=145) there we go all the planes are facing the camera now [Music] now let's add a join geometry node and plug in the original Cube and the planes 
[02:43](https://www.youtube.com/watch?v=1jWNeLujtV8&t=163) together now I see that some planes are clipping through the cube so I want to move them forward to the camera by adding this translate instances node just after the instance on point node 
[02:56](https://www.youtube.com/watch?v=1jWNeLujtV8&t=176) and I will drag the C down a little bit see it's is moving towards the camera then let's add a set material note so that we can add material to the planes 
[03:09](https://www.youtube.com/watch?v=1jWNeLujtV8&t=189) later let's add a store name attribute note so that we can store some information of our geometry allowing us to use them later in the Shader put one of them here and set the 
[03:20](https://www.youtube.com/watch?v=1jWNeLujtV8&t=200) name to UV map change the type to vector and plug in the UV map of the grid into the node drag the other one and put it just after the translate instance node set 
[03:33](https://www.youtube.com/watch?v=1jWNeLujtV8&t=213) the name to normal select Vector change from point to instance and plug in the normal back from the dist points on face node to this node then let's add a self object node 
[03:45](https://www.youtube.com/watch?v=1jWNeLujtV8&t=225) and an object info node plug in the self object and the object info together and grab another node called Vector rotate we want to rotate the normal by the rotation of our sub object change 
[03:58](https://www.youtube.com/watch?v=1jWNeLujtV8&t=238) the type to Al and put it just before restore the normal and plug in the rotation of the cell object into the rotation of the vector rotate node and there you go just a few notes some 
[04:09](https://www.youtube.com/watch?v=1jWNeLujtV8&t=249) camera tricks and voila you've got a forest of planes that would make even an airline [Applause] tless now let's talk about 
[04:25](https://www.youtube.com/watch?v=1jWNeLujtV8&t=265) [Music] Shader first you will need a brush texture forget about buying an actual brush and pain you can do it but we are in the digital age my friends so what I 
[04:38](https://www.youtube.com/watch?v=1jWNeLujtV8&t=278) would do is casually yeah save that Masterpiece as a transparent jpg and then we can use it later now back in blender click on material properties click new material 
[04:52](https://www.youtube.com/watch?v=1jWNeLujtV8&t=292) name it and in Geometry node set the material to the one you just created in the Shader we're can add two attribute nodes set the name to UV map and normal add an image texture Noe and 
[05:06](https://www.youtube.com/watch?v=1jWNeLujtV8&t=306) find the brush texture that we just created then plug UV map Vector output into the image texture now we will see our brush texture on our planes when we build the alpha of the 
[05:16](https://www.youtube.com/watch?v=1jWNeLujtV8&t=316) [Music] image now add the mix node and set the first input to one plug the alha of the image into the B input and set the normal attribute type to in 
[05:28](https://www.youtube.com/watch?v=1jWNeLujtV8&t=328) sensor plug the alpha into the factor and plug the result of the mix node into the principal bsdl then plug the bsdf into the 
[05:38](https://www.youtube.com/watch?v=1jWNeLujtV8&t=338) material output after that we have to change the blend mode to Alpha hash and the shadow mode to Alpha clip and then let's see the 
[05:48](https://www.youtube.com/watch?v=1jWNeLujtV8&t=348) result oh wait um all right we rotated our plane so now the normal is facing the wrong way and I think I know exactly how to fix it you 
[06:02](https://www.youtube.com/watch?v=1jWNeLujtV8&t=362) might remember that we use the store name attribute node to start the correct normal in the geometry node that's right we will fix the normal with some Shad of magic so we need to correct them with a 
[06:12](https://www.youtube.com/watch?v=1jWNeLujtV8&t=372) setup like this and let's see the result then plug the result into the normal of the principal bsdf now let's get rid of the brush Shadow by adding a math node setting it 
[06:25](https://www.youtube.com/watch?v=1jWNeLujtV8&t=385) to multiply and add a light path node connect them like this [Music] this plug the bsdf of the principal Shader into the material output and 
[06:38](https://www.youtube.com/watch?v=1jWNeLujtV8&t=398) there you [Music] go let's go back to Geometry node to turn up the density of the brush a little bit so that it's more brush 
[06:47](https://www.youtube.com/watch?v=1jWNeLujtV8&t=407) strokes and there it is painter Cube but hold on we are not done just just yet you see when I press n on the viewport and lock the camera to view and 
[07:06](https://www.youtube.com/watch?v=1jWNeLujtV8&t=426) move the camera the brush seem to rotate in an unpredictable way and the color seems a little bit flat doesn't it I want to add some Randomness into the color and make this even more paintly so 
[07:19](https://www.youtube.com/watch?v=1jWNeLujtV8&t=439) let's first fix the rotation grab a combine XYZ and align all to Vector a vector math and Vector rotate we set the Y to 
[07:32](https://www.youtube.com/watch?v=1jWNeLujtV8&t=452) one PLU the vector into the vector of the vector rotate change the type to other and plug the rotation of the camera to the vector [Music] 
[07:43](https://www.youtube.com/watch?v=1jWNeLujtV8&t=463) rotate now change the vector math node to cross [Music] product then plug the output of the subtract node into the cross product 
[07:58](https://www.youtube.com/watch?v=1jWNeLujtV8&t=478) plug the vector rotate into the cross product put the new align Aller to Vector node in between the rotation output and the rotation input of the instance on points node then plug the 
[08:08](https://www.youtube.com/watch?v=1jWNeLujtV8&t=488) output of the cross product node into the input of the Align all to Vector after that we can add a rotate all [Music] node set it to local then we can put in 
[08:21](https://www.youtube.com/watch?v=1jWNeLujtV8&t=501) any custom rotation we want then let's do the randomization duplicate this store name attribute number for the normals and change the name to random add a random 
[08:32](https://www.youtube.com/watch?v=1jWNeLujtV8&t=512) value node and set the mode to rector set the minimum to negative one on the xyc then plug the value into the store attribute no now jump back to the Shader let's randomize the brush color I will 
[08:45](https://www.youtube.com/watch?v=1jWNeLujtV8&t=525) add a hue saturation color and a separate color node then duplicate the normal attribute node change the name to random be sure that the type is set to inst staner and plug the color into the 
[08:56](https://www.youtube.com/watch?v=1jWNeLujtV8&t=536) separate color node now you see that each color give us a random -1 to one value but we need to analyze how the Hue saturation value node works first so this value 0.5 for the heel one for the 
[09:09](https://www.youtube.com/watch?v=1jWNeLujtV8&t=549) saturation and another one for the value is the default values for this node which mean that right now the node does not do anything to our selected color but the more we deviate from these 
[09:20](https://www.youtube.com/watch?v=1jWNeLujtV8&t=560) values the more the output color changes so I will add three math nodes and send them all to multiply add plug the red into the first one and then into the hue of the H saturation value node now this 
[09:31](https://www.youtube.com/watch?v=1jWNeLujtV8&t=571) multiplier acts as the factor for how much we want to change the color of our brushes then do the same with green and blue and connect them to saturation and value be sure to set the added of the 
[09:43](https://www.youtube.com/watch?v=1jWNeLujtV8&t=583) green and blue to one because remember the initial value of saturation and value is one and then we got the slider for this input too then look at that now we got color randomization for our 
[09:55](https://www.youtube.com/watch?v=1jWNeLujtV8&t=595) brushes and you know what I think I can use the tune Shader I made my my previous video If you haven't seen it please check it out I will import it and I will replace the principal bsdf with 
[10:06](https://www.youtube.com/watch?v=1jWNeLujtV8&t=606) the tune Shader plug just the normal for now and then we can plug the result of our tune Shader into the color input of our Hue saturation value now our tun Shader does not have an alpha input so 
[10:19](https://www.youtube.com/watch?v=1jWNeLujtV8&t=619) we have to implement that ourselves grab a transparent node and a mixture the node then plug the node like this then plug the alpha into the factor of our mix Shader also make sure to set 
[10:33](https://www.youtube.com/watch?v=1jWNeLujtV8&t=633) the world color to Black and change the real transform to standard and there you go that's is a painter Cube then the last thing that we need to 
[10:45](https://www.youtube.com/watch?v=1jWNeLujtV8&t=645) do is to edit the geometry note a little bit so it will be easier to use in the future I will duplicate the group input plug the sizes and the 
[10:56](https://www.youtube.com/watch?v=1jWNeLujtV8&t=656) density I will duplicate it again and plug in the custom rotation and duplicate again and plug in the material rename this to paintery brush 
[11:07](https://www.youtube.com/watch?v=1jWNeLujtV8&t=667) and there you go now I can add other objects go to modifiers select geometry node and select the paintery brush from the doop down adjust some parameters create a new material make 
[11:21](https://www.youtube.com/watch?v=1jWNeLujtV8&t=681) sure to select that new material in the modifiers too and copy and paste the same Shader setup earlier into the new material [Music] 
[11:33](https://www.youtube.com/watch?v=1jWNeLujtV8&t=693) and do this a couple of times and here's the final outcome of the [Music] study and there you go that was a long 
[11:55](https://www.youtube.com/watch?v=1jWNeLujtV8&t=715) journey but look at our creation we have created a new G comary note setup ready to be used in any scene we want all right everyone I think we have reached the end of this episode non photo 
[12:07](https://www.youtube.com/watch?v=1jWNeLujtV8&t=727) realistic rendering is a vast Universe with Endless Possibilities I hope that the stuff in this video was useful for you guys to start your own Journey if you have any questions or suggestion 
[12:18](https://www.youtube.com/watch?v=1jWNeLujtV8&t=738) feel free to comment down below thank you guys so much for watching until next time stay positive and happy blending 