---
URL: https://www.youtube.com/watch?v=K8Gc5ys5Ba8&t=6s
thumbnail: https://i.ytimg.com/vi/K8Gc5ys5Ba8/default.jpg
channel: "[[SouthernShotty]]"
date: 2024-07-21
published: 2024-07-09T15:00:21
duration: 724
tags:
  - video/3D/blender
done: true
cover: "[[Pasted image 20240715172056.jpg]]"
---
[time:: "12m 4s"]
(Note::[[../../../../05 Notes/3D/Eevee settings|Eevee settings]])
# Will Eevee 2.0 Replace Cycles? | Blender 4.2
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715172056.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Will Eevee 2.0 Replace Cycles? | Blender 4.2" src="https://www.youtube.com/embed/K8Gc5ys5Ba8?start=6&amp;feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
👇My Products 👇
Dynamic VFX Pack (Free Sample Pack): https://blendermarket.com/products/blender-dynamic-vfx---elemental-asset-pack
Crafty Asset Pack (Free Sample Pack): https://blendermarket.com/products/crafty-asset-pack
Patreon: https://www.patreon.com/southernshotty
Skillshare (affiliate link): https://www.skillshare.com/r/user/southernshotty
Tag me in your artwork on Instagram and Twitter @SouthernShotty
Instagram: https://www.instagram.com/southernshotty/
Twitter: https://twitter.com/SouthernShotty

(Description:: The release of Eevee 2.0 in Blender 4.2 has sparked a fascinating debate within the 3D community: Could this enhanced real-time render engine possibly replace Cycles? In this video, we delve deep into the capabilities, improvements, and potential implications of Eevee 2.0, comparing it directly with Cycles to see how they stack up against each other.)

Eevee 2.0 brings significant upgrades, offering near real-time rendering speeds with improved lighting and shadow fidelity, which makes it a tempting option for many projects. However, Cycles, known for its path-tracing capabilities that provide photorealistic results, holds its ground in scenarios where ultimate realism is paramount.

Join us as we explore use cases, performance benchmarks, and visual quality comparisons between Eevee 2.0 and Cycles. This analysis will help both new and seasoned Blender users understand the strengths and limitations of each engine, guiding you in choosing the right tool for your specific needs in Blender 4.2.

