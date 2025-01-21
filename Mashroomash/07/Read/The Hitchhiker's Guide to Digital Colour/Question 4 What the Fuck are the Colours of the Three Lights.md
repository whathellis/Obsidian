---
URL: https://hg2dc.com/2019/03/26/question-4/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/03/c3f34-1dsscuqjmjw7mts4jzm875q.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-31
duration: 6
done: true
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
# Question #4: What the F*ck are the Colours of the Three Lights?

Have you ever taken a random set of paints and started mixing them? If you have, you probably have realized the not-quite-groundbreaking idea that the paint mixture colour depends on which paints you mix and in what quantities you mix them.

This profound, almost Aristotle-like breathtaking and earth shattering conclusion holds a not-too-distant connection to digital RGB colour work. As you may have noticed from the very first question, some things that are painfully obvious sometimes go without an actual analysis. Let’s try to smash that up…

---

If we have a single channel of RGB light in a pixel, [we can increase or decrease the intensity without changing the underlying primary’s colour](https://hg2dc.com/2019/03/24/question-3/). Hopefully you are seeing that there are two axes that we have managed to focus on. Here, intensity is to the colour as volume is to a note played on a speaker. We can increase or decrease the volume without changing the note in question. The same holds for colour.

How then, do we change the colour? Just as with the introductory paragraph, the answer is simple; we mix in other lights. If we have a reddish light, we can represent exactly one colour, at varying intensities. If we add a light, perhaps a greenish light, we can now mix a two dimensional set of combinations. These colours will be extremely familiar to you all, because all you have done is push around pixels and “paint” in mixing interfaces and colour pickers.

![](https://hg2dc.com/wp-content/uploads/2019/03/c3f34-1dsscuqjmjw7mts4jzm875q.png)

Mixing the two dimensional gamut between red and green, at 100%, 75%, and 50% intensity

As discussed, we can say that the chromaticity of the three sets of mixture swatches above are the same across the columns of values, and only the intensity of the light ratios are changing uniformly. Note that at no time are we able to mix an *achromatic*, or without colour, mixture¹ from only these two particular choices of light chromaticities. The two dimensional array of combinations always traces from red to orange to yellow to lime to green and back. Always.

If we add a third light, we of course get another whole range of colours and values we can mix. That third light in an RGB encoding is typically blueish. By adding the blueish light, we can indeed mix a colour that looks achromatic. Note how I said the word achromatic, instead of that blasted nightmare word “white.” The reason is, “white” creates the illusion of a fixed and absolute thing, as opposed to the idea that it is just another colour at some intensity. You will also notice how I avoid conflating code value `0.0` with “black”, as it too, isn’t a single, absolute thing. More on that later…

In all of this basic light mixing, we have neglected the elephant in the room. It’s sitting over there, crunching away and pooping, and no one has really asked what it is doing there.

***Question #4: What are the actual colours of the three RGB lights?***

Dumb question, right? If only it were…

---

How many times have you pushed a pixel around on a screen, been yelled at by clients, answered snarky emails, or tried to chase down getting paid for the hot dog logo you did up two months ago? The answer, I’ll guess, is far more times than the number of times you asked what colour the lights were in the pixels in your display.

The question is darn important, and sadly is as ignored or overlooked as that invoice sitting on your client’s desk for that hot dog logo. The answer is also contextual; it depends on what equipment you have. In most instances though, the computing industry has historically rallied around a much overloaded and horribly confused standard. In keeping true to making things as foundational as possible, we will make an assumption here.

***Answer #4: There is a good chance that the colours of the three primary lights in your display are darn close to the REC.709 red, green, and blue chromaticities.***

Gotcha there, didn’t I? You were waiting for that s word… that one that everyone mutters in shallow breaths and tosses around in all sorts of different and confusing contexts. That word is of course sRGB, and it is probably one of the most commonly overloaded terms in graphics ever. I purposefully used the more correct answer to try and pull you out of that sad little loop of nightmare². With that, we’ve generated yet more questions.

---

So what’s the takeaway here? We’ve exploded all sorts of crazy new questions, and answered even fewer. I’d hope you focus on one very specific conclusion here; the colours in your display are physical hardware constraints, and that physical element is defined using a chromaticity map to nail down the physical colours of the lights, using an absolute colour encoding model. In many cases, the standard targeted is the sRGB standard, which uses primaries that are identical to the primaries in the REC.709 standard. The lights are the same chromaticities!³

But what about if you happen to have a MacBook Pro with that fancy Display P3 mumbo jumbo or some Eizo magical +6 Wide Gamut of Costly Dollars? The answer, as you hopefully may have suspected, is that they actually have *different coloured lights* at each pixel position in the hardware of the display; the paint pots are different from the paint pots outlined in the sRGB / REC.709 standards!

Like all good investigators though, we need to retrace our footsteps a bit before going further. We need to go back to talk about measurement units. Remember that `0.6` in the earlier question? [That’s a unit of measurement, and we need to dive a little deeper before we can start tackling more complex questions…](https://hg2dc.com/question-5/)

---

¹ It should be worth noting that I’m deceiving you a bit here. *Achromatic*, or without colour, is something that happens in your *psychophysical* perceptual system, and isn’t something that exists absolutely outside in the spectral world. More on that later…

² The sRGB specification utilizes the primary light chromaticities defined in the REC.709 specification that predates it. As such, I have honoured the historical precedent as the origin for the label. There is a minor difference in how the chromaticities are defined that yields a discrepancy in the decimal places, but for all intents and purposes, it is relatively safe to refer to the chromaticities of the primaries as the same in the REC.709 and sRGB standards.

³ As above, there’s a bit more to the story. How precisely we identify a chromaticity via the decimal places or format plays a role here. To this end, there are subtle differences from a technical standpoint on REC.709 vs sRGB chromaticities, but for all intents and purposes, it’s healthy to think of them as the same. This is the same information presented in the footnote above, but redundancy redundancy are fine in paragraphs that no one bothers to redundantly read anyways.

