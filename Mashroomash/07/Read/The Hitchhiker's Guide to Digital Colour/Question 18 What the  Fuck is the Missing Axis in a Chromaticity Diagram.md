---
URL: https://hg2dc.com/2020/01/27/question-18/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/01/happy-little-locus-xyy.jpg
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:19:12
duration: 8
topics: 
done: false
cover: 
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
word-goal: 2500
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Question #18: What the  F*ck is the Missing Axis in a Chromaticity Diagram?

Description:: We’ve touched on the importance of the CIE’s chromaticity model, and its relationship to visible light spectra as ***the*** single most important framework for pixel pushers to get a firm grasp on to understand all of colour. Some folks may also likely have come to realize that the two dimensional representation is missing some important information.

That’s because that as wonderful as the CIE chromaticity two dimensional diagram is, it’s missing one crucial axis that should be made more apparent.

***Question #18: What is the missing axis in the CIE chromaticity diagram?***

---

So we’ve established that the chromaticity diagram is an absolute, two dimensional map of mixtures of visible light1. The terrific part of this is that we can express any mixture and get a resultant absolute coordinate that no one on the planet can muddle up. And it works pretty damn good, plus or minus some more complex details.

The downside? It’s not exactly useful for expressing how a mixture relates to overall radiometric or perceptual quantities of light. That is, for any given chromaticity coordinate, there are an *infinite number of mixtures of intensities that can produce it*.

Whoa that was quite a mouthful. Let’s backtrack a little bit…

---

We know that much like a conventional map, we have two dimensions that we can move in. For a conventional map we have one axis along north to south, and another axis along east to west. Even if we have an absolute map coordinate that tells us we are standing on Mount Everest, we don’t quite have enough information to tell us how high up we are, do we? In theory, with a big enough shovel, we could be standing at the exact same latitude and longitude, but at *any* altitude.

If we go back to our ever crucial CIE 1931 chromaticity diagram, we have our north and south axis via the *y* coordinate, and we have our east and west axis via our *x*. But what about that… “altitude”?

---

The xy chromaticity diagram is in fact a top down view of chromaticities, and if we were creative, we could use some tools to visualize how our view of the map is in fact hiding the “altitude”, to use our Mount Everest analogy above.

Let’s quickly return to the basic two dimensional CIE 1931 chromaticity diagram. We’ll start super simple, and slice up the visible spectrum up into 1nm increments. Think of it as 471 laser pointers of different wavelengths that you might buy from Amazon. That long straight line remember, cannot be expressed using any single visible light Amazon laser, and instead we need to mix the lowest and highest visible wavelength to achieve any of the chromaticities along that edge. If we needed a purple laser pointer along that edge, we’d need to mix two lasers, not one!