# Transcript
[00:00](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=0) EV 2.0 is here and is it replacing Cycles no it's not but it is closing the Gap by a large margin what that means is that if Cycles is too slow to render on your computer that now you can get much 
[00:12](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=12) closer results with EV 2.0 they've added a lot of features like Ray tracing displacement maps and emission lighting and we're going to go through all of that but in this video we're also going 
[00:21](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=21) to go through every setting in the render Eevee engine that way if you're a beginner you should feel pretty confident working in Eevee by the end of this video so with that being said let's 
[00:29](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=29) dive in and start learning so diving into the biggest new feature of course which is Ray tracing check this out if I turn this off look at that look how flat that is and I turn it on 
[00:39](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=39) and look how nice that looks now here it is compared to the original Cycles version and I'm going to be using this scene from my short film to show off how to use these Ray tracing effects because 
[00:49](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=49) I have a lot of normal Maps I have World Lighting I have regular lighting and if I zoom in here I have this seethrough glass reflective bottle up front and a high depth of field so this is just kind 
[00:58](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=58) of a great scene to show off the power of E's new rate tracing so let's dive in and look at all these settings that we have here so first just clicking on rate tracing is going to make everything look 
[01:07](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=67) better if you're not familiar what Ray tracing is it means that it's tracing light rays as they Bounce Around the scene this is what cycles does and why it looks so realistic now if I go ahead 
[01:17](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=77) and dive into the method here our first option it's by default set to screen Trace what this is going to do is Trace all those light rays and get them within the screen space it will only use light 
[01:29](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=89) probes if if the ray exits that screen space the other method you have is light probe here and if you've used ev2 prior versions you know that you have these light probe objects where you can bake 
[01:39](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=99) in lighting data so by using light probe you can kind of return to that old method however I recommend staying on screen trace and just using light probes which will help inform kind of outside 
[01:49](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=109) the screen space now next up you have the resolution this is a bit misleading the lower the numbers actually the higher the resolution this is a one:1 resolution you just want to set this as 
[01:58](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=118) low as you can with your scene lagging too much next up we have the max roughness which will set the max roughness for kind of the screen space bouncing around if I go ahead and turn 
[02:08](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=128) this up you can see here in the back how my rocks are becoming much more diffuse and if I set this back down to 0.5 you can see how that's kind of altering that back there so you can set that to 
[02:19](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=139) whatever you want next up is screen tracing now Precision by default is set to 0.25 the higher you can get this the more precise it will be and the better it will be however the slow it will be I 
[02:30](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=150) recommend bumping this one in particular as high as you can next up we have thickness and this is going to determine how thick to consider pixels are for depth buffers it gets pretty complicated 
[02:41](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=161) let's just show what it does in a practicality example here if I zoom in here on this bottle and I turn this thickness up you can see that I'm getting more like visible Reflections 
[02:52](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=172) through here but it's also starting to stretch those Reflections so i' recommend for thickness is setting this as kind of low as you can without losing that that reflective ability so by 
[03:01](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=181) setting mine to like 0.15 you can see that I can still see through my glass here but I'm losing those stretched pixels next up we have Den noising now of course this will remove noise at your 
[03:12](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=192) image but at the expense of a bit of sharpness now you see that you have various options here you can play with these options if you like but honestly I think you just need to decide whether 
[03:21](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=201) you're going to use D noising or not you don't need to worry about these individual controls here if you're enjoying this video please maybe stop and check out my patreon I put up a lot 
[03:28](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=208) of projects on there that you can download and use I put up shaders and I also put scene breakdowns and kind of casual tutorials as well but let's get back to the main video now the global 
[03:38](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=218) illumination here is a massive setting to consider because with global illumination here we can get light bouncing so you know this red can bounce red onto her body something that 
[03:49](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=229) previously wasn't possible in Eevee now there's two methods here there's Global illumination which is going to give you more realistic colored bounces in between light rays or you can turn on 
[04:00](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=240) ambient inclusion here which will render a bit faster at the expense of a little bit of realism and then if we come down here we again have a resolution option again you want to get this as close to 
[04:10](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=250) 1: one as you can that your computer can handle but now we have rays and steps so we can actually turn up the amount of rays that Global illumination is using to calculate those light bounces Now by 
[04:23](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=263) default it's set pretty low to something like two but the higher you can get this the better it is but you really don't need to go above 12 in my opinion and then below that we have these steps 
[04:34](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=274) which is the amount to kind of sample those per GI and I think that by default that's set to eight again you want to bounce this as high as you can if you go up to something like 64 you're going to 
[04:43](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=283) be in a really good spot and then here we have Precision Again by default this will be set to something like 0.25 but getting that as high as you can to one to create a more precise Global 
[04:53](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=293) illumination calculation lastly we have some real in-depth control here about the distance so Global illumination as I said is lights bouncing off objects near each other so if you wanted you could 
[05:03](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=303) limit that distance and say that objects could only bounce off each other from 1 meter away and then you can control the thickness how far and the bias of all of that however I recommend just leaving 
[05:13](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=313) these at default settings and they look pretty good as is so that covers all the settings in the ray tracing menu but the thing is that rate tracing affects the overall render engine so our light 
[05:22](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=322) probes our light objects and some of these other menus also have settings that pertain to rate tracing as well so let's look at those next so here we have clamping now if you're not familiar with 
[05:31](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=331) clamping what this does is reduce the amount of light that can bounce around a scene and limit it because when you put something like a really bright light source in a dark room it can create 
[05:41](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=341) Firefly pixels which are bright noisy pixels Now by default they've set it to 10 this should remove most things however if you add a volumetric fog to your scene that can introduce fireflies 
[05:53](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=353) and you could go ahead and set this to 10 here too now you can bump up this direct light but that's going to go ahead and start removing light rays from your scene and really darken the overall 
[06:02](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=362) scene so I don't recommend putting anything in here but if you really can't get rid of them you can set something really small like 0.1 or just one let's take a look at this sampling menu next 
[06:13](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=373) now that we're using light rays and Ray tracing we're going to need more samples here in our viewport you'll see that we have temporal reprojection and Jitter Shadows this is just to help in the 
[06:21](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=381) viewport just to create a little bit more of a stable look while you're looking at it in real time here of course in the render you can set your samples the higher the better but don't 
[06:29](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=389) need to go super high and Eevee I wouldn't really go past 512 and then here we have our shadows and here in the shadows we can contribute how much light rays are bouncing around so here if I 
[06:40](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=400) come to the Rays I can bump this up and I believe four is the highest you can set it to by default it's one or two and then you can also bump up the steps on how it processes those and then you can 
[06:50](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=410) also turn up your Shadow resolution here now if you have a volumetric fog on the scene I would click this on and set your steps around something like between 16 and 64 now on Advanced here you can also 
[07:00](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=420) change your light threshold though you shouldn't really need to ever adjust that setting now the depth the fields actually just kind of been improved by default so you shouldn't have to change 
[07:10](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=430) much for it to look this good however there are settings here you can control and there's a lot to do here but you really rarely need to adjust these settings what you really need to pay 
[07:19](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=439) attention to is Jitter camera you can turn this on and this can sometimes kind of help over blur the pixels and provide a somewhat more stable looking depth of field 
[07:29](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=449) now with Ray tracing it's also changing how our lights work too so if we grab one of these lights you'll notice that we have a lot of different options over here that we didn't before so let's go 
[07:38](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=458) ahead and take a look at these so one thing we can do to improve the lighting quality here is we can turn on this Jitter option here and what this is going to do is Jitter the soft Shadows 
[07:47](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=467) to increase the shadow Precision the problem being that it's going to have a high performance impact so the more these you turn on the slower your scene's going to get but the more 
[07:56](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=476) realistic it's going to get and you'll notice under Jitter we have this over blur option what this is going to do is kind of reduce under sampling artifacts so you can turn this up and get less 
[08:06](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=486) sampling issues and then below that we have the filter which will blur the shadow aliasing this can kind of help depend with the map resolution and then below that we have the resolution limit 
[08:18](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=498) now the lower you set this the better it's going to look so if I set mine down to something like 0.1 it's going to give me a bit more realistic Shadow resolution and then down here we can 
[08:28](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=508) control the influence over every Ray diffuse glossy transmission volume scatter but the thing is if you change any of these to any value besides one it will be inaccurate however these are 
[08:42](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=522) here for artistic control now lastly I want to dive into the light probes so the light probes are just like they were before we have spheres planes and volumes that we can add into our scene 
[08:54](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=534) however before everything was baked under this menu here and you may notice that that is no longer here well now it is on the light probes themselves so go to the light probe come down to the data 
[09:05](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=545) tab here and then under bake you can set the bake and just like before we can increase our resolution the amount of samples and everything now as I mentioned before if you're using screen 
[09:15](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=555) Trace it's only going to rely on these light bakes for things that fall outside of the screen space so they can still help enhance your scene with lighting but they're not nearly as necessary as 
[09:26](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=566) they were before to get realistic renders [Music] so you may also notice here that if we come into our materials and we come down 
[09:34](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=574) to the settings we have a lot more options here in terms of how they work with Ray tracing so whenever you're doing things like refractive objects these settings are going to become very 
[09:42](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=582) important as are when you're trying to displace materials as well so diving into these settings individually backface calling refers to the back faces of your object according to the 
[09:52](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=592) camera's position so by turning this on for the camera you can see that what I'm doing is reducing the transparent effect back there and effectively making this glass slightly more see-through this is 
[10:03](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=603) a creative decision not necessarily a realistic decision you can do the same thing and calculate it for Shadows if you like and if you're using light probes with the volumes here baked you 
[10:13](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=613) can use that as well now for the displacement here you can set this to bump displacement or displacement and bump just like you can in cycles and then you can also set the maximum 
[10:23](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=623) distance here for how much you're allowed to displace this material this is awesome because displacement takes forever to render and Cycles so being able to do this so quickly in a software 
[10:35](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=635) like Eevee is really exciting below that we have transparent Shadows where we can turn on transparent shadows as you can see here that is helping greatly with the glass and then down here we have 
[10:46](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=646) rendered methods called dithered and Blended this is going to be how it's kind of handling those seethrough parts dithered will make it so that it allows for a grayscale transparency and it will 
[10:59](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=659) render it in layers this will actually work with render layers and other things whereas Blended won't so I recommend leaving it on dithered then you can also retrace the transmissions and if I turn 
[11:12](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=672) that on you can see that we're getting slightly more realistic transmission Rays there now down here on the thickness you can set this to slab or sphere so sphere is going to be more 
[11:22](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=682) spherical objects and slabs going to be more like flat surfaces like glass planes so since I have a bottle here I'm going to go ahead choose sphere and you can see how that immediately changes how 
[11:32](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=692) the reflections work and then down here you can tick on from Shadow and what this will do is use Shadow maps and casting lights to kind of help refine the thickness so I'm going to go ahead 
[11:42](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=702) and click that on and hope that it helps get me a little bit more of a realistic result lastly down here if you have volumes in your scenes or materials you can change between fast and accurate so 
[11:52](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=712) that's like a deep dive into how Ray tracing works in the new version of Eevee I hope you found this useful let me know know what you think in the comments below are there other things 
[12:01](https://youtu.be/K8Gc5ys5Ba8?si=yELRyOHlPlBBzzhe&t=721) you'd like me to cover in Eevee if so let me know 