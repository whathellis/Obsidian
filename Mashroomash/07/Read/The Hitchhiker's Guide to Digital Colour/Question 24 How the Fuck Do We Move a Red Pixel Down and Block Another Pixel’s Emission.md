---
URL: https://hg2dc.com/2020/07/20/question-24/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/05/50red-over-60green-30unitsdown-only-cyan-grid.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:21:56
duration: 10
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #24: How the F*ck Do We Move a Red Pixel Down and Block Another Pixel’s Emission?

***Question #24: How can we move the red pixel from [Question #23](https://hg2dc.com/question-23) down and block the green pixel?***

To answer the question, we need to build atop of the more recent subjects we have covered, and in particular, think about how light and geometry interact. Remember, as [Mr. Blinn](https://en.wikipedia.org/wiki/Jim_Blinn), [Mr. Smith](https://en.wikipedia.org/wiki/Alvy_Ray_Smith), [Mr. Catmull](https://en.wikipedia.org/wiki/Edwin_Catmull), [Mr. Porter](https://en.wikipedia.org/wiki/Tom_Porter_(computer_scientist)), and [Mr. Duff](https://en.wikipedia.org/wiki/Tom_Duff) have set forth, everything amounts to an abstracted model, frequently riddled with confusing Greek math-nerd glyphs for symbols.

From the digital image maker’s vantage, it is crucial to ignore the ritualistic patterns we survive on, the “magic” numbers thinking, the f\*cking ridiculous Greek math nerd glyphs, and focus on one thing. We need to focus on *the meaning of what is attempting to be modelled.*

Luckily, we’ve already covered 90% of it in the last three questions. All we need is one, minor, itsy, tweak. There’s a tiny bit of math in this post, but I’d encourage every single pixel f\*cker to struggle through it. Understanding this core bit of digestible math will greatly aid image making and understanding of subsequent posts. There are also plenty of images to help us along…

---

Enter stage right, our familiar Brother Red pixel at 50% sRGB red emission.

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-on-2.png?w=800)

**FIGURE BROTHER RED** The ever familiar Brother Red, emitting at 50% sRGB red.

Enter stage right, Sister Green pixel at 60% sRGB green emission.

