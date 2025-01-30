---
URL: https://hg2dc.com/2019/05/23/question-5/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/05/bc5c1-1wslfbvitbaj0owqtleyowa.png
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-04
duration: 4
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #5: What the F*ck does 0.5 mean?

Continuing along the analogy of mixing paints, the colours of the paints matter. If we ask two people to pick out three paints each, at random, and ask them to mix certain amounts according to a recipe, there is a zero percent chance the same colour would result between the two people using the identical recipe measurements. However, even if we ask them to pick out precisely identical coloured paints, we would still need them to have agreed upon a measurement system!

I’ll get the question out early on this one. It’s a helluva important one…

***Question #5: What is the basic unit of RGB then, specifically?***

A few questions ago, we scratched the surface of code values and their representations. We can summarize a few things about code values:

-   Bit depth, or the *quantity* of “steps”, has no impact on the [chromaticity](http://cie.co.at/eilvterm/17-23-052) of the primary lights, or [*tristimulus values*](http://cie.co.at/eilvterm/17-23-038)*,* nor change the minimum or maximum emission of said lights. That is, it is like the number of slices we choose to slice up a banana; more slices isn’t going to make the banana an apple, nor make the banana longer or shorter.
-   Code values can be *represented* a number of different ways in a computing environment. Up to now, we have discussed whole numbers, or integers, which typically are used as a ratio of the maximum integer range. `8/255` or `67/1023` can be considered a *ratio* of the banana’s whole. From within the DCC application of your choice, consider garbage eight bit representations such as `255` and equally garbage hex codes such as `0x1A` as different representations of integers. These can be more clearly expressed as decimal values.
-   Code values can be *interpreted* as anything, and depend on context. We examined how normalized integer code values could be interpreted as ratios from minimum to maximum expressing a quantity of light being emitted from a display, or interpreted as a percentage of a banana that has been eaten. *Code values must be decoded and assigned meaning*.
-   RGB code values *alone* carry *no additional context* that explain what the values mean. We cannot examine an RGB triplet in isolation, no matter how accurate they appear, and know what they represent; we need additional contextual information to decode a code value. We cannot look at `0.372734234211` and infer that it means 37.27% of a banana; we need to know that you are talking about bananas and not apples, and whether the value is in fact a ratio or some other measurement such as overall banana length according to some measurement system.

The last point is worth focusing on a little bit more. We know that a code value in an RGB system can be used to change the intensity of the light in a display, but what we don’t know is how code values are measured against each other. We can’t assume we are talking about units of orange slices when the intention was a quantity of bananas.

---

You might already have a sniff as to what the answer is to this question. If you haven’t, you haven’t fully embraced how much crap there is out there that is impeding your comprehension. I’ll go out on a limb and suggest that your understanding is likely greatly inhibited by the fact that…

***Answer #5: The basic unit of measurement in an RGB triplet of code values, when considered in isolation, without any further information, means absolutely nothing.***

Much like the last example of oranges to bananas, *RGB code values, in isolation, are* ***meaningless***. Specifically, the increments between code values have no constant meaning. That deserves a paragraph break for it to settle in.

---

We’ve all seen numbers with long, scary decimal places. Although we are seduced into thinking they hold inherent meaning, they too are meaningless. They are nothing more than codes waiting to be interpreted. Countless StackExchange posts, idiot YouTube comments, and even application documentation are frequently a miserable bog of misinformation. They’ll give you all sorts of fancy long numbers when talking about RGB, but what they won’t tell you is that they are horribly confused in most instances. It’s mostly utter bulls\*t.

While we now know that we need additional data to describe the chromaticity¹ of the light a code value is intended to control, we *also* require additional information about the intensity measurement ratio.

[Back in another question, we touched on how code values represent some ratio of light](https://hg2dc.com/question-2/). But what are the units between the ratios? What would `0.5` *represent*, in terms of intensity?Is it a physical measurement such as half of the number of photons when compared to maximum? Is it some absolute quantity of light? Is it some strange “Gee whiz that value looks half as bright as maximum?” perceptual sort of thing? And if we understand `0.5`, what is its relationship to `.051` or `0.6`? Once again, [more nasty questions…](https://hg2dc.com/question-6/)

---

¹ Remember that chromaticity is best described at this point as an absolute measurement of colour. It’s a little more complex than this, but for now, that will do just fine.

