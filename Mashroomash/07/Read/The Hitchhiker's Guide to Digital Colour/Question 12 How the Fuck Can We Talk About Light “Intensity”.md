---
URL: https://hg2dc.com/2019/11/04/question-12/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/01/dual-axis-12.png
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:14:56
duration: 8
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #12: How the F*ck Can We Talk About Light “Intensity”?

Brighter? Lighter? More light? Less light? Where the hell does physics and energy fit into all of this? Arrgh.

If we don’t have a clear grasp on what linear means and it’s relationship to digital colour, we are going to have a hard time discussing deeper subjects. So what the hell is happening when we slide those RGB sliders like [we asked back at Question #1](https://hg2dc.com/question-1/)? We can sort of [understand that the code value representation is bound to some notion of a ground truth of “linear light energy”, but just what the hell is that](https://hg2dc.com/question-6/)?

Given you are all likely digital pixel pushers and image smiths, let’s make this simple and start with an image. It’s a quiz of sorts, and a not-super-challenging one at that…

![](https://hg2dc.com/wp-content/uploads/2019/11/3bfc5-1ciubudgzubbeqcolkltnea.png)

**FIGURE WHAT IS LIGHTER** Which square appears “brighter”?

And now, the question…

***Question #12: How can we describe light intensity?***

Order those three swatches above in the order you would consider lightest to least light, then we will see you after the break…

---

As a pixel pusher you’ve probably noticed more than a few things about the nature of certain colours and their respective lightness relative to each other. While you may not have made the connection between a given colourspace’s code value and it’s relationship to linear light output from your display, you certainly may have noticed that, when you set the RGB sliders to an equal value, the damn colours don’t maintain an “equivalent” lightness!

The simple answer to the above visual quiz is of course that the three colours are unequal looking in lightness, with the green square appearing the lightest, the red square second, and the blue square being the least light. That is, each swatch is set to an identical RGB code value emission level, yet the three squares are not the same *perceptual* intensity.

---

As we learned quite a ways back, colour is a psychophysical phenomenon; one part is psychological and the other part is physical.

> *“Color is not actually a property of light or of objects that reflect light, it is a sensation that arises within the brain.”* 
> 
> *—  [Biologist Timothy H. Goldsmith, What Birds See](https://www.scientificamerican.com/article/what-birds-see/)*

If the sRGB code values are equal, and we see a difference in lightness, which part of the problem here is wrong? To understand the answer, we need to divide the discussion into two axes that we can use to communicate “intensity” of the light.

---

When we look at the three swatches above, and assuming our vision is in accordance with what has become known as [the Standard Observer model](http://cie.co.at/eilvterm/17-23-048), our perceptual system sees the green swatch as the “lightest” of the three. When we use a *perceptual description*, we could say that the green swatch is more [luminous](http://cie.co.at/eilvterm/17-21-039); it appears to have more *perceptual* energy than the red or blue swatches.

Yet at the same time, we know that the sRGB values are set to maximum intensity via their code values. How can we reconcile the swatches appearing at varying lightness if the code values are equal? The answer is quite simple; various colours of light hold differing levels of luminance at equal *physical* energy. We call the physical energy value of light [*radiance*](http://cie.co.at/eilvterm/17-21-049), or *radiant energy*.

That’s right… there’s two “energies” at play here. One, [*radiant flux or radiant power*](http://cie.co.at/eilvterm/17-21-038), is relative to our constructed physical radiant energy models. The other, [*luminous flux*](http://cie.co.at/eilvterm/17-21-039), is relative to our psychophysical perceptual models. An easy way to remember which is which is to remember that radiant is tied to *radiation*, and we know that radiation is related to physics and energy*.*

---

Let’s refine our rough hewn knowledge by adding a bit of sanding via a couple of useful terms.

***Answer #12: There are two useful axes to discuss the intensity of light; radiant energy is a ratio of physical energy required to generate an emission, and luminance is a photometric measure of how much perceptual energy the light holds relative to our psychophysical systems.***

That means that we could have a very saturated blue laser at equal input radiant energy to a green laser, and the green laser will appear vastly more luminous than the blue. There’s a whole model that describes the relationship between luminance and radiant energy of the various visible light spectra, but we won’t bore you with those details just yet, [even though we have sort of let the cat out of the bag in the previous post](https://hg2dc.com/question-11/).

As a pixel pusher, you are likely more interested to learn if we’ve uncovered anything useful here when thinking about our digital colour work. The relationship between the visible light wavelengths and how much perceptually luminous the energy will appear is described in the following [luminous efficacy](http://cie.co.at/eilvterm/17-21-035) diagram.

![](https://hg2dc.com/wp-content/uploads/2020/01/luminous-efficacy.png?w=640)

**FIGURE LUMINOUS WTF** The plot of how the various visible wavelengths contribute to perceptually luminous energy, also known as a *[luminous efficacy](http://cie.co.at/eilvterm/17-21-035)* plot.

So if you are wondering if we can apply this knowledge to pixel pushing, the answer is of course yes! For all intents and purposes, we can consider the linear RGB values after we remove the nonlinear encoding for a particular transfer function, to be the *radiant energy ratios*. We need to use colour science math¹ to derive the *luminous perceptual energy ratios*, which is a fancy way of describing a greyscale image. So how do we convert a colour to a greyscale representation of the coloured light value? Great question…

---

In order to convert a coloured RGB pixel into a greyscale pixel, we know that we need to set each of the red, green, and blue channels to some identical value, otherwise the pixel will have a colour cast. When we set the pixel to have equal code values, the output colour of the light will appear achromatic if we are fully adapted to the “white colour” of the display. But how do we figure out just what to set the RGB values to when we are converting from a coloured pixel to an equivalent greyscale pixel?

![](https://hg2dc.com/wp-content/uploads/2019/11/3bfc5-1ciubudgzubbeqcolkltnea.png?w=580)

**FIGURE WHAT IS LIGHTER AGAIN** The three sRGB lights projected at 100% emission.

In the above image, we have three RGB swatches, each at 100% emission of the (assumed) sRGB display’s red, green, and blue lights. How do we convert those swatches to greyscale? We know that from a radiant energy perspective, each value in our triplet is outputting roughly the same display emission energy, just out of the individual lights. Great, so why not just set each of the RGB code values to 100% then, if the individual channels are set to 100%?

Wait a minute… they don’t appear to be the same *perceptual energy* when they are in colour, so setting the red, green, and blue swatches each to 100% RGB emission will make them appear identical to each other! That’s not going to work, is it? The green doesn’t look like 100% RGB emission, and the red and blue certainly don’t!

![](https://hg2dc.com/wp-content/uploads/2020/01/greyscale-overlay-wrong.png?w=1000)

Taking 33% of each emission level doesn’t work!

The solution to the problem, as you may have inferred, is that we need to “weight” each of the emission strengths based on their respective coloured light contributions to the *luminous perceptual energy.* We can’t use *equal ratios of the RGB radiant energy values*.

We aren’t going to get lost in math here, so let’s just accept that for REC.709 / sRGB based RGB lights, the luminance ratios are roughly 21.26% red, 71.52% green, and 7.22% blue, which we then sum together². The green light in an sRGB / REC.709 display contributes 71.52%, the red 21.26%, and the blue 7.22% to the overall greyscale result. If we do that, the resulting achromatic pixel will *appear to have the same luminous perceptual energy as the swatch had when it was in colour³*! The result is below.

![](https://hg2dc.com/wp-content/uploads/2020/01/greyscale-overlay.png?w=1000)

**FIGURE KINDA GREY** Properly converted to greyscale based on the sRGB primary light contributions to luminance, and converted to their nonlinear sRGB code values.

And with that, we’ve closed another chapter. Hopefully it didn’t hurt your head too much, and you’ve managed to add a little more clarity to discussions of light “intensity”. A handy question to ask is whether the value is trying to describe physical radiant energy or perceptual luminous energy? [On to the next question…](https://hg2dc.com/question-13/)

---

¹ Whoo daddy there is no shortage of people “helping” other people out there on those question and answer sites who screw this up royally. Let’s be painfully clear; the luminance coefficients are derived from the chromaticity of the light mixture. That means that for any given colourspace, with a set of three fixed primary lights, there is precisely *one* correct method to derive the luminance coefficients. Those online sites throw numbers around that are frequently historical artifacts that are completely and utterly wrong given the context in this decade and into the next. The TL;DR is that you should be extremely weary of deriving luminance coefficients from online sites if you are building software. The other TL;DR is that there are plenty of folks utterly confused about digital colour out there apparently. Be warned. Trust no one. Including this idiot⁴. This is a **very** deep rabbit hole, however. For further reading on the subject of “colourful” as “brightness”, consider Ralph Evans “The Perception of Color” 1974, or skimming over [the Helmholtz–Kohlrausch effect entry over at Wikipedia](https://en.wikipedia.org/wiki/Helmholtz%E2%80%93Kohlrausch_effect).

² The astute reader will likely have a question or two about whether you should calculate the result based off of the display linear or the display nonlinear code values, and she’d be right for thinking there will be a difference. This is also why there are two terms typically for the linear versus nonlinear calculations, *luminance* and *luma*, where *luminance* typically refers to calculations derived from the linear light energy code values, and *luma* referring to the greyscale calculation based off of the nonlinearly encoded code values. I’ll leave you to ponder that question on your own, and perhaps try to deduce which version is more “correct”.

³ It should be duly noted that, as always, colour is a complex psychophysical sensation. As such, there are a myriad of psychophysical effects that cannot be accounted for with a pure luminance based evaluation of spectra. In particular, the [Helmholtz–Kohlrausch phenomenon](http://cie.co.at/eilvterm/17-22-066) cited above plays a large role in determining overall sensations of luminance, for example.

⁴ Always fact check. The keen colour science folks will note that the post uses “lightness” here, where many folks might flip flop between lightness and brightness, using the two terms interchangeably. In terms of [Colour Appearance Model](http://eilv.cie.co.at/term/200) language, the two terms are specific and unique. As always, there’s a risk of losing the audience, and “lightness” was chosen as the means of communication. Also note that footnote 4 is a meta footnote of a footnote. It’s an Inception footnote.

