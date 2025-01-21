---
URL: https://www.youtube.com/watch?v=DDeB4tDVCGY
thumbnail: https://i.ytimg.com/vi/DDeB4tDVCGY/default.jpg
channel: "[[Joey Carlino]]"
date: 2024-07-16T16:05:06
published: 2023-05-06T01:22:26
duration: 602
tags:
  - video/animation/rig
done: false
cover: "[[Pasted image 20240716160542.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "10m 2s"]
# Rigging for impatient people - Blender Tutorial
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716160542.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Rigging for impatient people - Blender Tutorial" src="https://www.youtube.com/embed/DDeB4tDVCGY?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: Learn to rig NOW. I show how to set up an armature, how to parent things to bones, weight painting and how to solve common issues, and basic inverse kinematics.)

Patreon, Gumroad Shop, Discord, and other stuff:
https://linktr.ee/Joeycarlino
 
Parent to nearest bone addon: https://github.com/g3ntile/parentToNearestBone
Rigging playlist: https://youtube.com/playlist?list=PLzg4_2BrWAVwkQvVPJoNaXNN4dXY0Xjkl
Character modeling playlist: https://www.youtube.com/playlist?list=PLzg4_2BrWAVyf8LKdr2XtEw2BCDvbEnuk

🔗Links
2nd YouTube Channel: https://www.youtube.com/@JoeyC-quel
Patreon: https://www.patreon.com/joeycarlino
Discord Server: https://discord.gg/dvmAZdwf5e
Gumroad Shop: https://gumroad.com/joeycarlino?a=844339507
Blender Market Shop: https://blendermarket.com/creators/joeycarlino
Second Channel: https://www.youtube.com/@JoeyC-quel
TikTok: https://www.tiktok.com/@joey_carlino
Instagram: https://www.instagram.com/robospunk/
Twitter: https://twitter.com/joey_carlino
Personal Email: JoeyCarlino@gmail.com
Busniness Email: JoeyCarlino@makrwatch.com

💰Support me by checking out these affiliate links:
https://linktr.ee/joeycarlinoaffiliate

🧠Things I Recommend (not affiliated)
Blender Launcher: https://github.com/Victor-IX/Blender-Launcher-V2
Blender Beginner Playlist: https://youtube.com/playlist?list=PLa1F2ddGya_-UvuAqHAksYnB0qL9yWDO6

🫂Places To Donate:
https://www.nrdc.org/
https://wck.org/
https://blacklivesmatters.carrd.co/
https://www.catf.us/
https://www.evergreenaction.com/
https://350.org/
https://www.conservationfund.org/
https://www.nature.org/en-us/
https://communitychangeaction.org/
https://www.aclu.org/
https://www.wri.org/
https://www.edf.org/

⚙️What's On My Desk?
GPU: EVGA GeForce RTX 2070 SUPER
CPU: AMD Ryzen 9 3900X
Motherboard: Asus PRIME X570-PRO
Memory: Team T-FORCE VULCAN Z 64 GB (2 x 32 GB) DDR4-3200
Monitor: LG 25UM58-P 25.0" 2560x1080 60 Hz
Drawing Tablet: XP-PEN Artist 15.6Pro
Mouse: Logitec MX Master 3s
Keyboard: Redragon K580 VATA
Speakers: Mackie CR3-X
Headphones: Beyerdynamic DT 700 Pro X
Microphone: Beyerdynamic M70 Pro X
Audio Interface: Universal Audio Volt 2
 
