---
URL: https://hg2dc.com/2020/03/17/question-19/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/02/rgb-does-not-mean.jpg
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:19:42
duration: 6
topics: 
done: false
cover: 
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
word-goal: 2500
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Question #19: What the F*ck is a “Gamut”?

Description:: Phew. It’s been a long time coming, but the time we have invested is starting to pay off! We can actually discuss colour in a meaningful way, and with [the introduction of perceptually uniform maps with Question #15](https://hg2dc.com/question-15/), we can even compare colours or get a sense as to “how different” chromaticities are! And we’ve just [started scratching the surface of how different displays behave with Question #16](https://hg2dc.com/question-16/).

Hopefully, with the sorts of questions answered since then you are beginning to appreciate why understanding the various chromaticity diagrams and their relationship to visible light are **the** most important set of concepts a digital artist needs to know; *it allows us to discuss colour in a meaningful way*. As a set of core concepts they are, in no uncertain terms, the ground truth for all things creative from print to display to rendering to photography to motion graphics to whatever little unique domain has found you here, reading this crap.

So you’ve heard about gamuts. You might even be staring at something someone or some marketer described as a “wide gamut” display right now! As is a familiar in this series, *we are here to figure out and investigate exactly what “gamut” means*…

***Question #19: What is a gamut?***

---

By focusing on physical things like displays and lights, we are able to give meaning to the nebulous concepts and keep the meaning out of the abstract bulls\*it quagmire of “colour spaces”. While a typical image hustler has no problem understanding that one of the three tiny and specific coloured lights in their display increases or decreases in emission, the ideas around transfer functions and chromaticities are tricky things to expect someone to “grab on to”.

Why are we rehashing these two darn things again? Because for the answer to our question, we are going to need to hyper focus on transfer functions and chromaticities. Let’s keep the following concepts fresh in our heads:

> ***Transfer function*s** are the Rosetta Stone between encoded RGB code values and physical quantities of light.
> 
> ***A chromaticity*** is a strict and absolute definition of a mixture of the most pure, laser-like wavelengths of visible light relative to a standard observer.

---

Let’s look at what the experts in the field of colours science have to say about [the term gamut](http://cie.co.at/eilvterm/17-32-007). It is the first few words that we are going to focus on:

> volume, area, or solid in a colour space
> 
> [Colour gamut definition from the CIE term list](http://cie.co.at/eilvterm/17-32-007)

For our purposes, we can get a sense of the “area” portion of this definition having covered a couple of very useful models and their respective diagrams. While we will keep our discussion grounded in something that pixel pushers all over are familiar with – a piece of display hardware – the general principles apply for the larger umbrella of colour spaces across different mediums, including print and other reflective media.

We already have discussed two reliable methods to discuss and plot “colour”1 via either [the non-perceptually uniform chromaticity diagram from Question #13](https://hg2dc.com/question-13/) or [the perceptually uniformly scaled variant in Question #15](https://hg2dc.com/question-15/). Let’s look at the *area* differences when comparing an sRGB display versus an iPad Pro again:

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-display-p3-1976.png?w=580)

**FIGURE STUPID AREA COMPARISON**: A comparison of the areas formed between the three lights of an iPad Pro (Display P3) and a typical display (sRGB). Remember, the specification that sRGB uses to describe the chromaticities of the three primary lights is taken directly from another standard in BT.709.

As useful as this diagram is in comforting you that your two thousand dollar display is “better” than your friend’s cheaper display, we can also see that it has limitations. While this variant shows us a two dimensional plot of colour mixtures, [we explored in Question #18](https://hg2dc.com/question-18) that it leaves out one crucial and vastly important aspect. We are missing *the range of intensity that visible light mixtures can be displayed at*!

---

First, let’s knock the answer out. The CIE seems to have a very clear and useful summary solution, so let’s roll with that…

***Answer #19: A gamut is a volume, area, or solid in a colour space.***

But what does that really mean? What does it look like? To answer that, let’s take a peek at a generic image.

![](https://hg2dc.com/wp-content/uploads/2020/02/rgb-does-not-mean.jpg?w=545)

**FIGURE SAMPLE RGB**: Seems fitting enough

Given we’ve spent more than enough time diving into chromaticity diagrams, let’s see what the above image, including the “white” text, looks like as a volume of colours expressed in the CIE 1931 xyY model…

Plot of the sRGB triplet values using the familiar xyY chromaticity diagram. This stupid thing took about three hours to render using the completely unoptimized plotting tools of MatPlotLib.

So what exactly are we looking at?

The above 3D plot maps every single pixel in the above sRGB **FIGURE SAMPLE IMAGE** and transforms the sRGB values properly to xyY. That means several hundred thousand pixels are plopped into the xyY model, and the above animation shows us the volume of colours in the 3D chromaticity diagram. The upper most white circle in the plot? That is the position of the white text pixels, all crammed into the exact same 3D xyY plot position, because… well… they are all the same chromaticity. The darker scattering near the sRGB triangle footprint? Those would be the extremely low intensity emissions near black in the image. If we were able to see through the cluster of points near the bottom, we’d find a single value representing the sRGB chromaticity point for `[0.0, 0.0, 0.0]`. The rest, as you can see, are quite orange-y to red-y to brown-ish looking, and map according to intensity along the vertical axis.

So if that oddly mountainous looking stack of chromaticity positions is indicative of the **FIGURE SAMPLE IMAGE**‘s pixels, what might the extremes of the sRGB gamut look like? Wait no further for the question that you never wanted to know the answer to!

The question you never asked nor cared about! The entire exterior solid hull shape of the sRGB gamut volume expressed using the CIE 1931 xyY model.

---

And that brings another installment to a close. Although there are several useful representations of gamut available as per the CIE defintion, we have highlighted the idea of gamut as a volume here. To appreciate why we have focused on gamut as a volume of values however, will have to wait for [some further questions…](https://hg2dc.com/question-20)

---

1 Always remember that the chromaticity plot only plots a direct connection between visible wavelengths of light and the limited experience of “colour” for a standard observer. While we might be loosey goosey with our terms at times, it is always important to draw a distinction between a *chromaticity* as a useful coordinate mapping and the more complex sensation of *colour*. We can use the former to reference loose ideas of the latter, but there is a nuanced and complex differentiation between the two terms. *Colour*, in the larger psychophysical sense, is hugely complex and contextual.

