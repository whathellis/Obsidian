---
URL: https://www.youtube.com/watch?v=6uaJ0L4E390
thumbnail: https://i.ytimg.com/vi/6uaJ0L4E390/default.jpg
channel: "[[Tradigital]]"
published: 2023-01-30T08:27:58
duration: 632
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715164551.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "10m 32s"]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715164551.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Turning 3D Models into Masterpieces: A Blender Tutorial" src="https://www.youtube.com/embed/6uaJ0L4E390?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: In this video, I introduce my Blender Live Paint Filter, an incredible tool that can turn your 3D scenes into stunning paintings in Blender. I'll share the story of how I created the filter, and you'll learn about how it works. Don't miss this exciting opportunity to bring your 3D art to the canvas!)

Links: 
Twitter: https://twitter.com/AlanWyatt3D
Gumroad: https://gumroad.com/a/492773203
Blender Market: https://blendermarket.com/creators/alanwyatt3d
Download Files: https://1drv.ms/u/s!AkT_M95NR0GkndVCJYOhvb98ZzgZlQ?e=puU0jT

# Transcript
[00:00](https://www.youtube.com/watch?v=6uaJ0L4E390&t=0) Almighty here have you ever tried to make your 3D renders look like a painting I feel like this is something that a lot of 3D artists have tried to accomplish and it is quite a journey so 
[00:08](https://www.youtube.com/watch?v=6uaJ0L4E390&t=8) today I'm going to share with you the joy of trying to achieve a painterly filter in blender with just six node groups it's been a fun full journey of endless frustration and just a bit of 
[00:17](https://www.youtube.com/watch?v=6uaJ0L4E390&t=17) disappointment but as you can see from these renders it was all totally worth it this is a little complicated so I think it's probably best to go ahead and watch the entire video first and then 
[00:25](https://www.youtube.com/watch?v=6uaJ0L4E390&t=25) come back and pause on the Node layouts if you want to try it yourself while also pulling out your hair in frustration so let's go back to the dark ages of 
[00:33](https://www.youtube.com/watch?v=6uaJ0L4E390&t=33) 2019. [Applause] new numbers showing covet cases on the right mandatory evacuations are underway with 
[00:46](https://www.youtube.com/watch?v=6uaJ0L4E390&t=46) I was trying to capture that beautiful painterly effect from the damn keeper by Taco House everyone kept telling me to just do it in the compositor mainly didn't because 
[00:55](https://www.youtube.com/watch?v=6uaJ0L4E390&t=55) I wanted the effects to be live in the viewport I decided to make my own compositor in the Shader Editor to view in the scene but how I'm not a coder so I had to find a way to mirror all of the 
[01:08](https://www.youtube.com/watch?v=6uaJ0L4E390&t=68) objects in the scene all at once and then alter them in some type of way almost like a camera filter one thing I definitely did not want was to have to do it on each individual 
[01:19](https://www.youtube.com/watch?v=6uaJ0L4E390&t=79) object in the scene like previous attempts that's when I came across this article about creating a fake zoom lens in front of your camera and zooming in without moving it it was from before the 
[01:31](https://www.youtube.com/watch?v=6uaJ0L4E390&t=91) dinosaurs with blender 2.7 this was before Evie even existed it was using the refraction Shader a pretty underused node in the Shader editor I parented a plane to the camera made a lot of 
[01:40](https://www.youtube.com/watch?v=6uaJ0L4E390&t=100) adjustments and tweaks to the refraction Shader and boom my first camera filter was born then I just altered the normals of the refraction Shader with the texture and 
[01:50](https://www.youtube.com/watch?v=6uaJ0L4E390&t=110) voila a painterly effect or at least the start of one fast forward two years and I was working on my illustration Shader I was using the new geometry notes to instance paint Strokes across an object 
[02:01](https://www.youtube.com/watch?v=6uaJ0L4E390&t=121) and transfer the normal of that object to The Strokes this was used to capture the lighting in the scene it worked okay but the only problem was that The Strokes were just randomly placed and 
[02:11](https://www.youtube.com/watch?v=6uaJ0L4E390&t=131) needed to flow with the mesh the whole painting looked like a drunken monkey had just thrown up on a canvas and I was not happy with that I did find that if I drew curves onto the scene I could make 
[02:21](https://www.youtube.com/watch?v=6uaJ0L4E390&t=141) The Strokes kind of follow them somewhat but it wasn't automated and what it needed constant tweaking for each frame of an animation another year later I finally started to understand the 
[02:30](https://www.youtube.com/watch?v=6uaJ0L4E390&t=150) mysteries of geometry moves thanks to some of the best Note artists out there I asked Airedale doppelganger and nugget if there was a way to transfer or replicate the grease pencil line art 
[02:38](https://www.youtube.com/watch?v=6uaJ0L4E390&t=158) modifier into geometry nodes as curves to basically use them as the curves that would control the stroke Direction and guess what there actually was with all these pieces in place I could finally 
[02:48](https://www.youtube.com/watch?v=6uaJ0L4E390&t=168) create the blender Live Paint filter it's not easy and it requires six Super complicated did no groups and a lot of tweaking but it's worth it trust me the satisfaction of finally achieving the 
[02:58](https://www.youtube.com/watch?v=6uaJ0L4E390&t=178) painterly effect is unparalleled or at least that's what I keep telling myself so what exactly did Aaron Doppel and nugget show me occlusion colony this delightful feature 
[03:11](https://www.youtube.com/watch?v=6uaJ0L4E390&t=191) deletes all the faces of an object that the camera can't see how does it work well it's pretty simple it just shoots Rays from each point of your mesh towards the camera if it hits it's in 
[03:22](https://www.youtube.com/watch?v=6uaJ0L4E390&t=202) the camera view if it doesn't hit it's not so basically we were able to determine which part of the objects were visible and which weren't and then extracted The Edge that were part of 
[03:32](https://www.youtube.com/watch?v=6uaJ0L4E390&t=212) both of those selections and what did we get from all this hard work well just a mediocre started to align art modifier it's not perfect but hey it's a start and let me tell you this line art trick 
[03:43](https://www.youtube.com/watch?v=6uaJ0L4E390&t=223) has been a lifesaver for me with my illustration Shader I used it to distribute Strokes along the silhouette of the object to make it more unique and break up the space but for this project 
[03:52](https://www.youtube.com/watch?v=6uaJ0L4E390&t=232) I'm using it to create a flow map for each of the brush Strokes as you can see here I'm using a collection input to be the base of the line art that collection is the entire scene so the objects that 
[04:03](https://www.youtube.com/watch?v=6uaJ0L4E390&t=243) you have in your scene that you want line art to be coming from you need to be inputting that into that collection next up was Distributing instrument Strokes across the model didn't take too 
[04:11](https://www.youtube.com/watch?v=6uaJ0L4E390&t=251) long with geometry nodes obviously but I immediately found that I wasn't a huge fan of this the main reason was that depending on where the stroke was compared to the camera each object would 
[04:19](https://www.youtube.com/watch?v=6uaJ0L4E390&t=259) have to have a different scale of Strokes in the scene I was also not a fan of how I would need to have geometry nodes and special shaders on each individual object 
[04:29](https://www.youtube.com/watch?v=6uaJ0L4E390&t=269) yeah so I decided to tackle this in a different way and this ended up being the best decisions that I made I ended up instead bringing back the camera 
[04:37](https://www.youtube.com/watch?v=6uaJ0L4E390&t=277) filter plane and painting all of the line art and strokes of the scene to that plane well let's face it who has the time to manually create that plane comparing it to the camera 
[04:48](https://www.youtube.com/watch?v=6uaJ0L4E390&t=288) no one so that's why I like any self-respecting artist decided to tackle the problem in Geometry notes again sounds easy right wrong because apparently the camera must have 
[05:00](https://www.youtube.com/watch?v=6uaJ0L4E390&t=300) some kind of opinion on the matter too with its fancy settings for resolution and field of view behold the completed canvas that stretches to fit your camera's resolution and can even change 
[05:11](https://www.youtube.com/watch?v=6uaJ0L4E390&t=311) size depending on that pesky field of view just don't try to use it in North graphic view next up was the fun part parenting this is where things get 
[05:21](https://www.youtube.com/watch?v=6uaJ0L4E390&t=321) interesting because we must constantly keep that plane in front of the camera no matter how much it moves or turns and the best way to do that is with just a bunch of vector map which is basically 
[05:32](https://www.youtube.com/watch?v=6uaJ0L4E390&t=332) just a fancy way of saying confusing equations that you have to follow perfectly or everything will fall apart yep but don't worry I won't bore you with 
[05:41](https://www.youtube.com/watch?v=6uaJ0L4E390&t=341) the details the only part that I really need you to set is the draw plane offset in the middle which basically just controls how close or far away the painting is from your 
[05:49](https://www.youtube.com/watch?v=6uaJ0L4E390&t=349) camera oh and this group also does the camera alignment for your strokes this will make it swear your Strokes are always facing towards the camera perfectly definitely important for this 
[05:58](https://www.youtube.com/watch?v=6uaJ0L4E390&t=358) filter it was time to finally create The Strokes which shouldn't be too difficult it's just a basic grid again but for the Shader of this filter I used a square brush stroke so I had to make sure that 
[06:08](https://www.youtube.com/watch?v=6uaJ0L4E390&t=368) the grids squashed or stretched to fit the desired final shape of The Strokes I also set up the stroke UVS using some basic Vector math in the materials for this stroke make sure to store that so 
[06:18](https://www.youtube.com/watch?v=6uaJ0L4E390&t=378) we can use it later in the Shader editor okay now it was time to start bringing everything together and create the painting this group combined the data 
[06:26](https://www.youtube.com/watch?v=6uaJ0L4E390&t=386) and the mesh from the previous groups taking our plain and distributed The Strokes along it it also uses the line art to generate the rotation and the scale of each stroke making the flow 
[06:36](https://www.youtube.com/watch?v=6uaJ0L4E390&t=396) much much better this group also controls intensity and offset of the painting making Strokes away from the line art larger and less dense to retain detail while keeping the 
[06:47](https://www.youtube.com/watch?v=6uaJ0L4E390&t=407) overall shape abstract and simplified all in all it was a pretty standard process just like creating a painting while simultaneously tearing out my hair and questioning my sanity and finally 
[06:56](https://www.youtube.com/watch?v=6uaJ0L4E390&t=416) it's time to get our brush Strokes looking super close up and magnifying with the magic of the zoom don't worry this is actually the easiest of all the groups all we must do is take the 
[07:06](https://www.youtube.com/watch?v=6uaJ0L4E390&t=426) position of each stroke and subtract the camera location from it this heat trick gives us the normal direction for each of the refraction shaders which we can then send over to the Shader editor just 
[07:16](https://www.youtube.com/watch?v=6uaJ0L4E390&t=436) like we did our UVS now we have stored the normal direction as an attribute just like that okay so now we are done with the geometry notes here's the full tree I have a high-res image of the tree 
[07:27](https://www.youtube.com/watch?v=6uaJ0L4E390&t=447) in the description that you can download just to see it more precisely okay before we head over to the Shader editor first we need to make some adjustments in our render properties 
[07:36](https://www.youtube.com/watch?v=6uaJ0L4E390&t=456) it's crucial to use Eevee for the Shader because without it we'll run into issues with objects refracting through each other another important step is to enable the screen space reflection and 
[07:46](https://www.youtube.com/watch?v=6uaJ0L4E390&t=466) changing the trace Precision to one and Edge rating to zero these small changes will make all the difference in your experience oh and lastly go down to film and turn 
[07:57](https://www.youtube.com/watch?v=6uaJ0L4E390&t=477) up overscans to 10. now I know that it's maxed at 10 but sometimes you might have to put it to like 15 or 20 percent just type it in and it will work fine if you're getting weird black Strokes on 
[08:07](https://www.youtube.com/watch?v=6uaJ0L4E390&t=487) the borders of your render that is what will probably fix it now head into the Shader burst things first you need to change your material blend mode from alpha blend to Alpha hashed this is 
[08:18](https://www.youtube.com/watch?v=6uaJ0L4E390&t=498) because Evie does not like multiple transparent objects in front of each other so if you are ever using any transparent object in your scene it will require Alpha hash 
[08:28](https://www.youtube.com/watch?v=6uaJ0L4E390&t=508) okay now in the Shader editor all you must do is use the attribute node to import your stroke formal into the refraction Shader and crank up the ior to a number of likes that you hope that 
[08:37](https://www.youtube.com/watch?v=6uaJ0L4E390&t=517) I get on this video anything over 100 more this will essentially turn each stroke into a zoom lens and simplify the scene while keeping all the colors and the 
[08:46](https://www.youtube.com/watch?v=6uaJ0L4E390&t=526) values and if you want to take it to the next level you can pop up the roughness to about .025 this will make things a little bit more simplified next use a brushstroke alpha 
[08:57](https://www.youtube.com/watch?v=6uaJ0L4E390&t=537) mask like this one to make all of your planes look like actual brush Strokes just make sure that you're using the UV map attribute we made earlier don't use the normal texture coordinate node and 
[09:07](https://www.youtube.com/watch?v=6uaJ0L4E390&t=547) that is rotated correctly because nobody wants some wonky stretch painting Strokes now if you're feeling extra ambitious you can even do a grid Vector node like this to randomly select from 
[09:18](https://www.youtube.com/watch?v=6uaJ0L4E390&t=558) 36 different images from a single texture or even combine your mask bump and alien occlusion map all into one image not necessary but it does help with the optimization here's the tree 
[09:29](https://www.youtube.com/watch?v=6uaJ0L4E390&t=569) for the grid Vector note as well if you're interested not necessary but it's cool well congratulations you just learned how to add a painterly filter to blender 
[09:37](https://www.youtube.com/watch?v=6uaJ0L4E390&t=577) but if you're still struggling to understand don't worry just re-watch the video a few more times and maybe pause on all the node layouts you'll get it trust me or if you really want to 
[09:45](https://www.youtube.com/watch?v=6uaJ0L4E390&t=585) impress your friends you can check out the advanced version of this filter that is available on my gumroad it's jam-packed with extra options including q and value variation Minimax scale 
[09:52](https://www.youtube.com/watch?v=6uaJ0L4E390&t=592) control detail level base color and normal baking and even a new Shadow support that makes it easy for your Strokes to follow the Shadows I have another video right here that shows you 
[10:01](https://www.youtube.com/watch?v=6uaJ0L4E390&t=601) how you can use that advanced version and add it to your own scenes thank you so much for watching this video I hope that you enjoyed learning about this ridiculous Journey if you like the video 
[10:09](https://www.youtube.com/watch?v=6uaJ0L4E390&t=609) don't forget to leave a comment give it a like and maybe even consider subscribing to my channel I appreciate your support so much and cannot wait to bring you more content in the future 