---
URL: https://www.youtube.com/watch?v=Gjr2CUczDpk
thumbnail: https://i.ytimg.com/vi/Gjr2CUczDpk/default.jpg
channel: "[[Nitro-Gen Studios]]"
date: 2024-07-22T16:02:10
published: 2024-05-15T05:16:43
duration: 483
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "8m 3s"]
# The coolest shader effect that nobody uses
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722160221.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=Gjr2CUczDpk
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/Gjr2CUczDpk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: So posterization is just so insanely cool and for some reason it's very underused in the gamedev industry. In this video I explain how posterization can be used in some unconventional ways to generate some incredible effects, and even custom color palettes at the end.

0:00 Intro
0:24 Example 1.
0:54 RGB Posterization
1:45 Example 2.
2:26 HSV Posterization
4:18 Palette generation
6:15 Multiple palettes
7:34 Outro

# Transcript
[00:00](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=0) Posterization, also known as color quantization 
is a quite uncommon filter that's mostly used in   stylized rendering. I've been experiementing 
with this unique effect for over a year now,   but I haven't managed to implement it into a 
game, until now. In simple terms, posterization   is about taking in a value and then doing some 
simple calculations to limit the range of the   output based on a parameter called &quot;steps&quot;.
Let's quickly take a look at this example.   
[00:26](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=26) Here we have this black to white gradient. After 
applying the posterization filter with 16 steps,   you get this image as a result. The color range 
gets limited to a smaller range of 16 colors,   so we get these nice bands of color. The step 
parameter doesn't necessarily set the number   of colors on the end result. This only happens 
for values between 0 and 1, while inputs outside   that range will be snapped to the closest step.
After seeing this example, the first thing you'd   
[00:53](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=53) probably try is applying this effect to the 
RGB channels of an image; however you might be   surprised to see that it doesn't resemble the 
first image I showed earlier at all! We get a   bunch of these really weird colors that weren't 
originally present on the input image and a very   high contrast that is probably not desired. 
These weird colors appear because each color   channel gets offset a little bit by the filter, 
but when multiplied by the 3 color channels,   
[01:19](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=79) this drastically changes the final color. This 
basic implementation could be very useful for   some temporary effects like getting hit, but I 
wouldn't use it all the time as a full-screen   effect. Let's see if we can take this further.
The use of posterization isn't only limited to   using it on RGB values - as I sort of teased that 
before - in fact, you can use it on any floating   point value! Let's take a look at this other 
example. Here's a cylinder that I subdivided   
[01:47](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=107) a bunch of times. I'm going to use a custom shader 
with a posterization function already implemented.   In the vertex shader, lets offset the vertices 
on the Z axis using a sine wave to make it look   wavy. As you'd probably expect, the result is very 
smooth, so let's change that with posterization.   By taking the calculated offset and running 
it through the filter, we get this interesting   looking choppy effect. By changing the step 
parameter, the range of valid positions increase,   
[02:14](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=134) which makes the animation look faster. Neat!
Now all of this is cool, but now you probably   want to know how I achieved this &quot;cleaner&quot; 
posterization look for the gamejam version of   my game. From our previous tests, posterizing 
the RGB values of an image seemed to be a bad   idea. However there exists a color space that's 
more suitable for what we're trying to achieve.   The HSV color space is something you definitely 
heard about if you are watching this video. While   
[02:43](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=163) RGB takes in red, green and blue values to make 
a certain color, HSV takes in hue, saturation   and value (also known as brightness). It's a very 
commonly used color space, and I highly recommend   using it as it's a lot more powerful than RGB. 
Converting from RGB to HSV sounds like a very   complicated thing, but thankfully some 
people have already done the work for us,   so we can just copy their solution instead. 
(credit popup for a few seconds)
  
