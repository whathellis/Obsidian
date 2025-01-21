---
URL: https://hg2dc.com/2019/07/21/question-9/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/07/1f911-1-skzxsakx8-7yv7zhufxog.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-09
duration: 6
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #9: Why the F*ck is Linear Light Important for a Digital Artist?

[In our last question, we took a quick dive into discussing what a particular type of linear, *display linear*, is related to.](https://hg2dc.com/question-8/) What we haven’t discussed yet, is why there has been all of this talk about linear in the first place. Why do linear versus nonlinear encodings matter if you’ve been happily painting in Photoshop or Affinity’s tools and not giving a crap about this rubbish? We’ll try to skip getting into the math and use a simple visual demonstration to hammer our point home.

So, let’s break the question out…

***Question #9: Why is linear light important?***

---

This answer will divide our audience into two unique groups. One group of you will have no real idea about linear light, and probably wonder why we’ve spent eight questions discussing displays and other garbage to get to a seemingly irrelevant question. If you are in the other group, you are probably thinking you’re already aware as to why using linear light RGB ratios is important, and hoping that we can move along faster.

As with all things pixels, a nuanced understanding will help you survive the onslaught of stupidity online. The details will help you understand the depth behind some trite video from some YouTube influencer, or some other equally hastily assembled and ridiculous content from some “cinematographer” or “photographer”. We aren’t here to make money from views, clicks, and likes, so we can afford to dig a little deeper.

Seeing is believing. I present a simple red star against a cyan background¹…

---

![](https://hg2dc.com/wp-content/uploads/2019/07/7ddfb-1w8euq4rpume8zb7-61qytg.png)

Keen observers will see something very peculiar near the slanting edges that will become more obvious down below…

So what’s wrong here? Anything? Can you spot it?

Let’s make it more apparent. Let’s blur our star a little bit…

![](https://hg2dc.com/wp-content/uploads/2019/07/1f911-1-skzxsakx8-7yv7zhufxog.png)

There, that’s better… or not…

At this point it doesn’t take a Frida Kahlo or Emily Carr to figure out something looks whacked. Most pixel pushers sense something is off, yet may have lacked the confidence to say that their beloved 1000$ DCC applications might be doing something wrong. After all, the software has the “experts” working on it, right?

The answer of course is the dark fringe. That dark fringe is present when compositing an element over another element using a broken internal model. In this case, the red star is composited over the cyan background². But what should it look like if composited³ “correctly”?

![](https://hg2dc.com/wp-content/uploads/2019/07/611cb-1_lmrsei1e8vzl5iqahnsbq.png)

That’s better…

There we go. That’s better! No hyper-darkened fringe. So why is this second image more “correct” and what is your DCC application doing when you see the fringe versus not seeing the fringe? Better still, this example makes it painfully clear that we are discussing something with a tremendous impact on our work, not something trivial that can be overlooked.

---

We are nearing the end of our allocated time, so we’ll answer the question:

***Answer #9:*** [***Linear light transport***](https://en.wikipedia.org/wiki/Linear_transport_theory) ***is crucially important in all DCC pixel compositing math because the RGB code values always represent light, and if the code values aren’t properly converted to light ratios, bad, awful, no-good math*** ***results. RGB code values always represent light emissions.***

Blending, smudging, generic painting, compositing, blurring, and any other operation where pixels are being manipulated absolutely **must** be performed upon RGB values that maintain a [radiometric linear light transport model set of ratios](http://cie.co.at/eilvterm/17-21-038) if we hope to have it model / emulate the experiential learned “correct” results from our physical reality around us.

In the case of the above, the upper star image with a fringe applies the simple math upon nonlinear light code values, while the second image without the fringe had the *exact same* math applied with linear light code values, and then nonlinearly encoded for the display in question. In the former, we have broken internal representation which yields the alien-looking fringe, while in the latter the linear light code values more greatly emulate the physically plausible model we are familiar with seeing. Believe it or not, the implications are present even in the first image. If you look closely at the first image, you’ll see that along the edges of the unblurred star, you can see that over-darkening happening even there were the edge pixels in the [antialiasing](https://en.wikipedia.org/wiki/Spatial_anti-aliasing) reveals the broken calculations.

---

“My DCC didn’t show the fringed star! I’m fine!” or “Using Photoshop’s ‘linear blend’ mode solves this! I’m good!” is typical at this point, yet it only scratches the surface. Even if your DCC applicaiton didn’t sh\*t the bed and you see something akin to the second image, I assure you that this wasn’t the case until more or less recently, and even then plenty of folks didn’t understand when or why or how it was applicable.

Your particular DCC application may of course break your image using some of its tools, and try to be galaxy brain genius level software in others carefully coddling *you*, the person who needs to understand *what* is going on, from understanding *what* is going on.

In all instances it can be stated with almost certainty, that mainstream DCC applications mangle this up all over their pipeline, and its up to the pixel pusher to sharpen their knowledge to be able to diagnose and test just how badly their DCC is potentially breaking their work.

---

We have started to scratch beneath the surface of transfer functions a bit and have peeked into some of the implications of using those nonlinear code values in the pixel manipulation math. Are there other transfer functions for different encodings? How can we know what our images are encoded with? What transfer function is a tool like Photoshop assuming under the hood, and are there issues with using incorrect transfer functions? Are there other types of “linear” that we need to explore? Is your random piece of “smart software” making meatheaded assumptions about the encoding of your image values quietly breaking the work you’ve just hammered on for the past week? [Great questions that will have to wait…](https://hg2dc.com/question-10/)

We will end this post with a simple guiding rule of thumb: ***If you are manipulating pixels, a linear light transport model inside your software is absolutely crucial. Always.***

---

¹ The astute observer may have noticed that the subpixels along the angled edges of the star exhibit the same incorrect nonlinear compositing problems.

² To the folks reading this series, it’s more precise to suggest that we are mixing a full intensity REC.709 red star over a full intensity REC.709 cyan background. And again, while a good number of us are looking at an sRGB display, the actual light chromaticities are defined in the REC.709 specification, and reiterated in the sRGB specification.

³ Don’t let the word “composited” scare you if it seems alien. In our example here, it’s a simple “over” in the [Porter Duff sense](https://keithp.com/~keithp/porterduff/p253-porter.pdf). You can achieve this via “layers” if your DCC application has them, or use a merge / alpha over node if you are using a nodal based compositor.

