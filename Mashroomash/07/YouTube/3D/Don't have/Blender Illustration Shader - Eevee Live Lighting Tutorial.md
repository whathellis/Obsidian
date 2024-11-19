---
URL: https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s
thumbnail: https://i.ytimg.com/vi/rXdeJ_sigf4/default.jpg
channel: "[[Tradigital]]"
published: 2021-03-19T12:18:28
duration: 2336
tags:
  - video/3D/texture/shader
done: false
cover: "[[Pasted image 20240715152739.jpg]]"
date: ""
---
[[Read it Later|Read it Later]] [time:: "38m 56s"]
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240715152739.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Blender Illustration Shader - Eevee Live Lighting Tutorial" src="https://www.youtube.com/embed/rXdeJ_sigf4?start=1036&amp;feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: This is a tutorial to show how to use my Illustration Shader on Gumroad. If you are interested in using it, check it out here! https://tradigital.gumroad.com/)

# Transcript
[00:00](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=0) hi guys uh this is like my third fourth take on trying to make this video i am not a youtuber at all um and i normally do not make videos like 
[00:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=12) this but i really wanted to try to make this as useful as possible for all of those who just recently purchased my shader thank you so much for all the 
[00:22](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=22) support but i really i i wanted to make this as easy as possible and it it is a confusing shader to use it's not 
[00:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=31) something simple that you can just slap onto an object so i completely understand why people are asking for a tutorial um it's just i'm a perfectionist so it's 
[00:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=40) going to take me a while to get this correct in the way that i want so um let's go ahead and get in and i'll try to explain as much as i can about this so 
[00:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=50) let's get started with just looking around first off this is a very very very simple scene as you can tell i've changed a few things 
[00:59](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=59) um with the scene and the shader since i released it on saturday i've done a few modifications mainly through doing this video i've kind of found little 
[01:11](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=71) mistakes and stuff that i wanted to personally fix so if you don't have the most recent version please go and download it and then come 
[01:20](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=80) on back on and we will continue with the tutorial so i'm going to walk you through the process of making one of these objects 
[01:30](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=90) completely from scratch i'm just going to go ahead and delete every single shader off of it delete the modifiers to where it it's just a basic 
[01:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=100) white sphere uh if we just hide every single other object and just bring in one of the lights um this will give us something to at least work with let's go ahead and change the 
[01:51](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=111) light just to a white a white color for now and we will work with this okay so i'm going to uh basically start from scratch with the sphere 
[02:05](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=125) nothing has been modified i do not believe in my settings so far and we're just going to get into it let's call this base 
[02:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=136) and we are going to add the illustration rendering node that i created last week it will basically do all the work that we're looking for right here but we need to add a few more 
[02:32](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=152) things to it first off we need to add our texture coordinates and we need to add our diffuse shader these are the only things you really need for it 
[02:46](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=166) now you can use any type of shader if you wanted to use a diffuse or uh glossy or if you wanted to even use principle you could um 
[02:57](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=177) but from my experience diffuse uses the least amount of data and this can be a very strenuous shader on your system depending on what you have 
[03:08](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=188) so in my opinion use the diffuse while you can or if you can and most likely it will work for whatever you're trying to do so let's go ahead and continue 
[03:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=201) now one thing is right now with the shader it doesn't accept proper uvs in the eevee shader that i'm showing you right now and the reasoning is because of geometry 
[03:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=215) nodes i took out a lot of the process if you ever read up my tutorial that was published by sketchfab a few months ago 
[03:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=224) it was created to where i could import a texture and it would create kind of like a painted effect on top of it this one cannot do that because i'm 
[03:54](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=234) instead of using solidify modifiers to give the effects that i do i'm using geometry nodes which is a lot easier to use but it comes with its limitations at the 
[04:04](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=244) moment i don't know if it's just a current error in the system or if it's going to be something that's permanent if they do fix it in the future or if i 
[04:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=252) find a way to fix it then i'm definitely going to correct it on the shader and i will email all of you and give an update on that um 
[04:22](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=262) okay so with this shader right now very default everything is just set to its um default level and so far it actually looks pretty cool 
[04:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=275) this basically is just giving you the light input and it's masking out a specific area where those brush strokes are now the thing is this is not just a texture that's applied on top and then 
[04:47](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=287) masked out this is a lot more complex each of those strokes individually are placed randomly across your object and each of them can be 
[05:00](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=300) either scaled individually or they could be changed value-wise or hue they're all on their own and it makes it that is what makes it so 
[05:14](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=314) complicated i guess you could say um because it isn't just a basic little texture input but it really does give some awesome effects 
[05:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=324) that you'll see later on let's go ahead and start by just going through the illustration rendering note and just explain what each of these settings mean so first off the rgb light input 
[05:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=335) this is a super cool one if you've ever watched any type of npr tutorial or stylized shading you might have seen where the where people use 
[05:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=350) light input color as a mask to make specific areas react to specific lights so let's say remember how earlier i had this this light where it was only giving red 
[06:06](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=366) light now what i could do is i could make it to where it only accepts red light or i could make it to where it only accepts blue 
[06:17](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=377) light and see currently there is none but there's also the secondary light that i have in the back that is emitting blue light while this 
[06:25](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=385) one is emitting red so you can make it input any specific color or light color i guess specifically so for this we're just going to stick 
[06:36](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=396) with red for our base layer we can actually have both lights on now but as you can see only one of them is getting affected by it 
[06:45](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=405) and that is a super cool tool to use especially if you're creating things like rim light if you need say a specific light just to be on the rim or the back 
[06:54](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=414) of the object then this is definitely a way to do that and it should work with any type of light as well i'm using point lights right now but if you wanted to use sun 
[07:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=423) spot or area it should work perfectly fine okay we'll move on so now this is basically color and fill color will be your light 
[07:13](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=433) and shadow normally but the thing is you can flip them around so i can't just name it light and shadow for right now we have color as our light 
[07:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=441) as you can see and we're just going to give it a bright reddish color kind of on the orange tint and then this is our shadow color 
[07:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=451) right here for our area fill and as you can see it's also going to be the background area that's why i call it the fill color it's basically everything that's in the 
[07:43](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=463) background or filling up the area for light and shadow pretty self-explanatory but it will flip um the two [Music] 
[07:54](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=474) colors and give you either your shadow side or your light side and that is all up to you and what you're doing this shader i'll go ahead and say it it 
[08:06](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=486) it requires some artistic knowledge like understanding light and shadow and how those things give you the form on your objects this isn't one of those type of shaders 
[08:17](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=497) that you can just slap on an object and expect it to work perfectly for you this is one where you have to tweak it adjust it get it to your liking and really portray that painted effect 
[08:30](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=510) but it won't happen by just throwing it on it'll just take some time and take some adjusting so with um the light and shadow 
[08:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=520) there are so many things you can do with that you may not think that right now you may think why not just invert it but it does do a lot and 
[08:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=530) i'll show you in the future next let's go ahead and actually go over here real quick to our blend mode and change it to alpha blend um if you've ever worked with 
[09:01](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=541) transparencies and e eevee you probably know the limitations to it it is quite annoying to work with sometimes but if you have it on alpha blend and 
[09:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=552) then have show back face off you can then use the fill and transparency setting right here and it will make it to where that fill 
[09:22](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=562) color is either transparent or the solid color and that is completely up to you and right now for our base layer this doesn't really make sense 
[09:33](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=573) but in the future once we get to our other layers it will make perfect sense so right now we're just going to leave it as fill okay stroke 
[09:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=584) and light mix so right here what we have is our light all this is is just the original mask that we had from the diffuse getting um converted into 
[09:58](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=598) the colors like it's going into a shader to rgb if you've ever used that before and then that rgb is getting transferred into a mask that is separating the two colors 
[10:07](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=607) and we can mix however much of those two we want so if say we don't want as dark of areas back here uh that is one of the options that we 
[10:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=616) can do that will kind of just clean up the inside a bit but we're going to keep it on probably about point one for now pretty low 
[10:27](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=627) okay soft and hard edge pretty self-explanatory again but what it does is it will soften or harden this edge if you look at it right here you can 
[10:38](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=638) tell it is harder now one of the things is like there's multiple ways to give a soft and hard edge to this shader um this is just the first method that 
[10:48](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=648) i'm showing you but you can also go into like your actual light setting and change the radius and you'll see it it does the same exact thing pretty much 
[11:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=663) and that is all up to you and it also depends on which objects you want this in because if you only want one object with a soft edge but like a lot of objects 
[11:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=672) with hard edges then you're probably gonna have to make your light radius pretty big and then just harden up everything else in the shader itself but that is all 
[11:23](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=683) going to depend on your project or whatever you're working on contrast basically moves it up and down [Music] 
[11:32](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=692) i mean it's pretty basic if you've ever worked with a gradient and you see contrast you'll see the center point basically move to both sides if you're ever raising or 
[11:41](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=701) lowering the contrast and that's what this does um if you have to fill the entire object ever then a good way to do that is just bring 
[11:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=710) contrast down to its zero i think its default is like .3 which is a good in between area but if you ever have to adjust that you definitely can 
[12:01](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=721) for object opacity pretty self-explanatory it just makes the entire object opaque for stroke opacity it will only do the strokes 
[12:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=732) on top of it so your first color input it will just make those um opaque and now stroke scale this one it will definitely affect the way that it looks and how realistic 
[12:29](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=749) try to stay as low on this scale as possible with bigger strokes because when it's very tiny strokes it's harder to tell that it is 
[12:41](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=761) um kind of painted on with the bigger ones it kind of gives a a better effect in my opinion um but that is up to you and whatever you're doing so i'm just 
[12:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=770) going to put this at like about 30 for now um stroke scale variation now this is where i was saying that each one is individual and can be 
[13:01](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=781) individually changed and kind of give a variation to specific areas so like say the value of the object or the strokes or the hue or the 
[13:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=792) scale and this one is the scale as you can see it is raising and lowering them all specifically but in a random way to where like 
[13:26](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=806) some strokes on here like this one right here is a lot smaller than this stroke so that gives you a good variation now the thing is you don't want to bring this 
[13:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=815) too high because it can kind of break your effect if we have all these areas in here it kind of gives a blotchy effect that 
[13:43](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=823) kind of breaks our whole light and shadow side and it's not quite what we're normally looking for so try to keep it on the low side not all the way down 
[13:52](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=832) because if you have it all the way down you'll get these hard edges that don't really look very good but if you keep it kind of at about 0.4 i think this gives a good effect yes 
[14:04](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=844) there is still some blotchiness in it but it's not enough to break the feel of where your light and shadow side is for value variation this one is super cool because it also affects 
[14:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=856) our fill color and what it does is basically just adds a little bit of value variation to everything but it also gives more of like a depth because now you 
[14:26](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=866) have strokes that are kind of underneath or over top other ones which is super cool because if you look at it right here everything is kind of just merged 
[14:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=875) but if you add that back in it gives a depth to it and this really makes a difference when you're working with the shader if you are 
[14:45](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=885) ever trying to make anything painterly then you are going to want to add value and hue variation because it's more realistic to actual painting because it's very rare that on an object 
[14:56](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=896) that you're using or if if you're painting like a flower or something you are going to have color variation not all of it is going to be the same yellow 
[15:06](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=906) or the same red like they will have a bit of variation depending on where it is so that's definitely something you can use you can also do the hue variation like i 
[15:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=916) mentioned again don't overdo it because if you do this way too much then you can definitely blow everything out of proportion 
[15:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=924) to where it doesn't make sense like i don't understand really what this color is anymore or what it's supposed to be but if you lower it down 
[15:32](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=932) to where you get just a bit then you still know okay well this is like an orangish sphere and that's really good because we can have all these different 
[15:41](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=941) um variations in the hue and in the value yet we're still understanding what our core color is and that's great so that is 
[15:51](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=951) just the basic shader by itself with no crazy settings on it but we're going to go ahead and show you what 
[16:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=963) the geometry notes do this is where things can get pretty crazy but i love it first off we notice that right when we turn it on it basically breaks whatever we have 
[16:15](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=975) and that is because we're using uvs right now this is really frustrating to me because i wanted to use uvs but i can't at the moment you can use generated 
[16:25](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=985) if you want but for objects like this with like a sphere it's not the best because it gives a weird um stretch effect on the side as you can see right here 
[16:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=995) it's not quite what i'm looking for and it might work for what you're doing but for what i'm doing this doesn't work so i use windowed now what window does 
[16:47](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1007) is it makes everything face towards your camera or your viewport whatever you're looking at because like if you zoom in everything just looks like a flat plane 
[16:57](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1017) everything moves along with you and in the viewport this may look weird but in the final render and if you have an animation or something it can actually look 
[17:09](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1029) very very good and it's because it kind of gives that flat effect that we're already looking for if you think about it because we are looking for a 2d 
[17:19](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1039) illustrated effect and it kind of gives that to us it adds it on so putting it on this is a very good idea but keep in mind that it will use 
[17:29](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1049) whatever the ratio is of your screen so sorry about the train whatever your ratio is like if i'm right here right now in my camera view 
[17:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1060) it's 1920x1080 so that's a very common um ratio to use but you've got to keep in mind that everything is going to still be kind of squashed down because if this is a 
[17:52](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1072) perfect square so if it was 1080 by 1080 then it would be perfectly fine but since we have it as an odd ratio like this we have to kind of tweak the texture to 
[18:05](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1085) make it look better so let's if you go underneath uv check right here and just input that there we go to where all we see is just the uvs 
[18:17](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1097) give it a second to compile you can tell that things are a bit squashed down now i just added this texture in there just to show people uh your scale and stuff and kind of help 
[18:29](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1109) you tweak all of it together at the same time and that just helps me personally you may never use this but to me it does come in handy at times 
[18:36](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1116) like this so what you're going to do is go over to your mapping node we're not going to actually mess with the shader itself because we don't want to mess up 
[18:43](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1123) anything on the inside because our cameras may be different for different scenarios we don't know if we ever have to do a vertical camera instead of a horizontal 
[18:53](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1133) then it could definitely add a completely different type of feeling to it so we want to just mess with the map uh the mapping node right here that's 
[19:02](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1142) connected into our texture coordinates and what you can do is just lower down your y value to match up with the square now i think i did the math i 
[19:14](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1154) think it's 0.56 is like the proper square if you're trying to make this into a square now i don't know if that is exactly right if i'm wrong 
[19:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1164) please correct me but it's what i've used for this scene and if you go back to the original shader you can tell okay this looks a lot more filled out it 
[19:33](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1173) doesn't seem squashed at all because if we go up you can tell like definitely squashed but then more filled so we will just work with that for now 
[19:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1184) and we're going to go ahead and move on so if you look underneath the geometry node you will see shadow thickness light thickness and stroke density 
[19:56](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1196) these are the three main settings that you're going to be working with whenever trying to do this the first one is shadow thickness and to us right now all this does is it looks like it just 
[20:06](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1206) makes the object a little bigger but what it's actually doing is if you go into wireframe you'll see that it has created a separate object outside 
[20:15](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1215) of your object it's basically adding a displacement and then duplicating the object but the thing is this object or this sphere is going to 
[20:26](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1226) accept a separate material than the one that we have on our original base one so we're going to go ahead and add on a second material and call this 
[20:38](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1238) shadow and we're going to create or copy what we have from our base material over to our shadow now you can either duplicate this one and just rename it or 
[20:52](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1252) you can copy and paste the nodes in there either way it doesn't really matter let everything compile it can take a little while sometimes but 
[21:01](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1261) once we have everything we can go into our shader view again or render view and um start tweaking this material so what we can do is 
[21:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1276) since this is our shadow layer that we're using we can turn it on shadow mode give it this darker material sorry one second right here and then make it 
[21:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1291) transparent if we go down and turn it on alpha blend you'll see that we have a good transparency to the object and this is really cool because 
[21:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1304) if we tweak this color just a bit make it a little darker maybe something like that and then if we look at it in our camera 
[21:57](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1317) view we can see that it kind of gives a broken edge effect and that's what i was after when i was first trying to create this shader my goal was for it to had 
[22:07](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1327) to have a broken edge because with anything that you're trying to make look painterly you kind of have to add the imperfections that are in painting 
[22:19](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1339) into the 3d model and one of the biggest imperfections is edges they are very hard to make look clean and uh when you're trying to paint something you rarely do 
[22:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1351) have a perfectly hard edge going around especially if it was a circle like a sphere that we're looking at right now it's very rare that you would have that 
[22:38](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1358) perfect edge going around so that's why we want it to be a bit more broken up now we can change a few things in here if we wanted we can make the 
[22:47](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1367) um the contrast a bit less or more depending on what you're going for one thing is this is where you can really use the stroke opacity to kind of just 
[22:57](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1377) add in or subtract however much you want if you want to add a bit less on the scale just to kind of give it more of a variation of different differentiation from the 
[23:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1392) original model and then also we can even change our scale variation so that it will create a more broken edge because see 
[23:25](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1405) if we have it all the way down where everything is just large we kind of lose that broken edge effect because it's just filling it all in so if we bring it up higher then we 
[23:36](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1416) get more of that broken edge and now if we go back into our shadow thickness right here you can see that all it's doing is just bringing it in and out now you'll see 
[23:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1424) this problem right here that is because this outside edge is casting a shadow on the inside now how we fix that is by going into our 
[23:55](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1435) shadow layer and then turning shadow mode to none we don't want that layer to be casting a shadow the only layer that we want to be casting 
[24:05](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1445) the shadow is our base layer because this base layer if if you also have it off on base layer then it's not going to have any cast shadows in your scene 
[24:15](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1455) which will look very odd if you start getting into things so it's best to just have the shadow layer and once we get to the light layer and 
[24:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1464) another particle layer all of those just have the shadow mode off while having the base layer on so just keep that in mind and if you ever do run into 
[24:34](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1474) weird shadow effects it's most likely going to be that issue so let's go ahead and put this at about point three or point two five and then we were going to 
[24:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1484) add in our our next layer 0.5 this is our light thickness it does the exact same thing as before if you look underneath wire frame we now 
[24:55](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1495) have three layers we have our outside or our base we have our shadow and we have our light which is our outside layer 
[25:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1503) and these all together are what create the entire shader effect and this is where i'm also going to show you how you can use that rgb light input because we're going to go ahead and i'll 
[25:18](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1518) show you this other way to create one of these materials if you just add on one and then do shadow and copy it this is maybe a lot easier 
[25:27](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1527) where you don't have to always duplicate the nodes and you don't always have to adjust the settings at the bottom because as you can see we're already on alpha blend 
[25:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1535) and shadows on none which is great so we kind of skip a step if you do something like that but now we can change this towards the light 
[25:45](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1545) let's add like a bright blue effect to it maybe i don't know like if we were using a cool light in the scene and then we can add on this to where it's only in the blue light 
[25:57](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1557) instead of the red one and right now it's not quite getting the effects that i want because we have some very soft edges 
[26:08](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1568) i think that it might be better if we had hard edges for this one and then raise the contrast up a bit and this is all up to you and what you're looking for i don't know 
[26:18](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1578) exactly so it is going to take a lot of artistic expertise just to get it how you want but once you do you can have a very cool 
[26:28](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1588) painterly effect to your objects in the scene i'm going to also raise the scale up a bit on this and raise the value variation 
[26:42](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1602) also up i also like to mess with the hue variation for like a light source like this it can look really cool to have a lot of hue variation now not on all colors it's going to 
[26:52](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1612) be a lot different like with the red color you remember how it was turning yellow and pink but with the blue it looks pretty cool because it kind of gives us this 
[27:00](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1620) um almost seafoam uh effect and it it really looks cool i like it so now we are going to add our last effect in 
[27:11](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1631) and this one is probably the one that is going to be the craziest and probably the most taxing on your system this is something that i had experimented in a long time ago 
[27:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1641) with particle nodes and with just the normal particle system particle hair on blender but with the new geometry nodes this is something that i was able to 
[27:32](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1652) change and make it a lot more optimized so with point distribution which is something that we use [Music] in blender for say spreading 
[27:43](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1663) grass across a field we can also use it to spread strokes across an object and this is basically a completely separate way of doing this whole shader 
[27:54](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1674) but we're combining both of the methods into one and it gives it a good variation it gives it a good way that looks randomized i guess you could say 
[28:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1683) because the more simple or the more um ordinary that your object looks like this sphere the more fake it's going to look the more 
[28:14](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1694) it looks like a 3d model it doesn't look like a painting so with the more effects that you can add on the better because the more it will look like a 
[28:23](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1703) painting we're going to go ahead and create a new material and just call this particles now the thing is we will never be actually using this material 
[28:37](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1717) on the object itself as you'll see in a minute but right now i just have it on the object so that it's easy for us to get to it if we ever have to adjust the settings 
[28:48](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1728) so let's go ahead and go into our group nodes again and we're going to use particle stroke node if you input that in and then let's 
[28:59](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1739) change our settings let's actually change them to the exact same that we have on our base shader so if we just hover over and do 
[29:08](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1748) control c and then control v we can actually get the exact same colors that we have on our base over to this oh i actually did it wrong one second 
[29:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1761) my fault that was the light input let's just make this red actually for what we're doing since this is going to just be basically adding on to the base layer 
[29:33](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1773) uh we're going to just use the red input and let's go ahead and lower this down a bit to maybe about 0.5 and 0.5 so now with this particle material we are going to create a new plane 
[29:49](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1789) this is just a ordinary plane nothing crazy about it but we're going to add that particle material on there and now we need to tweak some of the 
[30:00](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1800) settings in here with the blend mode and the shadow first off shadow on none make sure that that is on and then also with blend mode we're not going to use 
[30:11](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1811) alpha blend for some reason with eevee this is one of the many issues that i've run into with transparency is it will cause some artifacts and weird effects 
[30:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1821) when you have alpha blend going over each other or intersecting with each other i don't really know how to explain that other than the fact that it just doesn't 
[30:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1831) work and it looks very bad so what we're going to use is alpha hashed and i don't really know what the difference is between all of these 
[30:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1840) like it makes sense to me but i don't really have the knowledge to explain it to you but i'm going to just use alpha hash because i know it works 
[30:50](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1850) and you can use that too now what this node group does it's not just putting this one texture on there it's actually making it random for every single plane that we create 
[31:02](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1862) so as you can see each of these strokes is different and they're also being changed depending on if they're in the light or or not so as you can see this is darker 
[31:11](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1871) whereas this is lighter and then we're also getting that hue variation in there as well so this is a very even though it may look simple it is still pretty 
[31:21](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1881) complex and it does a lot and it's awesome like i really love it because it makes things like um particle distribution or point 
[31:31](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1891) density it makes it a whole lot easier if you want to add variation to those specific things if you're ever using this on just a texture feel free to use this node 
[31:41](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1901) because you can use whatever texture you don't have to use my strokes if you don't want to this is something that can be used on a lot of different tools 
[31:51](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1911) so let's go ahead and just put this in here and just hide it for now it'll just be below the ground plane once we add it back in but what we want to do is go to our 
[32:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1923) object and then underneath the geometry node right here with stroke object we are going to select that plane and what this will do is once you add density 
[32:14](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1934) you will see that it is adding these strokes all across the object which is super cool but it can get out of hand very fast because if you add too much 
[32:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1944) then it'll almost make no sense compared to just adding the amount that you need so make sure that you're being careful with it don't overdo it 
[32:34](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1954) and just keep it at it down low so these settings are pretty similar to like what we were working with with the shader itself stroke offset though will 
[32:44](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1964) basically displace it in and out depending on how much now each of these strokes is partially randomized by how far they are from the object 
[32:55](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1975) so if you say do offset to a point like this some of them are inside and some of them are outside and it'll give a kind of an odd effect to it so you have to 
[33:05](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1985) you have to just find that good spot where it will work perfectly it's going to be different for every object so i can't just give you that magic number and expect it to work 
[33:16](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=1996) but we're going to go ahead and look we have our stroke scale pretty simple easy to understand but what's cool about the stroke scale is if you want just tiny little strokes 
[33:29](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2009) just to break up that edge then this is all you need you may be able to with like get rid of everything else in the shader and just use this 
[33:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2020) but in my opinion it works better if we have everything on there and kind of giving it a good mix of all these different techniques and then stroke scale random 
[33:52](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2032) randomization pretty much the same as what we were working with earlier don't overdo it because as you can see it will make a mess but you can just tweak it to your liking 
[34:02](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2042) we can add more density or lower it down whatever you think is best for your specific project and then you'll have down here the seed now this is just a random c that goes 
[34:14](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2054) across the whole thing and what we can do is input our frame to where if you were doing an animation each frame would be a different seed 
[34:24](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2064) so all you have to do is do hashtag frame and this will automatically put whatever your frame is into this and it's just a driver like if you've ever worked with drivers before 
[34:36](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2076) you understand but what it'll do is whenever you play your animation it will automatically change for every single one and this is super cool for animation 
[34:45](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2085) because whenever you're thinking about something that would be 2d if you were doing it in a 3d type of scene like this 
[34:56](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2096) you would want to fake it as much as possible and you would want there to be difference between each and every frame because when it comes to painting on like 
[35:08](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2108) an animation every single frame is going to be different there is not going to be one area that is going to have the same stroke in the exact same spot so you want that randomization and i've 
[35:18](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2118) already got that built into the shader if you go in here you'll have this value node right here and all that is is just frame divided by 100 
[35:29](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2129) i'm pretty sure it would work fine if it's just on frame itself but right now i just have it on frame divided by 100 which also works perfectly fine and if if you are ever running into issues why 
[35:41](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2141) it wouldn't be which can sometimes happen when like appending um the material to another scene or something just go in here and add that back in and that should fix 
[35:51](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2151) the problem for you but that is pretty much the basics of this shader i know it is quite complex and it may not be what you were looking 
[36:03](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2163) for but it has definitely helped me personally like this is this is a dream actually getting to see it finally happen because i've been working on this shader for months 
[36:13](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2173) trying to tweak it and get it to a reasonable level for other people to use but it has had its hurdles and it's been hard but i'm very excited that i was finally able to release it and now 
[36:27](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2187) i'm finally able to release this tutorial one thing that you'll notice right before we leave is you'll have this um edge that is happening with the 
[36:35](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2195) particle node where it's it's kind of showing the back face of those specific areas and since it's not getting any shadow it's like why is there this light 
[36:46](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2206) edge on the shadow edge all you have to do is just turn on back face culling and it should fix it for you um it basically just makes it to where the 
[36:54](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2214) back ground or the back of each stroke is invisible and it's pretty simple self-explanatory but that will make a big difference once you 
[37:05](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2225) get into rendering so we can go ahead and just bring back our entire scene if we wanted and take a look at it one thing that's cool 
[37:12](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2232) is that if you ever have to just transfer over the object or the materials and stuff to another object you just do that simple copying and pasting like we did earlier 
[37:22](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2242) where all you have to do is say go in here and bring in our base our shadow and our light and then just duplicate them 
[37:37](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2257) right here and then if you want to just tweak the colors a little bit you can make them green like this one or keeping them the same that's all up to you you can do whatever you want with that 
[37:49](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2269) so it's very nice like i i love using this i'm excited to see what other people do with it because i know that i have not even reached the full 
[38:00](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2280) capabilities of what it can do i know that it can do a lot more and i know that there's a team right now that's actually going to be trying to use it 
[38:07](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2287) for an animation and i'm super excited to see how that ends up so it's really exciting to see you all getting passionate for this and i'm hoping that it's what you were looking 
[38:20](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2300) for if it's not please contact me if if there's something that you think it might need that i could uh try to implement 
[38:28](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2308) or if you know of a better way of doing specific things that i'm doing please tell me because i would love to know and i would love to make this right so i will be updating 
[38:40](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2320) the file like i said earlier and i will be uploading this video uh in the next few hours so keep an eye out for it and i i really hope it's what you want 
[38:53](https://www.youtube.com/watch?v=rXdeJ_sigf4&t=1036s&t=2333) thank you guys see ya 