[03:09](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=189) Using their function, we can split any color to 
hue, saturation and brightness channels. We can   already do a bunch of fun things with this, like 
making a slider to control saturation for some   accessibility settings in the future. But of 
course with any float value, we can posterize   these as well. We're mainly interested in the 
brightness value, as modifying it will keep most   of the original colors intact. Let's save this 
and try it out! Huh! You might be either very   
[03:37](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=217) surprised or you completely expected this result. 
The problem is quite obvious. Even tho we are   using the HSV colorspace to calculate our values, 
the screen is expecting to receive RGB values, but   currently we are assigning hue to the red channel, 
saturation to green, and brightness to blue. To   fix this, all we need to do is to convert our HSV 
color back to RGB, and pass that to the output. 
  This was surprisingly simple, and this is 
basically all I did for the jam version   
[04:06](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=246) of the game. I made some improvements since 
then, which allowed me to generate and use   color palettes in real-time. Let's take a look at 
how I achieved that as I think it's really cool!
  The base shader is still the same as before, 
however we're going to be overriding the HSV   values with a couple new functions. We're going 
to start off with 5 variables that control the   artstyle: the base color, brightness, darkness, 
tint and saturation. The goal is to mimic how   
[04:36](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=276) pixel artists choose their color palette based 
on a starting color. The brighter the color,   the more hue shifts towards yellow, and the less 
saturated it gets, while darker colors are more   saturated and their hue shifts towards purple. 
As preparation we're going to convert the input   color and base color to HSV colorspace. For 
the first step, let's calculate the brightness,   as that influences both the hue and saturation of 
the final color. I honestly can't really explain   
[05:04](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=304) what's going on here as most of it just came 
down to experiementing with different functions   to see what works the best, but essentially the 
brightness parameter makes bright parts brighter,   while the darkness parameter makes everything 
darker. We're going to use this calculated   brightness to add extra tint and saturation 
to the output color based on it's difference   to the base color's brightness. This will get 
us more color and a nicer palette from an art   
[05:31](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=331) standpoint. After the coloring is done, it's time 
to posterize the result! I'm using a different   global variable for each channel to have a bit 
more control over how it looks. At the end we   need to convert back to RGB as always, and I pass 
the original alpha for transparency support.
  Offseting the output brightness before 
calculating the tint and saturation with a   scrolling noise texture can be used to break 
up the circles that this implementation is   
[06:01](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=361) currently generating. Different noise patterns 
will look completely different, so take your   time to experiement! This is very easy to do in 
Godot because there's a built in noise texture   generator thats surprisingly powerful!
Now that we're done with this part,   there's still a bit more to add before we can 
call our shader finished. A quite obvious addition   would be adding support for multiple palettes 
at the same time. This by itself doesn't sound   
[06:28](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=388) that hard, but figuring out how to decide 
which parts of the screen are part of a   different palette is going to be a bit tricky.  
The current best solution I found was assigning a   seperate render layer for objects that use a 
different color palette, and then rendering   those objects onto a seperate texture using 
sub-viewports, which are basically the same as   render textures in Unity. These textures are going 
to be transparent if a pixel doesn't hit a mesh,   
[06:54](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=414) and so we can use that to determine which 
layer the current pixel is part of.
  In the shader, we're going to do the exact same 
palette calculations as with the main layer,   but with different parameters this time. At the 
end of the shader, we'll check if the current   pixel hit anything on the second layer, and 
if it did, we will overwrite the result with   that layer's color. As you can see, we have a 
second layer now! I'm actually using another   
[07:19](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=439) layer made specifically for the enemies only, 
but currently all of them are work in progress,   so I'll save them for a later video. I also added 
a layer where the filter gets completely bypassed,   so I can make some complex effects later.
So to summerize, posterization is a very cool   effect that can be used in many ways, but for 
some reason it's incredibly underused. Using   it on HSV channels can lead to generating 
some controlled bands of color in real time   
[07:46](https://www.youtube.com/watch?v=Gjr2CUczDpk&t=466) which can turn into some very unique artstyles 
that I haven't really seen before that much.
  If you enjoyed this video and want to support me, 
you know what to do; and also please tell me in   the comments if you know of other games that 
use posterization for their artstyle! See ya! 