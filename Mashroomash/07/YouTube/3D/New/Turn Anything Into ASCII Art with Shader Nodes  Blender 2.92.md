---
URL: https://www.youtube.com/watch?v=9R_JBq3Hm6E
thumbnail: https://i.ytimg.com/vi/9R_JBq3Hm6E/default.jpg
channel: "[[Joey Carlino]]"
date: 2024-07-16T16:30:41
published: 2021-03-25T02:00:03
duration: 1682
tags:
  - video/3D/node
done: false
cover: "[[Pasted image 20240716163110.jpg]]"
---
[[Read it Later|Read it Later]] [time:: "28m 2s"]
# Turn Anything Into ASCII Art with Shader Nodes || Blender 2.92
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240716163110.jpg]]
````
````col-md
flexGrow=1
===
<iframe title="Turn Anything Into ASCII Art with Shader Nodes || Blender 2.92" src="https://www.youtube.com/embed/9R_JBq3Hm6E?feature=oembed" height="113" width="200" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;" allowfullscreen="" allow="fullscreen"></iframe>
````
`````
(Description:: ⚠️ There is another way to do this with geometry nodes! Watch this to learn more: [[../../Inspo/The new ways of Blender|The new ways of Blender]])
Get it on Gumroad: https://joeycarlino.gumroad.com/l/jdlrQ

Patreon, Gumroad Shop, Discord, and other stuff:
https://linktr.ee/Joeycarlino
 
I used Affinity Designer in this video, but if you want to use something free, check out Inkscape or GIMP.

Intro sounds by Samaquias Lorta:
https://www.samaquiaslorta.com/

Timestamps
Intro 0:00
Summary 0:31
Making Sprite Sheets 2:22
Text FX 3:21
Sprite Sheet Layout 7:11
Pixelation 8:17
Tiling 13:38
Sprite Sheet Setup 16:31
Converting Image Into Characters 19:02
Contrast and Color 20:51
Switching Texture Coordinates 22:25
Removing Empty Space 25:28
Outro 27:35

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
# Transcript
[00:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=2) [Applause] in this one i'll be showing how you can convert your images and videos into ascii art basically so your picture is made up of a bunch of characters like 
[00:12](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=12) this and we're going to do this without the compositor this is all using shader nodes for those of you who want this effect 
[00:17](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=17) without making it you can grab it for a few bucks on gumroad and made it neat easy to adjust and it includes a few different character sprite sheets links are in the description before we 
[00:25](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=25) dive in here's a little summary of the steps we'll be taking and if you want to jump forward on putting time stamps for each step first we make a sprite sheet that has all the 
[00:33](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=33) characters we want to use i use a free add-on for this called text effects that makes it easy to export each character as a separate square image 
[00:39](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=39) then i bring it into affinity designer and lay out the characters in order of how much space they take up basically like light dark values i'm doing mine horizontally 
[00:48](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=48) you could use a free program for this like or inkscape too then you just have to export that image second step is pixelation we go back into blender add in a plane and put our 
[00:57](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=57) video onto it with the window texture coordinate to pixelate the texture coordinate i separate it into xyz channels and then i add a math node set to snap 
[01:06](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=66) onto each one of those channels and then combine them back together the snap nodes let you decide how many pixels you want on each axis third step is tiling basically we take 
[01:14](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=74) our pixelated texture coordinate and subtract it from the original coordinate this places the zero position in the corner of each pixel so that we can place our characters from the sprite 
[01:22](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=82) sheet into each pixel accurately you just have to multiply the coordinate by however many pixels you have to make them the right size step four is 
[01:30](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=90) getting our sprite sheet to work we bring in our sprite image and plug the tiled texture coordinate into it since our image is horizontal and each character is a square just like our 
[01:38](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=98) pixels we just have to scale our sprite image down on the x axis to get rid of any stretching the x scale needs to be 1 divided by however many 
[01:46](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=106) characters are in your sprite sheet so if you have 10 characters in your sprite sheet the x scale would be 1 divided by 10 or 0.1 to choose which character to 
[01:53](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=113) place we just move the x location like this i use a math node set to snap for this too if you give the increment the same value as the x scale you'll only see one 
[02:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=122) character at a time and there won't be any weird sliding problems like this step 5 is getting our image to control the sprites to do that i use a separate hsv node 
[02:10](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=130) and plug the v or the value into the value of our snap node if it doesn't look right you might have to invert it first and that's pretty much it there's more you can do but 
[02:18](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=138) those are the basic steps to get this result alright let's walk through from the beginning now all right so i'm in blender 2.92 for this one 
[02:25](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=145) first thing i'm going to do is just delete everything except for our camera and then i'm going to select our camera and hit alt g and r to just reset its location and 
[02:34](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=154) rotation and next i'm going to go to edit and preferences and you're going to want to install the text effects add-on if you're doing it 
[02:44](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=164) the same way i am it is free you just have to you know select it turn it on and also later i'm going to be using the node wrangler so you might as well turn 
[02:52](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=172) that one on too and then i'm going to select our camera and just pull that up slightly and with that still selected go over to this little camera button right here 
[03:00](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=180) and i'm just going to change this from perspective to orthographic and then if we hit zero we'll look through our camera right here i'm just going to select output properties right 
[03:09](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=189) here and change our resolution to something that's square you can set it to anything you want i'm going to make mine pretty small it's just going to be 32 by 32. 
[03:17](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=197) our characters are going to be pretty small in the end so i don't need a lot of resolution all right next you want to hit your n button to open up the side panel right 
[03:25](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=205) here go to text effects right there and just click the add button and choose simple and it'll add this in for you right here 
[03:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=212) and for the effect i'm going to choose read lines and right here it gives us an option to add a text document right here and so i have to make one of those i'm 
[03:42](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=222) just going to drag this down and make a new window and i'm going to select text editor so now that we have this open i'm just going to hover over it and hit 
[03:52](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=232) control spacebar and it'll just maximize that window so i'm going to hit new right here to add a new document and we can just put in whatever characters we want just 
[04:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=242) separated by a line break like that so i already have my character selected i made this earlier and i'm just going to use the same ones it's just nine characters with a space 
[04:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=251) at the end but we don't need to put the space that's later so we have them all input right here we can just hit ctrl spacebar again and over here we're just going to select 
[04:20](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=260) that document it's just called text right here and then hit time control and then we can select which one we want with this right here we just have to choose the right 
[04:30](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=270) duration so i'm going to change this to nine because we have nine different lines right here this is just selecting what line we're 
[04:37](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=277) on basically so we can do it like that so with this selected i'm just going to go over here to object data properties the little a right there and under alignment 
[04:48](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=288) paragraph and alignment i'm just going to change both of these to center so our text is in the center and if you want to change the font you can do that right here too 
[04:57](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=297) i'm going to change mine to uh courier and we can just scale this up until it's pretty close to the edge right there i'm just going to want to run through 
[05:07](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=307) this and make sure that it's not going off the edge at all and if it is you just scale it down slightly another thing we can do is in here just 
[05:16](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=316) type in hash and then frame and it'll just match the frame that we're on like this you can use the arrows to navigate 
[05:24](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=324) and for our timeline we only want nine characters so i'm just gonna change the end point to nine like that see this is going off the edge like that 
[05:36](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=336) so when you have it all scaled the way you want i'm just going to add some materials so i'm going to go into render the viewport shading right here and i'm 
[05:43](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=343) going to turn off any um world lighting you have so it's just going to be black like that for the material i'm just going to add a new one 
[05:52](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=352) i'm going to change this to emission you're going to want to turn bloom off for this i'm using evie so i'm going to turn bloom off you can pretty much shut all of this off because 
[06:03](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=363) it's just black and white and i also want this to be completely white so i'm going to color management right here 
[06:10](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=370) and change this from filmic to standard and this will make it completely white then you just want to set your output settings so i'm going to change this to 
[06:21](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=381) black and white because we have no color compression i'm going to turn down all the way and i'm going to keep it as a jpg sequence and you just want to select 
[06:29](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=389) your folder when you have everything set up you just want to go to the first frame and make sure that you're on your first character right here turn off 
[06:36](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=396) all your gizmos and all overlays and stuff like that and then go to view and viewport render animation and then we just want to check this in 
[06:45](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=405) the folder that it exported to see if we have everything it looks like we're missing the period at the end and we're this is duplicating like i said it gives me some weird errors 
[06:53](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=413) sometimes i haven't completely figured out the quirks but i know how to get it to do what i want so i'm just going to add another frame in here so this is 10 
[07:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=422) and we're just going to try again viewport render animation and now we have all of them i'm just going to delete the first one so we don't have any duplicates 
[07:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=431) all right now i'm just going to shut this i'm going to open up a design program called affinity designer which isn't free it doesn't cost a lot i think it's like 
[07:19](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=439) 50 maybe something like that yeah but you can use something like inkscape or or whatever so i'm going to make our document we know that each of our images 
[07:29](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=449) is 32 pixels by 32 so i'm going to make the height 32 and we're going to make this horizontal so 32 times 10 is 320 and then we just want to drop 
[07:38](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=458) all of our images in here and i'm just going to spread them out evenly except for the end which is going to be a blank spot so here we are and i'm just going to 
[07:54](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=474) swap these two because i think this one does look a little darker slightly like that i'm just going to distribute these again and then for the last one i'm just going 
[08:06](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=486) to make that black like that so we have a blank spot and then i'm just gonna export this as a jpg so we're on to our second step now 
[08:19](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=499) i'm just gonna add in a plane and i'm gonna look uh down onto it from the top like that and go into the shading tab right here 
[08:31](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=511) and for this i'm going to want to look through the camera and just zoom in until the plane is filling up the screen like that and you just want to select 
[08:39](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=519) your plane and we're going to put um our whatever image you want to convert into ascii art you're just going to want to put that on here so i'm going to add a new material 
[08:47](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=527) right here and delete this add in an image texture plug that into the surface you can just plug it in directly or you can feed it into an emission 
[09:00](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=540) shader and then i'm going to bring in a texture coordinate and we're just going to plug in the window right there and we just want to load in our texture now 
[09:10](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=550) and when you plug in the window right there it's just going to be the same shape as the window that you're using so you just want to make sure 
[09:20](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=560) if if this looks warped at all to you you want to make sure that your output resolution is the same as the video that you're using or the image or whatever i'm using a video for this and i know 
[09:30](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=570) that it is 628 frames so i'm going to change this number to 628 i'm also going to change this over here to 628 
[09:39](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=579) our ending frame and i want to turn on cyclic and auto refresh and i'm also going to change this from linear to closest and instead of repeating i'm going to do 
[09:51](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=591) extend like that all right so what we need to do is we need to pixelate this that's what we're going to be doing first basically we're just going to be taking 
[09:59](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=599) our window texture coordinate right here i'm going to bring in a separate xyz and for this we only need x and y 
[10:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=611) but i'm going to do it for all three just to be thorough and then i combine x y z and you just want to feed all these back in 
[10:23](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=623) and this might seem silly to just like separate them and then combine them again but what we're going to be doing is putting stuff in between here so we're going to be 
[10:29](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=629) separating each channel altering them and then putting them back together and what we're going to do is add in a math node i'm going to put that 
[10:38](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=638) right there and change this to snap and so let's take a look at what this is doing this is what the texture looks like originally and then when we snap it 
[10:49](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=649) now it's just two different portions just black and white and why is that happening it has to do with the increment right here so if i add in i'm just going to 
[10:59](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=659) duplicate it to add a second math node and change this to divide and so i'm going to make the top one one and the bottom one is going to be however many different colors we want 
[11:09](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=669) right here so if we want two i'm just gonna plug this into the increment we have two if i want four it's gonna split the gradient into 
[11:20](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=680) four solid colors and that's how it works basically so we're gonna do this for each channel right here for the x y and the z like i said you don't need to do this 
[11:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=692) for the z but i like doing it just in case i decide to make this three dimensional it's now a three dimensional texture and you can just plug this into the 
[11:43](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=703) increment for each and then when we put them back together now it's pixelated you can see all you have to do is change this value right here 
[11:53](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=713) to change the resolution like that you can also get this effect just by using a voronoi texture like this and choosing position and turning the randomness all the way 
[12:08](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=728) down that gives you the same thing but you don't have as much control over like the resolution the way i'm doing it you can adjust the size of the pixels so what we need 
[12:19](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=739) to do to make these squares is just change the increment but only on one axis i'm going to change it on the x-axis so to do that 
[12:27](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=747) you just need to use your aspect ratio basically just know your screen resolution what you have your your camera set to right here i'm just going to duplicate this divide 
[12:36](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=756) node and i'm going to plug in 1080 on the top and 1920 on the bottom so we have our height and our width right here and then i'm going to duplicate this 
[12:47](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=767) again i'm going to put this between the snap and i'm going to feed the uh the increment into it change this to multiply 
[12:56](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=776) i'm just going to change this to 1 for now so nothing is changing you want to make sure that this is plugged into the increment or else it's not going to work right and 
[13:05](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=785) then you just want to plug this into the second value and this should work fine now these should all be uh square and you just got to remember 
[13:14](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=794) that when you're setting the resolution that's the height right here so you can see our value is 4 and we have four pixels going up like that and then you just wanna plug this into your image 
[13:24](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=804) right there and let's take a preview so this is pretty low resolution so let's turn this up you can see it's pixelated now you can 
[13:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=812) change the resolution like that so i'm just gonna have this set to eight for now while we do everything else so we have our pixelation now and we can move on to 
[13:40](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=820) step three which is tiling basically to do this it's pretty easy we're just gonna take vector math node and with the vector math you want to set that 
[13:49](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=829) to subtract i'm going to plug this one into the bottom and we're going to plug our original um window right here into the top 
[13:59](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=839) and let's take a peek so now what this is doing is putting the zero point into each of the corners right there and what this does is it lets us tile it but this isn't working right because we 
[14:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=851) need to scale this up afterward so i'm going to add in a mapping node and i'll show you how i like to test this out instead of using this image texture 
[14:18](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=858) i'm going to add in another vector math node and i'm going to change this to length and then after that i'm going to add a math node 
[14:27](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=867) set to greater than i'm gonna change that to one and basically we just need to um scale up to whatever our resolution is which 
[14:37](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=877) is pretty easy we have our resolution right here so i'm just gonna create a value node and i'm gonna put our resolution in it so we can reuse this value we have this 
[14:45](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=885) set to eight right now plug it in there and i'm also going to plug that into the scale right here of our mapping texture now you can see we're actually 
[14:55](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=895) able to see some things but it's stretched out on the x-axis so once again i'm going to add in a combine xyz that way we can alter each of these 
[15:05](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=905) separately i'm going to plug this into all of them for now and let's see which one we need to change add a math note in put this into the x basically what the length node is doing 
[15:20](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=920) is checking the distance to the zero point so when i set this to one it's making a black circle with the radius of 
[15:28](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=928) one basically what i'm looking for is for it to be touching both of the sides like that and then we know that this is actually square but 
[15:38](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=938) i don't want to have to guess like that i want it to be automated and so the easiest way to do that is once again we need our aspect ratio because it's the same number 
[15:47](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=947) but it's uh it's flipped so an easy way to solve this is add in two value nodes these are going to be once again our uh our width and our height 
[16:00](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=960) so our height is on the top 1920 is our width and we can just plug these in here and then i'm going to create a second one that's just going to be the same thing but the values are switched 
[16:14](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=974) like that and you can plug this into that multiply node and now this should match just fine and we can get rid of these because we're just using that for viewing 
[16:26](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=986) and now we can see it's actually tiling but we don't want to tile this we want to tile our characters so now that we have our tiling working we can move on to step 4 which is our 
[16:35](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=995) which is getting our spreadsheet to work so first i'm just gonna bring in our sprite sheet image you can just duplicate this and load it in there we go you can see 
[16:46](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1006) it's pretty stretched out so i'm just going to plug in the um the tile vector that we just made into that we're going to view it you can see this is pretty stretched out 
[16:57](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1017) so i'm going to add a mapping node in and put that before it and basically what we need to do since we know that all of our pixels are squares 
[17:09](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1029) and all of our tiles are squares all of our characters are also square because that's how we made it we just have to stretch this out until it lines up 
[17:17](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1037) right here you can see if we take this and just divide it by 10 that's how many characters we have this lines up perfectly so that's what we need to do 
[17:27](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1047) so what i'm going to do is i'm going to add in another combine x y z and this is gonna be for the scale i'm just gonna change all these to one for now so when we plug it 
[17:37](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1057) in it doesn't you know go to zero and i'm gonna use another math node change this to divide and i'm gonna do one 
[17:44](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1064) on the top and then however many characters we have in our sprite sheet on the bottom like that so we only have ten and i like to do it this way because if you switch 
[17:53](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1073) out the sprite sheet all you have to do is update this number right here to match the amount of characters you can just plug that into x and that 
[18:01](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1081) should work fine and if we want to select a different character we just have to move the x location right here you can see it just slides between them like 
[18:10](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1090) that but we don't want it to slide like that so i'm going to add in another math node i'm going to change this to snap like we did before and i already 
[18:19](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1099) explained how this worked earlier basically we're just going to use the same number for here because it needs to match however many characters we have 
[18:28](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1108) and once again another combined xyz so because we only want to edit the x so i'm going to change all these to zero plug it in and we can plug this into the x 
[18:39](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1119) and now when we move this value right here it just snaps between them instead of sliding and when it gets to the end it just goes black because we have this 
[18:48](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1128) set to extend if we have this set to repeat it will just repeat itself like that but we do have one black space in there which is nice 
[18:58](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1138) so i am going to take this and keep it on extend right there next we want to make sure that our image is actually driving how these are selected 
[19:07](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1147) so make sure that your image is using the pixelation vector and not the tiling one we can just view that and i'm going to turn this up to something a little higher 
[19:19](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1159) and our resolution is right here so i'm going to set this to maybe 32 just so we can actually make sense of what's going on and i'm just going to bring in a 
[19:29](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1169) separate hsv and this stands for hue saturation and value so when we plug it in here each of these is going to be black and white but if we bring in a combined 
[19:41](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1181) uh hsv and just change all of these to one you'll see that this drives the hue the strides the saturation and then this is the value right there what we want to do 
[19:54](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1194) is we just want to use our value which is like how light and dark things are and we know that this is only ever going to go as low as zero and as high as one 
[20:03](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1203) so we can just plug this directly into our value because this is only ever going to go as high as one if this goes past one it's just going to be black which is 
[20:14](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1214) fine so we're just going to plug this in and i think this is reversed so i'm just going to add in an invert node 
[20:21](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1221) plug that in right there so now you can see when we turn our resolution up even higher maybe something like 96 we're actually getting what we want now 
[20:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1232) and it's actually picking up the lighter spots with the first color this is this is why you got to make sure your sprite sheet is in order of you know like how much space each 
[20:41](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1241) character takes up and if this doesn't look right to you when you do it you just might have to rearrange your characters so that they're in the right order we 
[20:48](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1248) can even play it and see it moving now so this is the basics of it but we're going to take it a little further i want to be able to control the 
[20:56](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1256) contrast and and brightness of this so there's actually a node just for that you can just type in contrast when you search and you can affect the 
[21:05](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1265) contrast like this you're also going to want to make sure that the snap node is clamped and i also want there to be color so 
[21:13](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1273) to do that i'm going to add in a mix rgb right here i'm just going to plug our character into the factor and we're going to use it like a mask so if you make the first one black 
[21:23](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1283) and the second one white we'll have just what we had before like that and if you want you can actually just use this to control whatever color you want your characters 
[21:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1292) to be but we are going to just plug our color directly into that white slot and you can see our color is coming through now but our periods are like really dark we 
[21:44](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1304) don't want that we just want it to be like basically like this we want the hue and the saturation with the value turned up so there's no black we don't have any darkness 
[21:53](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1313) because our value is already being controlled by the sprites themselves so we just want to separate the hsv and combine it again but don't plug in the value just turn it 
[22:03](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1323) all the way up to one and you can plug that into that second slot right here and now let's take a look at that so that looks a little better oh yeah one 
[22:13](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1333) thing i didn't mention is that um you should probably turn this to to not be filmic to instead be standard and that'll give you more accurate 
[22:22](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1342) colors that actually match the image you brought in one thing i'd like to be able to do is zoom in on this and actually look around and change the 
[22:29](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1349) angle and stuff but you can see when we move this because it's using the window coordinate it doesn't really work that way but there is kind of an easy way to 
[22:40](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1360) to switch the texture coordinate basically what i'm going to do i'm just going to shift right click and drag to create this group node right there 
[22:49](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1369) and i am going to add in another mix rgb and plug window into the bottom and uv into the top and this lets us switch between the uv and the window 
[23:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1382) coordinates basically just by changing the factor right here but you can see it stretches it a little when we switch it to uv 
[23:10](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1390) so in between here we just need to add in a mapping node and just warp the scale just like we did with the tiling so i'm going to add in a combine x y z right here and plug this 
[23:24](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1404) in make sure all of those are set to one so we're not messing it up too much and what i want to do is affect the y right here 
[23:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1412) and so i know we need a bigger value so once again we're going to go back to our aspect ratio but which one do we want we want the bigger one which is going to have the bigger number 
[23:41](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1421) on top so that would be our bottom one right here we can just plug this one into our y and that should work fine so now we can actually look at it from a 
[23:52](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1432) different angle and it'll work okay too and one reason i like doing this so much being able to switch back and forth is because if you want this to be really high res see if i set this to 
[24:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1442) something like 480 and then i try to render it you can't really make sense of each individual character when you zoom in it kind of maxes out at i think around 
[24:13](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1453) like 96 you can still render it and zoom in and still see each individual character and so if you do 
[24:21](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1461) want to be able to like zoom in closer and get more dynamic with it you just want to switch to uv right here and then you can actually get like as close as you want and still 
[24:32](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1472) be able to see each character like that you can shoot it from different angles and stuff i think that's pretty cool and if you want to change the art that you're 
[24:41](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1481) converting you just have to you know load up a new image right here so this one is a simulation that i did you just have to make sure that it 
[24:48](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1488) matches the frames again so we have this right here it's just a fluid sim that i made earlier 
[25:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1502) and if you want to change the sprite sheet because i already have a few you just want to load up your new sprite sheet right here and you just want to change 
[25:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1511) this number to match the amount of characters that are in that so in this one i have 95 characters quite a bit more now you can see we have some other 
[25:22](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1522) characters going on in there and i also have a block that's fully white i thought that would be interesting another thing if you don't want any 
[25:30](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1530) black space right here and you want your darkest value to be something to be a character you know like a period or something like that you are going to 
[25:38](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1538) have to change one more thing so let me load in a sprite sheet here 93. this one doesn't have any uh any black space so then i just need to change this to 93 
[25:51](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1551) so it's the right amount of characters what we want to do is instead of extend we want to repeat like this you can see when we turn the contrast up 
[26:00](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1560) the dark spots are getting bright for some reason and that's because when this rolls over one it goes back to the same um as zero to stop so to stop that from 
[26:13](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1573) happening i'm just going to make a a clamp node put it right here and we just want to change the maximum to not to basically be a little lower so it 
[26:26](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1586) never actually gets to one so to make the value that we need i'm going to add in a math node set to subtract i'm going to make the top number one 
[26:36](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1596) and we're going to subtract this number right here so we're just going to subtract 1 divided by 93. we're going to subtract this little number 
[26:45](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1605) from one so it's really close to one but it never actually reaches one and now you can see our lowest value is this period and since we're clamping 
[26:54](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1614) it you can uh you can turn clamp off right here if you want to it doesn't really matter it's just a redundancy and if you want this to be more than just a filter 
[27:02](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1622) you can also use this you can just plug it into you know whatever other texture you want so you could plug it into a mission you want to be like a tv screen 
[27:11](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1631) something like that or you could plug it into like a principled bsdf just into the color see what that looks like 
[27:21](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1641) and then i'll just switch this to the uv coordinates we can have a look at a different angle let's see turn the roughness all the way down that's kind of neat so that's it if you 
[27:36](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1656) don't want to make your own sprite sheet i put some on gumroad for free and once again you can get the completed ascii art generator for a few bucks over there too 
[27:43](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1663) as well as some other things like lightning models barbed wire and my glitch effect i also recently set up a discord server so if you need help with blender stuff 
[27:51](https://www.youtube.com/watch?v=9R_JBq3Hm6E&t=1671) if you want to help others or if you just want to hang out you can find the link in the description thanks for watching have a good one 