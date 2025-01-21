---
URL: https://www.youtube.com/watch?v=8wOUe32Pt-E
thumbnail: https://i.ytimg.com/vi/8wOUe32Pt-E/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:55:42
published: 2022-05-14T10:00:02
duration: 715
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "11m 55s"]
# Color Quantization and Dithering
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722155553.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=8wOUe32Pt-E
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/8wOUe32Pt-E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: In this third installment of the post processing series we learn how all these indie games have been faking their pixel art. Topics covered include texture filtering, bayer dithering, color palette quantization, sharpness, and color palette swapping.

Support me on Patreon!
https://www.patreon.com/acerola_t

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Code: https://github.com/GarrettGunnell/Post-Processing
Join My Discord Server! https://discord.gg/FxGQvbfm6Y

Music:
Joy - Persona 3 OST
During The Test - Persona 3 OST
Afternoon Break - Persona 3 OST
Sandgem Town (Day) - Pokemon Diamond/Pearl OST
This Mysterious Feeling - Persona 3 OST
New Game - World Of Horror OST
Blow Me Away - Cover by @LittleVMills 

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=0) hello everyone every time i make a new video i look at what i've created and i think wow i should really make a video on anti-aliasing just look at those jagged edges so today 
[00:13](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=13) we're talking about the exact opposite of anti-aliasing by now it's common knowledge that dead cells despite looking acting and behaving like pixel art 
[00:28](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=28) isn't actually pixel art because we as artists have to gatekeep our mediums dead cells uses a shader to flatten and upscale a 3d model then it bakes the animations to a sprite sheet to emulate 
[00:41](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=41) fluid pixel or animations which allows them to support the wide variety of weapons in the game without having to spend years animating each individual weapon this technique is really common 
[00:54](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=54) nowadays with a recent example being loot river in which all the enemies and the player are actually 3d models at least i think they are it's hard to tell sometimes regardless how does a 
[01:07](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=67) shader like this even work pixel art has several distinct aspects that separate it from other art mediums the most obvious feature of pixel art is its low resolution which accentuates the 
[01:19](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=79) individual pixels so our shader needs to be able to replicate this appearance accentuating pixels in this context means enlarging them but unfortunately for us our render is already the same 
[01:33](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=93) size as the screen if we enlarge it then the pixels have nowhere to go except back down to the same resolution which wouldn't accomplish much instead we need to downscale our render first in the 
[01:46](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=106) same way we did for blurring as described in my elden ring video but ace rolla wouldn't this blur the whole image maybe that depends on the texture sampler we use when we do the scaling 
[01:59](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=119) texture samplers control what happens to pixels when they are upscaled or down scaled specifically they define what happens when there's either not enough space for all the pixels or there's too 
[02:11](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=131) much space the four most common sampler types are point filtering by linear filtering tri-linear filtering and anisotropic filtering point filtering is the cheapest easiest smallest brain 
[02:26](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=146) sampler available when there's not enough space for two pixels then it uses the color of the closest pixel to that coordinate and when there's too much space then it fills in the space with 
[02:36](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=156) the color of the closest pixel bi-linear filtering is what we used for our blurring when there's not enough space for two pixels then it takes a weighted average of the four nearest pixels it 
[02:48](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=168) does this when space needs to be filled in as well tri-linear filtering and anisotropic filtering are the same as bi-linear filtering except they also interpolate 
[02:59](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=179) between the two nearest mipmap levels what are mipmaps you ask i don't know man google it or something out of these four options the one we want for pixel art is quite obvious the 
[03:12](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=192) point filtering will preserve our pixel art as it gets upscaled back to full resolution back to our shader if we down scale our render a few times the pixels become very large as a rule of thumb you 
[03:25](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=205) only want to down scale and upscale by powers of 2 which will keep your pixels square if you don't do this you will get pixels of variable width and height which will look really bad unfortunately 
[03:37](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=217) we have one issue that is outside our shader's control which is the camera projection currently our camera is set to perspective projection mode meaning that objects have depth to them if we 
[03:49](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=229) want to emulate pixel art then we want to change the projection mode to orthographic which will flatten all objects in view and remove any depth perception 
[03:59](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=239) as you can see sheik looks much more like pixel art when rotated with the orthographic projection [Music] now downscaling by itself might be 
[04:13](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=253) satisfactory for you and your game but we're still missing a crucial aspect of pixel art which is a limited color palette how can we convert our image into a smaller color palette dithering 
[04:25](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=265) is an intentionally applied form of noise which is used to prevent large scale patterns like color banding one of the most common uses of dithering is converting grayscale images to black and 
[04:37](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=277) white such that the density of black pixels is roughly equivalent to the average gray level of the original image this conversion could be thought of as reducing the color palette to 2-bit 
[04:49](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=289) where pixels are either white or black thankfully the algorithm expands to support any n-bit color palette from 2 to 256 but first we need to decide on a dither 
[05:01](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=301) pattern to use for my demonstrations i will be using ordered dithering also known as bayer dithering this pattern utilizes something called a threshold map which is a matrix of equally 
[05:13](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=313) distributed values from 0 to n squared minus 1 where n is the dimension of the matrix while it is possible to calculate these threshold maps in real time it's really 
[05:25](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=325) inefficient instead we can pre-compute the values and store them in a lookup table to be used by the shader finding the new color of a pixel with dithering starts by retrieving the threshold map 
[05:38](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=338) value we take the position of our pixel on the screen which is obtainable by multiplying the uv coordinate by the width or height of the screen then we mod the position by n where n is the 
[05:49](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=349) dimension of the threshold map which converts it into the coordinates of the threshold map value with the threshold map value we multiply it by 1 over n squared to convert it into the 0 to 1 
[06:02](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=362) range then we subtract 0.5 this final value is the noise that we'll be adding to our image we multiply it by a user-defined spread value which will control how much the noise spreads the 
[06:13](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=373) color this results in a strange lattice pattern across the whole image while this looks neat we still haven't compressed our colors to obtain our new color palette we first take the number 
[06:25](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=385) of colors we want and subtract one then we multiply our new color with this value add 0.5 and take the floor lastly we divide by the number of colors minus one this will convert any color value to 
[06:38](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=398) its nearest neighbor in the new color palette for example let's consider the two color case if we passed in a color value of 0.2 then we would multiply it by 1 add 0.5 and take the floor then we 
[06:51](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=411) divide it by 1 which gives us a new color value of 0. if we instead passed in 0.6 we would multiply it by 1 add 0.5 take the floor and divide it by 1 which would give us a new color value of 1. 
[07:05](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=425) from this we can deduce that any color value less than 0.5 will be 0 and any color greater than 0.5 will be 1 meaning that our image is only allowed two values per color channel our chic render 
[07:19](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=439) has now been reduced from sixteen million seven hundred and seventy thousand two hundred and sixteen available colors to eight this obviously doesn't look very good so 
[07:29](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=449) here's a montage of larger color palettes [Music] they fall in line one at a time no time to 
[08:10](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=490) [Music] throw me lose [Music] [Applause] me 
[08:29](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=509) [Music] [Applause] now that our color palette is reduced to whatever we think looks good we can utilize the same down scaling technique 
[08:48](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=528) to enlarge the dithering and accentuate the individual pixels our effect is now complete if you want flat color sections like dead cells then you can simply set the dither spread to zero but then you 
[09:00](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=540) don't really need to do any dithering in the first place this shader looks pretty good on chic but what about in an environment like my grass field while it looks nice without any down 
[09:10](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=550) scaling and eight colors per channel if we down scale it all or reduce the number of colors we lose all visual information on the grass and it turns into this big green blob thankfully 
[09:22](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=562) there exists a simple image effect that remedies this issue sharpness is an effect that increases the contrast between edges in an image this increased contrast tricks us into thinking images 
[09:35](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=575) are more detailed than they actually are sharpening an image involves taking a pixel's neighbors and multiplying them by a sharpness value and negative 1. then we multiply the center pixel by a 
[09:48](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=588) sharpness value and 4 and add 1. lastly we add the neighbor's values to the center pixel and this is our new pixel color if we first sharpen the image and then apply our pixel art filter we can 
[10:01](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=601) see a lot more detail out of our grass field instead of a giant green blob even when down scaled another neat effect is using sharpness after the dithering which i think looks 
[10:13](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=613) pretty cool since it accentuates the pixels we're not quite finished yet i still have one more effect to show to you back when i was explaining dithering i mentioned converting a grayscale image 
[10:24](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=624) to black and white this is the two color case since all color channels are the same value then all pixels become either black or white but if we increase the color count we get an equivalent amount 
[10:37](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=637) of grayscale values if we visualize these colors in a row it begins to sort of look like color palettes you see on those fancy color websites i wonder if we can do anything with that looking at 
[10:49](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=649) our grayscale colors on the left we have zero and on the right we have one then we have 0.25 and 0.75 in the middle coincidentally the horizontal uv coordinate of each color block is 
[11:03](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=663) identical to the grayscale value if we were to perhaps take this grayscale value and use it as the horizontal uv coordinate for a separate new color scheme we could theoretically replace 
[11:15](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=675) our grayscale values with any color palette as long as our palette has the same amount of colors as grayscale values we can create any size color palette from two colors to 256 here's a 
[11:28](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=688) demonstration of a few different color palettes well that's about it for me as usual the code is in the description if you'd like to play around with it i'm pretty happy 
[11:45](https://www.youtube.com/watch?v=8wOUe32Pt-E&t=705) with how these effects turned out so please let me know what you think thanks for watching everyone i hope you have a great rest of your day and i'll see you next time 