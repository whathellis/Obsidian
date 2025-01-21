---
URL: https://hg2dc.com/2019/05/28/question-6/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/05/e3524-1k29kohmsu2v8myc6aocksw.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-04
duration: 8
topics: 
done: false
cover: 
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
word-goal: 2500
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Question #6: What the F*ck is a Transfer Function?

Description:: Whoa. There’s a term that you probably haven’t bumped into before, eh? You’ve been pushing pixels for how long, and some bozo tosses a made-up term at you? You might even start to believe that this rubbish series of posts that promised to inform has cheated you, and instead just keeps looping back to the crap you don’t know.

First up, take heed reader… we are at least identifying the things that we don’t know. As it turns out, much of the problems with understanding digital colour comes from understanding that our knowledge stands *relative* to something. That is, when we first removed the rusty old boat that was covering the stinky well, and asked “[What the f\*ck happens when we change an RGB slider value?](https://hg2dc.com/question-1/)”, we discovered that we were detached from what the value *referred* to. What did it *control*? So sit down, buckle up, and prepare to hear *referred* quite a bit more in the coming inquiries…

---

Having read through the past five questions, you are likely starting to draw a connection between the code values and some device or some model. That is, up to now, we have discussed maximum intensity versus minimum intensity, but not yet described the device they are referring to. [We somewhat superficially learned that the colours of the lights in a typical display are described by the sRGB specification](https://hg2dc.com/question-4/), but we haven’t gone much further than that.

While we are starting to define a useful model here, we still can’t drill down into the bedrock and answer hard questions like “What does a code value of 1.0 mean?” until we more deeply consider the thing we are connected to. That is, a code value as we’ve hammered repeatedly, needs decoding to give those three teeny RGB flashlights in our pixels meaning. How do we decode it though?

---

To give our code values meaning, we are going to hook them up to a display device. We’ll use the bog standard display device known as an sRGB display. What is an sRGB display? [We again touched on a teeny component of this in Question 4](https://hg2dc.com/question-4/), but it’s not good enough to dive deeper…

Somewhere in a galaxy far, far away around 1996, a group of folks gathered together and [designed a specification that describes an imaginary device](https://webstore.iec.ch/publication/6169). Henceforth, vendors went about and constructed a real device from said imaginary device’s specification blueprint.

Take the device home, plug it into a computer, send some code values to it, and hopefully it will behave as that device specification outlined. Whether you realized it or not, and [as we touched upon in Question #3](https://hg2dc.com/question-3/), the display you are on has a high probability to be designed to the sRGB standard.¹

Looping back, we take that encoded value, run it through our computer and out to the display, and the display takes the code value and turns it into light. This leads us to our wonderful question number six, which is…

***Question #6: What exactly is a transfer function and why is it important?***

---

So what happens when we wrap up a code value and send it to our brand new sRGB display? If we send a code value of `[1.0, 1.0, 1.0]`, do we have any idea how much light is coming out? *That question*, wise reader, is exactly what a transfer function helps to answer. It’s the peanut butter and jam between the slices of code value and decoded value bread.

So what does `1.0` spit out in terms of light?

“Maximum” you say, gleefully aware of what we’ve discovered. You’d be correct. But can we quantify how much light should come out of one of our RGB lights? The answer is yes, but we would need some metric. While there are quite a few of them out there, the one chosen by the standard is known as [a candela per square metre](http://cie.co.at/eilvterm/17-21-086)². You may have heard it before, as some folks call it, somewhat colloquially, a *nit*.

If you had the sRGB specification in front of you, you’d see that ideally, in a reference display, the output from an sRGB display is 80 nits. But let’s focus on our question, which is sorting out specifically what a transfer function is…

---

Given we know that we have a code value of `1.0`, and knowing that we are sending that code value to our display, we can also have faith that the display is *decoding* that code value according to the specification. You’ve probably already guessed that if our maximum code value is `1.0`, and that our maximum idealized nit output of our sRGB display is 80 nits… that yes… we’d get out 80 nits worth of intensity if all three channels were set to maximum! Whatever a nit is…

This is great. Off to digital painting you go, freshly armed with your new knowledge that there is an actual way to calculate light output from your strange code value. But uh… let’s take a moment to ponder other values. What about `0.5`? Seems innocuous enough right? I mean it’s 50%… of our sRGB display’s pixel channel intensity… erm… is that… physical energy as in 50% of our maximum 80 nits… or is it uh… something… else?

And now for a preemptive nuclear strike on the WANKS³…

“I ALREADY KNOW THIS SH\*T!!!11!! IT’S GAMMA!!1!!” I hate to break it to you my dear Sealioning WANK, but that’s only going to lead you down the path of pain if you discard what you can learn from transfer functions under an umbrella of “gamma”⁴. For everyone else, and maybe even one of the WANKs who has crossed over to being a normal human being… onto that answer…

***Answer #6: A transfer function is a math formula that describes how a code value relates to light energy input or output.***

---

Wow if that isn’t too vague, eh?

See how I said “math formula” and not some perceptual mumbo jumbo? Note how I also didn’t say the godforsaken dumpster fire of a term “gamma”? There’s good reason for this. For now, let’s realize we’ve learned a new term, and we will use it henceforth. Rejoice, and say the words [*colour component transfer function*](http://cie.co.at/eilvterm/17-32-004) or again, simply *transfer function*, with me.

I gave you a loose term, that isn’t entirely clear, that describes output *and* input, yet we are talking about displays. I apologize. I did that in the interest of the future, however! “But what about the sixteen times you’ve asked what a code value is and then ask another damn question? What about `0.5` dammit? EXPLAIN SOMETHING, WILL YOU?!!?”

We are getting there, but sadly, we also have to keep these posts brief in this Attention Economy, so go grab a cup of covfefe and relax for a bit [until that next question…](https://hg2dc.com/question-7/)

---

¹ If you happen to be on a MacBook Pro from 2016 onwards, an iMac with a Retina 5k display from the latter half of 2015 onwards, an iMac Pro, or any of the many wider gamut Eizos and other displays, your lights are actually a different colour. For now, we will ignore this facet and try to bolt down the foundational concepts.

² Sorry Team USA, the rest of the world is on the metric system. No, really. Here’s a useful map of all of the folks, shown here in red, using that other system…

![](https://hg2dc.com/wp-content/uploads/2019/05/46b19-0ivg0ehphexag_z2n.jpg)

³ See [footnote 2 in the first question](https://hg2dc.com/question-1/).

⁴ If you had the sRGB specification sitting in front of you, you’d open it up to plenty of math and strange terms. Those math and strange terms though, help to describe how the device in question operates. On some level, that includes some absolute metrics and models, one of which we learned above, known as a *candela per square meter*, or *nit*. It also describes two formulas for getting to and from sRGB code values. Those functions are typically called *transfer functions*.

“Aha!” you might say, “That’s GAMMA!!!!111!!!” Well I have some bad news for the you. The actual standard has a little note in it. The little note reads:

> 1) The term “gamma” is not used in this standard for the reasons discussed in annex A.

If we flip to annex A, we find this extremely wise bit of text:

> Annex A  
> (informative)

> Ambiguity in the definition of the term “gamma”

> Historically, both the photographic and television industries claim integral use of the term “gamma” for different effects. Hurter and Driffield first used the term in the 1890s in describing the straight-line portion of the density versus log exposure curves that describe photographic sensitometry. The photographic sensitometry field has used several interrelated terms to describe similar effects, including gamma, slope, gradient, and contrast. Both Languimier in the 1910s and Oliver in the 1940s defined “gamma” for the television industry (and thus the computer graphics industry) as the exponential value in both simple and complex power functions that describe the relationship between gun voltage and intensity (or luminance). In fact, even within the television industry, there are multiple, conflicting definitions of “gamma”. These include differences in describing physical aspects (such as gun “gamma” and phosphor “gamma”). These also include differences in equations for the same physical aspect (there are currently at least three commonly used equations in the computer graphics industry to describe the relationship between gun voltage and intensity, all of which provide significantly different results). After significant insightful feedback from many industries, this standard has explicitly chosen to avoid the use of the term “gamma”. Furthermore, it appears that the usefulness of the term in unambiguous, constructive standard terminology is zero and its continued use is detrimental to consistent cross-reference between standards and unambiguous communication.

That’s right folks… the sRGB standard, way, way, way back in 1999, chose to drop the awful term “gamma”, for good reason. It’s a piece of junk term that is sufficiently overloaded to mean close to nothing when we are trying to discuss digital colour on a technical level such as these postings. Worse, when you utter it as an incantation, all sorts of drooling meatheads come out of the woodwork and start sealioning bullshit at you. You’d be wise to skip the term, and stick to the one outlined in the many specifications that define the very things digital artists use on a daily basis. To the Sealions? F\*ck off.

*Friends don’t let friends say “gamma.”*

