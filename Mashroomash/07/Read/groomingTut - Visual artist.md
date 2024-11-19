---
URL: https://www.deniszen.com/groomingtut
thumbnail: 
site: "[[Visual artist]]"
date: 2024-09-20T17:44:47
duration: 18
topics: 
done: false
cover: 
---
# groomingTut | Visual artist

## INTRODUCTION

During my last Summer holidays, I spent some time to write this tutorial to share what I learned during almost two years of research and development. 

Grooming is a challenging task. There are billions of haircuts, and trusting only your references sometimes is not enough. The more you know about hair and hairstyles, the better your results will be.

Knowing how hairdressers work is crucial if you want your grooming to be realistic, especially if you will simulate the hair.  This tutorial aims to mimic real-world procedures using 3D grooming tools. It's a quick guide where you can find many production tips to speed up your work and keep things well organized.

Using this method, you will easily groom any hairstyle.
`````col
````col-md
flexGrow=1
===
![groom1.jpg](https://static.wixstatic.com/media/b46b09_d0aff5def76a46d7ab5e1bf5cf96b831~mv2.jpg/v1/fill/w_322,h_414,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groom1.jpg)

![groom2.jpg](https://static.wixstatic.com/media/b46b09_57a7d66c876e433ba22c7e2badf82661~mv2.jpg/v1/fill/w_376,h_414,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groom2.jpg)

````
````col-md
flexGrow=1
===
![groom3.jpg](https://static.wixstatic.com/media/b46b09_f9949966d3d44e2d9283ac65ec2357a4~mv2.jpg/v1/fill/w_345,h_414,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groom3.jpg)

![groom4.jpg](https://static.wixstatic.com/media/b46b09_03ebf912836e497897f067009100a602~mv2.jpg/v1/fill/w_359,h_414,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groom4.jpg)
````
`````

To better follow the tutorial, you can download a simple scene withe the base graph here:

[Download](https://drive.google.com/file/d/16dCVpBYroUy_llqO5B9Y6wkr7J6HxrYq/view?usp=drive_link)

Using this menu, you can easily go through it as many times as you want:

- [HAIR](https://www.deniszen.com/groomingtut)
    - [scalp zones​](https://www.deniszen.com/groomingtut)
    - [hairline](https://www.deniszen.com/groomingtut)
    - [baldness](https://www.deniszen.com/groomingtut)
    - [growing direction](https://www.deniszen.com/groomingtut)  
- [HAIRSTYLES](https://www.deniszen.com/groomingtut)
    - e[levation and cutting angles​](https://www.deniszen.com/groomingtut)
    - [haircut planning](https://www.deniszen.com/groomingtut)  
- [HOUDINI](https://www.deniszen.com/groomingtut)
    - [scalp creation​](https://www.deniszen.com/groomingtut)
    - [guides](https://www.deniszen.com/groomingtut)
    - [node anatomy](https://www.deniszen.com/groomingtut)
    - [hda](https://www.deniszen.com/groomingtut)
    - [start grooming](https://www.deniszen.com/groomingtut)
    - [using a single node](https://www.deniszen.com/groomingtut)
    - [guide sculpting](https://www.deniszen.com/groomingtut)
    - [first example](https://www.deniszen.com/groomingtut)
    - [sculpting tips](https://www.deniszen.com/groomingtut)
    - [second example](https://www.deniszen.com/groomingtut)  
- [CONCLUSIONS](https://www.deniszen.com/groomingtut)  
- [RESOURCES](https://www.deniszen.com/groomingtut)

Let's dive in

# HAIR
 
Thickness and amount

"Hair with a small diameter—or fine hair—has a typical diameter of about 50 microns," Spengler explains. "Hair with a larger diameter—or coarse hair—has a typical diameter of about 120 microns."

For comparison's sake, a piece of copy paper is 70 microns thick."

"Those with thin hair might have about 80,000 fibers on their head, and an individual with thick hair will have about 150,000 fibers," Spengler says. "The greater the number of fibers, the greater the interaction between each fiber." In other words, dense hair usually looks and feels fuller than thin hair."

Extract from [Byrdie.com](https://www.byrdie.com/find-your-hair-type#:~:text=%22Hair%20with%20a%20small%20diameter,paper%20is%2070%20microns%20thick.)

But thickness and number vary within the scalp, too.​ For this reason is important that you add a couple of nodes at the bottom of your graph (so Houdini calculates this only at the end) that do the job.

If you are a nerd, you can use vex to do this. If you are not, like me, you can use an "Attribute Randomize" to randomly change the hair strand width.  
​
But @width is a "point attribute", which means that the variation is per point:

`````col
````col-md
flexGrow=1
===
![pointAttr.jpg](https://static.wixstatic.com/media/b46b09_fd338c4de83f40e8882b104398541136~mv2.jpg/v1/fill/w_307,h_200,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/pointAttr.jpg)
````
````col-md
flexGrow=1
===
![pointWidth.jpg](https://static.wixstatic.com/media/b46b09_5fa73764bce34921be9dcc7bd591f003~mv2.jpg/v1/fill/w_129,h_200,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/pointWidth.jpg)

````
`````

So, to get it to work on primitives (the hair strands), you have to "promote" this attribute:

![attrPromote.jpg](https://static.wixstatic.com/media/b46b09_8b55a7c283b242d58087c4032ff8db0d~mv2.jpg/v1/fill/w_348,h_423,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/attrPromote.jpg)

Now you can add the "Attribute Randomize" node to vary hair strand width:

`````col
````col-md
flexGrow=1
===
![attrRandomize.jpg](https://static.wixstatic.com/media/b46b09_0a36fbf0a91c40a18d26a3556f06a9d5~mv2.jpg/v1/fill/w_251,h_478,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/attrRandomize.jpg)
````
````col-md
flexGrow=1
===
![strandsWidth.jpg](https://static.wixstatic.com/media/b46b09_61ad7d0e4b26484894e7c084ffad88e2~mv2.jpg/v1/fill/w_249,h_478,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/strandsWidth.jpg)
````
`````

Now, the tapering, since the tip is thinner than the root. To do this, you can use the "curveu" attribute (which goes from 0 to 1 along the curve) and times it with the width attribute.

Since curveu is a point attribute, we have to bring the width attribute to its point attribute nature using an "attribute promote" node (as you did before). After that, using some very simple vex, you can get a realistic hair strand:

![tapering.jpg](https://static.wixstatic.com/media/b46b09_4bf1c84f8d4a416d9e53856011b7fe97~mv2.jpg/v1/fill/w_251,h_366,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/tapering.jpg)

In the first line, I invert the curveu direction (since it is 0 at the root and 1 at the tip), and in the second line, I time it with the width.

The value I add at the end is extremely important. Since the lowest curveu value is 0, if I did not add it, I would get a curve ending in nothing. And this is not what happens in reality. Hair gets thinner, but never a 0 value:

`````col
````col-md
flexGrow=1
===
![tapering.gif](https://static.wixstatic.com/media/b46b09_d8a337c5ce7a455cb4028af0106b35d5~mv2.gif)
````
````col-md
flexGrow=1
===
![tips.jpg](https://static.wixstatic.com/media/b46b09_60076c60fcd84e26ada3fb5deb4b8b0c~mv2.jpg/v1/fill/w_600,h_368,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/tips.jpg)
````
`````

Variation is very important, and you have to use it for as many parameters as you can. Each strand is different in shape and color, and keeping this in mind makes the difference.

## SCALP ZONES
 
The scalp is the common word used for the head area where hair grows and it is subdivided into different zones:

![scalpZones.jpg](https://static.wixstatic.com/media/b46b09_4c762846cbb44a1abd70d1032b1e7c8d~mv2.jpg/v1/fill/w_600,h_317,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/scalpZones.jpg)

Actually, things are a little bit complex, and you could divide the scalp more precisely:

`````col
````col-md
flexGrow=1
===
![moreScalpZones.jpg](https://static.wixstatic.com/media/b46b09_c620326f317944ba851438f13ea2a520~mv2.jpg/v1/fill/w_393,h_373,al_c,q_80,enc_auto/moreScalpZones.jpg)
````
````col-md
flexGrow=1
===
![scalpMeshComplex.jpg](https://static.wixstatic.com/media/b46b09_e099c08c165c4d17bc48523b52aa4fdb~mv2.jpg/v1/fill/w_349,h_346,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/scalpMeshComplex.jpg)
````
`````

## HAIRLINE

Hairline is the word used to identify the front part of the scalp, it has different shapes, and changes a little bit from men to women:
 
`````col
````col-md
flexGrow=1
===
![hairlineVar.jpg](https://static.wixstatic.com/media/b46b09_71212019986342f3964582253f210c0f~mv2.jpg/v1/fill/w_384,h_506,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hairlineVar.jpg)
````
````col-md
flexGrow=1
===
![hairlineManVar.jpg](https://static.wixstatic.com/media/b46b09_93bba93f5a2c4783a087a4258d9a0a33~mv2.jpg/v1/fill/w_361,h_366,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hairlineManVar.jpg)
````
`````
[healthline.com](https://www.healthline.com/health/hairline-types)

## BALDNESS

As time goes by, hairline, especially in men, varies considerably. The Norwood scale is the reference for this change:
 
![norwoodScale.jpg](https://static.wixstatic.com/media/b46b09_7ce0a1c2ca7446d8a63563c7946c0778~mv2.jpg/v1/fill/w_394,h_557,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/norwoodScale.jpg)
[healthline.com](https://www.healthline.com/health/norwood-scale)

Baldness can be a good ally for your groomers, and you can quickly get many variations. This could be useful for B characters, for example, or if you want to have an elder version of your  hero:

![Baldness.jpg](https://static.wixstatic.com/media/b46b09_d9e0ec7941e94c36be688c51e093b811~mv2.jpg/v1/fill/w_653,h_793,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/Baldness.jpg)

## GROWING DIRECTION

Another critical aspect to take into consideration is how hair grows. This is especially important in short and mid-haircuts. Once again, the references help you, but having this knowledge is essential.​

The most critical point in terms of direction is the crown:
 
`````col
````col-md
flexGrow=1
===
![swirl.jpg](https://static.wixstatic.com/media/b46b09_17acfc5544564faea354907ae39e2cb9~mv2.jpg/v1/fill/w_600,h_431,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/swirl.jpg)
````
````col-md
flexGrow=1
===
![hairFlow.jpg](https://static.wixstatic.com/media/b46b09_ecf7edc08ef54c7caa3a6c5aa848a102~mv2.jpg/v1/fill/w_500,h_497,al_c,q_80,enc_auto/hairFlow.jpg)
````
`````

# HAIRSTYLES: MACRO CATEGORIES

Even if there are billions of haircuts, they can be divided into 4 categories:​
`````col
````col-md
flexGrow=1
===
### BUZZ CUT
![buzzcuts.jpg](https://static.wixstatic.com/media/b46b09_d958550c507f4d6fb53adb120e0faf3f~mv2.jpg/v1/fill/w_285,h_331,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/buzzcuts.jpg)

### PIXIE
![pixie.jpg](https://static.wixstatic.com/media/b46b09_9ee3726e84724e05ac41b0c29a6d091c~mv2.jpg/v1/fill/w_284,h_331,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/pixie.jpg)
````
````col-md
flexGrow=1
===
### BOB CUT
![Bob.jpg](https://static.wixstatic.com/media/b46b09_8cdea209b85f498dad56c5af926f4152~mv2.jpg/v1/fill/w_285,h_331,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/Bob.jpg)

### MID - LONG
![midLong.jpg](https://static.wixstatic.com/media/b46b09_118e52bbc139415e8d35748f5df0cf5d~mv2.jpg/v1/fill/w_285,h_331,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/midLong.jpg)
````
`````

As you can notice, the main difference is the length of the scalp zones. ​

## ELEVATION AND CUTTING ANGLE

![elevation.jpg](https://static.wixstatic.com/media/b46b09_7279f10516ed464a800a8f35c98f6010~mv2.jpg/v1/fill/w_600,h_430,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/elevation.jpg)

Elevation determines if the hairstyle is:
- LAYERED
- GRADUATED
- BLUNT (one length)

If you elevate the hair from 90° to 180° and you cut it, the bottom strands are longer than the above ones, and once they reach the rest position, the volume decreases:

![90Layered.jpg](https://static.wixstatic.com/media/b46b09_fe53582eef5144bf90a7502ab8d2fa8c~mv2.jpg/v1/fill/w_600,h_299,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/90Layered.jpg)

![180Layered.jpg](https://static.wixstatic.com/media/b46b09_fe8e1f55a0e341518698a30c8351e5e6~mv2.jpg/v1/fill/w_600,h_299,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/180Layered.jpg)

![volume.jpg](https://static.wixstatic.com/media/b46b09_4b348de8c0bb4c63a575b0540875e46c~mv2.jpg/v1/fill/w_600,h_363,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/volume.jpg)

Opposite, from 90° to 0°, the volume increases (maximum at 0°):

![graduated.jpg](https://static.wixstatic.com/media/b46b09_676f0fc0c03e48f8a7e5f343421d5f40~mv2.jpg/v1/fill/w_600,h_576,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/graduated.jpg)

![volumeIncrease.jpg](https://static.wixstatic.com/media/b46b09_2e0926ec4ce0428fb45c4dd7a1956f00~mv2.jpg/v1/fill/w_600,h_363,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/volumeIncrease.jpg)

So, as you can see, working with scalp zones and elevation lets you create any kind of hairstyle. Not convinced? Let's see how real hairstylists work.

## HAIRCUT PLANNING

If you had the chance to look at those hairdresser magazines, you probably noticed the haircutting diagrams.  They are a visual project hairstylists use to explain how they get the result.

[Hairtech](https://hairtechapp.com/) is an app that helps hairdressers do the job:

![hairtechDiagrams.jpg](https://static.wixstatic.com/media/b46b09_aacce4c0043b4f0ba1ebf2fe2c7b7ddb~mv2.jpg/v1/fill/w_600,h_283,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hairtechDiagrams.jpg)

As you notice from these diagrams, the elements that build the haircut are elevation, cut angle, and scalp zones. Other than that, you can see multiple lines inside each scalp zone. They identify the sections, something we don't need to consider for now.

Before approaching the tech part in Houdini, please have a look at this video:

[![pixieVideo.jpg](https://static.wixstatic.com/media/b46b09_e5170ad99b5b40dc8cb99526a70f3c5f~mv2.jpg/v1/fill/w_600,h_410,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/pixieVideo.jpg)](https://www.youtube.com/watch?v=o-wqvc42NzQ)

# HOUDINI

Now it's time to see how we can approach all this in Houdini.

The first task is to build the scalp and subdivide it. You can do it in different ways. I decided to use a method that I can use on multiple heads without starting from scratch every time.

Let's dive in.​

## SCALP CREATION

![scalpModelling.jpg](https://static.wixstatic.com/media/b46b09_8758eca9f23046cf9bc6f055c7e9ed39~mv2.jpg/v1/fill/w_238,h_522,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/scalpModelling.jpg)
`````col
````col-md
flexGrow=1
===
After importing the head, I subdivided it (to have more resolution), and I painted the hairline, which I will use as a guide for the scalp mesh and, later, as a growing region (for guides and hair).
````
````col-md
flexGrow=1
===
Then, using TopoBuild, I first built one side of the skull, mirrored it, and finally used a Fuse node to have one single piece of geometry:
````
`````
`````col
````col-md
flexGrow=1
===
![01.gif](https://static.wixstatic.com/media/b46b09_56a62bd7c2e540c59547dd9a3d52d134~mv2.gif)
````
````col-md
flexGrow=1
===
![02.gif](https://static.wixstatic.com/media/b46b09_67d9a16ba05a42a888d1d07d7315ef65~mv2.gif)
````
`````

Now it's time to subdivide the scalp:
`````col
````col-md
flexGrow=1
===
![coloredScalp.jpg](https://static.wixstatic.com/media/b46b09_0bb7a8f3468c499a9f8ad0f11405db78~mv2.jpg/v1/fill/w_443,h_425,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/coloredScalp.jpg)
````
````col-md
flexGrow=1
===
![zones.jpg](https://static.wixstatic.com/media/b46b09_32f3afb3cefc4847addfe55f2dc3fe2e~mv2.jpg/v1/fill/w_262,h_600,al_c,q_80,enc_auto/zones.jpg)
````
`````

I used a Group Create node and a Color node after that (I could have used a Name node, but this way is more clear):

![groupCreate.jpg](https://static.wixstatic.com/media/b46b09_526c7e2522f44253abd7f546731cd4ec~mv2.jpg/v1/fill/w_419,h_478,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groupCreate.jpg)

If you want not to have so many nodes in your graph, you can collapse them into a subnet:

![collapse.jpg](https://static.wixstatic.com/media/b46b09_3c96b0cc1a034680ae50c4caaab5ea55~mv2.jpg/v1/fill/w_600,h_636,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/collapse.jpg)

## GUIDES

Time to add the guides. Simply use a Hairgen node and connect its first input (skin) with the output of the last color node. Use Total Count for the amount of the guides and Relax Iterations to evenly distribute them:

`````col
````col-md
flexGrow=1
===
![hairGuides.jpg](https://static.wixstatic.com/media/b46b09_778cce5d624944daabab098fc0108a8a~mv2.jpg/v1/fill/w_313,h_646,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hairGuides.jpg)
````
````col-md
flexGrow=1
===
![scalpGuides.jpg](https://static.wixstatic.com/media/b46b09_191962bcd2db49e9abbcea0d00b26f1c~mv2.jpg/v1/fill/w_542,h_500,al_c,q_80,enc_auto/scalpGuides.jpg)
````
`````

Now, we need a tool to adjust each zone length. We can use a Length (Guide Process) node for each group - zone we created. But before that, we have to transfer the groups from the skin (we selected polys) to the guides using a Group Transfer node:

![groupTransfer.jpg](https://static.wixstatic.com/media/b46b09_0339b5bc06754a6fbea1766a8648c045~mv2.jpg/v1/fill/w_277,h_602,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groupTransfer.jpg)

## NODE ANATOMY

At this point, it is worth to spend some time speaking about the anatomy of the node. We use them all day, but, especially we artists, do not pay attention to what is inside them.

I'd like to handle it now to explain why we need to transfer groups.

![nodeAnatomy.jpg](https://static.wixstatic.com/media/b46b09_6ce14d468da144408d54f683c4c54044~mv2.jpg/v1/fill/w_600,h_410,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/nodeAnatomy.jpg)

To access this window, go over the node and click the "i" icon on the left. To stick it, click the pin on the left top corner.

The important info is those inside the red rectangles: number of Points, Primitives and Polygons, Point Attributes, and Primitive attributes.

As you have noticed, no groups are listed. But we created them, so where did they go?

They are there, but we are looking in the wrong place since the info window relates to the first output of the node. 

To see the other outputs info, connect a Null to it and, like before, go over it and click the "i" icon:

![2ndInput.jpg](https://static.wixstatic.com/media/b46b09_1d37b9b815a146da83f9232929144891~mv2.jpg/v1/fill/w_600,h_335,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/2ndInput.jpg)

This time, we are considering the skin output; in fact, the groups are there, and all the other parameters are updated.

Now, the point is that we need to transfer them to the guides because we want to change their length. To do this we can use a Group Transfer node:

![groupTransferTrip.jpg](https://static.wixstatic.com/media/b46b09_482a735ca7f14a88b8c5f455a9193349~mv2.jpg/v1/fill/w_473,h_590,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/groupTransferTrip.jpg)

Now, groups are in the right place and you can control each zone length:

![guideGroups.jpg](https://static.wixstatic.com/media/b46b09_c3d97407090a4ba88b04727deba66d38~mv2.jpg/v1/fill/w_600,h_328,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/guideGroups.jpg)

## HDA

But you can go a step forward.

To quickly adjust the length, you can transform your "Length node chain" into one hda. This way, you can concentrate all the sliders into one single node:

![lengthHda.jpg](https://static.wixstatic.com/media/b46b09_2bd59ac71db243f7afbfdebf3cefc282~mv2.jpg/v1/fill/w_600,h_179,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/lengthHda.jpg)

Hda is a crucial feature of Houdini, and it can speed up your work. You can learn how to create them by watching this video:

[![hdaTut.jpg](https://static.wixstatic.com/media/b46b09_04339d1efdf64fe89a3b9470dcde7ae1~mv2.jpg/v1/fill/w_440,h_280,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hdaTut.jpg)](https://www.youtube.com/watch?v=0uCrncu6_cY)

## GROOMING

It's time to see how all this works inside Houdini and why I could be useful using this approach. 

Have a look at this image:

![scalpComp.jpg](https://static.wixstatic.com/media/b46b09_f77c2cdbf9134848a446a8fa862fcbad~mv2.jpg/v1/fill/w_600,h_860,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/scalpComp.jpg)

As you can see, when you change topology, you have to paint your scalp subdivision from scratch, while the mesh one adapts quite perfectly to the new geo.

Only a small fix you can do moving the points in the Topo Build node:

`````col
````col-md
flexGrow=1
===
![scalpIssue.jpg](https://static.wixstatic.com/media/b46b09_6dc635629caa467e80a9cc330050e75b~mv2.jpg/v1/fill/w_354,h_422,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/scalpIssue.jpg)
````
````col-md
flexGrow=1
===
![scalpIssueFixed.jpg](https://static.wixstatic.com/media/b46b09_7b2bc2687fb7478c8a4380943925d9e0~mv2.jpg/v1/fill/w_354,h_422,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/scalpIssueFixed.jpg)
````
`````

To match the new head, you have to add a Ray node after the Scalp zone Subnet node (where you created the zones by selecting the polys). Set its method to Minimum Distance and feed the second input (Collision Primitives) with the "new head" (the one you will groom). If you subdivided the head (to paint the hairline, add a Subdivision node before the Ray):

![rayGraph.jpg](https://static.wixstatic.com/media/b46b09_75f08331747a4105badddb9ccf84ed2a~mv2.jpg/v1/fill/w_358,h_457,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/rayGraph.jpg)

![rayNode.jpg](https://static.wixstatic.com/media/b46b09_7314fd35ad9541c1bb6133fc578e4710~mv2.jpg/v1/fill/w_330,h_192,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/rayNode.jpg)

## USING A SINGLE NODE

Before starting the guide sculpting, let me show an essential thing.

As you can see from the scene you downloaded, I'm working inside just one node:

`````col
````col-md
flexGrow=1
===
![allHere.jpg](https://static.wixstatic.com/media/b46b09_993ac851cb5d4033b0037a20fc182629~mv2.jpg/v1/fill/w_218,h_133,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/allHere.jpg)
````
````col-md
flexGrow=1
===
![allHereInside.jpg](https://static.wixstatic.com/media/b46b09_4420bb70df1b417496c76932367b7471~mv2.jpg/v1/fill/w_268,h_133,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/allHereInside.jpg)
````
`````

If you are new to Houdini grooming, maybe you start your scene by adding, at the root level, the Guide Groom node and the Hairgen node using the Add Fur icon on the shelf:
`````col
````col-md
flexGrow=1
===
![hairShelf.jpg](https://static.wixstatic.com/media/b46b09_b22867c40df5460b919cecdc1fcfec86~mv2.jpg/v1/fill/w_166,h_68,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/hairShelf.jpg)
````
````col-md
flexGrow=1
===
![normalGrooming.jpg](https://static.wixstatic.com/media/b46b09_2397ce4ab6844126af21fffc870252db~mv2.jpg/v1/fill/w_406,h_337,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/normalGrooming.jpg)
````
`````

This is the way we all started, and sometimes, the way we use it. But if you want to develop your own tools (or other people for you), it's better to use the nodes at their lowest level. Why? Look at this:
`````col
````col-md
flexGrow=1
===
![doubleClick.jpg](https://static.wixstatic.com/media/b46b09_fa1a2617b9de40b4b8d31cc3f34a578c~mv2.jpg/v1/fill/w_356,h_297,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/doubleClick.jpg)
````
````col-md
flexGrow=1
===
![greyed.jpg](https://static.wixstatic.com/media/b46b09_bda2835e6eab473e9ea6fb1f23137cae~mv2.jpg/v1/fill/w_309,h_297,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/greyed.jpg)
````
`````

![insideGroom.jpg](https://static.wixstatic.com/media/b46b09_088e71f6ded844b682a92f37c51f19da~mv2.jpg/v1/fill/w_297,h_468,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/insideGroom.jpg)

If you double-click the Guide Groom node at the root level, you go inside it, but as you can see from the red arrow in image 2 above, there is a greyed node. If you click it, you dive inside and can see all the nodes used mainly for visualization purposes: with, color, etc.

This is very useful, but if you developed your own code, you can not be sure if the error you get during the development is your fault or a conflict with one of these nodes.

Besides this, you have to go constantly inside and outside of your nodes to work with guides and hair.

So, what I usually do is build a simple guide visualizer that also has some features missing in the vanilla node. Let's see it quickly.

![dViz.jpg](https://static.wixstatic.com/media/b46b09_ce771aa8b592462e92a1245100937dc3~mv2.jpg/v1/fill/w_255,h_302,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/dViz.jpg)

DViz is the visualizer. It's an hda, and before diving into it, let me explain why I used a split node before it.

As we will see in a second, I can change the color and width of the active and non-active guides with my visualizer. I need a way to feed it with this guide separation to do this.

If I were a nerd, I could have used some vex to put into my hda, but since I'm not, I have to use a more straightforward way. But, as you can see, I got to the point. This is crucial because if you have little nerd knowledge (I'm speaking to artists), you can make these little things that are extremely helpful in your everyday work.

The first step is to link the Guide Groom Group selection to the split Group. To do this, simply copy the parameter and paste the relative reference:

![copyParm.jpg](https://static.wixstatic.com/media/b46b09_52316a10872341c38e9950deb49dd441~mv2.jpg/v1/fill/w_393,h_311,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/copyParm.jpg)

![pasteRef.jpg](https://static.wixstatic.com/media/b46b09_bc974e3b908044869de605577941684e~mv2.jpg/v1/fill/w_394,h_338,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/pasteRef.jpg)

![activeNoactive.jpg](https://static.wixstatic.com/media/b46b09_3b9ffb9d74ae413898baa52d5ef85d44~mv2.jpg/v1/fill/w_394,h_589,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/activeNoactive.jpg)

After that, I put Color and Wrangle nodes that I wrapped into an hda:

![insideViz.jpg](https://static.wixstatic.com/media/b46b09_623bc410b7c34d0788ce5fa3943f9189~mv2.jpg/v1/fill/w_393,h_499,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/insideViz.jpg)

This is the vex I used in the Wrangle node to adjust the Width using a slider:

@width = ch("width");

And this is the result:
`````col
````col-md
flexGrow=1
===
![04.gif](https://static.wixstatic.com/media/b46b09_9aacf8a985ea4e51a71bfe4ba77bb112~mv2.gif)
````
````col-md
flexGrow=1
===
![dvizSliders.jpg](https://static.wixstatic.com/media/b46b09_17ae6fe0b6fb4741ac1044889c458226~mv2.jpg/v1/fill/w_313,h_219,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/dvizSliders.jpg)
````
`````

Just to have some fun, if you want, you can have a gradient version (darker at the roots) by adding these three nodes in each branch (so you can have complete control):

![gradientNodes.jpg](https://static.wixstatic.com/media/b46b09_320431b9431f432fa1892e59c7f4dd2e~mv2.jpg/v1/fill/w_600,h_500,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/gradientNodes.jpg)

The Resample node is to get the Curveu attribute. So, disable the resample options (1) and check the Curve U Attribute option (2):

![curveuSettings.jpg](https://static.wixstatic.com/media/b46b09_19aa87f729b34e54bfc66ce0f14a1f26~mv2.jpg/v1/fill/w_600,h_392,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/curveuSettings.jpg)

Now that we have added the Curveu attribute we can multiply it by the color using this vex inside the Wrangle node:

@Cd = @Cd * @curveu;

Finally drag and drop the Select Input parameter in you hda (as explained in the video above):

![switch.jpg](https://static.wixstatic.com/media/b46b09_f596c870483542ab8286167934bd841f~mv2.jpg/v1/fill/w_394,h_168,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/switch.jpg)

This is the upgraded version:

![vizGradient.jpg](https://static.wixstatic.com/media/b46b09_5efd7744a7ce492b8139cb00c8a11078~mv2.jpg/v1/fill/w_419,h_270,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/vizGradient.jpg)

![05.gif](https://static.wixstatic.com/media/b46b09_c8b1e6ad08204122aa7611b54ef7908e~mv2.gif)

## IMPORTANT

1.  If you want to sculpt, delete, etc., all the guides, you have to write (means everything) in the Group field.
If you want to work on multiple groups, you have to write them since the Guide Groom node does not accept more than one selection
If you want to exclude a group, write * ^crown (for example)
2. To see the width variation, you have to check the "Shade Open Curves In Viewport" option. You find it in the Misc tab of the Geo (allHere in my case) node where you have all your nodes:

![shadeOption.jpg](https://static.wixstatic.com/media/b46b09_583729a2385349568c8454361eba7687~mv2.jpg/v1/fill/w_341,h_517,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/shadeOption.jpg)

Remember that this is a simple tool made by a no-nerd artist for visualisation purposes and it's far from being perfect.

## GUIDE SCULPTING

To sculpt the guides, we need a Guide Groom node. 

One important thing.

The second input of this node is for Skin, which is also used as a collision object. Since our guides grow from the scalp, the head is not taken into consideration. For this reason, we have to feed this input with it:

`````col
````col-md
flexGrow=1
===
![skinGroom.jpg](https://static.wixstatic.com/media/b46b09_2d77c863afa74b7d8524770b793de237~mv2.jpg/v1/fill/w_325,h_408,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/skinGroom.jpg)
````
````col-md
flexGrow=1
===
![07.gif](https://static.wixstatic.com/media/b46b09_a63cc74c42d94bb3a1ee9dec6bde5f20~mv2.gif)
````
`````

## FIRST EXAMPLE

Having photos, drawings, or scans of the haircut is crucial. Unfortunately, not always, even in production, you can have them. Sometimes, you get only a frontal or three-quarter image and have to guess what's on the back.

Putting into practice what you have learned so far could be a solution.

Let's start with something simple, just to warm up:

![groomingSchemes.jpg](https://static.wixstatic.com/media/b46b09_23e36011baf0445286c835048626ad30~mv2.jpg/v1/fill/w_600,h_634,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/groomingSchemes.jpg)

[lordhair.com](https://www.lordhair.com/)

This is an image I found on the web. he cool thing is that you have all the lengths for each scalp zone for the most common haircuts.

With only this image, it isn't easy to understand how lengths all go around the head. Nothing fancy, but having the scheme is very helpful:

![SchemeSample.jpg](https://static.wixstatic.com/media/b46b09_b1780f849ca44c74abeb82d9daef12ef~mv2.jpg/v1/fill/w_209,h_481,al_c,q_80,enc_auto/SchemeSample.jpg)

All we have to do is to set our Length Control using those values:

![complexScalp.jpg](https://static.wixstatic.com/media/b46b09_6c1ebaac17a842aca28de7912ebd93c2~mv2.jpg/v1/fill/w_194,h_229,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/complexScalp.jpg)

![08.gif](https://static.wixstatic.com/media/b46b09_86df7994bf494ed0b9e6446baeeb105b~mv2.gif)

Houdini is not CAD software, so setting lengths is not possible (or complicated). Anyway, we are artists and don't need to be perfect. To roughly match the haircut sheet, since the head is 8 inches high and the front scalp area length is 3.9 inches, the guides are half the head. I used a couple of boxes to set this:

![divider.jpg](https://static.wixstatic.com/media/b46b09_08033fc1a75a4e02a24997161a0638c2~mv2.jpg/v1/fill/w_431,h_427,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/divider.jpg)

At this point I added "/2" after the sheet value in my Length Control:

![divideFactor.jpg](https://static.wixstatic.com/media/b46b09_c464a582d53b459188f50946c0d6301a~mv2.jpg/v1/fill/w_290,h_368,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/divideFactor.jpg)

After a very little work, we can get this:

![10.gif](https://static.wixstatic.com/media/b46b09_b5196193d2f744d8bcae66de1462f0a2~mv2.gif)

The cool thing is that if you change your Length Control "divider", you can have a new version that is consistent with the previous one:

`````col
````col-md
flexGrow=1
===
![lengths.jpg](https://static.wixstatic.com/media/b46b09_b8afda7e0ee04b31b102a3c6d437a23f~mv2.jpg/v1/fill/w_262,h_376,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/lengths.jpg)
````
````col-md
flexGrow=1
===
![09.gif](https://static.wixstatic.com/media/b46b09_22e0d4b38fc344b699ccabf50d902a65~mv2.gif)
````
`````

Obviously, since the Guide Groom node is not procedural, you have to sculpt your guides again, but using scalp zones is very simple.
`````col
````col-md
flexGrow=1
===
For example, having only the front image, with shorter guides, the back could be like this:
````
````col-md
flexGrow=1
===
Or with very little effort, using the "smart selection" like this:
````
````col-md
flexGrow=1
===

````
`````

`````col
````col-md
flexGrow=1
===
![backDown.jpg](https://static.wixstatic.com/media/b46b09_c4441eba65684e40a3375b827cd76292~mv2.jpg/v1/fill/w_329,h_500,al_c,q_80,enc_auto/backDown.jpg)
````
````col-md
flexGrow=1
===
![11.gif](https://static.wixstatic.com/media/b46b09_0320e6d470c64f73a2bc79f4c1434cd4~mv2.gif)
````
````col-md
flexGrow=1
===
![backUp.jpg](https://static.wixstatic.com/media/b46b09_0285ba1fef17443b955b8dbaad6cb9eb~mv2.jpg/v1/fill/w_329,h_500,al_c,q_80,enc_auto/backUp.jpg)
````
`````

## SCULPTING TIPS

Besides using the scalp zones, which allow you to have precise and quick selections, there are other very simple but helpful tips.

### 3 MOVES SCULPTING

It's a good practice to sculpt in steps: front, side, and top:

![3Moves.jpg](https://static.wixstatic.com/media/b46b09_8a255be7e8654bd8a57190d009016815~mv2.jpg/v1/fill/w_656,h_281,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/3Moves.jpg)

### LIFT TOOL AND CURVE MASK​

Using these two features can be very helpful to get neat sculpted guides quickly:

![combedGuides.jpg](https://static.wixstatic.com/media/b46b09_f67720c15c31498682dc5f55a768660c~mv2.jpg/v1/fill/w_296,h_437,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/combedGuides.jpg)

As first step use the sculpt tool until the guides stick the head:

![stickGuides.jpg](https://static.wixstatic.com/media/b46b09_6dc5f2b50fb946389089aa6e6fbbf8f3~mv2.jpg/v1/fill/w_600,h_429,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/stickGuides.jpg)

Then use the lift tool adjusting the strength ramp to bulge the guides:

![curveMask.jpg](https://static.wixstatic.com/media/b46b09_cf218513f81141528126d711864c57db~mv2.jpg/v1/fill/w_600,h_573,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/curveMask.jpg)

### BLUR TOOL​

In any sculpting process, blurring is fundamental. Groom sculpting is not an exception. As you can see in the image below, you can fix messy guides (circle) but also create smooth length transition (arrow):

![blur.jpg](https://static.wixstatic.com/media/b46b09_d0bc1acdc08c4641b47b96c36bbef2d7~mv2.jpg/v1/fill/w_600,h_700,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/blur.jpg)

# CONCLUSIONS

Well, this is the end of this long tutorial. I hope it can be of any help.

This is only one of the billions of methods you can use to get your job done. The key point is that everyone should shape his or her workflow to work joyfully. We spend countless hours moving guides, and thanks to his toolbox structure, Houdini helps you get the best out of it. Evaluate what is the most important for you (for me, visualization) and shape your working tool accordingly.

One more thing before stepping into the resources.

Writing a tutorial is very time-consuming, but it gives you the chance to put it in order, elaborate on what you learned, and acquire new knowledge.

Writing this one, I went deeper into many of the concepts I described and built new tools I will use in my daily job.

So, I encourage you to do the same every time you learn something new. Write a tutorial and share it with the community.

## RESOURCES

Besides the links I will give you in a second, I strongly suggest getting in touch and taking some lessons from a hairdresser. We usually approach grooming like sculptors, but we work in a 3D environment, and hair is usually simulated.

Second, observe natural hair while you are in a queue, when you play with your kids, when you are with your wife, and in every other situation when you interact with other people.

Third, add some nerditude to your job. Not that much, just a little bit. Keep painting your maps and moving every guide you need, but use Houdini nodes to build new tools (hda) that speed up your work and get as many variations as possible.

## LINKS
[3D.sk - Grooming photos](https://www.3d.sk/photo_sets/search/query//thumb/small/standard/1/premium/1/category-2007/groom-photo-references/page/1)
[hairfinder](https://www.hairfinder.com/)
[hairtech app](https://hairtechapp.com/)
[Sassoon Academy](https://www.sassoon-academy.com/)
[Lordhair](https://www.lordhair.com/)
[Men's Hairstyle Trends](https://www.menshairstyletrends.com/)
[Shannel Mariano](https://www.instagram.com/shannelmariano/)
[Sanja Cari](https://www.youtube.com/c/SanjaCaricaKarasman)[ca Karasman](https://www.youtube.com/c/SanjaCaricaKarasman)
[The One Minute Barber](https://www.youtube.com/@theoneminutebarber)

​