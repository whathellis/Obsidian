---
URL: https://www.youtube.com/watch?v=fv-wlo8yVhk
thumbnail: https://i.ytimg.com/vi/fv-wlo8yVhk/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T13:11:30
published: 2023-10-01T04:15:17
duration: 2221
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "37m 1s"]
# Your Colors Suck (it's not your fault)
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722131142.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=fv-wlo8yVhk
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/fv-wlo8yVhk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: The first 100 people to use code ACEROLA at the link below will get 60% off of Incogni:
https://incogni.com/acerola !

Digital color theory is a mysterious black box that few resources bother explaining, but how does it all work? Where did it all come from? And why are the color pickers in the art programs you use so bad?

Topics covered include: Quantization, color banding, dithering, value mapping, palette swapping, radiometry, photometry, how humans perceive color, colorimetry, spectral rendering, the rgb color model, deriving srgb, the hsl color model, gradient mapping, randomly generated color palettes, perceptual color spaces, the lab color model, oklab

Use the palette generator here:
(sorry website is down for the foreseeable future but there are much better color palette generators you can find lol this was for an experiment not meant to be used as an actual service)

Check out Evan's stream!
https://www.twitch.tv/evanmmo

Photoshop OK Color Picker:
https://exchange.adobe.com/apps/cc/66314516/ok-color-picker

Support me on Patreon!
https://www.patreon.com/acerola_t

Socials:
Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y

Code: https://github.com/GarrettGunnell/AcerolaFX/blob/main/Shaders/AcerolaFX_PaletteSwap.fx

References:
- Real-Time Rendering Chapter 8: Light And Color
- https://bottosson.github.io/posts/oklab/
- https://raphlinus.github.io/color/2021/01/18/oklab-critique.html
- An Interactive Method for Generating Harmonious Color Schemes
- https://www.oceanopticsbook.info/view/photometry-and-visibility/from-xyz-to-rgb
- http://www.brucelindbloom.com/index.html?Eqn_XYZ_to_RGB.html

Thanks so much to these artists!
https://twitter.com/denixsucks
https://twitter.com/ethanwijk
https://twitter.com/hayny
https://twitter.com/kaemble
https://twitter.com/martinw59426021
https://twitter.com/pigeonpeanit
https://twitter.com/toman800
https://twitter.com/waumny

Music:
Afternoon Break - Persona 3 OST
Master Of Tartarus - Persona 3 OST
This Mysterious Feeling - Persona 3 OST
Midori Eyes - Paradise Killer OST
During The Test - Persona 3 OST
Junes Theme - Persona 4 OST
New Game - WORLD OF HORROR OST
In A Moment's Time - Skullgirls OST
A New Frontier - VA-11 Hall-A OST
Every Day Is Night - VA-11 Hall-A OST
Underground Club - VA-11 Hall-A OST
Your Love Is A Drug - VA-11 Hall-A OST
Karmotrine Dream - VA-11 Hall-A OST
GO!GO!STYLE - Paradise Killer OST
Police Station - Persona OST

Thanks for watching!

This video is dedicated to my friend, Alotryx.