00:00 - Armature setup
01:23 - Names and symmetry
01:56 - Automatic weights and common issues
03:13 - Weight tricks
04:17 - Weight paint settings
05:34 - Rigid rigging
07:32 - Inverse kinematics
# Transcript
[00:00](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=0) rigging can get pretty complicated especially as you get into more advanced topics like constraints and drivers but maybe you only need something simple or maybe you're just impatient so here are 
[00:09](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=9) some of the basics of rigging for when you want to get started fast [Music] I'll be talking about two main rigging Styles one is a rig that deforms the 
[00:20](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=20) model and the second keeps each piece rigid and separated for the first one I'm using a character I made but this will work for anything you want to bend and to form press shift a to add an 
[00:30](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=30) Armature and if you don't want your bones to be covered by the model then you can go to object data properties it looks like a little running person and turn on in front this is also where you 
[00:39](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=39) can change the shape of your bones and show the names and axes then just select the Armature tab into edit mode and you can select the head or tail of the bone move them around with G and extrude with 
[00:49](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=49) e to place your bones the thick end is the head and that's where the bones will pivot from when you're in pose mode I'll usually do the center of the body and then one half if the model is 
[00:58](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=58) symmetrical you can get the bones close to the body by using snapping I'll usually set it to face project and Center then when you're moving around you can hold Ctrl to snap and you can 
[01:08](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=68) adjust it from there this is good for shapes that get a little weird like you could rig tree branches more easily this way you can also shift d to duplicate bones parent bones with Ctrl P either 
[01:18](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=78) connected or keep offset and you can unparent or disconnect bones with alt P if your model is symmetrical then select all of the bones that aren't in the middle and press Ctrl F2 to batch rename 
[01:30](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=90) set this to Bones this to set name and suffix type period L and press ok now all of the bones on the left side of your character have a DOT L at the end of their names this is important if you 
[01:44](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=104) ever want to mirror poses there's also an auto naming option that does pretty much the same thing if you right click now with all of those bones still selected right click and choose 
[01:52](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=112) symmetrize to copy all of the left side bones over to the right tab back into object mode select your model shift-click your armor aperture control p and choose Armature to form with 
[02:03](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=123) automatic weights and you can do this if your model is multiple objects too just select all of the objects and then the Armature last this should add an Armature modifier to your objects and 
[02:12](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=132) also a bunch of vertex groups that have the same names as your bones this is where the weight painting information is stored and if at some point you mess up and want to start over you can remove 
[02:21](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=141) the Armature modifier and delete all of the vertex groups with this Arrow select the Armature press control tab to go into pose mode and start moving things around to test your reg out if this gave 
[02:32](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=152) you a good result then this could be the end of the video for you if you got an error that says bone heat weighting failed that's because your mesh has too many overlapping Parts I'd recommend 
[02:42](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=162) either re-meshing it doing reach apology or editing it to make Parts not overlap or you can split the model into multiple objects and try applying automatic weights that way another common issue is 
[02:53](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=173) deformation like this which is caused by not having enough geometry like if you want a cube to bend and be all curly you can't really do that with only eight points so try adding more Loop cuts and 
[03:04](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=184) then applying automatic weights again it's also pretty likely that you'll get some deformation that looks wrong to you this is the automatic approach after all and you can fix this with weight 
[03:13](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=193) painting whoa whoa don't leave yet people love to joke about how scary or painful weight painting is and they're right but it's not as bad when you know a few tricks first of all you can redo 
[03:23](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=203) automatic weights for your entire model or only for specific bones just go into pose mode and select the bones you want then go back into object mode select your model and go into weight paint mode 
[03:34](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=214) go up to weights and assign automatic from Bones blender will remember what bones you had selected in pose mode and redo those weights and this is nice if you don't want to start over completely 
[03:45](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=225) you can also try moving bones around and reapplying weights to get different results if you have to do this a lot I recommend going to edit and turning lock object modes off then you should be able 
[03:55](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=235) to click on different objects in your scene you can select from the outliner too and blender will remember what mode you were in last so it's a lot faster when your Armature is in pose mode and 
[04:05](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=245) your model is in weight paint mode you should be able to control click to select bones and view their weights shift-click for multiple bones and as usual a to select everything and ALT a 
[04:15](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=255) to deselect posing Works in here too and before painting let's talk about settings I recommend using hambone will save your life someday first is under viewport overlays turn on wireframe you 
[04:26](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=266) should use this especially if your model has a subdivision surface modifier on it because the weights are only going to affect the points on the original mesh and that's what this is showing next go 
[04:35](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=275) to Tool settings options and turn on auto normalize this makes it so when you add weights to one bone it will take them away from others and you won't have multiple bones that are trying to 
[04:47](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=287) control the same area there's also a symmetry option here that could save you some time and if you want to paint all the way through your model then you have to turn on projected under fall off and 
[04:56](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=296) turn off front faces only under Advanced brush settings just be careful and make sure you change it back when you don't want it to work this way now you can start painting set the weight to decide 
[05:06](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=306) whether you want to add or remove influence blue is zero or no influence and red is one or complete influence and use f to change the brush size you can also turn the strength down to adjust 
[05:18](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=318) the weights a small amount at a time if your painting is a little sloppy then you can smooth it out by going to weights and choosing smooth and then decide whether you want to smooth 
[05:28](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=328) everything or only the bones you have selected and when you're done Weight painting make sure to turn lock object modes back on if you want a more rigid result with no bending then you'll need 
[05:37](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=337) a different approach the first way of doing this is by parenting directly to bones and avoiding weights altogether but this only works if your model is made of a bunch of separate objects 
[05:46](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=346) select one of your objects then shift-click the Armature and go into pose mode select the bone you want to parent it to control p and choose bone now that object should follow the bone 
[05:56](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=356) when you move it this gets pretty annoying when you have to do it over and and over again so you can use this add-on to make the process faster you can get similar results using weights 
[06:05](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=365) and this also works if your model is only one object unlike the previous way and this is easier when you make bone names visible under object data properties select your model and then 
[06:15](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=375) your Armature Ctrl p and parent with empty groups then select your model and go into edit mode there should be a bunch of vertex groups with the same names as your bones and if you have a 
[06:25](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=385) lot of Bones you can click this Arrow to search by name then all you do is select the vertex group of the bone you want select the body part by hovering over it and pressing L make sure the weight is 
[06:35](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=395) set to 1 and press assign and just like before that piece should now follow the bone this process is arguably even more annoying when you have a lot of Bones so here's a way that usually gets the 
[06:45](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=405) weights pretty close go into edit mode press period or go up here to change your pivot point to individual Origins then press s and 0.1 to scale everything down to one tenth of the size go back 
[06:58](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=418) into object mode select the model and then the Armature and parents with automatic weights then go back into edit mode select everything and scale up by 10 to return everything to its original 
[07:08](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=428) size this usually works for most of the model but depending on the shapes you're using you might have to clean it up with the more manual method that I showed before just make sure to remove the 
[07:17](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=437) weights on the part you're selecting before you try to assign otherwise you might get some overlapping weights and to clear up small weight issues like this you can try using this quantize 
[07:26](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=446) option in weight paint mode and set it to one that should make all of the weights be either zero or one let's go into pose mode and rotate some bones around then press I to insert a keyframe 
[07:37](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=457) for the bones that you have selected change the pose and press I to insert another keyframe and now it's animated and if you named your bones the way I mentioned earlier then you can copy a 
[07:47](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=467) pose with Ctrl C and mirror it with Ctrl shift V if you want to be able to pose by moving the ends of the limbs the quick way is by turning on auto ik under pose options then when you move your 
[07:59](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=479) bone you can and use your scroll wheel to change the chain length this is nice for quick and dirty animations but for maximum control you'll need to set up some real inverse kinematic constraints 
[08:09](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=489) that's what ik stands for select the Armature and go into edit mode and I'll set this up for the legs so you can either create a new bone by extruding from the ankle or you can just use the 
[08:19](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=499) foot bone if you make a new bone make sure deform is turned off so when you do the weights it doesn't actually influence the mesh select that bone press alt p and clear parent then go 
[08:29](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=509) into pose mode select the ik bone shift select the leg bone press shift I and add ik to active bone you should get a different result now when you move the ik bone and the yellow bone should have 
[08:41](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=521) a bone constraint on it not a regular constraint the one with the bone on it you can also add it from here if you don't use the shortcut shift I these options let you change the chain length 
[08:52](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=532) for legs two or three is usually what you want if your legs don't bend try going into edit mode and moving the joints a little bit in the direction that you want them to bend and if you 
[09:02](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=542) want more control over where the bone chain is pointing then you need a Target bone which is what the spot is for do this the same way we added the ik bone go into edit mode and extrude from the 
[09:11](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=551) knee and ALT P to clear the parent I'll usually name this something with Target in the name go back to the constraint select the Armature then select the target bone if your leg isn't pointing 
[09:22](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=562) the right way then change the pole angle if you set all of this up on half of your model and name it properly with DOT l or dot r at the end then when you symmetrize the ik constraints we'll copy 
[09:32](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=572) over as well so save yourself some work and do it from the beginning if you plan to do it at all this video is supposed to be short so I left a bunch of topics out like bone roll drivers shape keys 
[09:43](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=583) and other bone constraints if you want to learn more about rigging then it might be time for something a little longer and more in depth and for that you can check out my rigging playlist if 
[09:53](https://www.youtube.com/watch?v=DDeB4tDVCGY&t=593) you want the file from this video you can get that on patreon oh yeah one last thing make sure to move your model by selecting the arm picture otherwise 