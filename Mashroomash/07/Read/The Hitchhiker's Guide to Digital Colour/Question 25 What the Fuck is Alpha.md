---
URL: https://hg2dc.com/2020/08/26/question-25/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/08/straight-alpha-meme.jpg
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:22:05
duration: 11
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #25: What the F*ck is Alpha?

***Question #25: What is alpha?***

***Answer #25: Yet another dumb f\*cking Greek glyph label that a math nerd arbitrarily decided to use.***

Done.

---

As with all things related to digital image making it seems, there are way too many horrible labels based on completely unrelated names for glyphs from the Greek alphabet. Math nerds, we love you, but your choice of placeholder terms absolutely f\*cking sucks.

We need to drill past terrible Greek glyph labels such as “gamma” and “alpha” to get to something meaningful. Let’s re-lens our question into something much more useful.

***Question #25: What does an alpha encoded pixel represent?***

I regret to inform you that as we connect the dots between the answers from the previous [Question #22](https://hg2dc.com/question-22), [Question #23](https://hg2dc.com/question-23), and [Question #24](https://hg2dc.com/question-24), we will also stumble over yet another wretched f\*cking term that will be addressed in the postscript.

The *actual* reason of the previous three questions is to make two *extremely* important manipulations around light clear, but in doing so, we have inadvertently stepped onto enough land mines to fully explain what a properly encoded alpha image represents.

So with that, let’s recap with a focus on RGBA encodings.

---

When looking at a properly encoded alpha pixel, we can nicely summarize what the values mean by asking two questions. Those two questions are as follows:

1.  How much light does this pixel emit?
2.  How much light from the pixels behind it does it occlude?

![](https://hg2dc.com/wp-content/uploads/2020/08/25-emission-occlusion.png?w=1000)

**FIGURE RGBA** The answer to the question, as a spoiler.

It’s worth pointing out that we could answer the above two questions in several combinatorial ways. For example…

-   “The pixel emits no light and occludes half of the light from behind it.”
-   “The pixel emits Foobar units of light and does not occlude at all.”
-   “The pixel emits some units of light and occludes some of the light from behind it.”

Each of these scenarios are entirely physically plausible via a few equivalent examples…

-   A super all-absorbing paint panel could emit no light and occlude half of a light behind it.
-   A reflection on a window we are looking out of will add light to our view, while not occluding any of the light being transmitted through the window from the scene beyond.
-   Something may reflect or emit a certain amount of light, while partially occluding the reflected or emitted light behind it.

As far as models go, the two aspects of emission and occlusion work rather well to describe a simplistic, albeit useful, physically plausible-ish light transport facet1.

---

In a *properly* *encoded* RGBA pixel, the RGB values have been previously calculated to express precisely how much light is to be emitted, and the A channel is indicative of the percentage of occlusion. Why do we need the percentage of occlusion included if the RGB values already contain the calculated emission levels? Because we need that value to properly calculate how much of the background emission we are left with.

In terms of simple language, a conventional *[over](https://graphics.pixar.com/library/Compositing/)* is achieved via a three step process:

1.  Figure out how much of the geometry window remains, if the foreground pixel is occluding.
2.  Use that remaining geometry region to scale the background emission.
3.  Add in the foreground emission to the result.

We can break those three steps down into simple math.

1.  Given a 100% window, subtract the foreground’s percentage of geometric occlusion to figure out the remaining geometry that the background emission will influence.
2.  Scale the background emission by that remaining geometric window.
3.  Add the foreground emission.

Even though we have walked through these exact processes prior, we will use a simple example to hopefully bolt down the idea. Let’s imagine Brother Red and Sister Green as something more interesting…

---

Let’s revisit the exact same contexts we have disclosed over the previous three questions, and keep many of the variables similar.

![](https://hg2dc.com/wp-content/uploads/2021/12/spaceship-zoomed-out.png?w=800)

**FIGURE BROTHER SPACESHIP** Brother Red still emits 50% of our display’s linear light ratio.

Now let’s zoom in on our Brother Red Spaceship against Sister Green’s Green Space background…

![](https://hg2dc.com/wp-content/uploads/2021/12/zoomed-spaceship-outline.png)

**FIGURE CLOSE UP** This is a simulation of the pixel geometry.

And if we were to divide up the pixel “window” as per our now familiar previous questions to evaluate the geometry, it might look like the following…

![](https://hg2dc.com/wp-content/uploads/2021/12/zoomed-spaceship-rasterized-1.png?w=800)

**FIGURE GRIDDED** Here we see an arbitrary division of coverage. To keep things simple, we divide the pixel into 100 subpixel units for calculating geometry.

And now, let’s manually perform an over!

---

As per our three stage solution for an alpha over, we first must calculate how much of the window remains after considering the foreground pixel. In this case, Brother Red’s Spaceship geometry of coverage would be as follows…

![](https://hg2dc.com/wp-content/uploads/2021/12/spaceship-red-geometry.png?w=800)

**FIGURE BROTHER RED GEOMETRY** Note how Brother Red’s Spaceship covers 64 units of the pixel window. Go ahead, add them up! This means that the pixel’s alpha could be represented as 64%, or `0.64`!

So to solve how much of the pixel window remains, it’s a matter of simple subtraction. Given Brother Red’s Spaceship hull covers 64 units according to FIGURE BROTHER RED GEOMETRY above, we know that Brother Red’s Spaceship occlusion is `0.64` in decimal. To figure out how much remains, we will subtract it from the 100 units, aka 100%, or in decimal, `1.0`.

`REMAINING_GEOMETRY = 1.0 - 0.64 == 0.36`

And with that, Step One is knocked down!

![](https://hg2dc.com/wp-content/uploads/2021/12/spaceship-red-and-green-geometry.png?w=800)

**FIGURE TOTAL GEOMETRIES Here we can see how much Sister Green Space’s geometry is remaining to project out of the pixel window.**

---

The second step in our operation is to scale the background emission by the remaining pixel window geometry. That is, we can see that Sister Green’s Space is assumed to be 100% coverage before Brother Red’s Spaceship entered into her pixel window, in much the same way we have covered in the previous questions. So here, we scale Sister Green’s 60% pure green display linear emission by the little bit of the window that remains uncovered, which is 36 out of 100 units, or `0.36`.

`SISTER_GREEN_EMISSION = 0.60 * 0.36 == 0.216`

Presto. We know that Sister Green Space’s pixel triplet is `[0.0, 0.216, 0.0]`. Onto the final step…

---

Our final step is to take Brother Red’s Spaceship emission and add it to Sister Green’s Space emission, and we will arrive at our final triplet. Brother Red’s Spaceship is emitting from 64 of the 100 units at 50% display linear light emission. Therefore…

`BROTHER_RED_SPACESHIP = [0.32, 0.0, 0.0]`

Now we have already scaled Sister Green’s Space region based on Brother Red’s coverage, so her pixel triplet would be…

`SISTER_GREEN_EMISSION = [0.0, 0.216, 0.0]`

And we sum the two triplets…

`[0.32, 0.0, 0.0] + [0.0, 0.216, 0.0] ==`  
`[0.32, 0.216, 0.0]`

It’s just that simple. We’ll leave the encoding for the particular display’s transfer function as an exercise for the reader.

---

So this post has been nothing more than a bundling and rehashing of the previous three questions…

[Question #22 discussed how pixels can be thought of as small regions of geometry.](https://hg2dc.com/question-22)

[Question #23 discussed how additive light works in conjunction with the idea of geometry.](https://hg2dc.com/question-23)

[Question #24 discussed the relationship between geometry and a degree of occlusion.](https://hg2dc.com/question-24)

With this final post, we are able to bundle up notions of geometry, additive light, and scaling light into one final punchline formula…

`FG.EMISSION +`  
`((1.0 - FG.OCCLUSION) * BG.EMISSION)`

That’s it! [That’s the classical alpha over formula as formulated by Porter and Duff](https://graphics.pixar.com/library/Compositing/). Hopefully we are so sick of the basic examples that we can get a clear picture as to how the three components of geometry, additive light, and scaling light, interact!

---

***Answer #25: In a properly encoded image, the red, green, and blue channels represent the precalculated emission, and the alpha represents the geometry of occlusion.***

It’s that simple, and with the previous questions, we have covered the concepts in painfully pedantic manner that will hopefully have left us with emotional scar tissue as to the underlying mechanics.

So you might be wondering about those two crucial light manipulations outlined above and how we can apply them elsewhere? Maybe we’ve thought about different orientations of geometry that are beyond the example provided above?

For the next question, we will focus on two of the light manipulations described in this post, and that should make the photographer friends rejoice! Better still, by delving into one specific aspect of the manipulations outlined above, we can explore beyond the display! Alas dear friend, [that will just have to wait…](https://hg2dc.com/question-26)

---

The inevitable postscript for the WANKers…

![](https://hg2dc.com/wp-content/uploads/2020/08/straight-alpha-meme.jpg?w=596)

**FIGURE SHUT THE F\*CK UP** No really, there is only One True Alpha.

I can hear the sound of distant Sealions WANKering off in the background…

If you scroll up, you’ll realize that we have referred to *properly encoded RGBA*. With this post, it should become very clear that an RGBA quadruple is only ever *properly encoded* if and only if *the emission is precisely the amount of light emitted from the pixel in question*.

As refreshing as that is, we need to address the fact that somewhere along the line we took an unfortunate turn and labeled something really shi\*tily. We’ve covered that The One True Alpha consists of a formula that:

1.  Considers geometry of occlusion, if present.
2.  Scales the background emission by the geometry of occlusion.
3.  Adds in an arbitrary quantity of emission from the foreground.

And this simplified model of a pixel for use in light transport has unfortunately become known as *premultiplied alpha*. It would be challenging to dream up a worse term for such an encoding. Put something math-nerd in a term and you can be guaranteed that math nerds will get obsessed with the math nerdism of the subject, and completely forget the idea that RGB values are emission intensities. Mr. Gritz, cited below, was one of few sane people who chose to use [the TIFF specification terminology associated alpha](https://www.graphicsmill.com/docs/gm/working-with-tiff-extra-channels.htm). As with All Things Gritz, it is a decision rooted in wisdom.

So we said *properly encoded* alpha, and some Sealion WANKer at the back will say something like “ThErE is AlSO StRAiGhT AlpHA!1?”

Guess what? You Sealions missed that part where we say *properly encoded*, didn’t you? Let’s look at the formula for this other burning dumpster fire of a format known as “straight alpha”…

(`FG_EMISSION * FG_OCCLUSION) + ((1.0 - FG_OCCLUSION) * BG_EMISSION)`

It looks awfully similar to The One True Alpha’s formula above, yet there is one minor difference. See that first term where there’s a new multiply tacked on? The `FG_EMISSION * FG_OCCLUSION`? Within that little term, you can see that this “alpha format” isn’t actually encoded! All that term does is scale the emission contained in the RGB triplet, which means that the RGB encoded in such an image is *not actually representing the emission*; it’s simply some pixel emission before consideration is given to its state. Hence it can be argued that a straight alpha encoding isn’t encoded at all… it’s just a state where the emission has not been calculated. Why does this matter?

To answer that, let’s turn to some exemplary image experts in the field. These three folks are three more deities in the digital halls of imaging. They have struggled in the trenches for many years, and have significant contributions to their fields, which will be left to the reader to discover and appreciate.

> The error here is \[…\] interpreting the word “premultiplied” literally. Many people do, incorrectly.
> 
> I really hate the word, actually, because it leads you to believe it’s literal meaning, that something has been multiplied with something “before” (i.e. “pre” something).
> 
> THAT IS WRONG. It is a total *misrepresentation* of what “premultiplied” means.
> 
> [Veteran Zap Andersson on the legendary and infamous and hilarious Adobe Thread of Doom](https://community.adobe.com/t5/photoshop/change-in-exr-open-from-cs2-to-cs3-can-this-be-fixed/m-p/1521042?page=19#M918)

> At this point, I’m going to go on a bit of a religious rant and just say that associated alpha (premultiplied color) is the only choice that makes sense. It’s the only thing that renderers are likely to produce naturally, it’s the only way that compositing and any other image processing math works, and in my opinion it’s the only sensible form to store any image.
> 
> It is also worth noting that associated alpha can express RGBA values that unassociated alpha (un-premultipled color) CANNOT. It’s just a fact of life; for example, an RGBA pixel that means “glow bright yellow but don’t block the view of the things behind it” can only be expressed in premultiplied colors (associated alpha).
> 
> [Academy Award Technical Achievement winner and all around f\*cking incredible person Larry Gritz](https://groups.google.com/g/osl-dev/c/3QKlnfW6dB0/m/KdziBfxeBgAJ)

> To the best of my understanding, premultiplication is the natural representation of pixels with alpha; the big confusing thing about it is the name.
> 
> I feel the simplest understanding of premultiplication is looking at it from a rendering perspective. If you’re writing a renderer, you ask yourself “how much energy is being emitted from within the bounds of this pixel”? Call that RGB. “and, how much of the background does this pixel occlude?” That’s alpha.
> 
> This is how all renderers work (prman, arnold, etc), and it’s called ‘premultiplied’. Note that at no time does prman have an explicit step that multiplies RGB by alpha, it’s implicit in our definition of ‘total pixel energy’. 
> 
> [Academy Award Technical Achievement winner and colour science bacon I mean beacon Jeremy Selan](https://groups.google.com/g/ocio-dev/c/ZehKhUFqhjc)

---

1 All models are purposeful simplifications. If we need something that works, we need to choose what facets work Good Enough, and model them. It should be pointed out the one of the imaging deities who created our contemporary understanding of alpha, [Mr. Duff of Porter and Duff, has extended the associated alpha model with further math that works more appropriately with depth compositing](https://graphics.pixar.com/library/DeepCompositing/paper.pdf). The approach outlined above seeks to explain the most conventional alpha compositing image makers will encounter, but shouldn’t be taken an an end point! [There’s much more nuance here to be covered in the future](https://hg2dc.com/question-26)!