![](https://hg2dc.com/wp-content/uploads/2021/12/add-in-green-pixel-2.png?w=800)

**FIGURE SISTER GREEN** The Sister Green pixel, emitting at 60% sRGB green.

To recap, let’s peek at their respective code values1 and the related display-referred emission strengths.

**BROTHER RED PIXEL**  
`DISPLAY ENCODED VALUE 0.73 -- EMISSION 0.50`  
**SISTER GREEN PIXEL**  
`DISPLAY ENCODED VALUE 0.79 -- EMISSION 0.60`

In regular image maker terms, the display encoded value for Brother Red is 73% of the entire display referred code value range, from 0% to 100%. We must *decode* the code value according to the *encoding’s* transfer function to arrive at the display light ratio. In doing so, we get 50% display light output.

For Sister Green, the display encoded value lands at 79% of the code value range, and when we decode the code value via the encoding’s transfer function, we get 60% display light output. Remember that the *encoded value* is not the actual display’s physical, radiometric light ratios directly, but holds an extremely important connection to them. It represents a ratio of the *total encoded values*, not the light ratio!

![](https://hg2dc.com/wp-content/uploads/2020/04/general-high-level-overview-2.png?w=580)

**FIGURE MAGIC DECODER RING** The transfer function is the glue that binds code values to radiometric linear light ratios.

So far, all is well and good. If any of what is expressed above is unclear, time travel back to [Question #20](https://hg2dc.com/question-20) and work back through the lower level concepts. If terms like [Question #6’s “*transfer function”*](https://hg2dc.com/question-6) or [Question #5’s discussion of “*encoded values”*](https://hg2dc.com/question-5) trips you up a bit, revisit those questions!

---

Just recently in [Question #23](https://hg2dc.com/question-23), we simulated moving Brother Red’s geometry down and over Sister Green’s window. Brother Red in that example could be thought of being some sort of crazy emitting space gas, and we can see right through him to Sister Green’s emission!

Relative to the display, Brother Red and Sister Green were combining their emissions in their overlapped geometry regions. Here’s the result as a refresher…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-moved-no-grid-1.png?w=800)

**FIGURE THE GASSES MIX** Here, the two geometries are akin to Brother Red being gaseous and permitting the light emissions to pass through from Sister Green.

---

But let’s imagine for a moment that Brother Red wasn’t something like a transparent and emissive space gas, and was instead akin to a fully opaque square with lights that emit 50% of the display’s total light range facing us. The “opaque square” here is fully blocking all light behind it. Think of it as a spaceship hull with space-tech illumination; the hull blocks what is behind it, but the surface of the hull emits light out of our displays.

That is, much like the gas, the region is *still* emitting light as when it was a gas, but in this case, Brother Red’s geometry is ***also*** blocking Sister Green’s geometry and emission! Another way of thinking about “blocking light” is *occluding*. And specifically here, Brother Red is occluding the light emission behind him not only in his own pixel window, but also over a portion of Sister Green’s window.

---

Let’s start by visualizing what our geometry and emissions look like.

![](https://hg2dc.com/wp-content/uploads/2021/12/red-over-green-moved-no-grid.png?w=800)

**FIGURE RED OVER GREEN** Here Brother Red is both emitting at 50% sRGB red intensity and fully occluding the small 30 unit portion of Sister Green’s window.

**FIGURE RED OVER GREEN** shows a zoomed in version of what Brother Red would look like if it were fully occluding a portion of Sister Green’s geometry and emission. That is, let’s take stock of what has *not* changed from our previous example:

-   Sister Green’s emission remains at 60% of the sRGB-like display’s linear light range.
-   Brother Red’s emission remains at 50% of the sRGB-like display’s linear light range.
-   Brother Red has moved precisely the same distance downward as in [Question #23](https://hg2dc.com/question-23), overlapping 30 units of Sister Green’s pixel window.

The sole difference here is that instead of Brother Red’s previous gaseous form permitting us to see *through* his unoccluding emission, we are modelling Brother Red’s geometry as though it is fully occluding Sister Green’s emission.

---

Let’s run the simple math that everyone is familiar with. First, let’s evaluate Brother Red and Sister Green’s geometry.

![](https://hg2dc.com/wp-content/uploads/2021/12/red-over-green-with-test-grid-on.png?w=800)

**FIGURE GEOMETRY VIEW** The above figure shows us the area of geometry that each pixel covers with respect to their pixel windows.

In order to calculate the final pixel window emissions, we will roll through the math using the geometry outlined in **FIGURE GEOMETRY VIEW** above, which is essentially identical to [the geometry math of Question #23](https://hg2dc.com/question-23).

---

Let’s start by assuming we are handed the *encoded* values, as outlined above, for the two initial pixels before the move. That is, if we start with Brother Red and Sister Green’s sRGB-like commodity display encoded values, we know that we need to get back to radiometric light quantities. How do we do that? The magic decoder ring of transfer functions!

Remember that we encode values for our specific display type, which has an output transfer function that is a pure power function of 2.21. So let’s take our encoded value and decode them to their meaningful radiometric display ratios of light.

**BROTHER RED’S CODE VALUE 0.73**  
`0.73^2.2 = 0.50 == 50% DISPLAY LINEAR LIGHT`  
**SISTER GREEN’S CODE VALUE 0.79**  
`0.79^2.2 == 0.60 == 60% DISPLAY LINEAR LIGHT`

That wasn’t so hard!

---

Now let’s calculate how much of the upper pixel window Brother Red remains in, and calculate the overall pixel window ratio. This is identical to what we have been doing in the previous three questions, and the answer remains the same!

Brother Red covers 70 units of the window, at 50% display linear light. We scale the overall light by the ratio to arrive at the final output value.

**BROTHER RED OVERALL EMISSION UPPER WINDOW**  
`0.70 * 0.50 = 0.35 == 35% DISPLAY LINEAR LIGHT`

And with that, the Upper Pixel Window is finished!

---

Let’s work through the Lower Pixel Window. The question we are asking is “How much of Sister Green’s emission remains in relation to her window after Brother Red’s occlusion?”

Let’s visualize the lower window with Sister Green at her 60% emission, with her window’s subpixels of emission “turned off” as though they were fully occluded or blocked individually by Brother Red’s geometry.

![](https://hg2dc.com/wp-content/uploads/2021/12/red-knocked-out-pixel-grid-on.png?w=800)

**FIGURE LIGHTS OUT EMISSION** Here we have scaled Sister Green’s emission by the degree of occlusion. That is, if her pixel is 100% occluded, exactly zero emission results.

Brother Red’s 100% occluding pixels, that cover 30% of Sister Green’s pixel window, leaves 70% of her geometry remaining with the emission turned on.

Again, a useful way to think about this is scaling of the light intensity. Here, if an object is fully occluding, it blocks 100% of the light behind it. That means that in terms of geometry, 0% remains. 0% of anything is zero, and as such, 0% of Sister Green’s geometry and emission remains. We could just as easily scaled her geometry by some other ratio, but for the sake of simplicity, we will leave that for now.

Note that we have *solely* focused on geometry here, and we have not considered emission. That’s an absolutely fundamental and crucial thing to pay attention to!

> Occlusion and emission are two individual facets of a pixel. It is entirely reasonable to occlude and not emit, and alternatively, to emit and not occlude.

You’ve read and re-read that pull quote above? Good. We will revisit it at the end.

---

With that out of the way, let’s focus on the emission levels. We know that Brother Red emits 50% of the total range of the display light. But his geometry is only covering 30% of that lower window. Total emission? Exactly the same as [in our previous Question #23](https://hg2dc.com/question-23)! When we consider his relative geometry, we end up scaling his emission accordingly.

**BROTHER RED’S EMISSION IN THE LOWER PIXEL WINDOW**  
`0.30 * 0.50 = 0.15 == 15%`

Sister Green’s emission? It is tied to her geometry of coverage.

Given that Brother Red fully occludes 30% of her window, only 70% of Sister Green’s window remains. Given her geometry has been effectively scaled down, we simply need to scale her emission now.

**SISTER GREEN’S EMISSION IN THE LOWER PIXEL WINDOW**  
`0.70 * 0.60 = 0.42 == 42%`

To get the total display linear light quantity, we add our channels together to give us the lower pixel window’s total emission`[0.15, 0.42, 0.00]` display referred, linear light ratios.

We know from our previous questions that to close the loop, we need to *re-encode* the display linear light to prepare it for the display to well… display.

To do so, we will use the inverse of our sRGB-like hardware’s transfer function. Remember, that’s the chips and or hardware that is deep within our the display hardware itself! For our examples, we’ve been using a simple 2.2 power function as the output transfer function, so the inverse is as below:

`0.15^(1.0/2.2) = 0.422 == 42.2%` ENCODING RANGE  
`0.42^(1.0/2.2) = 0.674 == 67.4%` ENCODING RANGE  
`0.00^(1.0/2.2) = 0.000 == 0.00%` ENCODING RANGE  
**FINAL ENCODED sRGB-LIKE PIXEL  
**`[0.422, 0.674, 0.000]`

And that looks like this in terms of the two pixel windows…

![](https://hg2dc.com/wp-content/uploads/2021/12/final-mixed-green-alpha-demo.png?w=800)

**FIGURE LITTLE LESS LITTLE MORE The upper red pixel is emitting a little less, and the lower green pixel now has a little more red emission, while having lost a little green due to the red pixel occluding the window a bit.**

---

***Answer #24: To move a pixel down and simulate blocking light, we consider the geometry and scale the background emission accordingly.***

But what about partially occluded pixels? What about how Digital Content Creation apps [are frequently screwing up our work as pointed out in Question #9](https://hg2dc.com/question-9)? And how come in the last post we were left with “discussing alpha” and the post doesn’t discuss “alpha”??!!1!?

Fair questions. Those will have to wait, but before we go, we need to hammer home something absolutely fundamental when discussing light and pixels and occlusions and all those bits of awesome light transport goodness…

---

In the faint distance, Sea Lions can be heard. “WeLl aCtuAlly thAt pOst iS wrOng bEcAusE occLusIon aNd emiSsIoN… aRf aRf… pRemULtipLIed… arf arf…”

Let’s revisit a critical statement…

> Occlusion and emission are two individual facets of a pixel. It is **entirely reasonable** to occlude and not emit, and alternatively, to emit and not occlude.

Those last five words tends to catch people out.

Let’s remember that in terms of our regular lives, plenty of things do not occlude and indeed emit. Everything from that CFL tube lamp that might be in your house, with emissive gasses, to the reflection of your coffee-needing face on the surface of your glass shower door, to an age old thing…

We won’t belabour the point, but simply take stock of the fact that our model of occlusion and emission are not entirely disconnected to models of how we consider our physical reality to work. The next time you look at that candle flame, that compact fluorescent gas based lamp, or even your reflection in your shower glass, bear in mind that they are only adding light, and not occluding! Conversely, it’s wise to think of a “black” pixel that moves over another pixel as occluding and not emitting.

Sorry for the delay, and the length, on this post. It was written and rewritten close to five times in an effort to distill the concepts down to the absolute minimum, without being overly-simplified and lose sight of those concepts. [Hopefully the next one won’t take quite as long…](https://hg2dc.com/question-25)

---

1 To stress, the Colour Component Transfer Function here corresponds to the output from the particular assumed display we are using. The colour-sciencey lingo for a display’s output is Electro-Optical Transfer Function, or EOTF. Note that every display may use a different specification EOTF! Also note that for a vast majority of “sRGB” displays, the hardware EOTF is *not* the specification’s sRGB EOTF, but rather a likely more inexpensive hardware based 2.2 power function. As such, the code values used here are *not* the canonized sRGB inverse EOTF encoding. They are representing a typical sRGB-like display. The article uses this simplified result for both accuracy of the common case, and clarity of the math. [This footnote is here to shut the WANKers up.](https://hg2dc.com/question-1)