![](https://hg2dc.com/wp-content/uploads/2020/01/happy-little-locus-xyy.jpg)

471 increments of visible wavelengths between 360nm and 830nm, plotted in the CIE 1931 chromaticity diagram

Enough of that boring bulls\*it… you’ve been staring at [those sorts of diagrams since Question #13](https://hg2dc.com/question-13/), and all the plot represents is a model that allows us to connect visible wavelength mixtures of light to a model in an absolute way. In our above case, the horseshoe has a representation of the lasers using sRGB colours.

But what if we kick it up a notch, [look back to Question #12](https://hg2dc.com/question-12/), and talk briefly about intensities? [We know from Question #12](https://hg2dc.com/question-12/) that each visible light wavelength carries different perceptual energy levels at equal radiant energy levels. So what would that look like? Funny you should ask…

Visible light divided into 1 nanometer increments and plotted in 3D

Et voila! All we have done is simply expressed our visible laser increments at constant radiometric energy. That shape should now connect directly back to illustrating why those blasted sRGB squares [we covered in Question #12](https://hg2dc.com/question-12/) appear brighter or less bright perceptually, despite being at equal emission intensities! That is, again, the *perceptual* intensity is quite different from the *radiometric* intensity.

You probably aren’t wondering what the lasers might look like if we plotted them relative to our peak fully-adapted set2? F\*ck it, you get to see the 471 laser-like wavelength increments at 100%, 75%, 50%, 25%, and close to 0% anyways…

Visible light divided into 1 nanometer increments, at adapted 100%, 75%, 50%, 25% and close to zero.

---

Now back to pixel pushing on your sRGB display…

Let’s take a small smattering of pixels in an sRGB image. For the sake of clarity, we’ll pretend our image is ridiculously uh… limited, and only features seven mixtures of sRGB light. That is, we can pretend our image has seven pixels of sRGB light mixtures in a row. We can of course visualize what that might look like on our CIE 1931 chromaticity diagram. You’ll be familiar with [the damn triangle from Question #16](https://hg2dc.com/question-16/), where we drew them out for an iPad Pro and an sRGB display.

The following plots the most saturated combinations of sRGB red, green and blue. That means that in the case of the “colour” mixtures, there are only one or two lights mixed.

The outer tips of the triangle, as we know, represent the pure primaries, with no complimentary light channel. The middle points are the mixtures of the two primaries at the tips. And of course our old friend maximum intensity R=G=B is in here too, aka sRGB primaries at 100% for each. Let’s have a look…

![](https://hg2dc.com/wp-content/uploads/2020/01/happy-little-srgb-xyy.jpg?w=1000)

The snoring sRGB specification chromaticities of the three primary lights, expressed in the boring triangle format. Notice the equal mixtures between the two primaries at the tips don’t land smack dab in the middle of the lines!

The tips of our triangle have small colour coded sRGB red, green, and blue dots, we introduce the other three members of the Notorious Six, being sRGB cyan, magenta, and yellow.

For a bit of a mental game, let’s pretend we are dealing with only sets of five intensity increments for our sRGB display linear light output. That is, let’s set those lights in the above combinations to 100%, 75%, 50%, 25%, and a low value near absolute 0%. For this purpose, we are going to remove the sRGB transfer function so we are dealing with linear energy ratios only. Any idea what they might look like if we were to plot them in 3D? Wait no longer!

sRGB, with the transfer function “undone” to illustrate the display linear output at common mixtures and purely saturated primary lights

Of particular note is that within the confines of sRGB, the Notorious Six member sRGB purely saturated “yellow” happens to also have the highest level of perceptual energy. The reason why is that the chromaticity coordinate for the equal energy mixture of green and red results in the highest luminous efficacy, being closest to the magic wavelength 555nm, which packs the most perceptual energy punch!

Also notice the perfectly vertical “legs” for each of the purely saturated Notorious Six members. The vertical “height” is maxed out at a certain point, and the purely saturated primaries and mixtures between *cannot become more luminous*, as they are expressed at 100% relative to the others! That means that again, [rehashing what was covered in Question #12](https://hg2dc.com/question-12/), the chromaticities do not output the same amount of perceptual energy at equivalent radiant energy.

If you have forgotten any of the yawn inducing concepts around intensity, feel free [to revisit Question #12](https://hg2dc.com/question-12/).

---

Alright… that’s a large enough of a dose of colour science for one day, I’d say. Let’s tidy this question up with an answer…

***Answer #18: The missing axis when looking at the CIE 1931 chromaticity diagram is luminance, expressed as an uppercase Y.***

So there you have it. Remember that in colour science, terms and little details such as uppercase or lowercase often carry additional meaning. In this case, the CIE 1931 chromaticity diagram uses the lowercase *x* and *y* to represent *normalized*, or scaled from 0% to 100%, values. If they were not scaled, you would read uppercase *X* and *Y*! And that brings one more puzzle piece to the table with clarity; the three dimensional models we have been plotting are in *xy****Y***, where *Y* represents the unscaled version of *y*. *Y* is also the bass player in the death metal act known as *XYZ*, and occasionally plays in his drill rap act offshoot known as *xyY*. He’s the same band member, and lowercase *y* is his little sibling.

Hopefully by examining the non-uniform perceptual energy vertical axis and the non-perceptually-distributed chromaticities in conjunction with the spectral locus itself has helped cement some of the previous concepts covered.

What’s interesting is that all of the above work is curiously plotted using a 0% to 100% framework though, and for you rendering wonks and photographers out there, you probably may have yet more questions that have become aware to you. But those [will have to wait for a while…](https://hg2dc.com/question-19)

---

1 There are indeed several versions of the Colour Matching Functions, and it’s worth noting so here now that you have a firm understanding of the groundbreaking 1931 version. There have been iterations since then that have attempted to more accurately model the standard observer response to visible light spectra, and “fix” certain problems with the 1931 model.

2 *[Adapted](http://cie.co.at/eilvterm/17-23-081)* is an absolutely critical idea here that we will explore later. The reason that adapted is crucial, is that it allows us to discuss our psychophysical response in terms of a ratio from the darkest to the lightest value we have adapted to. Otherwise our scale will change. And yes, rendering wonks or photographers might be generating more questions right now because of that, and rightfully so!

