---
URL: https://hg2dc.com/2020/04/26/question-22/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/04/general-high-level-overview-2.png
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:20:44
duration: 6
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #22: How the F*ck do we Move a Red Pixel?

In the last post, we took a very high level peek at what might happen in a code value to display output chain. Let’s take a quick look at a recap…

![](https://hg2dc.com/wp-content/uploads/2020/04/general-high-level-overview-2.png?w=800)

**FIGURE HIGH LEVEL BULLS\*IT** This gives a very high level overview of a code value / slider representation to display output chain.

Without further ado…

***Question #22: What happens when we “move” a pixel?***

---

Let’s begin where we started in the previous [Question #21](https://hg2dc.com/question-21), with our theoretical pixels, outlined below in dotted cyan, turned “off”.

![](https://hg2dc.com/wp-content/uploads/2021/12/two-pixels-large-grid-1.png?w=800)

**FIGURE OFF** Here the two pixels are turned off entirely.

Now let’s turn on one pixel such that it is emitting 50% of the total light from the red pixel’s light.

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-on.png?w=800)

**FIGURE 50%** Here we turn up the pixel to 50% of the overall display’s range.

Recall that in order to turn up the pixel to 50% emission, we have to encode and prepare it for the display’s internal hardware. That math, on conventional commodity sRGB-like displays is rather simple. The sRGB-like displays use a pure power function of 2.2 in their hardware as [a transfer function](https://hg2dc.com/question-6). To get the display to sh\*t out 50% light, we encode it via the *inverse* of the output hardware:

`0.50^(1.0/2.2) == 0.73`

And presto… our sRGB-like display will output the above pixel emission.

---

Now let’s move the pixel. What if we wanted to shift the pixel down a bit, such that it straddles the border of the two display pixels? Could we do that? Let’s see…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-moved-down-grid-off.png?w=800)

**FIGURE LIVE STRADDLE** Here is what we are hoping for. We want to create the illusion that our pixel is straddling the actual hardware pixels. How can we do that?

We know that our hardware isn’t a super duper Uber Retina Quantum Nano F\*ckery display, so we don’t have the actual pixel resolution to precisely move it down by the amount we are wanting here. So what could we do? Let’s take stock of what we know…

1.  We know that our pixels are always emissions.
2.  We know that our pixels also are geometry as discussed in [Question #20](https://hg2dc.com/question-20).

So what if we think in terms of geometry? What if we fully embrace our pixel as a “square” of geometry, and figure out the ratios of coverage it is emitting? This feels an awful lot like [Question #20](https://hg2dc.com/question-20) again, doesn’t it? Let’s take a peek at what our geometry might look like in our above image…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-on-moved-down-grid-on.png?w=800)

**FIGURE THAT WAS F\*CKING CONVENIENT** The yellow dotted lines represent imaginary pixel divisions, or creating a simulated area for subpixels.

That was convenient, wasn’t it? Our imaginary box just happened to land on some imaginary boundary lines. In **FIGURE THAT WAS F\*CKING CONVENIENT**, we have overlaid some yellow lines that divide each pixel up into ten slices along the width and height. That’s right, one hundred total units for each pixel!

---

Notice how our original pixel was a full square of 10×10 units? Now we’ve slid it down roughly three units using our simplified geometric divisions? Can we calculate how much each of our two display pixels are emitting now?

Let’s try…

![](https://hg2dc.com/wp-content/uploads/2021/12/descriptive-text-grid-on.png?w=800)

**FIGURE STRADDLE AREA** Here we can see the total units of coverage the shifted red pixel occupies.

As we can see, even someone who dropped out of school likely has the math ability to figure out our answer. The final output of light are some simple ratios. That is, if our red pixel “square” is emitting 50% of the display’s total light, we can calculate the total area relative to the upper and lower pixels with a tiny bit elbow grease.

---

Our pixel now occupies 70% of the upper display pixel window. We know the emission was 50%, so what’s our total emission if we use the simple math from [Question #20](https://hg2dc.com/question-20)?

**UPPER PIXEL**: `0.70 * 0.50 = 0.35 == 35%`

Simple enough. We take the total area (70 units) and scale the 50% original emission by that amount. Total? Our upper pixel emits 35% now!

Let’s look at our lower pixel, which our original 50% emission pixel now covers 30% of…

**LOWER PIXEL**: `0.30 * 0.50 = 0.15 == 15%`

And there we have it. We’ve “shifted” our pixel down by 30% of our wacky made up geometry. We have “scaled” each of the two pixel’s emissions to represent the original pixel’s 50% emission. We know we have done this correctly because if we take the upper pixel’s 35% and add it to the lower pixel’s 15%, it somehow sums up to our original single pixel’s 50%!

---

What does it look like? Well to figure that out, we have to remember that we haven’t dealt with the display linear light ratios properly yet, have we? We need to *encode* them for the specific hardware we are using. Again, this is our simplified sRGB-like display, so [the display’s output transfer function](https://hg2dc.com/question-6) is pure 2.2 exponent it *always* decodes with. So let’s encode both values, as we have two pixels now:

**UPPER PIXEL**: `35% = 0.35^(1.0/2.2) == ENCODED VALUE 0.62`

**LOWER PIXEL**: `15% = 0.15^(1.0/2.2) == ENCODED VALUE 0.42`

There we go. To shift our original pixel down by those three “units”, the result is that we’d have to set the upper pixel to the encoded value of `0.62` to get out 35% emission, and the lower pixel encoded value to `0.42` to get out 15% emission. This simulates the geometry shifting of the pixel as though it were a square of emission shifting downwards!

![](https://hg2dc.com/wp-content/uploads/2021/12/final-red-subpixels.png?w=800)

**FIGURE OUTPUT** It’s not pretty, but if we looked at the two pixels from far away, they would create the illusion of our original 50% emission pixel having shifted down slightly.

---

You might be worried that you understood the above.

Don’t be. Light is pretty basic stuff. The whole bullsh\*t of display encoding and decoding can sometimes make people think things are way more complex than they are. They aren’t.

***Answer #22: We can move pixels around by treating them as small geometry that represent emissions using super simple math.***

But wait… there must be a catch, right? Surely there’s something here that we are missing? The answer is sadly, yes.

Many pieces of DCC software are absolute sh\*t. Instead of doing the math on the display’s linear light ratios as we did above, they use some bungled up mess of ideas that some random idiot thought was a good idea. Typically, software folks will conflate the *encoded value* with its *decoded* meaning. You can probably guess where this is going.

Instead of doing the *proper* thing and calculating the math on light ratios, the math is often *wrongly* applied to the encoded values. That’s right, some poor soul never bothered to ask the question way back in [Question #1](https://hg2dc.com/question-1), and as a result, they completely screw up the most fundamental math. Imagine doing the math for audio processing on an encoded MP3 signal and you can guess just how wrong the results would be. This leads to all sorts of broken software ideas all over the damn place!

Stupid software comes back to kick you, the lowly pixel crafter, right in the teeth with garbage broken output when all you wanted to do was blur the sun or smudge a tree line.

*“But aren’t there different types of displays?” “What about different RGB colour spaces with different transfer functions?” “Don’t we need to take the colour spaces into account before doing math?”*

These are all terrific questions. Perhaps you are even starting to understand why some software breaks on even simple things like those outlined in [Question #9](https://hg2dc.com/question-9). But let’s take a break from this and leave the subsequent excellent questions [for another question or two…](https://hg2dc.com/question-23)

