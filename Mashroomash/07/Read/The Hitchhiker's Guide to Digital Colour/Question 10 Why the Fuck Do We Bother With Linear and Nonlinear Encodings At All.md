---
URL: https://hg2dc.com/2019/07/29/question-10/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/07/0d55d-1gzfawarouivsxf25actgsa.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-10
duration: 9
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #10: Why the F*ck Do We Bother With Linear and Nonlinear Encodings At All?

Hard to believe we’ve hit Question #10. Hopefully you are all finding the series useful. Nothing is more valuable than you reading these posts and leaving comments and suggestions via email, DM, or even here.

A brief recap of salient details:

-   In [our previous article Question #9](https://hg2dc.com/question-9/), we’ve discovered that whenever we are manipulating pixels such as via a blur, rotation, smudge, blend, etc. it’s necessary to emulate physical light transport ratios within our internal DCC application models. Specifically, we identified that when we use nonlinear light intensity code values, the output of light transport math results in horrifically broken garbage.
-   We learned in [Question #6](https://hg2dc.com/question-6/) that a display referred transfer function defines how our code values are mapped with respect to the ratio of linear light emitted from a display. In the case of sRGB and common displays, that’s a *relative* ratio measurement, existing as a quantity of light in relation to a maximum and minimum light output. And of course, after the display decodes the code values it is sent, it emits linear light, served up and ready for our perceptual systems to ingest and bend and warp and mangle and turn into magic psychophysical “sight”.

---

When CRT displays roamed the earth, there was a nonlinear relationship between code values and the ratio of linear light output from the CRT display. Inside the CRT, electricity moved through the dark and mysterious box and projected a beam of energy onto the phosphors on the glass of the screen which excited them into emission. [Input nonlinear code values to our computer, the computer pushed those code out as a signal, and the signal is “undone” by the CRT back into linear light ratios](https://poynton.ca/PDFs/SMPTE93_Gamma.pdf)¹. It was due to the hardware construction of the CRT that a nonlinear transfer function existed between the code values sent to the display and the ratio of linear light excitation of the phosphors.²

Fast forward to contemporary LED and LED-like displays, and that nonlinear disconnect no longer needs to exist at the lower hardware level. Want to increase or decrease the light coming out of one of your Light Emitting Diodes? Increase or decrease the current by roughly the same ratio that you desire the light ratio to be. Want to double the radiometric quantity of photons coming out of the display? Double the current. Decrease it by half? Halve the current. Quarter? Quarter the current. For our purposely and grotesquely overly simplified understanding, we can say that the current to light emission output is, in a contemporary display, mostly linear-like as well. Yet this isn’t how contemporary LED displays behave!

In both the CRT and modern LED case, the key takeaway here is that our displays are *always outputting linear light ratios*. Historically, we sent nonlinear signals to our displays due to the display CRT hardware, and, despite not being fundamental to the hardware of LED displays, that tradition continues to today.

However, you might be wondering something. Let’s list our facts:

-   The output of our displays is always a linear light based ratio
-   A contemporary Digital Content Creation application must use linear light transport models to get “correct” results in modern image manipulation work
-   Modern displays are more or less linear with regards to the current input and light output

It would seem that we have arrived at a fitting question…

***Question #10: If everything in a modern Digital Content Creation application behaves more closely to “what we expect as correct” under a linear light model and our displays output linear light, why do we bother with nonlinear transfer functions to encode our RGB code values at all?***

Great question! And of course… it’s a nuanced answer…

---

If you’ve crawled around online, you’ve probably run into more than a huge amount of misinformation about how our perceptual systems are nonlinear and that *that is the reason* why we need to convert our RGB imagery into nonlinear encodings. Yes, this is all complete and utter bullsh\*t; **our perceptual systems don’t need some idiot piece of software to encode nonlinear signals**.

The meatballs forwarding that sort of garbage didn’t stop for a second and ask themselves that, if we need the display to magically bend linear light code values to a nonlinear encoding to support our million-year-old perceptual systems, why don’t we require some sort of magical goggles to do this for us when we look out a window? Alas, here we are, capable of looking outside of a window perfectly fine without our Meatball-Idiot-Filter-Out-The-Reality-Through-Magic-Goggle devices…

Let’s give a quick outline as to what we know, and we’ll use an image because well… no one has the time to read anymore, and article posts have more clicks when there are images.

![](https://hg2dc.com/wp-content/uploads/2019/07/acbf6-1z6jto3wx-94lr0zoicgoua.png)

Loose Overview of the Transforms Between Linear and Nonlinear Encodings

The first step is our scene, which is of course encoded with linear light. In the second step, we transform the scene to a nonlinear RGB encoding³ via a series of transfer functions in preparation for a particular display type. From there, the hardware in the display *undoes* the nonlinear encoding of the RGB code values via the display’s output transfer function and converts *that* result into linear light. From there, the linear light ratios are handed off to our perceptual system, which expects linear light ratios to function properly⁴. And the crazy nonlinearities begin inside our perceptual system…

The obvious question is “Why not just cut out the second step where we nonlinearly encode the scene and use linear light code values the whole way?” We have already established that the math works vastly better on linear light code values, so why not just keep the entire chain linear light?

---

![](https://hg2dc.com/wp-content/uploads/2019/07/df856-1jvbxoofk5kol2v7hxhrxhw.png)

Linear light as compared to our nonlinear internal processing of the linear light

The above image shows a loose idea as to what happens if we uniformly divided up the linear light representation of a given scene / image into increments and mapped what those increments to what we end up using / seeing from *inside* our adapted perceptual systems. That is, plenty of the arrows end up stacking up on the right side; our perceptual systems internally bend the received linear light into a nonlinear representation, [as we hinted at in Question #7](https://hg2dc.com/question-7/). Our perceptual systems sort of have a built-in transfer function too!

If we used a linear light encoding as a transfer function, plenty of those values would be “wasted” in the final product; our perceptual system wouldn’t bother to differentiate between some of the values, and we’d barely be able to see the differences, if at all, in some of the range of the values. Plenty of the linear light values towards the right side of our measurements would end up collapsed into an identical looking perceptual system experience. While the image would display perfectly fine on our mythical linear light display, the additional code values might as well not be there if the intention is to *optimize* the encoding!

Instead, what would happen if we used a series of code values that was optimized for the important values our perceptual system will end up “seeing”? What if we exploited the nonlinearities of our complex perceptual systems to *compress* the data range by throwing out certain “redundant” code values from the linear light representation?

![](https://hg2dc.com/wp-content/uploads/2019/07/0d55d-1gzfawarouivsxf25actgsa.png)

Note the position of the two transfer functions in the code value to display pipeline

So we’ve done a bunch of work and effort, but we haven’t changed much from the input linear light to the output. Or have we?

---

[Back at Question #7](https://hg2dc.com/question-7/) we hinted that transfer functions play a crucial role in the lives of digital artists. As many of you might have inferred, there are many types of transfer functions that facilitate different needs. As we drill down into the meat and bones of digital RGB colour, we can see that when it comes to displays and certain RGB encodings, some transfer functions are directly related to how a display expects data to be encoded; the transfer functions describe the characteristics of the light emission from code values. sRGB is one such display referred encoding, and indeed the transfer function we encode the RGB values with is the transfer function that an ideal sRGB display uses to decode the values back to linear light ratios. And that leads us to the answer of our question:

***Answer #9: Using a transfer function to nonlinearly encode data in accordance with a display referred output is nothing more than a compression scheme; it removes code values from the range of values that are redundant for our perceptual systems.***

If we devised a DCC application and display hardware pipeline with purely linear code values from manipulation to linear light output ratios at the display, we’d be wasting bits at the end of the pipeline that our perceptual systems wouldn’t “see”. That website you designed would be gobbling up around 25% more bits, and gobbling up bandwidth when saved on disk or being shipped out over the internet. As a compression scheme, nonlinear encodings can be tremendously efficient, with a reasonable degree of trade-off for loss of data. Indeed, the secret of transfer functions unlocks how higher end industrial motion picture cameras manage to cram the scene’s light ratios into a smaller parcel efficiently!

---

The next time you look at an RGB image, it has hopefully become clear that the contemporary digital artist should be aware of it’s particular encoding. What transfer function does it use? If you want to have the goodness of linear light manipulations, or even simply send it out to a display as you intended your work to be seen, it’s imperative that the image is encoded in such a way that the display’s hardware or software based transfer function will decode it correctly. Only with the proper encoding will the correct ratios of linear light be output for the audience on their intended display. If your encoding doesn’t properly match the context, you can expect contrast or other things to be completely off in one case, and your entire chain of manipulations off in another.

Digging more deeply into that however, [will have to wait for a few more questions…](https://hg2dc.com/question-11/)

---

¹ As with all things colour and transfer functions, I’ve linked you to none other than Dr. Charles Poynton’s article, which as a nice little blurb on the transformation of electricity into light near the end of the PDF. I’d also like to take this moment to give a shoutout to Dr. Poynton, who has always managed to find time to answer this rando idiot’s questions about the peculiarities of digital signals and other such dark and arcane things. There are other luminaries who we will come across, and Dr. Poynton is indeed one of the deities in the Colour Pantheon.

² The important part of the nonlinear response of a CRT was due to the control grid. Historically, it happened that the nonlinear code values supplied “just worked”, and were a useful feature that ties in with the answer to this post.

³ The reader who has spotted that the heading reads “Nonlinear Transfer Functions” in the plural form will be rewarded in the future. This wasn’t a mistake, and you get a cookie for spotting it.

⁴ Labelling our perceptual system as requiring a “Linear Light Transfer Function” isn’t exactly the most biologically terrific description, but hopefully reusing the concept around transfer functions can help you grasp the nature of the ratios more clearly; our perceptual system only works with linear light, even if it internally interprets and bends that linear light into something more useful for our perceptual systems.

