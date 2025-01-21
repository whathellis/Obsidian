---
URL: https://hg2dc.com/2019/03/24/question-3/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/03/28569-1v-ocykmreavtnivc6cxrnw.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-31
duration: 5
done: true
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
# Question #3: Does the F*cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?

With the first couple of questions out of the way, we have a concrete, albeit simplified, understanding as to what happens in most DCC painting applications when [we change an RGB slider value](https://hg2dc.com/question-1/); we are changing the intensity of some colour of light along some undisclosed measurement system. It’s useful to think about the possible implications for an imager working in a DCC now that they have a firm idea that they are rendering light emissions on a display.

Trying to stick to the most simplistic core concepts, we will occasionally need to use some useful terms to keep ourselves on the same proverbial page¹. As mentioned before, an additive RGB light colour encoding model consists of three RGB *primaries*, and we will try to use that term going forward. As we discovered in the previous question, we change the ratios of intensities of the light emission when we change the values in a typical DCC application. But what about the actual colour, or in fancy pants colour science-y terms, *chromaticity*, that results from the changing our values? Specifically, we need to answer one important question…

***Question #3: Does changing the intensity of a single RGB light change its colour?***

Once again, I highly encourage you to muck about in your favourite DCC application to hammer the ideas home. Set your colour to something like `[0.0, 1.0, 0.0]`, `[0.0, 0.75, 0.0]`, and another to `[0.0, 0.5, 0.0]`. Do the three greenish looking colours appear to change colour?

![](https://hg2dc.com/wp-content/uploads/2019/03/28569-1v-ocykmreavtnivc6cxrnw.png)

The green light emission at 100, 75, and 50%

---

As you may or may not have realized, changing a single channel in an RGB encoding model changes one thing and one thing only.

***Answer #3: Changing the intensity of a single RGB channel will only change the quantity of light emitted from that channel, not the underlying “colour”, or chromaticity, of the primary light in question.***²

That is, if we take a series of values such as `[0.0, 1.0, 0.0]`, `[0.0, 0.75, 0.0]`, `[0.0, 0.5, 0.0]`, and even `[0.0, 0.0000001, 0.0]`, they all will be the exact same greenish colour³, at different intensities of emission. Again, in colour science terms, we can say that in an ideal scenario, the chromaticity of the primaries never changes, only their respective individual intensities⁴.

---

So where does this leave us? We started the Guide with a simple question and all we seem to have done is answer a question with another question, or worse, *questions*! That is, we have been slowly revealing *what we don’t know and thought we did*, more than learning what we *do* know. Don’t worry adventurer. Knowing what you don’t know is absolutely as important as knowing what you think you know, you know?

Here’s a loose summary of what we *do* know:

-   We know that when we adjust a slider in a DCC, we are solely changing the intensity of a light.

More clearly, this is two statements:

-   We know that when we change the value, we are changing the quantity of light.
-   We know that when we change the intensity of the light, for all intents and purposes, the colour of the light primary never changes.

Knowing these things though, leads us down to further questions. Given the bullet points above, we might start asking questions about the first point. That is, if we are changing the intensity of a particular chromaticity of light, what is the chromaticity of the light in the first place? [Let’s make it official and ask the question…](https://hg2dc.com/question-4/)

---

¹ Terminology is damn important. Part of the problems with the random noise online is that folks tend to be far too loose and free with their usage of terminology, or use overloaded terms. For those interested, the ISO-22028–1 document has a handy dandy glossary at the beginning. These posts try to adhere to the some of the terms outlined there, or via specifications. Hopefully the terminology will trickle down slowly like an intravenous drip to not overwhelm the reader.

² Ok, I can already hear the WANKs wanting to take deep dives into voltage and power functions, and Abney effect, and physical colorimetry aspects of a display device, and how no physical display is perfectly idealized, and how “colour constancy” is a psychophysical effect, etc. etc. etc. As per the second footnote in the first entry, please shut the f\*ck up and sit down for a moment. You aren’t helping the intended audience here, nor is taking a deep dive into psychophysical effects. If you are here and are one of the WANKs, the goal is to lay a solid foundation for understanding, and in doing so, we are going to have to leave out some of the puzzle pieces that can be explored at a later time. If you are here and are not a member of the WANK club, rest assured, I’ll do my best to keep the WANKers at bay, and introduce the elements in the most digestible morsels possible.

³ The term “colour” here has been used interchangeably with “chromaticity”, which isn’t entirely accurate. Colour exists only in the human perceptual system, and as such it’s really quite complex. [That is, the appearance of a given colour and it’s chromaticity can be different things.](https://hg2dc.com/question-27) Using a term before it is well defined though, would complicate the more important concepts. As we move on, the balance of terminology will shift towards more correct usage.

⁴ Yes, the WANKers are chomping at the bit wanting to wax lyrical about the nature of non-uniform application of 1D lookups or per-channel applied expressions and how it alters the chromaticity. Yes, yes, yes… go take a suckle on your milk bottle nipple for awhile or mash some hours away raging in the comment section of YouTube. While you are gone, the folks following along the path will carry on quietly…