# Transcript
[00:00](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=0) this video has been sponsored by incogni hello everyone hello everyone are you an artist have you wait ERS trying to pick colors that look good me too 
[00:16](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=16) when I'm not reading shaders writing shaders or manifesting shaders I'll write in the future I'm using my shaders from simple color corrections to Advanced stylization I'm always finding 
[00:26](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=26) new and novel ways to combine effects to get unique visuals that hopefully no one has ever seen before my stylizing usually starts with posterization also known as quantization posterization 
[00:38](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=38) involves reducing a gradient to several regions of fewer tones this helps with stylizing because it's much easier to work with eight or so colors instead of the entire visible spectrum it turns out 
[00:48](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=48) this is true for most mediums of art for example the posterization of light is the foundation of most tuned shaders instead of a full gradient for shading we reduce that to a smaller range of 
[00:58](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=58) possible values resulting in defined Blobby areas of Shadow but in image processing the lighting and shadows have already been drawn so we have to posterize what we've got instead since 
[01:08](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=68) all we have is a bunch of RGB values then obviously we posterize the color data in this context a color is made up of three components a red Channel a green Channel and a blue Channel which 
[01:19](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=79) additively blends together to make white in graphics these values are normalized to zero to one we can quantize each color channel to control how many shades of each primary color we want if we 
[01:30](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=90) reduce each channel to 8 values then we have 512 possible colors left out of the original color count of nearly 17 million doing this to our image unfortunately results in an encounter 
[01:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=105) oh no color banding color banding usually looks very ugly like a blight or a stain it means we didn't have enough colors to fill a gradient resulting in visible transitional artifacts across 
[01:56](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=116) the image but a stroller didn't we just intentionally cause color banding with the posterizer yes what we've done is forbidden under article 183-a put in place by the High Council of physically 
[02:07](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=127) based rendering the current ruling nation of Graphics programming the article states that no rendered image shall ever be made to intentionally suffer from color banding the Republic 
[02:17](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=137) of non-photorealistic rendering believes the opposite that through the destruction of the image we can reshape it into something much more beautiful and intellectually unique this is a 
[02:27](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=147) wonderful sentiment but it involves the intentional crippling of what was already a beautiful image we will go over the moral implications of this in the next episode Ethics and Graphics 
[02:37](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=157) programming but first something entirely different about a year ago when I first started gaining subscribers I did a bit of an ego check and Googled my name I expected to see my GitHub or something 
[02:47](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=167) to appear but instead I was met with a website that showed my full name address and phone number all on the first page of Google what I had found was a people search site a website that makes money 
[02:57](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=177) by publishing personal information of people without their knowledge or consent the good news is that you can ask these sites to remove your data but the bad news is that there are so many 
[03:06](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=186) of them that it isn't really feasible to ask all of them this is where incogni the sponsor of this video comes into play andcogni automates the data removal request process they will make all the 
[03:16](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=196) requests on your behalf and deal with any objections the data broker may have with a subscription to incogni you won't have to worry about data Brokers profiting off your personal information 
[03:25](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=205) and selling it to Bad actors they even show off exactly how many Brokers they have removed your data from so you know something's actually happening the first 100 people to use code Ace roller at the 
[03:36](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=216) link in the description below will get 60 off of an incognitive subscription don't wait to take back control of your data before it's too late thank you so much to incognia for sponsor during this 
[03:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=225) video now back to the color banding to recap most NPR techniques are built on posterization the intentional introduction of color banding through math or other demonic rituals most 
[03:56](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=236) people would agree that color banding looks ugly and so the point of most NPR techniques can be interpreted as attempts to make color banding look like an intentional artistic decision and not 
[04:06](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=246) a compression artifact one fix for color banding artifacts is known as dithering we intentionally inject noise into our quantization process to provide the illusion of a gradient the spread of the 
[04:16](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=256) dither also gives the image more form which helps the readability there's many other methods of dealing with color banding but today we'll mostly be using the dither if you'd like more in-depth 
[04:25](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=265) info on this topic check out my video on the subject you now have sufficient contextual knowledge and the stage has been set for the main problem of this video an image with quantized RGB 
[04:35](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=275) actually looks kind of really bad there's a major lack of mid-tones and overall the colors and gradients just aren't that Pleasant outside of the obvious retro aesthetic The Simple 
[04:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=285) Solution to this is of course extensive color correction several color Corrections later and you can have much more interesting and stylized colors that are modifications of that original 
[04:54](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=294) reduced palette there isn't much of a science to this though you're kind of just messing around with a ton of parameters until it looks okay which isn't a very good fix to the problem 
[05:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=302) thankfully three months ago I devised the perfect solution on stream what if we could get absolute control over the colors in the image enough of this quantized RGB I'll just choose 
[05:14](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=314) the colors myself a quantized grayscale gradient will give us an arbitrary one-dimensional set of values we can then associate anything we want with these values in a technique known as 
[05:24](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=324) value mapping we desaturate the image by dotting the image with this Vector quantizing the desaturated image gives us the amount of values we want my genius idea was then to expose eight 
[05:34](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=334) color parameters to the artist who could put in whatever colors they wanted to replace the grayscale values this color palette swapper was a great success it gave absolute control over the pal of 
[05:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=345) the render and lots of cool screenshots were taken with the effect but it still suffers from the same issue of the earlier color correction solution it turns out it's pretty time consuming to 
[05:55](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=355) mess around with even just eight colors and ideally we'd want to be able to go up to 16 or maybe 32 colors a verbose palette swapper like this might be ideal for a development setting because you 
[06:06](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=366) could easily programmatically swap out these colors based on different game States or maybe the artist wants the total control for art design in the context of video game photography though 
[06:15](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=375) the thought of having to hand input 8 colors for a quick photo sounds kind of exhausting so my next genius idea random color palettes the concept couldn't be more simple we pass a seed through a 
[06:29](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=389) hashing function to get a bunch of pseudo-random values that we interpret as RGB colors these colors become our color palette and we insert them into our palette swamper 
[06:39](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=399) you know now that I think about it I'm not sure why I thought this would look good clearly some more effort has to be put into it and I was working on the water at the time so I split off a 
[06:47](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=407) version of myself to go think about it really hard for a while it's now been three months since I split in two so let's hear from my clone on why RGB actually really sucks question where do 
[06:57](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=417) you think color theory lies on the complexity Spectrum that's right remember that color is a psychophysical phenomenon our brain's perception of physical stimuli to figure out where 
[07:08](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=428) this physical stimuli comes from we start with the simple fundamentals of radiometry radiometry is a set of techniques for measuring electromagnetic radiation this radiation propagates as 
[07:20](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=440) waves electromagnetic waves of differing wavelengths have very different properties some wavelengths will ruin your day just like really you up especially if they entered your eyeballs 
[07:31](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=451) but when a wave with a length inside a very specific range enters your eye your brain goes oh a color if you recall from my last video on simulating the ocean a range of possible wavelengths is 
[07:42](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=462) referred to as a spectrum which means the range of wavelengths that our brain can perceive is called the visual Spectrum in fact the word spectrum was first used to describe the range of 
[07:52](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=472) visible colors for the first time ever I will actually be talking about units because these terms can be confusing and many people including myself accidentally use them interchangeably 
[08:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=482) which makes it even more confusing the basic unit in radiometry is radiant flux which sounds like a Minecraft mod mechanic radiant flux is the flow of radiant energy over time this means that 
[08:12](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=492) Radiance is a measure of electromagnetic radiation in a single Ray Radiance is what is being measured by sensors like cameras or our eyes which means that Radiance is the important concept when 
[08:23](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=503) it comes to rendering the cool thing about Radiance is that it is unaffected by distance if nothing is in the way then light just keeps on going at the same intensity all day every day forever 
[08:34](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=514) this kind of only applies to the vacuum of space though because in most cases there is lots of of stuff in the air that will affect light as it travels through the atmosphere before entering 
[08:43](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=523) your eye so even though Radiance as a unit is unaffected by distance other phenomena will absorb that radiant energy before it reaches you to conclude our little tangent on radiometry colors 
[08:54](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=534) are modeled as a plot of energy distributions across certain wavelengths these graphs are known as spectral power distributions since colors can be composed of many different wavelengths 
[09:04](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=544) which is starting to sound suspiciously similar in concept to our simulated ocean from the last video an SPD visualizes what wavelengths a color is composed of and the radiant intensity of 
[09:14](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=554) those wavelengths taking a few example spds from the book real-time rendering this top one here is the SPD for a green laser pointer which we would see as green this middle SPD is the same one as 
[09:25](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=565) before but with an additional blue and red laser pointer which we would perceive as a neutral white this last SPD is much more complex and is used as a general reference to represent outdoor 
[09:36](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=576) lighting a mixture of pretty much the entire visible Spectrum now despite how different these two spds look it might surprise you to hear that we perceive this bottom one as the exact same color 
[09:47](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=587) as this middle one if our eyes can't tell the difference between these two then somebody should probably adjust our spds to be a bit more relative to the human eye radiometry is measuring the 
[09:57](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=597) real deal just raw dog quantities of light but as demonstrated our eyes clearly don't care about a large portion of this graph or some of the intensities thankfully another area of study 
[10:09](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=609) photometry is like radiometry but transforms the spds according to the sensitivity of the human eye so it's easier to work with and understand although people who prefer Celsius to 
[10:19](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=619) Fahrenheit would probably disagree this is where the confusing units come into play radiometry deals with radiant flux and Radiance whereas photometries units are equivalent to radiometries but with 
[10:29](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=629) the context that they are relative to human eyes the photometric version of radiant flux is Luminous flux measured in lumens the equivalent of Radiance is lumen meaning that while Radiance is the 
[10:41](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=641) actual radiant intensity in the real world the luminance is how we as humans perceive that Radiance this is a very important distinction ideally we would do all of our mass and light transport 
[10:51](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=651) in Ray tracing with the actual light quantities modeling our colors with the full spectral power distributions this is known as spectral rendering an extremely Advanced and relatively new 
[11:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=662) form of rendering since Hardware is only now being able to handle it in a not real-time context because it's so new and so expensive I will probably never make a video about it since my videos 
[11:13](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=673) are on real-time rendering techniques but if you're interested check out articles in the new editions of Ray tracing gems spectral rendering is how we can achieve approximate photorealism 
[11:23](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=683) since we're simulating the actual propagation of electromagnetic radiation in order to see the results of spectral rendering though we would need to convert it into something that can be 
[11:32](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=692) displayed on monitors because pixels can't interpret an SPD this is where photometry comes in we convert our radio geometric units to photometric by multiplying them with the photopic 
[11:42](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=702) spectrol Luminous efficiency curve designed by the international Commission on Illumination in 1931. this is a mouthful so everyone calls it the cie curve the acronym is cie because they're 
[11:53](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=713) French this curve represents the Luminous efficiency of a given wavelength a fancy way of saying how much the wave's intensity actually matters to our eyes more specifically it 
[12:03](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=723) represents how our eyes respond when the cones in our eyes are active since in low light conditions we instead see with rods which have a different luminous response to help us see in the dark the 
[12:13](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=733) cie curve tells us that green wavelengths impact our perceived brightness the most with blue being very far behind and red luminance being essentially non-existent if you recall 
[12:23](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=743) from earlier when we desaturated our image we used this Vector which when dotted with the image results in a weighted sum of the RGB components with green being the highest contributor to 
[12:33](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=753) the desaturated output now that we have color modeled as a spectral power distribution awaited by the sensitivity of the human eye we can finally move on to color theory earlier I stated that 
[12:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=765) color is a psychophysical phenomenon our brain's response to a physical stimulus we now have the physical stimulus the colorway of entering our eye modeled as a spectral power distribution this is 
[12:56](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=776) where the third and final area of study comes in colorimetry colorimetry is the science and technology used to quantify and describe physically the human color perception a fancy way of saying that it 
[13:07](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=787) is concerned with establishing a relationship between our SPD and a perceived color so how do humans perceive color the wave enters your balls and then what earlier I said the 
[13:17](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=797) cie curve was for cones in our eyes it turns out your eyes have a lot of these cones because they're cells a person without color vision deficiency has three kinds of cones each kind of cone 
[13:28](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=808) has a different sensitivity to a different set of wavelengths we've got the S cones which are sensitive to short waves the M cones which are sensitive to medium waves and the L cones which are 
[13:38](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=818) sensed of the long waves this means that a perceived color is the combination of three separate signals a tri-stimulus response so given an SPD our brain receives a signal from each kind of cone 
[13:50](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=830) cell meaning that a color perceived by a human can be described with only three numbers the problem is then figuring out which three numbers will result in the desired color we want to perceive the 
[14:01](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=841) international Commission on illumination did this in the most straightforward way possible they got three individual beams of light projected onto a wall such that their colors combine then a test color 
[14:11](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=851) was projected onto the wall next to the blend of the three beams the test color is a single wavelength the goal of the experiment is then to basically fiddle with a bunch of knobs that controlled 
[14:21](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=861) the individual energy of the three beams to try and match the test color in a process called color matching the knobs had a range of negative one to one a negative value means the energy of the 
[14:31](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=871) beam was added to the test color instead of the main blend after color matching was done for every single individual wavelength in the visual spec Spectrum the result was a set of color matching 
[14:41](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=881) functions that can convert a spectral power distribution to three separate distributions which we can then integrate to get the values needed for the knobs to match the SPD color now I 
[14:51](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=891) know what you're saying GA scrolla you said this color theory stuff was complicated but it seems pretty easy to think about to me that's a wonderful point and I'm glad you're following 
[15:00](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=900) along unfortunately these color matching functions cannot directly represent the full visual spectrum because there are negative weights present for some wavelengths and a negative cone response 
[15:10](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=910) doesn't exist to fix this the cie said what if we just made it positive and they did they proposed three new color matching functions XYZ which are linear combinations of the original RGB curves 
[15:23](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=923) which have positive weights for all wavelengths also Y is the same cie curve from earlier what a coincidence as a consequence of these negative weights being made positive in order to get some 
[15:34](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=934) of these outputs a given SPD would need a negative intensity for some way wavelengths therefore the light that corresponds to those input spds is an unrealizable mathematical abstraction 
[15:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=945) that is it cannot exist in the real world does this mean that the basis of all color theory is fundamentally flawed no the negative values imply something referred to as an imaginary color a 
[15:57](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=957) color that maps to a combination of cone cell responses that cannot be produced naturally since we can't produce that response we cannot see imaginary colors or can we 
[16:09](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=969) if you stare at this very intense green for a decent amount of time about 30 seconds or so don't worry I'll keep talking when I swapped this circle to a neutral 
[16:40](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1000) white background you will now see a reddish Circle that maybe appears brighter than the white itself this is a chimerical color an imaginary color that can be seen temporarily by intentionally 
[16:50](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1010) fatiguing the cone cells in your eyes it's kind of like burning your retina but more interesting Wikipedia says that you should see a reddish Circle but personally I see a very deeply saturated 
[17:01](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1021) fuchsia the reality is that due to genetic mutation everyone has slight variance in the population of their cone cells and everyone will see color just a little bit differently chimerical colors 
[17:11](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1031) cannot be explained by current trichromatic models hence their imaginary status these colors can involve saturation signals outside what is physically thought possible which is 
[17:20](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1040) pretty cool it's a big reminder that in the world of color theory not only are we concerned with the physical representation of light we must also be aware of the biological mechanisms of 
[17:30](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1050) our eyes and brain because even though it's not possible for an object to have the color you just saw we were still able to trick our brains into seeing something that wasn't there thankfully 
[17:39](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1059) it's at this point nerds can finally come to terms with color as an abstract concept but this is all fairly recent a lot of this information including the accurate color matching functions for 
[17:49](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1069) our cone cells was only discovered in the past 70 or so years this means that colorimetry and related fields are about as Cutting Edge as you can get so if it interests you maybe it's a field you can 
[17:59](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1079) do research in to provide some genuine value fairly quickly in fact it wasn't even three years ago when Bjorn invented a color space with a casual blog post and changed the entire industry 
[18:10](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1090) instantly wait what's a color space impossible spds and imaginary colors aside these XYZ curves Define the mapping of real-life quantities of light to a color perceived by a human sure we 
[18:22](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1102) can take existing spectral data and convert it to a perceived color but we can now do the opposite ask for a specific color and get the necessary spectral data that would stimulate our 
[18:32](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1112) cone cells to perceive that desired color we do this by defining our own X Y and Z values which Define a color in the cie XYZ color space a color space is a specific organization of colors emphasis 
[18:45](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1125) on organization in fact cie XYZ is the absolute color space the reason it's absolute is that it encapsulates all colors that can naturally be perceived by a human within its domain and so 
[18:58](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1138) mostly everything uses it as a base reference which means mostly everything is derived from XYZ the last bit of technical jargon we have to come to terms with is the color Model A color 
[19:09](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1149) model is very simply an abstract way of describe describing a color for instance XYZ is a color model because each coordinate describes an aspect of the color so what does each component of XYZ 
[19:20](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1160) mean it turns out it's not very intuitive X is kind of the Hue of the color and after all of this Theory it's a little hard to describe what Hue actually is the cie technically defines 
[19:33](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1173) Hue as the degree to which a stimulus can be described as similar to or different from stimuli that are described as red orange yellow green blue or Violet Y is the luminance of the 
[19:44](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1184) color since Y is quite literally the exact luminance curve from earlier lastly Z is kind of equal to the blueness of the color which is a weird metric considering the meaning of the 
[19:55](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1195) other two components it'd be a lot easier to understand if we could graph the color space but these colors are three-dimensional so it's kind of hard to do the cie aware of this devised 
[20:06](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1206) something called a chromaticity diagram chromaticity means the purity of a color a high chroma means no white gray or black is added to it which you could abstractly think of like noise in the 
[20:17](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1217) SPD while it's technically different from saturation the terms are used interchangeably very often to create the chromaticity diagram the XYZ color space is projected onto a two-dimensional 
[20:27](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1227) plane ditching one of the dimensions in the process the easiest and most obvious one to ditch is the luminance of the color since it just defines the gradient to Black this results in a graph of the 
[20:37](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1237) entire visual Spectrum independent of luminance with our colors now modeled as two-dimensional X Y coordinates you've probably seen this image before and thought it looked kind of weird but how 
[20:49](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1249) do we read it this dot here in the center is the white Point called aluminant d65 which sounds like an SCP but it's actually the result of that crazy SPD from earlier for any given x y 
[21:00](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1260) coordinate we draw a line that intersects that point and the white point the intersection on the boundary gives us the wavelength of the color and the distance from the white point is the 
[21:09](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1269) intensity or saturation since a desatur treated color is grayscale it's pretty cool that something like this even exists as a reference to begin with but these X Y coordinates kind of make no 
[21:19](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1279) sense intuitively either and most of the values result in colors that don't exist it'd be nice if we could map these X Y coordinates to something much more familiar okay I promise this is finally 
[21:30](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1290) where it comes full circle the XY color Space controls only the Hue and saturation ideally we'd like to control the brightness of the color too so we bring back y to give us the x y y color 
[21:41](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1301) space which is not confusing at all with a defined uppercase y we can return to the absolute XYZ which we can now map to any other color space we desire for fun let's invent our own color space let's 
[21:54](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1314) say we wanted to Model A color as a tuple of three values each value ranges from zero to one at max value the first component is a fully saturated red the second component is a fully saturated 
[22:05](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1325) green and the third a fully saturated blue when nothing is present we have black and each Channel additively blends to White remember that to have any real purpose at all a color model must also 
[22:16](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1336) come with a mapping to an absolute color space so we have to devise a way to transform our XYZ into our hypothetical RGB and if that's possible we can do the inverse to go back and forth to create 
[22:27](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1347) the transformation we Define the Pure Color reference points for each component as X Y coordinates in the chromaticity diagram for red let's choose this point green will be 
[22:37](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1357) represented by this point and pure blue will be this point these points form a triangle within the chromaticity diagram and the area of the triangle represents all the possible colors our new color 
[22:48](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1368) space contains this is referred to as the gamut of the color space the last thing we need to do is Define the white point which will be the point at which everything is done relative to let's use 
[22:58](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1378) the same d65 white point from earlier for Simplicity we take the points in x y space and convert them to XYZ do some linear algebra to adjust for the white Point shove it all into a matrix take 
[23:09](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1389) the inverse and out comes a matrix we can multiply with any XYZ coordinate to map it to our new shiny RGB space technically we made a matrix that maps from RGB to XYZ but we inversed it to go 
[23:21](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1401) the other way we can prove it all works by assuming our RGB map to be true we modeled pure blue as a tuple of zero zero and one if we multiply this with our derived Matrix from earlier we get 
[23:32](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1412) the following XYZ coordinates we then convert to the X Y coordinates and we see it to be equivalent to the point we defined pure blue to be earlier since it works for one surely it works for all of 
[23:42](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1422) them and if it doesn't work we simply clamp it within the space in an operation called gamut clipping with our RGB model and our mapping to an absolute reference we have invented the RGB color 
[23:52](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1432) space which is definitely not the same color space that most of devices output on the screen known as srgb probably what you're looking at right now does this mean most screens can only 
[24:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1442) represent around 35 percent of the visual Spectrum yeah this is also where the difference between color space and color model becomes apparent the because there are lots of color spaces that use 
[24:13](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1453) RGB as a model to describe their colors but have differing gamuts and a different mapping from XYZ this is why it's incorrect to say RGB color space as really you're talking about the color 
[24:24](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1464) model but whenever anyone says this they are generally referring to the space we have derived srgb this brings us all the way back to square one we have successfully gone from measured physical 
[24:33](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1473) quantities of light to measured icon spectral sensitivities to an abstract absolute reference of natural human color perception to a small subset of that reference Which models color as an 
[24:44](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1484) additive blend of a red quantity green quantity and blue quantity since this is how our devices interpret color the final output of anything displayed on a screen is in this color space we have 
[24:55](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1495) derived which means that the color data we are posterizing in Final Fantasy 14 is in the srgb color space as it thinks it's ready to present to the screen this is where we come in to desaturate the 
[25:05](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1505) image and posterize we want a randomly generated color palette and since we are working in srgb our ran random values are interpreted as such we value map our grayscale image to the generated palette 
[25:16](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1516) and unfortunately we see that srgb is not the greatest space for this in order to figure out why this is the case we must first figure out where RGB comes from question where do you think color 
[25:28](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1528) theory lies on the complexity Spectrum that's right remember that color is a psychophysical whoops it seems like I didn't give my clone enough memory to solve what I thought would be a pretty 
[25:39](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1539) simple topic do you think it would be more ethical to let him continue this learning process for all of eternity or kill him either way he's in Hell thankfully apparently we only had to do 
[25:49](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1549) one thing to fix our color palette generator this whole time anyways so my bad we use RGB mainly because it kind of just makes sense as a generic model for color as the spectral sensitivities of 
[26:00](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1560) our cone cells happen to peek at the wavelengths we perceive as red green and blue but is it the best color space to work with it's easy to interpret RGB values in some context such as this one 
[26:12](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1572) which is obviously a very reddish color but what about this color or this color can you tell at a glance what its appearance might be it would be easier to interpret colors if our model 
[26:22](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1582) described other behaviors of the color instead of the redness greenness or blueness which is hard to mentally blend back to the drawing board let's keep the triplet structure of the previous models 
[26:32](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1592) the first component will control the Hue the second component will describe the saturation of the color and the last component will describe the lightness or brightness of the color this is the hsl 
[26:42](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1602) color model and it's effectively an alternative representation of RGB or rearrangement of the space I won't waste your time with the explanations of any more mappings so just trust me when I 
[26:52](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1612) say we can go from XYZ to RGB to hsl and back and forth or any which way any value in each base that can't exist in the other will be gamut clipped as discussed earlier hsl is a standard 
[27:04](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1624) model for color Pickers in digital art programs because it's definitely more intuitive and easier to work with than RGB while it's hard to imagine the Hue of a color from a given value this is 
[27:14](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1634) easily replaced with an interactable color wheel and the other two components very obviously describe the behavior of the color how saturated or how bright it is which isn't as clear with the RGB 
[27:24](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1644) model hsl also lends itself much better to our random color palette generator since we have explicit gradients to work with we can mimic real world color theory techniques for picking harmonic 
[27:35](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1655) colors this is finally where the actual art part of color theory comes into play that is the study of colors that work well together and are aesthetically pleasing I have no formal art education 
[27:46](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1666) so I'll be making use of some very surface level techniques let's say we want eight monochromatic colors we generate a random starting point on the color wheel to be the initial Hue value 
[27:56](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1676) then we generate a random value to be the initial saturation and a third random value to be the initial brightness this color will be the first entry in our color palette before we 
[28:06](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1686) generate the next color we want two more random values when we move on to the second color we take the Saturn iteration and lightness from before and add our two random values to it to get 
[28:15](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1695) the next color keeping the Hue the same because it's monochromatic we repeat this process until we have all the colors we want it's important to increment by the same amount each time 
[28:24](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1704) because if we don't then according to Wilhelm Oswald this will break the Harmony and Order of our colors we want the differences on each Dimension to be equidistant to prevent this breaking of 
[28:34](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1714) Rhythm the result of our algorithm is a theoretically harmonious monochromatic color palette in order to actually see it remember that we have to finish in a device color space so we convert our 
[28:44](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1724) generated hsl to RGB before putting it into our pallet swapper the palette looks much better than our random RGB colors but monochromatic palettes are really easy and we could have done that 
[28:55](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1735) in RGB very simply by generating a single RGB color and then multiplying it with an exposure gradient to get more colors we unlock the Hue Dimension up to a point to get a specific range of 
[29:05](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1745) colors we want note that when we increase the Hue Dimension we are going clockwise around the color wheel Rel relative to our random starting points it's also important to note that 
[29:15](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1755) according to Wilhelm Oswald a set of harmonious colors has one dimension that stays constant so if we are changing the Hue and saturation we keep the brightness constant for each color a 
[29:24](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1764) constant brightness doesn't really look good in our use case though so for every color palette from here on it will have a constant random initial saturation for each color this finishes our color 
[29:34](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1774) palette generation algorithm despite its Simplicity it produces decent results in hsl and even if it's not a good palette it takes no effort to generate a new one well what if I told you that hsl has 
[29:46](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1786) actually been making your life as an artist worse without your knowledge it turns out hsl is breaking the very simple rules we've laid out for color Harmony and if we didn't understand 
[29:55](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1795) human color vision we'd never know any better thankfully a better option exists let's take a look at a few hsl color palettes remember that our saturation is a constant value for each color and 
[30:07](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1807) brightness increases from left to right for many of these colors that person absolutely doesn't make sense whether or not you see this is dependent on your own eyes and also your screen but 
[30:17](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1817) remember that each color should be perceptually equidistant from each other in terms of brightness and the saturation should be the same across the board in this palette at the lower end 
[30:26](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1826) the darker colors feel more saturated than their neighbors even though they have the same saturation value with this palette some neighboring colors look almost identical even though they should 
[30:36](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1836) have an equidistant luminance difference hsl is particularly egregious with Blues in fact most color spaces are like what is even going on here Reds also tend to be way more intense than they should be 
[30:47](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1847) or at least compared to other colors with the same intensity all of this is because hsl is poorly spatially structured earlier my clone put emphasis on the arrangement of a set of colors as 
[30:58](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1858) the definition for a color space and it's because the arrangement matters way more than you would think to formally State the problem hsl does not have perceptually uniform gradients as it 
[31:08](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1868) turns out our perception of color is non-euclease what does that mean I don't know I read it in this article basically it means that the result of our equidistant increments in the hsl color 
[31:18](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1878) space while numerically uniform are not perceptually uniform the operation does not match our perception to fix this we need to make use of you guessed it another color space specifically a color 
[31:29](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1889) space that seeks to be perceptually uniform color spaces like this have existed for a while but it was only recently when Bjorn audison created one specifically for image processing known 
[31:39](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1899) as OK lab describing it in a blog post it's called OK lab because according to him it's just okay but it's sort of humble because in only three years OK lab has been integrated into image 
[31:51](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1911) processing libraries everywhere this color space is also just now reaching graphics and has tons of applications because Graphics is image processing OK lab is derived from XYZ and serves as an 
[32:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1922) alternative to cie lab which is the cies attempt at a perceptual color space derivative of XYZ the color model is lab L is the perception a lightness a is how red or green the color is and B is how 
[32:15](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1935) blue or yellow the color is it's based on the opponent color model of human Vision if you care about how ok lab is derived from XYZ Bjorn explains it in depth in his article but really all you 
[32:25](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1945) need to understand is that ok lab gradients are much more perceptually correct than hsl an example photo from Bjorn's article shows the predicted lightness of an hsl gradient with 
[32:35](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1955) constant value and lightness and you can see that it is all over the place especially around the blues while OK lab remains rock solid with its Hue transitions if OK lab is so much better 
[32:46](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1966) at gradients than hsl then clearly it would be a far superior choice to generate our color palettes in for our gradient mapping technique I didn't want to just say OK lab is better than hsl 
[32:56](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1976) though I wanted to measure it and demonstrate how much better it is with some data so I devised a way to prove that ok lab is far superior to hsl in order to prove OK lab is actually goat 
[33:08](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1988) lab I implemented my palette generator in JavaScript and this palette generator outputs three pallets of the same Hue saturation lightness and contrast for each the only difference is the color 
[33:18](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=1998) space it's generated in I added HSV as a color space because three sounded better than just two I then went into my friend Evan's twitch chat demanded he make me a website I wasn't going to pay him for 
[33:28](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2008) and a few hours later I had a front-end website that could generate palettes on command palette one is hsl palette 2 is HSV and Palette 3 is ok lab this information is obscured for the 
[33:39](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2019) experiment I then went on my public platforms and requested everyone to use the website and submit screenshots of palettes they liked choosing one of the three as their favorite my hypothesis is 
[33:49](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2029) that if perceptual uniformity matters aesthetically then OK lab should be chosen far more than the other two options in the end hsl was picked 46 times HSV 11 times and OK lab 67 times 
[34:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2042) sorry HSV no one likes you there was also an overwhelming consensus that ok lab looked consistently the best across all randomly generated palettes now not just favorites several people created 
[34:13](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2053) art with their palettes and out of the 13 pieces of art eight of them were made with OK lab thank you so much to everyone who made some art I appreciate it very much 
[34:32](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2072) foreign Discord user noxy in particular made the same piece of art with all three palettes which is an amazing example of the differences between them hsl has 
[34:42](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2082) overly intense darker colors resulting in this very strange looking purple bridge and Mountain HSV on the other hand is much less egregious on the mid-tones but in my opinion is heavily 
[34:53](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2093) lacking in the contrast apartment noxy said they liked second the most but I'm biased and I think three looks the best because of this value difference right here it's stunningly beautiful is this 
[35:03](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2103) study extremely biased and not very scientific in the slightest perhaps but this didn't stop me from using OK lab for my real-time color palette generator for in-game photography which I used to 
[35:13](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2113) take several amazing photos that otherwise would have taken me a while to pick proper colors for as usual these shaders are free to download use and reference in the description you might 
[35:22](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2122) be wondering how any of this has been relevant to you at all but if you're a digital artist it should be quite clear why you should drop the hsl Color Picker that comes default in your art program 
[35:31](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2131) and swapped a cie lab or ideally an okay lab Color Picker it's true that having an eye for color trumps all of these problems a competent artist can use the hsl Color Picker to get the right color 
[35:43](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2143) they want but it'll just make your life easier working in a perceptually uniform color space as now instead of having to fiddle with the saturation and lightness after moving around to the color wheel 
[35:52](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2152) in OK lab moving around the wheel is the only thing you have to do to be consistent with your values most art programs should have cie lab built in all you have to do is switch a route but 
[36:02](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2162) if you're using clip Studio paint you're out of luck who would have thought that modeling something that children finger paint with would be so difficult I also hate to inform you that we've only 
[36:11](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2171) scratched the surface of digital color theory I didn't even talk about color blending in this video which is another major problem that color spaces like mixbox try to fix and that stuff is all 
[36:22](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2182) closed source so it seems like another job for me later if you would like to give me a job please consider supporting me over on patreon all the patrons get to vote on the next video topic just 
[36:31](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2191) like how this video was voted on last month as usual a huge thank you to all of my patrons without your support I wouldn't be able to wake up after everything in my town is closed with 
[36:40](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2200) 7-Eleven as my only option for grocery shopping also I'm streaming right now over on Twitch I'm adding some features to my final fantasy shaders if you have any questions about the video come ask 
[36:51](https://www.youtube.com/watch?v=fv-wlo8yVhk&t=2211) away anyways that's all from me I hope you have a great rest of your day and I'll see you next time don't forget to check out incogni to stop data Brokers from profiting off your data 