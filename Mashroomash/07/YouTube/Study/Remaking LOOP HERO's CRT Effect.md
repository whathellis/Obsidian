---
URL: https://www.youtube.com/watch?v=aWdySZ0BtJs
thumbnail: https://i.ytimg.com/vi/aWdySZ0BtJs/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:54:53
published: 2022-03-19T10:00:01
duration: 488
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "8m 8s"]
# Remaking LOOP HERO's CRT Effect
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155504.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=aWdySZ0BtJs
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/aWdySZ0BtJs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: In this shader case study we analyze and recreate the CRT effect from Loop Hero. CRT Shaders are an effective way to add a nostalgic feel to your pixel art and should be part of any technical artist's visual library. 

Support me on Patreon!
https://www.patreon.com/acerola_t

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Code: https://github.com/GarrettGunnell/CRT-Shader
Join My Discord Server! https://discord.gg/FxGQvbfm6Y

Music:
Empty Ocean - Loop Hero OST
During The Test - Persona 3 OST
Afternoon Break - Persona 3 OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=0) hello everyone and welcome to a new video or a not so new video if you're watching this in the future today we're recreating an effect from loop hero a decently fun and unique roguelike where 
[00:11](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=11) you walk around in a loop killing monsters along the way if you look in the options you will find a crt shader option that when enabled toggles an effect that makes the game 
[00:23](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=23) look as though you're playing on a crt this sort of effect isn't exactly unique to loop hero but it's the most recent game i've played that has the effect [Music] 
[00:40](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=40) the first step of any case study is to try and identify the main components of the effect taking a look at this screenshot we can see that the corners of the image are spherically warped 
[00:52](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=52) there's a vignette or border gradient and the most important part each row of pixels is accentuated and visibly distinct to emulate the appearance of an actual crt an important observation is 
[01:06](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=66) that these crt lines are not warped along with the corners they remain completely straight since this is a post-processing effect we are going to use the uv coordinates to create all of 
[01:18](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=78) these effects for the uninformed uv coordinates are used to sample the pixels of the final render of the game and increase from 0 to 1 from the bottom left corner of the 
[01:29](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=89) screen to the top right this leads us into the first effect warping the corners of the screen this is achievable by utilizing a cubic function that takes in the linear uv coordinates and outputs 
[01:41](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=101) spherically warped uv coordinates that we can then sample the image with we start by converting the uv coordinate range to negative one to one which functionally centers the coordinates 
[01:53](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=113) then we create an offset value which will control how much warping occurs this value is calculated by taking the uv coordinates and dividing them by a curvature value the higher the curvature 
[02:05](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=125) value the less curvature there is finally we add to the uv coordinates by the coordinates times the squared offset value and then we convert the range back to 0 to 1 so that we can sample the 
[02:18](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=138) texture properly using a curvature value of 5 we can see that the corners are very clearly warped but due to how texture sampling works any uv coordinates outside the bounds of 0 to 1 
[02:31](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=151) are going to cause the image to repeat so we need to check if the uv coordinates are outside the range and if so color it black looking back at loop hero the corners 
[02:41](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=161) aren't warped nearly as much i found that with a curvature value of 10 the warping matched up perfectly with this curvature implemented we can now see the purpose of the vignette in the original 
[02:53](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=173) effect which is to obscure these hard edge cutoffs once again we want to center our warped uv coordinates by taking the absolute value we can see that the values 
[03:05](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=185) converge to zero as the coordinates approach the center of the screen if we then invert the values it sort of looks like a vignette but we can do better using any arbitrary number as a two 
[03:16](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=196) component vector for our vignette and dividing the x and y by the width and height of our screen respectively we get a value that covers a percentage of each side of the screen then we smooth step 
[03:29](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=209) between zero and our vignette vector using the inverted uv coordinates as the interpolator and we obtain a gradient around the border of our screen with any width we want since we used our existing 
[03:41](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=221) warped uv coordinates the vignette is thinner at the center of the edges as well there's many different ways to achieve a vignette but this method appears to be closest to the one loop 
[03:52](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=232) hero uses with a width of 30 it looks nearly identical to the original effect now that the warping and vignette are out of the way we can get to the fun part but we should learn a bit more 
[04:03](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=243) about crts so that we know what we're actually trying to model a crt is a television or monitor that utilizes a cathode ray tube a sealed glass vacuum tube that contains an electron gun a 
[04:16](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=256) system that deflects the electron beam and a screen that glows when struck by said beam the beam is distorted at an incredibly fast rate and scans over the screen over and over again to trick your 
[04:29](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=269) eyes into thinking there is a moving image the screen is curved to minimize the distortion of the image that is drawn on the screen which is why we have warped the corners of our image in the 
[04:40](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=280) crt shader the lines we see on crts are the blank gaps in the scan lines of the electron beam which is what the loop hero crt shader is trying to emulate if we zoom in on the loop hero effect we 
[04:53](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=293) can learn a bit about what they're doing the crt line effect repeats every three lines and the brightness oscillates so clearly they are using a sine wave since the crt lines are not warped along 
[05:05](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=305) with the corners in the loop hero effect we want to use our original uv coordinates if we take the vertical coordinate multiply it by the height of our screen shove it into a sine wave and 
[05:17](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=317) then multiply our final color by this value we can achieve these crt line visuals we know that they are multiplying their colors with this trig value because the 
[05:27](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=327) black parts of the image stay black since zero times anything is zero looking at our version of the effect we see that our pattern repeats every six lines instead of 3 so we need to double 
[05:39](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=339) our sine wave frequency we have the pattern correct for the most part but something isn't quite right the original effect has these green and red scan lines while ours does not if we go into 
[05:51](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=351) photoshop and sample the color values of each line we can find out even more about the effect this gray color has an rgb value of 192. when the crt shader is turned on it 
[06:04](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=364) oscillates between these three colors as we can see the first row of pixels has its red and blue channels increased while the green channel stays mostly unchanged the second row of pixels has 
[06:16](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=376) its green channel heavily increased and the third row is mostly unchanged this reveals to us that they are actually using cosine in addition to sine the cosine wave operates on the red and blue 
[06:29](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=389) channels and the sine wave operates on the green channel we know this because the red and blue channels have their peak amplitude opposite to the green channel additionally the sine wave has a 
[06:40](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=400) higher amplitude than the cosine wave for whatever reason another important observation is that all these color corrections are an increase on the original color values for the most part 
[06:52](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=412) which means the trig functions don't dip below one at its peak the green color channel increases by 30 percent and the red and blue channels peak at a twenty percent increase if we convert the sine 
[07:04](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=424) waves range to one to one point three and the cosine waves range to one to one point two and then multiply the color channels by their respective trig values we get a similar look to loophero's crt 
[07:17](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=437) shader a side by side comparison between the original and my recreation shows that it's basically the same with only very minor differences since this is a post-processing effect i 
[07:29](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=449) can apply it anywhere i want here's the effect applied to my game jam project the dating game which i think heavily improves the aesthetics but the vignette looks a little tacky i have a firm 
[07:41](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=461) appreciation for this effect from a design standpoint it's very unintrusive and does not obscure ui features like these but still meaningfully changes the visuals of the game reverse engineering 
[07:53](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=473) this effect was a lot of fun so if you like this kind of case study video style please let me know i've got to go now i hope you have a great rest of your day and i'll see you 
[08:03](https://www.youtube.com/watch?v=aWdySZ0BtJs&t=483) next time [Music] 