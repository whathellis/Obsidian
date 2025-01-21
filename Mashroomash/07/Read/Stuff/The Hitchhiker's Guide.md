---
URL: https://hg2dc.com/2024/07/25/question-33/
thumbnail: https://hg2dc.com/wp-content/uploads/2024/07/gamut-expansion-high-articulation-1.jpg
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:32:50
duration: 9
topics:
  - "[[Color Management|Color Management]]"
done: false
cover: ""
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
!
# Question #1: What the F\*ck Happens When We Change an RGB Slider Value?

(Description:: For reasons that are still somewhat alien and strange to me, I get weekly emails reaching out from digital image makers in smaller studios to independent one-person-army types. Every single post is unique, yet at their core, the foundational concepts remain extremely similar. *“What the hell can I do to fix my pixel pushing in Random Digital Content Creation Application.”* I try my best to give a leg up and help out the folks asking to the best of my abilities. Frequently, I’m looping over a path that I’ve slowly refined over the years.)

This post is essentially a means for me to link to and avoid copy pasting over and over again. I’m not going to make any grandiose claims or promises that there will even be a follow up post. Take from it what you will. Every entry is an attempt at a simple, short, and concise question.

As of writing, I can think of no better entry point to pixel pusher clarity than what I’m going to present in this post. I hope you find it as fascinating as I have…

---

Pushing pixels for anyone who has done it for any length of time appears to be such a mundane concept that discussing sliders isn’t even worth bothering with. Pick a colour, slap it down. It’s sadly so mundane that many seasoned veterans haven’t bothered to stop to ask themselves just what the hell is going on at the simplest level. Nevertheless, the following is the most informative entry point question I’ve arrived at:

**Question #1: What the hell happens when you slide or adjust one of the RGB values in your favourite digital content creation painting application?**

For those of you who can’t answer it clearly, and become somewhat shocked at how nebulous and slippery developing an answer seems, congratulations! The question is designed to not only reveal one of those hidden blind spots in your vision, but also to fork off into the crucial concepts behind colour for you as a pixel pusher.

Any ideas? Take your time, or better still, crack open your favourite DCC and give those sliders a whirl with the question firmly in front of you. I’ll wait…

---

Welcome back.

If you thought a bit about the answer, or perhaps even mucked about with a colour picker for a while, and arrived at the correct solution, congratulations, you are in a minority! I’ve posed that question to over a hundred well-seasoned, veteran image makers, and the response is always the same; one part confusion, one part surprise, and one part curiosity.

*“It makes the colour redder.”*
*“It makes the colour less greeny.”*
*“It changes the colour to make it different.”*

All of which are of course descriptive effects of the answer here, but none of which describe what is the affecting force. The answer is that, when you are picking a colour in a majority of DCCs, you are doing precisely one thing and one thing only. I’m going to make a bit of an oversimplification for some edge case readers here and provide you a working answer that *hopefully* makes clear sense for the intended audience[[The Hitchhiker's Guide#^24f5b6|1]]. ^385914

**Answer #1: You are increasing or decreasing the emission intensity of one of the three RGB lights.**

How simple was that?

If we are sliding a slider in Photoshop or Procreate or any of the other popular mainstream DCCs, we are connecting the slider up to the little diodes in our display[[The Hitchhiker's Guide#^7ffa09|2]]. ^6a601b

As you are already likely well aware, most displays are composed of an array of pixels, which in turn are composed of a series of three extremely small lights of three particular colours, or RGB *primaries*. We so frequently refer to the RGB model that we sometimes forget that there are three physical little lights per pixel in our displays that are increasing or decreasing in emission strength. 

When a slider is increased, it increases the intensity of the given channel based on a ratio. That is, if we slide the green slider upwards, we are increasing the quantity of the light emitted from the little green diode in the pixel(s) in question toward the maximum intensity output of the little green diode. This leads us to [[The Hitchhiker's Guide#Question 2 What the F *ck Does 0.6 Mean?|our next crucial question…]]

---

1.  It should be made clear that this short post is for anyone who has ever had to push a pixel around on a computer in their life and experience nausea when someone utters the words Colour Management openly. This isn’t a f\*cking article about Colour Management per se. It’s about colour, and more specifically at times, RGB, for the poor pixel crafters out there who quietly want some clarity in their work. If [Leonardo Da F\*cking Vinci can cut apart cadavers to hone his craft](https://www.telegraph.co.uk/culture/art/leonardo-da-vinci/10202124/Leonardo-da-Vinci-Anatomy-of-an-artist.html), it seems reasonable that someone getting paid to push pixels around should be able to cultivate a sense of pride in their craft enough to research and understand just what the hell they are doing. This site is for them, and not the ever wise group of folks I typically discuss and bicker about colour with. If you are pushing pixels around for free, self inflicting a horrible sense of imposter syndrome on some personal project, this series is perhaps even *more* for you…[[The Hitchhiker's Guide#^385914|↩︎]] ^24f5b6

2.  For those of you wise ass *“Well actually…”* Number Kids (WANKs henceforth) that want to dissect what is happening in the reference space versus what is output to the display, and the role of a colour management system, and the potential for gamut mapping transformations and the… just shut the f\*ck up and sit down for a moment. You are part of the problem. You aren’t helping the intended audience of this piece by diving so f\*cking deep so quickly that you are drowning them. [[The Hitchhiker's Guide#^6a601b|↩︎]] ^7ffa09


 
# Question #2: What the F\*ck Does 0.6 Mean?

As we learned through our [[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|entry question #1]], changing the value of an RGB slider changes the intensity of light emitted from a single channel of our display. Depending on your DCC of choice, you might see a range of values change from some small value to some larger value. Sometimes, instead of a legible value such as `0.6`, you may see goofy looking values such as `121` or even more confusing cryptic looking codes such as `0x1A`.

This is a nice little segue right into our foundational concept number two, and it too is a nice tidy question…

**Question #2: What does** `0.6` **represent in a typical DCC context?**

Ponder on it a little bit, as it’s another one of those so-obvious-that-most-folks-haven’t-thought-about-it sorts of questions. What is the something that `0.6` is part of? Why do some of our graphics friends use other representation systems? I’ll see you when you come back…

---

As you have probably realized, seeing the value `0.6` is a rather less tricky question than pondering what `153` means, or the more ridiculous and bats\*it stupid value `0x99`. Decimals are a sane way to begin our deeper dives into RGB colour. The refreshingly good news is that the last two absurd representations are in fact synonymous with the more legible `0.6` above. The better news is that after this post you won’t have to suffer listening to the crazies who insist on using the latter two awful formats, because you’ll know they don’t carry any more magical meaning than the entirely comprehensible decimal approach.

---

The first thing we need to understand is that, crucially, `0.6` is not a universally meaningful value with some sort of absolute attached meaning. In fact, it’s *absolutely meaningless* in the bigger picture, and is wise to think of it as a *code value*; it is an *encoded value* that requires *decoding*. Before we can fully comprehend how to decode the code values, we need to backtrack a little and realize that in most DCC applications, `0.6` represents a value within a *range of values*. That is, just like your basic understanding of percentages, it’s nothing more than a ratio, and that ratio specifically relates to our first answer regarding the intensity of light output.

**Answer #2: In an RGB DCC application,** `0.6` **is a ratio between a minimum and maximum, representing some ratio of light intensity.**

You might be wondering why I said *some* in the above statement and just what that *some* is. You’ll have to wait a few more questions before we can answer that question with a degree of authority.

At this point though, it is worth noting how `0.6` holds a synonymous meaning with the idiot-inducing value `153` or the other circle-jerk value `0x99`. To understand that, it requires focusing on a small, itsy bit about representing values in our computing devices. If you are already way ahead of this teeny dive and know where it is going, feel free to skip it. If the values are a bit head-scratchy for you, read on…

---

At risk of boring the hell out of you, computers are pretty low tech calculators. You are probably well aware that computers process based on low level electronic toggles known as bits. If we had a single bit, we could create meaning for the bit by assigning it context. The bit could represent up or down, on or off, yes or no, yin or yang, apple or orange, or whatever meaning we choose to assign to it.

If we were fleshing out an RGB model, we could say a single bit of information has a range of 2¹, or two, positions just like a coin. That means we could assign the *meaning* of those positions to represent the states of our little lights in our little pixels as being either on or off, or minimum and maximum. If we add a single bit of information, we have 2² positions, or four [[The Hitchhiker's Guide#^322857|1]]! That might mean minimum, maximum, and two values in between. Carry on with this, and we hit the magic number eight, which for reasons I won’t go into here, is an historical quantity of information “steps” that we have used to represent colour for a long while. It’s a boring historical romp into computer colour for those who want to dive deeper. ^d1888b

Why is eight bit relevant here? Eight bit gives rise to the two latter *encodings* we see above. That is, value `153` and the ridiculous `0x99` are nerdy computer methods of describing the much more legible value `0.6`. At eight bits, we can encode a total of `256` unique combinations. If we were to go a step further in refining the meaning of those combinations, we could interpret them as whole-numbers, or in nerdy-speak *integers*. Under such an interpretation, the values could be thought of as simply a number of steps from the first combination to the last, which would be from `0` to `255`. So what then, is `153/255`? You guessed it! `0.6`! And if we go down the gobbly gook hole of computer history, we discover that `0x99` is *hexadecimal* for the integer whole-number value `153`, which again, is nothing more than a fractional representation of the maximum value, or more simply, the decimal value `0.6`. Seems like a lot of work to make `0.6` *less* legible, agree?[[The Hitchhiker's Guide#^766fc5|2]] ^aeea29

Thankfully, I’ll keep the cryptic WANKer speak to a minimum, and try to refer to the more sane decimal representation where possible.

---

Given we know that RGB sliders impact the intensity of emission of the lower level reddish, greenish, and blueish lights that compose a single pixel, we now can concretely cut through the bulls\*it of the various representations of code values. `0.6` represents a ratio along the way from minimum to maximum. We know it is somehow tied to the lights in our display, but sadly, we aren’t much better off than when we started. What the hell is it `0.6`, or 60%, *of* exactly? Better, if we set it to 100%, does the colour change from when we had the light set at 60%? That seems like [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|a pretty darn good next question…]]

---

1. A simple way to understand the basic math is to think in terms of coins. A single coin has a number of sides (2), and the number of coins gives us the exponent. If we had 6 coins, the total number of unique positions if we laid them out on a table would be 2⁶, or 64 unique combinations. [[The Hitchhiker's Guide#^d1888b|↩︎]]
 ^322857

2. I have some bad news for you WANKs who think you are doing the world a wonderful service by confusing the hell out of everyone using eight bit code values `153` or the ever more super-secret-I-know-what-I-am-doing-and-you-don’t cryptic value `0x99`; you haven’t added any meaning. No really, you haven’t. Feel free to head home with your lunch box and tell your mom I insulted you. To everyone else, let’s wrap this nightmare of nerd-speak up and forge ahead to the next question.[[The Hitchhiker's Guide#^aeea29|↩︎]] ^766fc5



 
# Question #3: Does the F\*cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?

With the first couple of questions out of the way, we have a concrete, albeit simplified, understanding as to what happens in most DCC painting applications when [[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|we change an RGB slider value]]; we are changing the intensity of some colour of light along some undisclosed measurement system. It’s useful to think about the possible implications for an imager working in a DCC now that they have a firm idea that they are rendering light emissions on a display.

Trying to stick to the most simplistic core concepts, we will occasionally need to use some useful terms to keep ourselves on the same proverbial page[[The Hitchhiker's Guide#^a2c26c|1]]. As mentioned before, an additive RGB light colour encoding model consists of three RGB *primaries*, and we will try to use that term going forward. As we discovered in the previous question, we change the ratios of intensities of the light emission when we change the values in a typical DCC application. But what about the actual colour, or in fancy pants colour science-y terms, *chromaticity*, that results from the changing our values? Specifically, we need to answer one important question… ^8abab8

**Question #3: Does changing the intensity of a single RGB light change its colour?**

Once again, I highly encourage you to muck about in your favourite DCC application to hammer the ideas home. Set your colour to something like `[0.0, 1.0, 0.0]`, `[0.0, 0.75, 0.0]`, and another to `[0.0, 0.5, 0.0]`. Do the three greenish looking colours appear to change colour?

![](https://hg2dc.com/wp-content/uploads/2019/03/28569-1v-ocykmreavtnivc6cxrnw.png)

The green light emission at 100, 75, and 50%

---

As you may or may not have realized, changing a single channel in an RGB encoding model changes one thing and one thing only.

**Answer #3: Changing the intensity of a single RGB channel will only change the quantity of light emitted from that channel, not the underlying “colour”, or chromaticity, of the primary light in question.**[[The Hitchhiker's Guide#^5802ad|2]] ^0d90f2

That is, if we take a series of values such as `[0.0, 1.0, 0.0]`, `[0.0, 0.75, 0.0]`, `[0.0, 0.5, 0.0]`, and even `[0.0, 0.0000001, 0.0]`, they all will be the exact same greenish colour[[The Hitchhiker's Guide#^f4b896|3]], at different intensities of emission. Again, in colour science terms, we can say that in an ideal scenario, the chromaticity of the primaries never changes, only their respective individual intensities[[The Hitchhiker's Guide#^9ac83b|4]]. ^6ee7ec

---

So where does this leave us? We started the Guide with a simple question and all we seem to have done is answer a question with another question, or worse, *questions*! That is, we have been slowly revealing *what we don’t know and thought we did*, more than learning what we *do* know. Don’t worry adventurer. Knowing what you don’t know is absolutely as important as knowing what you think you know, you know?

Here’s a loose summary of what we *do* know:

-   We know that when we adjust a slider in a DCC, we are solely changing the intensity of a light.

More clearly, this is two statements:

-   We know that when we change the value, we are changing the quantity of light.
-   We know that when we change the intensity of the light, for all intents and purposes, the colour of the light primary never changes.

Knowing these things though, leads us down to further questions. Given the bullet points above, we might start asking questions about the first point. That is, if we are changing the intensity of a particular chromaticity of light, what is the chromaticity of the light in the first place? [[The Hitchhiker's Guide#Question 4 What the F *ck are the Colours of the Three Lights?|Let’s make it official and ask the question…]]

---

1. Terminology is damn important. Part of the problems with the random noise online is that folks tend to be far too loose and free with their usage of terminology, or use overloaded terms. For those interested, the ISO-22028–1 document has a handy dandy glossary at the beginning. These posts try to adhere to the some of the terms outlined there, or via specifications. Hopefully the terminology will trickle down slowly like an intravenous drip to not overwhelm the reader.[[The Hitchhiker's Guide#^8abab8|↩︎]] ^a2c26c

2. Ok, I can already hear the WANKs wanting to take deep dives into voltage and power functions, and Abney effect, and physical colorimetry aspects of a display device, and how no physical display is perfectly idealized, and how “colour constancy” is a psychophysical effect, etc. etc. etc. As per the second footnote in the first entry, please shut the f\*ck up and sit down for a moment. You aren’t helping the intended audience here, nor is taking a deep dive into psychophysical effects. If you are here and are one of the WANKs, the goal is to lay a solid foundation for understanding, and in doing so, we are going to have to leave out some of the puzzle pieces that can be explored at a later time. If you are here and are not a member of the WANK club, rest assured, I’ll do my best to keep the WANKers at bay, and introduce the elements in the most digestible morsels possible.[[The Hitchhiker's Guide#^0d90f2|↩︎]] ^5802ad

3. The term “colour” here has been used interchangeably with “chromaticity”, which isn’t entirely accurate. Colour exists only in the human perceptual system, and as such it’s really quite complex. That is, the [[The Hitchhiker's Guide#Question 27 What the F *ck is Perceptual Colour?|appearance of a given colour and it’s chromaticity]] can be different things. Using a term before it is well defined though, would complicate the more important concepts. As we move on, the balance of terminology will shift towards more correct usage.[[The Hitchhiker's Guide#^6ee7ec|↩︎]] ^f4b896

4. Yes, the WANKers are chomping at the bit wanting to wax lyrical about the nature of non-uniform application of 1D lookups or per-channel applied expressions and how it alters the chromaticity. Yes, yes, yes… go take a suckle on your milk bottle nipple for awhile or mash some hours away raging in the comment section of YouTube. While you are gone, the folks following along the path will carry on quietly…[[The Hitchhiker's Guide#^6ee7ec|↩︎]] ^9ac83b



 
# Question #4: What the F\*ck are the Colours of the Three Lights?

Have you ever taken a random set of paints and started mixing them? If you have, you probably have realized the not-quite-groundbreaking idea that the paint mixture colour depends on which paints you mix and in what quantities you mix them.

This profound, almost Aristotle-like breathtaking and earth shattering conclusion holds a not-too-distant connection to digital RGB colour work. As you may have noticed from the very first question, some things that are painfully obvious sometimes go without an actual analysis. Let’s try to smash that up…

---

If we have a single channel of RGB light in a pixel, [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|we can increase or decrease the intensity]] without changing the underlying primary’s colour. Hopefully you are seeing that there are two axes that we have managed to focus on. Here, intensity is to the colour as volume is to a note played on a speaker. We can increase or decrease the volume without changing the note in question. The same holds for colour.

How then, do we change the colour? Just as with the introductory paragraph, the answer is simple; we mix in other lights. If we have a reddish light, we can represent exactly one colour, at varying intensities. If we add a light, perhaps a greenish light, we can now mix a two dimensional set of combinations. These colours will be extremely familiar to you all, because all you have done is push around pixels and “paint” in mixing interfaces and colour pickers.

![](https://hg2dc.com/wp-content/uploads/2019/03/c3f34-1dsscuqjmjw7mts4jzm875q.png)

Mixing the two dimensional gamut between red and green, at 100%, 75%, and 50% intensity

As discussed, we can say that the chromaticity of the three sets of mixture swatches above are the same across the columns of values, and only the intensity of the light ratios are changing uniformly. Note that at no time are we able to mix an *achromatic*, or without colour, mixture[[The Hitchhiker's Guide#^393e99|1]] from only these two particular choices of light chromaticities. The two dimensional array of combinations always traces from red to orange to yellow to lime to green and back. Always. ^677237

If we add a third light, we of course get another whole range of colours and values we can mix. That third light in an RGB encoding is typically blueish. By adding the blueish light, we can indeed mix a colour that looks achromatic. Note how I said the word achromatic, instead of that blasted nightmare word “white.” The reason is, “white” creates the illusion of a fixed and absolute thing, as opposed to the idea that it is just another colour at some intensity. You will also notice how I avoid conflating code value `0.0` with “black”, as it too, isn’t a single, absolute thing. More on that later…

In all of this basic light mixing, we have neglected the elephant in the room. It’s sitting over there, crunching away and pooping, and no one has really asked what it is doing there.

**Question #4: What are the actual colours of the three RGB lights?**

Dumb question, right? If only it were…

---

How many times have you pushed a pixel around on a screen, been yelled at by clients, answered snarky emails, or tried to chase down getting paid for the hot dog logo you did up two months ago? The answer, I’ll guess, is far more times than the number of times you asked what colour the lights were in the pixels in your display.

The question is darn important, and sadly is as ignored or overlooked as that invoice sitting on your client’s desk for that hot dog logo. The answer is also contextual; it depends on what equipment you have. In most instances though, the computing industry has historically rallied around a much overloaded and horribly confused standard. In keeping true to making things as foundational as possible, we will make an assumption here.

**Answer #4: There is a good chance that the colours of the three primary lights in your display are darn close to the REC.709 red, green, and blue chromaticities.**

Gotcha there, didn’t I? You were waiting for that s word… that one that everyone mutters in shallow breaths and tosses around in all sorts of different and confusing contexts. That word is of course sRGB, and it is probably one of the most commonly overloaded terms in graphics ever. I purposefully used the more correct answer to try and pull you out of that sad little loop of nightmare[[The Hitchhiker's Guide#^bc4005|2]]. With that, we’ve generated yet more questions. ^ef59ad

---

So what’s the takeaway here? We’ve exploded all sorts of crazy new questions, and answered even fewer. I’d hope you focus on one very specific conclusion here; the colours in your display are physical hardware constraints, and that physical element is defined using a chromaticity map to nail down the physical colours of the lights, using an absolute colour encoding model. In many cases, the standard targeted is the sRGB standard, which uses primaries that are identical to the primaries in the REC.709 standard. The lights are the same chromaticities! [[The Hitchhiker's Guide#^f3b100|3]] ^eb25fc

But what about if you happen to have a MacBook Pro with that fancy Display P3 mumbo jumbo or some Eizo magical +6 Wide Gamut of Costly Dollars? The answer, as you hopefully may have suspected, is that they actually have *different coloured lights* at each pixel position in the hardware of the display; the paint pots are different from the paint pots outlined in the sRGB / REC.709 standards!

Like all good investigators though, we need to retrace our footsteps a bit before going further. We need to go back to talk about measurement units. Remember that `0.6` in the earlier question? That’s a unit of measurement, and we need to dive a little deeper before we can start tackling [[The Hitchhiker's Guide#Question 5 What the F *ck does 0.5 mean?|more complex questions…]]

---

1. It should be worth noting that I’m deceiving you a bit here. *Achromatic*, or without colour, is something that happens in your *psychophysical* perceptual system, and isn’t something that exists absolutely outside in the spectral world. More on that later…[[The Hitchhiker's Guide#^677237|↩︎]]
 ^393e99
2. The sRGB specification utilizes the primary light chromaticities defined in the REC.709 specification that predates it. As such, I have honoured the historical precedent as the origin for the label. There is a minor difference in how the chromaticities are defined that yields a discrepancy in the decimal places, but for all intents and purposes, it is relatively safe to refer to the chromaticities of the primaries as the same in the REC.709 and sRGB standards.[[The Hitchhiker's Guide#^ef59ad|↩︎]]
 ^bc4005
3. As above, there’s a bit more to the story. How precisely we identify a chromaticity via the decimal places or format plays a role here. To this end, there are subtle differences from a technical standpoint on REC.709 vs sRGB chromaticities, but for all intents and purposes, it’s healthy to think of them as the same. This is the same information presented in the footnote above, but redundancy redundancy are fine in paragraphs that no one bothers to redundantly read anyways.[[The Hitchhiker's Guide#^eb25fc|↩︎]] ^f3b100



 
# Question #5: What the F\*ck does 0.5 mean?

Continuing along the analogy of mixing paints, the colours of the paints matter. If we ask two people to pick out three paints each, at random, and ask them to mix certain amounts according to a recipe, there is a zero percent chance the same colour would result between the two people using the identical recipe measurements. However, even if we ask them to pick out precisely identical coloured paints, we would still need them to have agreed upon a measurement system!

I’ll get the question out early on this one. It’s a helluva important one…

**Question #5: What is the basic unit of RGB then, specifically?**

A few questions ago, we scratched the surface of code values and their representations. We can summarize a few things about code values:

-  Bit depth, or the *quantity* of “steps”, has no impact on the [chromaticity](http://cie.co.at/eilvterm/17-23-052) of the primary lights, or *[tristimulus values](http://cie.co.at/eilvterm/17-23-038),* nor change the minimum or maximum emission of said lights. That is, it is like the number of slices we choose to slice up a banana; more slices isn’t going to make the banana an apple, nor make the banana longer or shorter.
-  Code values can be *represented* a number of different ways in a computing environment. Up to now, we have discussed whole numbers, or integers, which typically are used as a ratio of the maximum integer range. `8/255` or `67/1023` can be considered a *ratio* of the banana’s whole. From within the DCC application of your choice, consider garbage eight bit representations such as `255` and equally garbage hex codes such as `0x1A` as different representations of integers. These can be more clearly expressed as decimal values.
-  Code values can be *interpreted* as anything, and depend on context. We examined how normalized integer code values could be interpreted as ratios from minimum to maximum expressing a quantity of light being emitted from a display, or interpreted as a percentage of a banana that has been eaten. *Code values must be decoded and assigned meaning*.
-  RGB code values *alone* carry *no additional context* that explain what the values mean. We cannot examine an RGB triplet in isolation, no matter how accurate they appear, and know what they represent; we need additional contextual information to decode a code value. We cannot look at `0.372734234211` and infer that it means 37.27% of a banana; we need to know that you are talking about bananas and not apples, and whether the value is in fact a ratio or some other measurement such as overall banana length according to some measurement system.

The last point is worth focusing on a little bit more. We know that a code value in an RGB system can be used to change the intensity of the light in a display, but what we don’t know is how code values are measured against each other. We can’t assume we are talking about units of orange slices when the intention was a quantity of bananas.

---

You might already have a sniff as to what the answer is to this question. If you haven’t, you haven’t fully embraced how much crap there is out there that is impeding your comprehension. I’ll go out on a limb and suggest that your understanding is likely greatly inhibited by the fact that…

**Answer #5: The basic unit of measurement in an RGB triplet of code values, when considered in isolation, without any further information, means absolutely nothing.**

Much like the last example of oranges to bananas, *RGB code values, in isolation, are meaningless*. Specifically, the increments between code values have no constant meaning. That deserves a paragraph break for it to settle in.

---

We’ve all seen numbers with long, scary decimal places. Although we are seduced into thinking they hold inherent meaning, they too are meaningless. They are nothing more than codes waiting to be interpreted. Countless StackExchange posts, idiot YouTube comments, and even application documentation are frequently a miserable bog of misinformation. They’ll give you all sorts of fancy long numbers when talking about RGB, but what they won’t tell you is that they are horribly confused in most instances. It’s mostly utter bulls\*t.

While we now know that we need additional data to describe the chromaticity[[The Hitchhiker's Guide#^f111de|1]] of the light a code value is intended to control, we *also* require additional information about the intensity measurement ratio. ^cd2761

[[The Hitchhiker's Guide#Question 2 What the F *ck Does 0.6 Mean?|Back in another question]], we touched on how code values represent some ratio of light. But what are the units between the ratios? What would `0.5` *represent*, in terms of intensity?Is it a physical measurement such as half of the number of photons when compared to maximum? Is it some absolute quantity of light? Is it some strange “Gee whiz that value looks half as bright as maximum?” perceptual sort of thing? And if we understand `0.5`, what is its relationship to `.051` or `0.6`? Once again, [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|more nasty questions…]]

---

 1.Remember that chromaticity is best described at this point as an absolute measurement of colour. It’s a little more complex than this, but for now, that will do just fine.[[The Hitchhiker's Guide#^cd2761|↩︎]] ^f111de



 
# Question #6: What the F\*ck is a Transfer Function?

Whoa. There’s a term that you probably haven’t bumped into before, eh? You’ve been pushing pixels for how long, and some bozo tosses a made-up term at you? You might even start to believe that this rubbish series of posts that promised to inform has cheated you, and instead just keeps looping back to the crap you don’t know.

First up, take heed reader… we are at least identifying the things that we don’t know. As it turns out, much of the problems with understanding digital colour comes from understanding that our knowledge stands *relative* to something. That is, when we first removed the rusty old boat that was covering the stinky well, and asked “[[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|What the f*ck happens when we change an RGB slider value?]]”, we discovered that we were detached from what the value *referred* to. What did it *control*? So sit down, buckle up, and prepare to hear *referred* quite a bit more in the coming inquiries…

---

Having read through the past five questions, you are likely starting to draw a connection between the code values and some device or some model. That is, up to now, we have discussed maximum intensity versus minimum intensity, but not yet described the device they are referring to. [[The Hitchhiker's Guide#Question 4 What the F *ck are the Colours of the Three Lights?|We somewhat superficially learned]] that the colours of the lights in a typical display are described by the sRGB specification, but we haven’t gone much further than that.

While we are starting to define a useful model here, we still can’t drill down into the bedrock and answer hard questions like “What does a code value of 1.0 mean?” until we more deeply consider the thing we are connected to. That is, a code value as we’ve hammered repeatedly, needs decoding to give those three teeny RGB flashlights in our pixels meaning. How do we decode it though?

---

To give our code values meaning, we are going to hook them up to a display device. We’ll use the bog standard display device known as an sRGB display. What is an sRGB display?We again touched on a teeny component of this in  [[The Hitchhiker's Guide#Question 4 What the F *ck are the Colours of the Three Lights?|Question 4]], but it’s not good enough to dive deeper…

Somewhere in a galaxy far, far away around 1996, a group of folks gathered together and [designed a specification that describes an imaginary device](https://webstore.iec.ch/publication/6169). Henceforth, vendors went about and constructed a real device from said imaginary device’s specification blueprint.

Take the device home, plug it into a computer, send some code values to it, and hopefully it will behave as that device specification outlined. Whether you realized it or not, and as we touched upon in [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|Question #3]] the display you are on has a high probability to be designed to the sRGB standard. [[The Hitchhiker's Guide#^438d48]|1]] ^7e07c1

Looping back, we take that encoded value, run it through our computer and out to the display, and the display takes the code value and turns it into light. This leads us to our wonderful question number six, which is…

**Question #6: What exactly is a transfer function and why is it important?**

---

So what happens when we wrap up a code value and send it to our brand new sRGB display? If we send a code value of `[1.0, 1.0, 1.0]`, do we have any idea how much light is coming out? *That question*, wise reader, is exactly what a transfer function helps to answer. It’s the peanut butter and jam between the slices of code value and decoded value bread.

So what does `1.0` spit out in terms of light?

“Maximum” you say, gleefully aware of what we’ve discovered. You’d be correct. But can we quantify how much light should come out of one of our RGB lights? The answer is yes, but we would need some metric. While there are quite a few of them out there, the one chosen by the standard is known as [a candela per square metre](http://cie.co.at/eilvterm/17-21-086) [[The Hitchhiker's Guide#^2a3337|2]]. You may have heard it before, as some folks call it, somewhat colloquially, a *nit*. ^9b5202

If you had the sRGB specification in front of you, you’d see that ideally, in a reference display, the output from an sRGB display is 80 nits. But let’s focus on our question, which is sorting out specifically what a transfer function is…

---

Given we know that we have a code value of `1.0`, and knowing that we are sending that code value to our display, we can also have faith that the display is *decoding* that code value according to the specification. You’ve probably already guessed that if our maximum code value is `1.0`, and that our maximum idealized nit output of our sRGB display is 80 nits… that yes… we’d get out 80 nits worth of intensity if all three channels were set to maximum! Whatever a nit is…

This is great. Off to digital painting you go, freshly armed with your new knowledge that there is an actual way to calculate light output from your strange code value. But uh… let’s take a moment to ponder other values. What about `0.5`? Seems innocuous enough right? I mean it’s 50%… of our sRGB display’s pixel channel intensity… erm… is that… physical energy as in 50% of our maximum 80 nits… or is it uh… something… else?

And now for a preemptive nuclear strike on the WANKS[[The Hitchhiker's Guide#^09d82d|3]]… ^6e4346

“I ALREADY KNOW THIS SH\*T!!!11!! IT’S GAMMA!!1!!” I hate to break it to you my dear Sealioning WANK, but that’s only going to lead you down the path of pain if you discard what you can learn from transfer functions under an umbrella of “gamma”[[The Hitchhiker's Guide#^2b8d62|4]]. For everyone else, and maybe even one of the WANKs who has crossed over to being a normal human being… onto that answer… ^b2b27b

**Answer #6: A transfer function is a math formula that describes how a code value relates to light energy input or output.**

---

Wow if that isn’t too vague, eh?

See how I said “math formula” and not some perceptual mumbo jumbo? Note how I also didn’t say the godforsaken dumpster fire of a term “gamma”? There’s good reason for this. For now, let’s realize we’ve learned a new term, and we will use it henceforth. Rejoice, and say the words [*colour component transfer function*](http://cie.co.at/eilvterm/17-32-004) or again, simply *transfer function*, with me.

I gave you a loose term, that isn’t entirely clear, that describes output *and* input, yet we are talking about displays. I apologize. I did that in the interest of the future, however! “But what about the sixteen times you’ve asked what a code value is and then ask another damn question? What about `0.5` dammit? EXPLAIN SOMETHING, WILL YOU?!!?”

We are getting there, but sadly, we also have to keep these posts brief in this Attention Economy, so go grab a cup of covfefe and relax for a bit [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|until that next question…]]

---

1. If you happen to be on a MacBook Pro from 2016 onwards, an iMac with a Retina 5k display from the latter half of 2015 onwards, an iMac Pro, or any of the many wider gamut Eizos and other displays, your lights are actually a different colour. For now, we will ignore this facet and try to bolt down the foundational concepts. [[The Hitchhiker's Guide#^7e07c1|↩︎]] ^438d48

2. Sorry Team USA, the rest of the world is on the metric system. No, really. Here’s a useful map of all of the folks, shown here in red, using that other system… [[The Hitchhiker's Guide#^9b5202|↩︎]] ^2a3337

![](https://hg2dc.com/wp-content/uploads/2019/05/46b19-0ivg0ehphexag_z2n.jpg)

3. See [[The Hitchhiker's Guide#^7ffa09|footnote 2 in the first question]]. [[The Hitchhiker's Guide#^6e4346|↩︎]]  ^09d82d

4. If you had the sRGB specification sitting in front of you, you’d open it up to plenty of math and strange terms. Those math and strange terms though, help to describe how the device in question operates. On some level, that includes some absolute metrics and models, one of which we learned above, known as a *candela per square meter*, or *nit*. It also describes two formulas for getting to and from sRGB code values. Those functions are typically called *transfer functions*. [[The Hitchhiker's Guide#^b2b27b|↩︎]]  ^2b8d62

“Aha!” you might say, “That’s GAMMA!!!!111!!!” Well I have some bad news for the you. The actual standard has a little note in it. The little note reads:

> 1) The term “gamma” is not used in this standard for the reasons discussed in annex A.

If we flip to annex A, we find this extremely wise bit of text:

> Annex A  
> (informative)

> Ambiguity in the definition of the term “gamma”

> Historically, both the photographic and television industries claim integral use of the term “gamma” for different effects. Hurter and Driffield first used the term in the 1890s in describing the straight-line portion of the density versus log exposure curves that describe photographic sensitometry. The photographic sensitometry field has used several interrelated terms to describe similar effects, including gamma, slope, gradient, and contrast. Both Languimier in the 1910s and Oliver in the 1940s defined “gamma” for the television industry (and thus the computer graphics industry) as the exponential value in both simple and complex power functions that describe the relationship between gun voltage and intensity (or luminance). In fact, even within the television industry, there are multiple, conflicting definitions of “gamma”. These include differences in describing physical aspects (such as gun “gamma” and phosphor “gamma”). These also include differences in equations for the same physical aspect (there are currently at least three commonly used equations in the computer graphics industry to describe the relationship between gun voltage and intensity, all of which provide significantly different results). After significant insightful feedback from many industries, this standard has explicitly chosen to avoid the use of the term “gamma”. Furthermore, it appears that the usefulness of the term in unambiguous, constructive standard terminology is zero and its continued use is detrimental to consistent cross-reference between standards and unambiguous communication.

That’s right folks… the sRGB standard, way, way, way back in 1999, chose to drop the awful term “gamma”, for good reason. It’s a piece of junk term that is sufficiently overloaded to mean close to nothing when we are trying to discuss digital colour on a technical level such as these postings. Worse, when you utter it as an incantation, all sorts of drooling meatheads come out of the woodwork and start sealioning bullshit at you. You’d be wise to skip the term, and stick to the one outlined in the many specifications that define the very things digital artists use on a daily basis. To the Sealions? F\*ck off.

*Friends don’t let friends say “gamma.”*



 
# Question #7: What the F\*ck Does “Linear” Mean?

This is perhaps one of the most ugly questions we are going to tackle, and I’ll warn you up front, it’s *very* ugly. The good news is that we are going to smash up a bunch of bogus misinformation in this question. The bad news is, much like all of these damn questions, is that there will be more questions left in the rubble.

The previous [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6]], we started chipping away at what a transfer function is. Let’s recap a little bit:

1. Back at [[The Hitchhiker's Guide#Question 2 What the F *ck Does 0.6 Mean?|Question #2]], we first posed the question as to what a code value represents in a typical DCC application. We learned that it relates to some intensity of light coming out of a display on some scale from minimum to maximum. Unlike what we thought as a “colour”, we learned that it is some *code* to be *decoded*.
2. Back at  [[The Hitchhiker's Guide#Question 5 What the F *ck does 0.5 mean?|Question #5]], we learned that while we have connected the dots to some sort of emission from a display, we haven’t really pondered what the measurement system is. That is, in learning that a particular value doesn’t mean anything, we learned that we need some means of defining a frame of reference, or *ground truth*.
3. Back in [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6]], we learned that the math formula that defines our measurement system is called a transfer function. This function is the glue between the *code values* and something to do with a *physical quantity of light*.

The last point is a doozy. If you thought folks are driving their digital colour cars into the ditch via the revelations accumulated over the previous six questions, the third point above is a canyon. We can’t discuss code values and their relationship to quantities of light until we bridge the canyon with a bit about how light works…

---

Hopefully at this point you’ve come to the conclusion that the misunderstandings you may have had regarding colour come from the lack of a frame of reference. “Linear” is just such a term. So let’s keep things in the commerce of the Attention Economy and get our question front and centre:

**Question #7: What does “linear” mean and what does it relate to?**

If you are reading this, you’re probably the sort of digital pixel pusher who has come across terms like “gamma” and “linear” many times. We learned that like hex codes, “gamma” is one of those garbage terms that we must struggle to avoid. The sad truth is that “linear” has now become one of those awful terms.

Why would “linear” fall into the same overloaded dumpster fire that “gamma” and the obfuscating junk known as hex codes? Because not many folks connect the dots to what the hell it means, and specifically with regard to digital colour, the “linear” frequently refers to something that is unspoken and unclear. What is “linear” referring to? Are there different types of “linear”? Is there an “anti-linear” or “nonlinear”?

To answer this, we will be revealed via the subjects of our subsequent questions, but without spoiling them, let’s talk about energy briefly.

---

Hopefully all digital artists reading this have done some good old fashioned physics in school. Even if you haven’t, you probably are aware that energy is part of that vast field of study. You might have even learned that energy is quite an interesting thing in that we can calculate varying levels of it, estimate how it will fall off or increase through space, and do a bunch of other complex calculations around it.

Light is, unsurprisingly, a form of energy. Being an energy, light has some simple rules for our purposes. If we quantify light into units, we can add them. That is, we could take one unit of light and add it to another unit of light and presto… two units of light. If we take six units of light and add it to seven units of light… thirteen units of light. This is the sort of math that, were we to plot the math multiplications or additions on a chart mapping input to output, we’d end up with straight lines. We can call light energy linear, or more specifically, *radiometrically linear.* The math behind light can be distilled down to relatively basic linear math.

---

If you ever want to make something messy, like *really* messy, there’s one terrific way to do it; add a human. While we know that physics for light energy is linear, something went sideways with humans. How loud is that sound? How hard is that touch? How “light” is that light? In a perfect mathematical world, those sorts of answers would be “Well… there’s a linear relationship between the quantity of sound energy and the level of loudness that an average human hears it as.” Sadly, as you may have guessed or known, this *is not the case*.

Humans are not to be bound to that linear to linear 1:1 relationship with the energies they experience. Sound is some whack-job-crazy-not-linear. Touch? Some nutty-not-linear relationship to perceived experience. And… you guessed it… light is also totally-not-straightforward-relationship-to-physical-energy. All of these examples, if we were to plot physical energy in a 2D graph along X against the sensation-perceptual-messy-human-experiential-metric along Y, would result in some crazy not-straight-line, or *nonlinear* relationship.

But what does that *really* mean?

---

We know that one unit of radiometric light plus one unit of radiometric light is two units, but how *light* does it appear compared to the base unit? The fact we are asking the question here probably tingles your trap-detection, and you’d be right. It’s not quite twice as light. Add another unit, and it becomes even more messy; human standard observer response to physical radiometric energy isn’t a linear relationship. At all. As with our above plotting example, if we plotted the input radiometric light level along the X axis, and the output “How light does it appear” along the Y axis, we’d not have straight lines, but instead an irregularly curved line.

Moving from one unit to two units, then from two units to three units will not result in the standard observer seeing three times as much light. In fact, we’d need to add on one or two *additional* radiometric units to make the equivalent increment of lightness. That is, if our first increment were one radiometric unit, our second “doubling” of lightness would be two to three radiometric units, a “tripling” of lightness would be somewhere around four to five radiometric units, and a “quadrupling” of lightness would be around eight to ten units.

Sadly, not even this rule of thumb really describes lightness [[The Hitchhiker's Guide#^0ad1f5|1]] very well. Remember how we said human perceptual systems are nonlinear? They are so nonlinear and strange that there’s no real perfect, idealized formula for it, and new research is being done even today. At a certain level, once we are adapted to a given range of light, light behaves one way, then above a certain level, it behaves slightly differently. It’s a sloppy mess. For our purposes, it’s great that it’s sloppy as we can simply accept wholeheartedly that our perception is a *nonlinear phenomena*. ^90c7db

![](https://hg2dc.com/wp-content/uploads/2019/06/eb077-1q5b2r_r312diag5okuycng.png)

A rough approximation of perceived lightness along the vertical axis against a known linear model variable known as luminance along the horizontal axis

---

We’ve just about hit our time allocation here, which indicates that our question is about as fleshed out as we can be at this point. So, let’s answer the question…

**Answer #7: “Linear”, when used in the context of digital colour, is referring to how radiometric light energy behaves, and how ratios can be described with respect to that radiometric energy ground truth via the physics and math of light energy.**

---

We can’t discuss digital colour without understanding that there is a need to subdivide our dive into different domains. In discovering that light is physical and that colour is psychological, it helps us to understand why colour exists as a [*psychophysical*](http://cie.co.at/eilvterm/17-21-012) phenomena; the experience of colour is tightly wound between physical stimuli and complex human psychological and organic reactions.

Specifically though, we need to understand that “linear” is a crucial aspect to how we are going to be describing light energy; it’s a foundational concept that connects all of the moving parts. With that understanding, we also must note that using a term like “linear” alone isn’t quite enough information to make meaningful inferences.

We know that we are referring to some sort of linear radiometric quantity of light, but we can clearly see that there’s many different contexts that could result in quite different interpretations of “linear” here, and yield different meanings from our code values in our precious RGB encoding model. And with that… take another break, and rest your RGB grey matter before we [[The Hitchhiker's Guide#Question 8 What the F *ck Type of “Linear” Have We Been Assuming?|move onto our next question]]…

---

It is easy to be a bit sloppy in using the terms [lightness](http://cie.co.at/eilvterm/17-22-063) and [brightness](http://cie.co.at/eilvterm/17-22-059) somewhat interchangeably. In terms of colour science and colour appearance models, it should be noted that there are strict definitions and differences between the two.[[The Hitchhiker's Guide#^90c7db|↩︎]] ^0ad1f5



 
# Question #8: What the F\*ck Type of “Linear” Have We Been Assuming?

I’m going to spoil our trend of not answering questions with an actual answer, that is somewhat not-too-secretly buried it the question itself. That is, this isn’t even a question, but more of a pit stop in the glossary. Specifically, the four previous questions culminate in the term we are going to Achievement Unlock:

1. Back at  [[The Hitchhiker's Guide#Question 2 What the F *ck Does 0.6 Mean?|Question #2]], we were able to discover the arbitrary nature of RGB code value triplets. We focused on the idea that in some instances, the code values represent a ratio, and specifically, a ratio between some minimum and some maximum.
2. At [[The Hitchhiker's Guide#Question 5 What the F *ck does 0.5 mean?|Question #5]], we dug a little deeper. We revealed that code values could be ratios, and hinted that the nature of the ratios could be related to a whole, such as with a percentage, or with regards to ratios between each code value.
3. [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6]] began to lay the structure in place to connect the dots between code values and meaning. We learned the crucial concept of a colour component transfer function, and how it decodes code values to something.
4.  Finally, with [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|Question #7]], we established what exactly the something is from above, and bolted it down to a concept around linear light and how our psychophysical perceptual system is nonlinear.

And with those four questions…

**Question #8: What type of “linear” have we been assuming the RGB code values are in reference to?**

---

“What a stupid question! Linear is linear right? Linear light energy is linear light energy. We’ve covered this sh\*t…”

The issue is that like all things colour and code value related, the confusion comes out of the bog of nightmare terms. Up to this point, we haven’t managed to find a term that gives this meaning specific context, and it’s clear we need one. It’s also an extremely crucial bit of terminology to keep in sight when discussing code value decoding as we have been.

---

**Answer #8: Up to now the “linear” have we been talking about stands in reference to a particular type of display, or more generally as output referred encodings.**

“WAIT A MINUTE. WE KNOW THIS ALREADY FROM QUESTION F\*CKING #1!!1! THIS IS A CONTENT SCRAPE!!11!!”

Yup. As mentioned, this is a cheated question. Why the cheat?

The specific term in question, [*output referred*](http://cie.co.at/eilvterm/17-32-052), is useful alone. More useful though, is that we can’t break down things further without it. We can now speak about the relationship of the intensity output of a code value in relation to a specific context, and concretely and accurately connect light emission of a particular code value in an output referred context.

Extending this, when we are discussing displays, we are speaking of the [display’s input / output characteristics](http://cie.co.at/eilvterm/17-32-022), which as we know from [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6]], is the mathematical function known as a [colour component transfer function](http://cie.co.at/eilvterm/17-32-004). We also get to add another term to our toolbox, and discuss code values related to displays as *display referred encodings*.

---

“Display referred, OK… but there are other things that aren’t displays… How do the digital code values in a photograph work? They can’t be in relationship to a display in the camera. What about a printer? That clearly isn’t in relationship to a display. A scanner?!? This is completely unuseful!”

You’d be 100% correct if you have these sorts of questions swirling around in your head. That’s a good thing! Better, you’ve hopefully grown bored of the idea that code values are always in *reference* to *something*, and that *something* isn’t always a damn display! In some instances, the code values refer to other contexts, and only take their meaning from that context. Hence, output referred is the umbrella under which many other references live, and the umbrella that display referred lives under.

So is there a commonality here? Is there something further we can add to our general output referred understanding? Yes. The key point to understand is that when discussing output referred encodings such as devices, printers, etc. is that their code values exist as a ratio of values from some minimum to some maximum, and that the *absolute* meaning is defined *solely* by that reference. A ratio of light from a display, a ratio of light that a sensor can detect, a ratio of reflectance off of an object, a ratio of values scanned into an image, or even a ratio of ink applied to a particular type of paper, etc.

In all cases, remove the referred device and RGB or CMYK or any other bogus code value, no matter how precise, utterly loses its meaning. So much for the sh\*t-f\*ck-metric-tonne of garbage articles that discuss RGB and CMYK as a *colour space*, eh? Hopefully you are beginning to see the horrible confusion between a [colour encoding model](http://cie.co.at/eilvterm/17-32-006) and a [colour space encoding](http://cie.co.at/eilvterm/17-32-018); the former’s code values hold no meaning without the details of the latter. In most cases, that meaning is derived from some specific reference [[The Hitchhiker's Guide#^ebf4e8|2]]. ^1539a0

---

I’m going to hope you found this question sleight-of-hand completely unsatisfactory and underwhelming. I’m also going to hope you found it somewhat obvious, and even hope further that this felt like a rehashing of things we’ve been tracing back and forth over. In fact, I’m going to hope this was a boring repeat of information you already fully understand and were simply lacking the appropriate term.

Armed with a new term, we can slip back to connecting the dots. There’s one specific question that frequently comes up, and that is, why do we bother with linear and nonlinear encodings at all?That seems like a good question to dig into over the  [[The Hitchhiker's Guide#Question 9 Why the F *ck is Linear Light Important for a Digital Artist?|next couple of questions…]]

---

1. The wise reader probably already knows or remembers that colour displays haven’t always had code values that represented intensity. In fact, the original colour displays weren’t terribly colourful, and had limited, specific colours they could represent. Those display encodings became known as [palettized](https://en.wikipedia.org/wiki/Palette_%28computing%29), and their semantics were basically like picking spot colours out from a given list. This post has left behind that era in the hope of removing some of that confusing history, not that you won’t see it come up time and time again as one confused idiot “explains” colour in a verbal diarrhea potpourri from time to time on those ever-awesome answer sites… |↩︎]] 
 ^442bdc
2. In some rare cases, the colour encoding model comes with a specific colour space encoding series of characteristics. They are few and far between, and it’s best to think of a colour encoding model as something separate from a colour space encoding. [[The Hitchhiker's Guide#^1539a0|↩︎]] ^ebf4e8



 
# Question #9: Why the F\*ck is Linear Light Important for a Digital Artist?

[[The Hitchhiker's Guide#Question 8 What the F *ck Type of “Linear” Have We Been Assuming?|In our last question]], we took a quick dive into discussing what a particular type of linear, *display linear*, is related to What we haven’t discussed yet, is why there has been all of this talk about linear in the first place. Why do linear versus nonlinear encodings matter if you’ve been happily painting in Photoshop or Affinity’s tools and not giving a crap about this rubbish? We’ll try to skip getting into the math and use a simple visual demonstration to hammer our point home.

So, let’s break the question out…

**Question #9: Why is linear light important?**

---

This answer will divide our audience into two unique groups. One group of you will have no real idea about linear light, and probably wonder why we’ve spent eight questions discussing displays and other garbage to get to a seemingly irrelevant question. If you are in the other group, you are probably thinking you’re already aware as to why using linear light RGB ratios is important, and hoping that we can move along faster.

As with all things pixels, a nuanced understanding will help you survive the onslaught of stupidity online. The details will help you understand the depth behind some trite video from some YouTube influencer, or some other equally hastily assembled and ridiculous content from some “cinematographer” or “photographer”. We aren’t here to make money from views, clicks, and likes, so we can afford to dig a little deeper.

Seeing is believing. I present a simple red star against a cyan background… [[The Hitchhiker's Guide#^480866|1]] ^258051

---

![](https://hg2dc.com/wp-content/uploads/2019/07/7ddfb-1w8euq4rpume8zb7-61qytg.png)

Keen observers will see something very peculiar near the slanting edges that will become more obvious down below…

So what’s wrong here? Anything? Can you spot it?

Let’s make it more apparent. Let’s blur our star a little bit…

![](https://hg2dc.com/wp-content/uploads/2019/07/1f911-1-skzxsakx8-7yv7zhufxog.png)

There, that’s better… or not…

At this point it doesn’t take a Frida Kahlo or Emily Carr to figure out something looks whacked. Most pixel pushers sense something is off, yet may have lacked the confidence to say that their beloved 1000$ DCC applications might be doing something wrong. After all, the software has the “experts” working on it, right?

The answer of course is the dark fringe. That dark fringe is present when compositing an element over another element using a broken internal model. In this case, the red star is composited over the cyan background [[The Hitchhiker's Guide#^eceeb8|2]]. But what should it look like if composited [[The Hitchhiker's Guide#^78d142|3]] “correctly”? ^d9d311

![](https://hg2dc.com/wp-content/uploads/2019/07/611cb-1_lmrsei1e8vzl5iqahnsbq.png)

That’s better…

There we go. That’s better! No hyper-darkened fringe. So why is this second image more “correct” and what is your DCC application doing when you see the fringe versus not seeing the fringe? Better still, this example makes it painfully clear that we are discussing something with a tremendous impact on our work, not something trivial that can be overlooked.

---

We are nearing the end of our allocated time, so we’ll answer the question:

**Answer #9:** [**Linear light transport**](https://en.wikipedia.org/wiki/Linear_transport_theory) **is crucially important in all DCC pixel compositing math because the RGB code values always represent light, and if the code values aren’t properly converted to light ratios, bad, awful, no-good math** **results. RGB code values always represent light emissions.**

Blending, smudging, generic painting, compositing, blurring, and any other operation where pixels are being manipulated absolutely **must** be performed upon RGB values that maintain a [radiometric linear light transport model set of ratios](http://cie.co.at/eilvterm/17-21-038) if we hope to have it model / emulate the experiential learned “correct” results from our physical reality around us.

In the case of the above, the upper star image with a fringe applies the simple math upon nonlinear light code values, while the second image without the fringe had the *exact same* math applied with linear light code values, and then nonlinearly encoded for the display in question. In the former, we have broken internal representation which yields the alien-looking fringe, while in the latter the linear light code values more greatly emulate the physically plausible model we are familiar with seeing. Believe it or not, the implications are present even in the first image. If you look closely at the first image, you’ll see that along the edges of the unblurred star, you can see that over-darkening happening even there were the edge pixels in the [antialiasing](https://en.wikipedia.org/wiki/Spatial_anti-aliasing) reveals the broken calculations.

---

“My DCC didn’t show the fringed star! I’m fine!” or “Using Photoshop’s ‘linear blend’ mode solves this! I’m good!” is typical at this point, yet it only scratches the surface. Even if your DCC applicaiton didn’t sh\*t the bed and you see something akin to the second image, I assure you that this wasn’t the case until more or less recently, and even then plenty of folks didn’t understand when or why or how it was applicable.

Your particular DCC application may of course break your image using some of its tools, and try to be galaxy brain genius level software in others carefully coddling *you*, the person who needs to understand *what* is going on, from understanding *what* is going on.

In all instances it can be stated with almost certainty, that mainstream DCC applications mangle this up all over their pipeline, and its up to the pixel pusher to sharpen their knowledge to be able to diagnose and test just how badly their DCC is potentially breaking their work.

---

We have started to scratch beneath the surface of transfer functions a bit and have peeked into some of the implications of using those nonlinear code values in the pixel manipulation math. Are there other transfer functions for different encodings? How can we know what our images are encoded with? What transfer function is a tool like Photoshop assuming under the hood, and are there issues with using incorrect transfer functions? Are there other types of “linear” that we need to explore? Is your random piece of “smart software” making meatheaded assumptions about the encoding of your image values quietly breaking the work you’ve just hammered on for the past week? [[The Hitchhiker's Guide#Question 10 Why the F *ck Do We Bother With Linear and Nonlinear Encodings At All?|Great questions that will have to wait…]]

We will end this post with a simple guiding rule of thumb: **If you are manipulating pixels, a linear light transport model inside your software is absolutely crucial. Always.**

---

1. The astute observer may have noticed that the subpixels along the angled edges of the star exhibit the same incorrect nonlinear compositing problems. [[The Hitchhiker's Guide#^258051|↩︎]] ^480866

2. To the folks reading this series, it’s more precise to suggest that we are mixing a full intensity REC.709 red star over a full intensity REC.709 cyan background. And again, while a good number of us are looking at an sRGB display, the actual light chromaticities are defined in the REC.709 specification, and reiterated in the sRGB specification. [[The Hitchhiker's Guide#^d9d311|↩︎]] ^eceeb8

3. Don’t let the word “composited” scare you if it seems alien. In our example here, it’s a simple “over” in the [Porter Duff sense](https://keithp.com/~keithp/porterduff/p253-porter.pdf). You can achieve this via “layers” if your DCC application has them, or use a merge / alpha over node if you are using a nodal based compositor. [[The Hitchhiker's Guide#^d9d311|↩︎]] ^78d142



 
# Question #10: Why the F\*ck Do We Bother With Linear and Nonlinear Encodings At All?

Hard to believe we’ve hit Question #10. Hopefully you are all finding the series useful. Nothing is more valuable than you reading these posts and leaving comments and suggestions via email, DM, or even here.

A brief recap of salient details:

- Inour previous article  [[The Hitchhiker's Guide#Question 9 Why the F *ck is Linear Light Important for a Digital Artist?|Question #9]], we’ve discovered that whenever we are manipulating pixels such as via a blur, rotation, smudge, blend, etc. it’s necessary to emulate physical light transport ratios within our internal DCC application models. Specifically, we identified that when we use nonlinear light intensity code values, the output of light transport math results in horrifically broken garbage.
- We learned in [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6]] that a display referred transfer function defines how our code values are mapped with respect to the ratio of linear light emitted from a display. In the case of sRGB and common displays, that’s a *relative* ratio measurement, existing as a quantity of light in relation to a maximum and minimum light output. And of course, after the display decodes the code values it is sent, it emits linear light, served up and ready for our perceptual systems to ingest and bend and warp and mangle and turn into magic psychophysical “sight”.

---

When CRT displays roamed the earth, there was a nonlinear relationship between code values and the ratio of linear light output from the CRT display. Inside the CRT, electricity moved through the dark and mysterious box and projected a beam of energy onto the phosphors on the glass of the screen which excited them into emission. [Input nonlinear code values to our computer, the computer pushed those code out as a signal, and the signal is “undone” by the CRT back into linear light ratios](https://poynton.ca/PDFs/SMPTE93_Gamma.pdf) [[The Hitchhiker's Guide#^6d9b66|1]]. It was due to the hardware construction of the CRT that a nonlinear transfer function existed between the code values sent to the display and the ratio of linear light excitation of the phosphors.[[The Hitchhiker's Guide#^f58a2d|2]] ^85cb77

Fast forward to contemporary LED and LED-like displays, and that nonlinear disconnect no longer needs to exist at the lower hardware level. Want to increase or decrease the light coming out of one of your Light Emitting Diodes? Increase or decrease the current by roughly the same ratio that you desire the light ratio to be. Want to double the radiometric quantity of photons coming out of the display? Double the current. Decrease it by half? Halve the current. Quarter? Quarter the current. For our purposely and grotesquely overly simplified understanding, we can say that the current to light emission output is, in a contemporary display, mostly linear-like as well. Yet this isn’t how contemporary LED displays behave!

In both the CRT and modern LED case, the key takeaway here is that our displays are *always outputting linear light ratios*. Historically, we sent nonlinear signals to our displays due to the display CRT hardware, and, despite not being fundamental to the hardware of LED displays, that tradition continues to today.

However, you might be wondering something. Let’s list our facts:

-   The output of our displays is always a linear light based ratio
-   A contemporary Digital Content Creation application must use linear light transport models to get “correct” results in modern image manipulation work
-   Modern displays are more or less linear with regards to the current input and light output

It would seem that we have arrived at a fitting question…

**Question #10: If everything in a modern Digital Content Creation application behaves more closely to “what we expect as correct” under a linear light model and our displays output linear light, why do we bother with nonlinear transfer functions to encode our RGB code values at all?**

Great question! And of course… it’s a nuanced answer…

---

If you’ve crawled around online, you’ve probably run into more than a huge amount of misinformation about how our perceptual systems are nonlinear and that *that is the reason* why we need to convert our RGB imagery into nonlinear encodings. Yes, this is all complete and utter bullsh\*t; **our perceptual systems don’t need some idiot piece of software to encode nonlinear signals**.

The meatballs forwarding that sort of garbage didn’t stop for a second and ask themselves that, if we need the display to magically bend linear light code values to a nonlinear encoding to support our million-year-old perceptual systems, why don’t we require some sort of magical goggles to do this for us when we look out a window? Alas, here we are, capable of looking outside of a window perfectly fine without our Meatball-Idiot-Filter-Out-The-Reality-Through-Magic-Goggle devices…

Let’s give a quick outline as to what we know, and we’ll use an image because well… no one has the time to read anymore, and article posts have more clicks when there are images.

![](https://hg2dc.com/wp-content/uploads/2019/07/acbf6-1z6jto3wx-94lr0zoicgoua.png)

Loose Overview of the Transforms Between Linear and Nonlinear Encodings

The first step is our scene, which is of course encoded with linear light. In the second step, we transform the scene to a nonlinear RGB encoding [[The Hitchhiker's Guide#^b0871e|3]] via a series of transfer functions in preparation for a particular display type. From there, the hardware in the display *undoes* the nonlinear encoding of the RGB code values via the display’s output transfer function and converts *that* result into linear light. From there, the linear light ratios are handed off to our perceptual system, which expects linear light ratios to function properly. [[The Hitchhiker's Guide#^8dbb7f|4]] And the crazy nonlinearities begin inside our perceptual system… ^437cef

The obvious question is “Why not just cut out the second step where we nonlinearly encode the scene and use linear light code values the whole way?” We have already established that the math works vastly better on linear light code values, so why not just keep the entire chain linear light?

---

![](https://hg2dc.com/wp-content/uploads/2019/07/df856-1jvbxoofk5kol2v7hxhrxhw.png)

Linear light as compared to our nonlinear internal processing of the linear light

The above image shows a loose idea as to what happens if we uniformly divided up the linear light representation of a given scene / image into increments and mapped what those increments to what we end up using / seeing from *inside* our adapted perceptual systems. That is, plenty of the arrows end up stacking up on the right side; our perceptual systems internally bend the received linear light into a nonlinear representation, [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|as we hinted at in Question #7]]. Our perceptual systems sort of have a built-in transfer function too!

If we used a linear light encoding as a transfer function, plenty of those values would be “wasted” in the final product; our perceptual system wouldn’t bother to differentiate between some of the values, and we’d barely be able to see the differences, if at all, in some of the range of the values. Plenty of the linear light values towards the right side of our measurements would end up collapsed into an identical looking perceptual system experience. While the image would display perfectly fine on our mythical linear light display, the additional code values might as well not be there if the intention is to *optimize* the encoding!

Instead, what would happen if we used a series of code values that was optimized for the important values our perceptual system will end up “seeing”? What if we exploited the nonlinearities of our complex perceptual systems to *compress* the data range by throwing out certain “redundant” code values from the linear light representation?

![](https://hg2dc.com/wp-content/uploads/2019/07/0d55d-1gzfawarouivsxf25actgsa.png)

Note the position of the two transfer functions in the code value to display pipeline

So we’ve done a bunch of work and effort, but we haven’t changed much from the input linear light to the output. Or have we?

---

Back at [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|Question #7]] we hinted that transfer functions play a crucial role in the lives of digital artists. As many of you might have inferred, there are many types of transfer functions that facilitate different needs. As we drill down into the meat and bones of digital RGB colour, we can see that when it comes to displays and certain RGB encodings, some transfer functions are directly related to how a display expects data to be encoded; the transfer functions describe the characteristics of the light emission from code values. sRGB is one such display referred encoding, and indeed the transfer function we encode the RGB values with is the transfer function that an ideal sRGB display uses to decode the values back to linear light ratios. And that leads us to the answer of our question:

**Answer #9: Using a transfer function to nonlinearly encode data in accordance with a display referred output is nothing more than a compression scheme; it removes code values from the range of values that are redundant for our perceptual systems.**

If we devised a DCC application and display hardware pipeline with purely linear code values from manipulation to linear light output ratios at the display, we’d be wasting bits at the end of the pipeline that our perceptual systems wouldn’t “see”. That website you designed would be gobbling up around 25% more bits, and gobbling up bandwidth when saved on disk or being shipped out over the internet. As a compression scheme, nonlinear encodings can be tremendously efficient, with a reasonable degree of trade-off for loss of data. Indeed, the secret of transfer functions unlocks how higher end industrial motion picture cameras manage to cram the scene’s light ratios into a smaller parcel efficiently!

---

The next time you look at an RGB image, it has hopefully become clear that the contemporary digital artist should be aware of it’s particular encoding. What transfer function does it use? If you want to have the goodness of linear light manipulations, or even simply send it out to a display as you intended your work to be seen, it’s imperative that the image is encoded in such a way that the display’s hardware or software based transfer function will decode it correctly. Only with the proper encoding will the correct ratios of linear light be output for the audience on their intended display. If your encoding doesn’t properly match the context, you can expect contrast or other things to be completely off in one case, and your entire chain of manipulations off in another.

Digging more deeply into that however, will have to wait for  [[The Hitchhiker's Guide#Question 11 How the F *ck Can We Talk About “Colour”?|a few more questions…]]

---

1. As with all things colour and transfer functions, I’ve linked you to none other than Dr. Charles Poynton’s article, which as a nice little blurb on the transformation of electricity into light near the end of the PDF. I’d also like to take this moment to give a shoutout to Dr. Poynton, who has always managed to find time to answer this rando idiot’s questions about the peculiarities of digital signals and other such dark and arcane things. There are other luminaries who we will come across, and Dr. Poynton is indeed one of the deities in the Colour Pantheon. [[The Hitchhiker's Guide#^85cb77|↩︎]] ^6d9b66

2. The important part of the nonlinear response of a CRT was due to the control grid. Historically, it happened that the nonlinear code values supplied “just worked”, and were a useful feature that ties in with the answer to this post. [[The Hitchhiker's Guide#^85cb77|↩︎]] ^f58a2d

3. The reader who has spotted that the heading reads “Nonlinear Transfer Functions” in the plural form will be rewarded in the future. This wasn’t a mistake, and you get a cookie for spotting it. [[The Hitchhiker's Guide#^437cef|↩︎]] ^b0871e

4. Labelling our perceptual system as requiring a “Linear Light Transfer Function” isn’t exactly the most biologically terrific description, but hopefully reusing the concept around transfer functions can help you grasp the nature of the ratios more clearly; our perceptual system only works with linear light, even if it internally interprets and bends that linear light into something more useful for our perceptual systems. [[The Hitchhiker's Guide#^437cef|↩︎]] ^8dbb7f



 
# Question #11: How the F\*ck Can We Talk About “Colour”?

Given we’ve hit a milestone in that we are approaching the teens in our question count, the time has come to start diving into the murky side of digital colour for all of you lovely pixel pusher types. Up to now, you’ve probably noticed that we have successfully managed to avoid the sticky subject like parents not wanting to talk about the birds and the bees with their children. That time has come to pass as we head into our teens…

We’ve established that [[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|RGB code values]] are [[The Hitchhiker's Guide#Question 2 What the F *ck Does 0.6 Mean?|meaningless]] when considered alone. We took a dive into [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|what they represent]], [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|what formulas they follow]], and what the ground truth the code values [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|relate to are]]. But all that time we’ve also managed to avoid discussing how the hell we can actually talk about colour in a meaningful numbers sort of way. So, let’s set the stage:

**Question #11: How can we discuss “colour” in an absolute manner for the folks who have to use digital colour?**

The good news is the answer leads us to a singular thing that absolutely everything “colour” is built atop of. [[The Hitchhiker's Guide#^f26764|1]] The bad news is that there’s plenty of things built atop of it, and those layers end up as a confusing and complex soup when the foundational concepts are unclear. To that end, let’s try to be as rudimentary as we can… ^1e2c8a

---

As discussed in previous articles, we’ve trod over that thing that many folks who are familiar with creative digital work have probably known all along; colour is damn complex. That is, when we consider our perceptual systems as a whole, they are constantly adapting and doing all sorts of crazy things. This is why when we use the term [*colour*](http://cie.co.at/eilvterm/17-22-040), we are stepping into a field covered in land mines. As we have learned, colour is [*psychophysical*](http://cie.co.at/eilvterm/17-23-001), and we sure as hell aren’t going to learn much wading into those waters when we want to focus on the basics of RGB colour.

Instead, we need something more practical for us to discuss with numbers. We have discussed how our code values relate to intensity and linear radiometric light energy but we haven’t crossed into a model to discuss the actual “colour” of the light in question. It’s hard to discuss what colour the RGB light is that we are adjusting code values for if we don’t have a meaningful model and metric.

---

Everyone likely already knows that there’s this crazy physical thing [called radiant energy](https://energyeducation.ca/encyclopedia/Radiant_energy). If we took the whole shebang, the radiant energy scale would be a long range of things that aren’t of too much of a concern to us when discussing digital colour. In fact, what we are wanting to focus on here is a small sliver of the entire range of radiant energy called visible light energy. It’s the thin slice of the entire radiometric range that “standard”, average visioned people can “see” with their perceptual systems.

![](https://hg2dc.com/wp-content/uploads/2019/09/21eee-07tpup_gc8fwgvnwz.png)

Image of the visible spectrum from [the radiant energy entry at energyeducation.ca](https://energyeducation.ca/encyclopedia/Radiant_energy)

If we focus only on the visible spectrum from the above image, we can see that there are some small numbers above it, ranging from 380 to 750. That loosely represents the range of wavelengths that are visible to “standard”, average observers. If we were to divide up that scale into single nanometers, or even partial nanometers, we could consider the “colour” of each of those slices as the “colour” that we’d see when looking at a very narrow sharp band of a laser of a particular wavelength; [[The Hitchhiker's Guide#^57d8b6|2]] *it’s the most “saturated” “colour” we could see of that particular flavour*. While we could vary the radiant energy of the laser in question, there would be nothing more “saturated” than the purest of laser lights represented within that thin wavelength. ^76848d

---

So how can we talk about “colour” if it is this crazy adaptive thing? How can we discuss digital RGB for creative folks in a manner that everyone can at least share values and numbers that mean things in an absolute sense? How can we even begin to discuss “saturation” if we don’t have a guiding map?

The answer comes from what is known as the CIE 1931 colour space. It is a culmination of research from the decades that preceded it, from a number of very experienced minds. Rest assured, whenever you see any colour encoding model such as CIE Lab, RGB, YCbCr, or any of the other nonsensical mumbo jumbo terms out there, **they** **all derive from that magical CIE 1931 entry point**.

So let’s answer our question in a way that is suitable, without getting too knee deep into sludge…

**Answer #11: The qualia of a given mixture of visible light is quantifiable in an absolute sense using the model that maps visible light spectra to chromaticities, which starts with the CIE 1931 colour space model.**

The key takeaway here is that the CIE 1931 colour space model glues the visible spectrum of laser-like wavelengths to a human oriented concept known as chromaticity in a single, convenient model. Further, it lays a critically important metric of numbers down, allowing us to discuss chromaticities using absolute values.

We first hit the term chromaticity back in [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|Question #3]], but we tip-toed around defining what it actually is. Up to that point, we’ve been rather careful to say the word “colour”, and yet not been able to discuss whatever it means in an absolute sense. That is, “colour” is a slippery term that dives deeply into contextual elements, while [*chromaticity*](http://cie.co.at/eilvterm/17-23-052) on the other hand, [is very clear and very absolute, relative to a specific model](http://cie.co.at/eilvterm/17-23-053).

---

And that brings this installment to a close! We haven’t really investigated just what chromaticity coordinates are, how the CIE 1931 model works, nor any of that stuff. What we have done though is flesh out the term chromaticity such that we are now able to discuss uh… that… uh… thing sort of kind of loosely described as “colour” in a way that is unambiguous. So while we have many relative colour encoding models such as RGB, with their endless supply of transfer functions and what not, we now have an absolute model to discuss the actual visible light qualia side of things.This will serve us extremely well in the  [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|lines of investigation to follow…]]

---

1. Don’t let the WANKers get you down here. Lab, YCbCr, RGB, Luv, Jab, and all those other crazy terms *all* derive from this magical bit of work in 1931. **All** of the other colour encoding models and various tidbits are nothing more than structures built on top of the CIE 1931 colour space. It’s single handedly **the most important model to learn and understand for a digital image maker**. [[The Hitchhiker's Guide#^1e2c8a|↩︎]] ^f26764

2. The crappy image is of course not actually the visible spectrum, but rather an sRGB downgraded artistic representation projected out of your display. You’ll also notice that the thing goes from some darkness to some colours and then back to some darkness. [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|This is]] in fact a complex thing to explain at this point, but worth noting: chromaticities are not equally “light” relative to each other. Heavily saturated blues can be very “dark” compared to heavily saturated greens at equal radiant energy! Damn that psychophysical rubbish… [[The Hitchhiker's Guide#^76848d|↩︎]] ^57d8b6



 
# Question #12: How the F\*ck Can We Talk About Light “Intensity”?

Brighter? Lighter? More light? Less light? Where the hell does physics and energy fit into all of this? Arrgh.

If we don’t have a clear grasp on what linear means and it’s relationship to digital colour, we are going to have a hard time discussing deeper subjects. So what the hell is happening when we slide those RGB sliders like we asked back at [[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|Question #1]]? We can sort of [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|understand]] that the code value representation is bound to some notion of a ground truth of “linear light energy”, but just what the hell is that?

Given you are all likely digital pixel pushers and image smiths, let’s make this simple and start with an image. It’s a quiz of sorts, and a not-super-challenging one at that…

![](https://hg2dc.com/wp-content/uploads/2019/11/3bfc5-1ciubudgzubbeqcolkltnea.png)

**FIGURE WHAT IS LIGHTER** Which square appears “brighter”?

And now, the question…

**Question #12: How can we describe light intensity?**

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

**Answer #12: There are two useful axes to discuss the intensity of light; radiant energy is a ratio of physical energy required to generate an emission, and luminance is a photometric measure of how much perceptual energy the light holds relative to our psychophysical systems.**

That means that we could have a very saturated blue laser at equal input radiant energy to a green laser, and the green laser will appear vastly more luminous than the blue. There’s a whole model that describes the relationship between luminance and radiant energy of the various visible light spectra, but we won’t bore you with those details just yet, even though we have sort of let the cat out of the bag in the  [[The Hitchhiker's Guide#Question 11 How the F *ck Can We Talk About “Colour”?|previous post]].

As a pixel pusher, you are likely more interested to learn if we’ve uncovered anything useful here when thinking about our digital colour work. The relationship between the visible light wavelengths and how much perceptually luminous the energy will appear is described in the following [luminous efficacy](http://cie.co.at/eilvterm/17-21-035) diagram.

![](https://hg2dc.com/wp-content/uploads/2020/01/luminous-efficacy.png?w=640)

**FIGURE LUMINOUS WTF** The plot of how the various visible wavelengths contribute to perceptually luminous energy, also known as a *[luminous efficacy](http://cie.co.at/eilvterm/17-21-035)* plot.

So if you are wondering if we can apply this knowledge to pixel pushing, the answer is of course yes! For all intents and purposes, we can consider the linear RGB values after we remove the nonlinear encoding for a particular transfer function, to be the *radiant energy ratios*. We need to use colour science math [[The Hitchhiker's Guide#^e30bcd|1]] to derive the *luminous perceptual energy ratios*, which is a fancy way of describing a greyscale image. So how do we convert a colour to a greyscale representation of the coloured light value? Great question… ^2c9bbe

---

In order to convert a coloured RGB pixel into a greyscale pixel, we know that we need to set each of the red, green, and blue channels to some identical value, otherwise the pixel will have a colour cast. When we set the pixel to have equal code values, the output colour of the light will appear achromatic if we are fully adapted to the “white colour” of the display. But how do we figure out just what to set the RGB values to when we are converting from a coloured pixel to an equivalent greyscale pixel?

![](https://hg2dc.com/wp-content/uploads/2019/11/3bfc5-1ciubudgzubbeqcolkltnea.png?w=580)

**FIGURE WHAT IS LIGHTER AGAIN** The three sRGB lights projected at 100% emission.

In the above image, we have three RGB swatches, each at 100% emission of the (assumed) sRGB display’s red, green, and blue lights. How do we convert those swatches to greyscale? We know that from a radiant energy perspective, each value in our triplet is outputting roughly the same display emission energy, just out of the individual lights. Great, so why not just set each of the RGB code values to 100% then, if the individual channels are set to 100%?

Wait a minute… they don’t appear to be the same *perceptual energy* when they are in colour, so setting the red, green, and blue swatches each to 100% RGB emission will make them appear identical to each other! That’s not going to work, is it? The green doesn’t look like 100% RGB emission, and the red and blue certainly don’t!

![](https://hg2dc.com/wp-content/uploads/2020/01/greyscale-overlay-wrong.png?w=1000)

Taking 33% of each emission level doesn’t work!

The solution to the problem, as you may have inferred, is that we need to “weight” each of the emission strengths based on their respective coloured light contributions to the *luminous perceptual energy.* We can’t use *equal ratios of the RGB radiant energy values*.

We aren’t going to get lost in math here, so let’s just accept that for REC.709 / sRGB based RGB lights, the luminance ratios are roughly 21.26% red, 71.52% green, and 7.22% blue, which we then sum together. [[The Hitchhiker's Guide#^9b959c|2]] The green light in an sRGB / REC.709 display contributes 71.52%, the red 21.26%, and the blue 7.22% to the overall greyscale result. If we do that, the resulting achromatic pixel will *appear to have the same luminous perceptual energy as the swatch had when it was in colour* [[The Hitchhiker's Guide#^4dde38|3]] ! The result is below. ^88aeb1

![](https://hg2dc.com/wp-content/uploads/2020/01/greyscale-overlay.png?w=1000)

**FIGURE KINDA GREY** Properly converted to greyscale based on the sRGB primary light contributions to luminance, and converted to their nonlinear sRGB code values.

And with that, we’ve closed another chapter. Hopefully it didn’t hurt your head too much, and you’ve managed to add a little more clarity to discussions of light “intensity”. A handy question to ask is whether the value is trying to describe physical radiant energy or perceptual luminous energy? [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|On to the next question…]]

---

1. Whoo daddy there is no shortage of people “helping” other people out there on those question and answer sites who screw this up royally. Let’s be painfully clear; the luminance coefficients are derived from the chromaticity of the light mixture. That means that for any given colourspace, with a set of three fixed primary lights, there is precisely *one* correct method to derive the luminance coefficients. Those online sites throw numbers around that are frequently historical artifacts that are completely and utterly wrong given the context in this decade and into the next. The TL;DR is that you should be extremely weary of deriving luminance coefficients from online sites if you are building software. The other TL;DR is that there are plenty of folks utterly confused about digital colour out there apparently. Be warned. Trust no one. Including this idiot⁴. This is a **very** deep rabbit hole, however. For further reading on the subject of “colourful” as “brightness”, consider Ralph Evans “The Perception of Color” 1974, or skimming over [the Helmholtz–Kohlrausch effect entry over at Wikipedia](https://en.wikipedia.org/wiki/Helmholtz%E2%80%93Kohlrausch_effect). [[The Hitchhiker's Guide#^2c9bbe|↩︎]]  ^e30bcd

2. The astute reader will likely have a question or two about whether you should calculate the result based off of the display linear or the display nonlinear code values, and she’d be right for thinking there will be a difference. This is also why there are two terms typically for the linear versus nonlinear calculations, *luminance* and *luma*, where *luminance* typically refers to calculations derived from the linear light energy code values, and *luma* referring to the greyscale calculation based off of the nonlinearly encoded code values. I’ll leave you to ponder that question on your own, and perhaps try to deduce which version is more “correct”. [[The Hitchhiker's Guide#^88aeb1|↩︎]]  ^9b959c

3. It should be duly noted that, as always, colour is a complex psychophysical sensation. As such, there are a myriad of psychophysical effects that cannot be accounted for with a pure luminance based evaluation of spectra. In particular, the [Helmholtz–Kohlrausch phenomenon](http://cie.co.at/eilvterm/17-22-066) cited above plays a large role in determining overall sensations of luminance, for example. [[The Hitchhiker's Guide#^88aeb1|↩︎]]  ^4dde38

4. Always fact check. The keen colour science folks will note that the post uses “lightness” here, where many folks might flip flop between lightness and brightness, using the two terms interchangeably. In terms of [Colour Appearance Model](http://eilv.cie.co.at/term/200) language, the two terms are specific and unique. As always, there’s a risk of losing the audience, and “lightness” was chosen as the means of communication. Also note that footnote 4 is a meta footnote of a footnote. It’s an Inception footnote.



 
# Question #13: What the F\*ck is a Chromaticity?

Another big word for someone who likely only wants to focus on painting on their iPad Pro. The bad news is that exploring new terms takes time and energy. The good news is that there is likely no more an important term for a pixel pusher to learn. Why haven’t you heard of it before? That’s a great question, but if you’ve followed along this series, it probably doesn’t surprise you.

---

Looping over things we’ve explored, we have learned [[The Hitchhiker's Guide#Question 5 What the F *ck does 0.5 mean?|that code values]] frequently are encoded and [[The Hitchhiker's Guide#Question 9 Why the F *ck is Linear Light Important for a Digital Artist?|sometimes]] even manipulated nonlinearly, according to [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|some transfer function]]. We also have learned [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|that]] the primary basis RGB lights never change their “colour”, and merely [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|increase or decrease in intensity]]. In order to get into exploring how different displays and colour spaces impact your digital work, we will need to tighten down our understanding on this last sentence. That is, to discuss “colour”, we need to investigate perhaps the most important colour science term called *chromaticity* a bit more…

**Question #13: What is a chromaticity?**

Given you are all folks interested in images, let’s plop one of those here. You will likely have seen this strange looking thing before…

![](https://hg2dc.com/wp-content/uploads/2019/12/73db7-11zt7bhif8p8bkgeue_ob4a.png)

**FIGURE WTF A**: What the f\*ck is this thing? And what’s the f\*cking triangle? [[The Hitchhiker's Guide#^861a84|1]] ^6dc3a2

So now that we’ve gotten the obligatory “This idiot must show you this stupid drawing so that you trust what they are typing on about” out of the way, let’s actually try to understand what the diagram is and, more importantly, what it *means* to you, as a pixel pusher.

I’d like to apologize. I can already feel you tuning out. Some person you thought who understood this sh\*t tried to explain that cursed image in some blog post, or some forum, or some random website on the infosupahighway. You are here likely because the “explanation” wasn’t… uh… an explanation that made much sense to you.

I completely understand. You’ve come this far though, so hopefully you have built up enough faith and can feel that all of this is building up your digital colour understanding. So chin up, and take the punch…

---

**FIGURE WTF A** is what is known as the [*CIE 1931 Chromaticity Diagram*](http://cie.co.at/eilvterm/17-23-045)*.* It is *helluva* important in your overall understanding of digital colour. Remember how in [[The Hitchhiker's Guide#Question 11 How the F *ck Can We Talk About “Colour”?|Question #11]] we said that everything colour related starts with that CIE 1931 thing? It’s true!

The first note worth pointing out is that the whole shape in **FIGURE WTF A** is a byproduct of that critical CIE 1931 work, and everything RGB, as well as anything you’ve ever done regarding printing in CMYK or anything else, relates directly back to it!

But just *what the hell does it represent?*

---

Observe that in **FIGURE WTF A** there is a strange oblong shape with a flat bottom. A critical introductory revelation is that *the cake is a lie*; *the literal colours displayed within it are pure garbage*. They are sort of like looking at a city map and understanding that millions of tiny little people don’t live inside of the markings, and that the names and positions aren’t actually the places. The colours are just sort of a creative rendering. The bulls\*it colour zone is graphically outlined in blue in **FIGURE LESS WTF B** below.

![](https://hg2dc.com/wp-content/uploads/2019/12/7f8fc-13pjsbztwangqs7vgx0vu1g.png)

**FIGURE LESS WTF B**: The colours inside the blue are sRGB colours that represent roughly where the chromaticity mixtures reside. Your display isn’t made up of lasers, so it can’t come close to displaying the actual full spectral locus area outlined in this figure.

But what about the shape itself? Why is it wonky?

If you trace your mouse or finger along the outside of the curved portion of the shape, where does this particular shape come from? The answer is, again, that damn CIE 1931 magic stuff. But what does that shape *represent*? That shape is known as the [*spectral or spectrum locus*](http://cie.co.at/eilvterm/17-23-056). That is, that infinitely thin line represents all of the colours of the visible spectrum, peeled apart into their components. The little numbers around the outside represent the [*wavelengths of visible light*](http://cie.co.at/eilvterm/17-21-003) *in nanometers, aka a really, really, really small part of a meter that describes the chromaticity, or more loosely “colour” [[The Hitchhiker's Guide#^658a86|2]] of the light.* ^18829d

![](https://hg2dc.com/wp-content/uploads/2019/12/98524-1qzbsyzikezuyk8cdf8qvhg.png)

**FIGURE LESS WTF C**: The purple line and purple arrows represent the visible wavelengths. Notice how there are no wavelengths mapped along the bottom straight edge!

Think of that thin black line overlaid in purple above in **FIGURE LESS WTF C** as an infinite number of little tiny lasers of completely different colours. That vibrant green laser you bought for nine dollars from Amazon? Chances are it has a very unique monochromatic wavelength specified on the side on a crappy sticker somewhere around the 500nm range. The red laser? It too will have a specific wavelength, but reds are somewhere above the 600nm range. Blue lasers? Maybe somewhere below the 470nm range. The thing about visible light spectra is that they represent the most heavily saturated isolated light hue a standard observer [[The Hitchhiker's Guide#^8708fa|3]] can see. You can’t go north of north with wavelengths of light, and there is simply no more saturated a chromaticity than viewing a single slice of a wavelength of light. ^9b0c17

Notice the straight edge that isn’t highlighted? It isn’t highlighted because no single purely spectral wavelength corresponds to that line. That means that no, you can’t buy a pure magenta laser of some single wavelength from Amazon, sorry. That straight, infinitely thin edge can only be achieved *by mixing pure spectra, as no single spectra represents those perceived colours.*

The final “gee whiz moment” may be to appreciate that if we have an infinite number of little lights, just like way back at [[The Hitchhiker's Guide#Question 1 What the F *ck Happens When We Change an RGB Slider Value?|Question #1]], you should now realize that the bulls\*it colours represented inside *represent all of the possible mixtures of the visible light wavelengths*, plotted out using some alien, human massaged, number system. Mix any combination of lasers, and you end up somewhere inside that ever important diagram! Project a pure laser out of… well… a laser, and you are projecting out a light that has a chromaticity somewhere around that purple outlined region in **FIGURE LESS WTF C**!

---

If we are making a map, we need some sort of unit that we can plop along the bottom or top of the map. Some maps use imperial measurements, while more sane maps might use a metric measurement. Some maps include north, south, east, and west. This map? It uses north, south, east, and west too, only it doesn’t call the coordinates that. The east to west metric is **x** on the chromaticity diagram, with **y** being north and south. This particular map is the [*CIE 1931 chromaticity diagram*](http://cie.co.at/eilvterm/17-23-045), with lowercase x and y being the cardinal directions.

Critical point worth noting here is that if someone gives you two chromaticity coordinates using x and y, there is absolutely no ambiguity as to what chromaticity they are speaking of; those values are absolute and every single “colour” the “standard observer” “sees”, can be identified on the CIE xy map. If that x and y coordinate is coupled with a Y, you have a precise definition of a single chromaticity, at a given luminance. [[The Hitchhiker's Guide#^c8ade7|4]] Recognize that last term? You had better not already forgotten the [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|last article…]] ^f00949

Now we have the map, we understand what it means, and we have some useful numbers via x and y [[The Hitchhiker's Guide#^2c4238|5]] that are bound to visible wavelengths of light. ^b0227b

---

**Answer #13: A** [**chromaticity**](http://cie.co.at/eilvterm/17-23-052) **is expressed on what is likely the most important coordinate system you will learn as a digital artist. A chromaticity is a coordinate that defines a mixture of visible light within an absolute encoding model. It is the crucial mapping of visible light spectra to how a standard observer’s perceptual system is stimulated.**

Literally every shred of colour stuff you are exposed to relates to chromaticities and that CIE coordinate system that [[The Hitchhiker's Guide#Question 11 How the F *ck Can We Talk About “Colour”?|we scratched the surface on in Question #11]], and fleshed out a bit more here. Don’t believe me though, dig around a little bit in whatever area of colour you are looking at and you can be assured you’ll find it. Hopefully now it actually makes a little bit more sense to you. And with that statement, a warning… [[The Hitchhiker's Guide#^0755f6|6]] ^4d21ea

> In short, the uses of such illustrations probably should be confined to making lovely wall decorations in places that never will be visited by budding color scientists and engineers.
> 
> [Digital Color Management: Encoding Solutions](https://www.wiley.com/en-ca/Digital+Color+Management:+Encoding+Solutions,+2nd+Edition-p-9780470512449)

You’ve probably seen some other “lovely wall decorations” too, and you might even know they are somehow related to this one. But that triangle?! What about the triangle?! What about terms like [perceptually uniform](http://cie.co.at/eilvterm/17-23-071) or some such!? Those things are damn close to understanding now, but they will have to wait [[The Hitchhiker's Guide#Question 14 What the F *ck is “White”?|for another question or two…]]

---

1. All of the imagery here has been flagrantly poached from the more than beyond awesome colour science library called [Colour](https://colour-science.org/). It’s an incredible library for Python created by incredible minds. Shout out to the creator Thomas Mansencal and the most elite code value guru Nick Shaw. I can’t stress how invaluable the library is, and how excellent the people who frequent the channel are. They are wise wizards of the highest colour science order. [[The Hitchhiker's Guide#^6dc3a2|↩︎]] ^861a84

2. SPOILER ALERT: You may have noticed that the words “colour” and “chromaticity” get tossed around here with a little bit of a sloppy approach. This has been on purpose, as the two words are tightly related. With that said, it’s prudent to perhaps break down the extremely complex idea of *colour* as representing the entire psychophysical phenomena of visible light experience, while *chromaticity* represents a very firm colour science model. [[The Hitchhiker's Guide#^18829d|↩︎]] ^658a86

3. You may have noticed *standard observer* littered all over. Why? Because all of this crap is totally bunko if the thing to which it refers is not a standard observer as defined by the CIE 1931 and onward models. Folks can have different vision sensations due to biological and genetic things, and for them, these models aren’t accurate. There is some work that tries to map these sorts of sensations to the existing models, but it’s safe to say that when the observer is no longer a member of the *standard observer* sample set, that all bets are off! [[The Hitchhiker's Guide#^9b0c17|↩︎]] ^8708fa

4. There is a “height” that isn’t presented on this map. It is in fact Y, or luminance as you may recall from [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|Question #12]]. That’s right, the CIE was wise enough to build a new “three imaginary light” model from their experiments, and somehow magically glued visible physical wavelengths into the psychophysical domain via Y. The CIE xyY chromaticity diagram is that monumentally important CIE XYZ model, scaled down to “fit” the zero to one range for X and Y, which is why they are lowercase, representing the same yet somehow different representation of XYZ! [[The Hitchhiker's Guide#^f00949|↩︎]] ^c8ade7

5. Because x and y are simply scaled versions of their big brothers X and Y from the CIE 1931 work, and because the formula is dead simple involving all three imaginary lights X, Y, and Z, you can in fact derive the original XYZ triplet from a single xyY triplet. That means for all intents and purposes, if you communicate a chromaticity via xyY, you are *also* simultaneously communicating an absolute XYZ value. XYZ is the CIE’s magical-three-physically-impossibly-non-existent-colour-yet-works-in-math-model derived in that important 1931 release. [[The Hitchhiker's Guide#^b0227b|↩︎]] ^2c4238

6. Edward J Giorgianni and Thomas E Madden make in [Digital Color Management: Encoding Solutions](https://www.wiley.com/en-ca/Digital+Color+Management:+Encoding+Solutions,+2nd+Edition-p-9780470512449): [[The Hitchhiker's Guide#^4d21ea|↩︎]] ^0755f6

> Odysseus had to go to great lengths to keep his sailors from being bewitched by the sirens. Similarly, people who want to specify color appearance with numbers must be wary of chromaticity diagrams with lovely colors on them. Such illustrations as this tend to imply (or the viewer tends to infer) that a particular perceived color is associated with a particular point on the diagram. This is false!
> 
> The chromaticity diagram is a stimulus specification. A given color perception can be elicited by a stimulus represented by just about any point on the chromaticity diagram, depending on the nature of the visual field and the viewer’s state of adaptation.
> 
> **Although a colored rendition of a chromaticity diagram does, perhaps, help to indicate to a novice that with a common illuminant, blue paint will have a chromaticity in the lower left, etc., that novice is likely to jump to all the wrong conclusions and consequently find the world of color very confusing**.
> 
> In short, the uses of such illustrations probably should be confined to making lovely wall decorations in places that never will be visited by budding color scientists and engineers.
> 
> [Digital Color Management: Encoding Solutions](https://www.wiley.com/en-ca/Digital+Color+Management:+Encoding+Solutions,+2nd+Edition-p-9780470512449)



 
# Question #14: What the F\*ck is “White”?

Phew. It’s been quite a few questions to be able to finally, just about, almost, kinda, sorta discuss what is “white”. The key here is to attach “white” to terms that will not only make sense to you, the happy pixel pusher, but also be able to discuss it in ways that apply to your digital image work.

Why does that colour science stuff matter? Because that’s how we take our creative pixels and migrate them from one medium to another. For pixel pushers, that’s how we get from numbers to what we see.

That short film you’ve spend months or years on getting to YouTube without looking like it has an orange tint? Colour science around “white”. The advertising print run of ten thousand pieces not ending up speckled with blue dots where no ink white paper should be? Colour science around “white”. That nice graphic you designed for your YouTube influencer channel not skewing blue on the web? Colour science around “white”. Even the most simple case of taking an encoded and compressed nonlinear code value generic image file and displaying it correctly? Colour science around “white”.

Seems like an important question, so…

**Question #14: What is “white”?**

---

You might be wondering why we’ve waited until Question #14 to tackle the idea of “white”. The truth is, we couldn’t answer this in any useful way without plenty of foundation!

- That invaluable bit of ground truth regarding radiometric light ratios in [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|Question #7]] is the rock that our perceptual system is anchored to.
- The connection between radiometric energy and our perceptual systems interpretation of that spectral energy as discussed in [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|Question #12]]. Plenty of tone ranges will appear without colour, but the one that appears as our reference of “white” will likely be one of the more luminous values that we’ve adapted to.
- The glue that binds your display’s radiometric ratios of linear light to its particular nonlinear encrypted compression is discussed in [[The Hitchhiker's Guide#Question 6 What the F *ck is a Transfer Function?|Question #6’s transfer function]]. What is “white” in the file with regard to the output context is a direct result of the transfer functions at work!
- The critical work that was released in 1931 by the CIE that amounted to the wonderful model we hinted at in [[The Hitchhiker's Guide#Question 11 How the F *ck Can We Talk About “Colour”?|Question #11]] is the foundation for being able to be able to talk about “white” at all.
- The absolute numerical values related to the CIE 1931 model discussed in [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|Question #13]] permits us to discuss different “whites”, compare and contrast them, and even adapt them!

That is a lot of ground to be able to discuss just what “white” is. Heck, it’s not a stretch to suggest that the entire series so far relates to ideas around “white”.

---

As we learned in [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|Question #13]], we can discuss colour in relation to physical spectral mixtures. As we learned, the canonized and referential absolute mapping is a means of plotting visible light spectra to  [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|useful numbers]]. Given it covers all visible light spectra, no mixture of visible light exists beyond its limits. That means that “white” isn’t some mystical narwhal unicorn that lives in the clouds somewhere else. Anything we call “white” will be a mixture of visible spectra and, as a result, be on that map!

But wait… some colours look like colours, and other colours… well… don’t look like colours. They look as though they are without colour, or [achromatic](http://cie.co.at/eilvterm/17-22-049).

As you may have guessed, the idea of “whiteness” is indeed related to colours and chromaticities, which tells us that an idea of “whiteness” is a psychophysical bit of magic around perceptual [chromatic adaptation](http://cie.co.at/eilvterm/17-22-013).

---

If you have ever walked inside of a large department store after having walked around outside during the day, you may have noticed something interesting regarding “white”. From the outside of the store, your field of view was largely lit by the daylight sky. Typically, even with a cloud cover, the light is biased towards the bluer wavelengths of spectral mixtures. Inside, quite a few department stores use those long fluorescent tubes, which while they can cover a varying range of spectral output, they tend to be biased toward yellowy-orangey spectral mixtures.

If we start outside the store, our constantly shifting perceptual systems will have [fully adapted](http://cie.co.at/eilvterm/17-23-081) to the blue weighted spectral mixture of light coming from the sky and clouds. This means that our perception of an achromatic object or light will be relative to that blueish spectral composition. Our perceptual systems will “dial” the actual spectral blue tint out such that it will create that sensation of not having any colour. So what happens to the rest of the scene?

When our perceptual systems adapt to a neutral achromatic axis it does something truly remarkable; *it shifts, bends, warps, and adjusts every single spectral combination in our field of view*. The entire rest of our colour sensation will be skewed to that adaptation! If we were to plot all of the colours in the scene to chromaticities, *all* chromaticities will appear to have shifted around [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|the chromaticity diagram]] after our perceptual system has processed them!

As we look inside the store, the fluorescent tube lighting looks rather yellowy-orangey from the outside. But what happens when we walk inside…

---

As we transition to inside the store, plenty of incredible things are happening within our perceptual systems. At first, the store will appear that yellow-orangey, and the outside will, if we check over our shoulder, still have “white” objects and lights.

After a few moments shopping for that ten pack of caffeine boosters to get you through that last video edit, you’ve found yourself realizing the label on the product is in fact… sort of “white”! You twirl around not realizing that while you were on the caffeine hunt that *the entire store appears perfectly normal*! Except… outside…

As you look from your fully adapted state inside the store, the outside scene through the store’s windows now looks distinctly blue twinged! You’ve fully adapted to the store’s illumination, and the outside is perceived relative to it. All of the chromaticities will appear to have shifted and changed invisibly, behind the scenes!

And in all of that magic, no such thing as “white” exists, only changing states of perceived achromatic “whiteness”.

---

So what is white?

**Answer #14: “White” is simply another mixture of visible spectral lights that our perceptual system has fully adapted to. As a colour, the idea of “white” has no grand, universal, absolute truth without considering the context of the observer. We can express the achromatic point on the CIE 1931 plot as a chromaticity.**

But wait! Does anyone know why this happens!? What the hell is showing when I set my RGB to 1.0 1.0 1.0?!? The lighting at my desk has an impact on my work on my iPad Pro then!?? How do I change my print run’s white to match the paper, because the five thousand copies are due tomorrow?! What about changing the colour temperature in my photograph to match the others in the set?!?! HELP!! 

[[The Hitchhiker's Guide#Question 15 What the F *ck is “Perceptually Uniform”?|More questions]] that will probably require more questions…



 
# Question #15: What the F\*ck is “Perceptually Uniform”?

We have laid some tremendously important groundwork in the most recent questions. Within that, even if you have seen or heard about the concepts introduced prior, it is helluva important to make sure that what we have explored is extremely clear. Sadly, the chromaticity diagram explored in [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|Question #13]] needs a bit of a revisit to help us out as we start talking about getting our work from one context to another.

So let’s have a bit of a deeper drill down into the chromaticity diagram…

---

Let’s get that ever-most-important diagram back fresh in your mind…

![](https://hg2dc.com/wp-content/uploads/2020/01/spectral-locus.png?w=640)

**FIGURE WTF 1931**: The CIE 1931 xy chromaticity diagram with the spectral locus plotted.

I can already hear you screaming out “WTF?” “Where did the colours go?” “Where’s the triangle?” I’ve plotted the diagram in **FIGURE WTF 1931** using [the colour wonk’s best toolkit “Colour”](https://colour-science.org/) without any confusing details.

1. The inside colour mixture gradient, as [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|we learned in Question #13]] can be quite confusing to newer folks. Your display can’t display all of the visible light wavelengths, so they have been removed.
2. The outer shape is what we want to focus on, which in the above image is an sRGB representation that *attempts* to give you a visual idea as to the colours of the respective wavelengths of visible light. Remember, given point 1. above, those colours are simply a vague approximation as your display isn’t projecting lasers out at you!
3. The inner triangle is gone. Even though this may be a familiar feature to this diagram, we aren’t quite ready to tackle what it means just yet. Darn close, just not quite…

Great. You already know all of this though, so why are we going over it again? Review is always great, but in this case, we need to *really* understand that the diagram is actually another “linear” plot. That is, *the plot is radiometrically uniform with respect to an observer*; the distances are all anchored in a physical energy relationship.

But as you will recall from [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|Question #7]], mixing humans with linear physics models is a great way to lose your marbles. [[The Hitchhiker's Guide#Question 7 What the F *ck Does “Linear” Mean?|In Question #7]], we hinted that standard observers do not experience a linear relationship with the radiometric intensities of light. Five times [[The Hitchhiker's Guide#Question 12 How the F *ck Can We Talk About Light “Intensity”?|the radiometric intensity of a light]] will not appear five times as *perceptually intense* to a standard observer. And guess what… standard observers also do not experience a nicely uniform relationship of sensations of “hue” or “saturation” with radiometric changes.

---

Somewhere around 1942, a number of people set out to model the nonlinearities between the physical wavelengths of visible light and the perceptual sensations observed in a standard observer. [David MacAdam](https://en.wikipedia.org/wiki/David_MacAdam) and others provided this critical bit of research, which ended up becoming known as [MacAdam Ellipses](https://en.wikipedia.org/wiki/MacAdam_ellipse)…

![](https://hg2dc.com/wp-content/uploads/2020/01/macadams-ellipses.png?w=640)

**FIGURE WTF ELLIPSES**: The MacAdam ellipses, which represent regions of chromaticities that create a sensation similar enough to appear equivalent perceptually.

You can see some teal coloured ellipses in **FIGURE WTF ELLIPSES**. The research showed that visible light spectra mixtures in those ellipses all appeared *virtually identical* within those mixture ranges. That is, the observers tested weren’t able to discern a noticeable difference between the radiometrically mixed quantities of visible light spectra; everything in the ellipses was for all intents and purposes the same “colour”.

At this point we realize that the ever important chromaticity diagram is entirely confusing in terms of its *dimensions*. It’s not a very good map to evaluate how *different* a particular mixture of visible light spectra is. How could we measure that? Of course, this is related to our question…

**Question #15: What does perceptually uniform mean?**

---

Imagine looking at map on your phone. You’ve walked about 1 cm on your phone’s map, and walked for about five minutes. But suddenly, the next 1 cm on your phone map took you thirty minutes, because it was straight up the side of a huge steeply inclined mountain. We could say that the map, relative to surface area, is nonlinear with regard to the overhead map. The 2D map is a misrepresentation of surface distance!

This is a similar handy analogy to remember when examining the CIE 1931 chromaticity diagram; it is not [perceptually uniform](http://eilv.cie.co.at/term/1369). That is, *the measurements we make with the chromaticity coordinates are not a useful metric for evaluating differences of a perceptual nature*. This is very similar to our above walking example, where there is a disconnect between the top down map on our phone and the surface distance that needs to be covered by foot.

Let’s cut to the chase and take a look at what one particular perceptually uniform-kinda-sorta-ish version of the CIE 1931 chromaticity diagram might look like…

![](https://hg2dc.com/wp-content/uploads/2020/01/macadam-1976ucs.png?w=640)

**FIGURE OH NO NOT ANOTHER PLOT**: The exact same MacAdam ellipses plotted in the CIE 1976 Uniform Colour Space.

Notice this is more or less the same spectral locus with the same ellipses in the earlier **FIGURE WTF ELLIPSES**. They aren’t quite as elliptical in **FIGURE OH NO NOT ANOTHER PLOT**, as the underlying CIE 1931 model is warped and bent in such a way to make the ellipses a little more uniformly shaped toward circular. Sorta. Kinda. Damn this perceptual rubbish…

**FIGURE OH NO NOT ANOTHER PLOT** is the [CIE’s 1976 remixed twist on the original CIE 1931 diagram](http://cie.co.at/eilvterm/17-23-074) that attempts to represent a more perceptually uniform variation of the original CIE 1931 diagram. It is known as the CIE 1976 Uniform Chromaticity Scale, and *scale* is very important here; the image is non-uniformly, or nonlinearly, scaled in an attempt to be more perceptually uniform.

Here, a measurement of a distance between two chromaticities on the CIE 1976 UCS is sort of, kind of, vaguely akin to *perceptual difference* for a standard observer. Because the underlying model is warped and bent, the **x** and **y** axes are transformed to new labels representing **u** and **v**. [[The Hitchhiker's Guide#^5c4151|1]] Project the wavelength mixtures of light and you get an idea as to how different they will be in relation to another mixture. ^336eec

In an ideal world, there would be some magical transformation of the CIE 1931 data that would make all of the MacAdam ellipses equally shaped circles, to make equivalent measurements uniformly different in the perceptual sense, *but no such transform has yet been created*.

---

**Answer #15: The term “perceptually uniform” refers to a means of comparing values with corresponding perceptual differences**.

I don’t know about you, but that’s about enough colour science mumbo jumbo for me for now. It is important to cover the term because you will now be able to discern between the plethora of different colour models out there, and have a greater insight as to why they are designed in different ways. You’ve also managed to stick another useful screwdriver into your artistic tool belt, and have hopefully started to appreciate that different colour encoding models can achieve different things.

Let’s see if we can build up our knowledge further to get to the nitty gritty details of practical artistic, creative, or batsh\*t-crazy-nutbar-remarkable digital work. We are almost there dear pixel pusher. [On to the next question…](https://hg2dc.com/question-16/)

---

1. You may have noticed that the **u** and **v** have little “prime” symbols to the right of each of them. In colour science things, the prime symbol typically denotes nonlinear with respect to the conventional linear plots and assumptions. Sometimes this nonlinearity is specified using a “star”, which in normal keyboard terms is an asterisk **\\**. [[The Hitchhiker's Guide#^336eec|↩︎]]  ^5c4151



 
# Question #16: What the F\*ck is the Triangle Thingy in the Chromaticity Diagram?

Recall back to [[The Hitchhiker's Guide#Question 13 What the F *ck is a Chromaticity?|Question #13]] where we explored how chromaticities are discussed. You may have wondered where that triangle went, and why I removed it in the subsequent diagrams in [[The Hitchhiker's Guide#Question 15 What the F *ck is “Perceptually Uniform”?|Question #15]].

Why did we have to learn about chromaticities instead of RGB values? Because, as you have hopefully learned from the preceding batch of questions, RGB is a *relative encoding model*, which means making comparisons becomes extremely confusing! How can we evaluate the Display P3 “green” value on your iPad Pro at 100% emission strength to the “green” value on one of your sRGB device, when the two values expressed in RGB are identical? We can’t!

Guess what? That leads us directly to the subject of our current question…

**Question #16: What is the triangle that appears commonly on a chromaticity diagram?**

---

The goal here in this back alley of the interwebs of colour debauchery, is for you, the pixel f\*cker [[The Hitchhiker's Guide#^5eecef|1]], to *completely* and *utterly* comprehend what is presented to you. So, let’s quickly recap a few important details about the CIE 1931 xy chromaticity diagram: ^4e9306

- The diagram is an invented model that lets us connect visible spectral light energy and mixtures to numbers.
- The xy chromaticity diagram uses a warped scale that is disconnected from how we perceive differences in the visible wavelengths of light.
- The diagram’s peculiar curved portion of the shape represents the visible light spectra in nanometers.
- The region outside the spectral locus does not exist in any physically meaningful way. It is only even given a shape due to the artificial model and the representations you have seen.

Let’s have a peek at the above summary on the diagram to reinforce understanding…

![](https://hg2dc.com/wp-content/uploads/2020/01/1931-recap.png?w=512)

**FIGURE OMFG NON-PERCEPTUAL SCALE**: A non perceptually uniform scale human crafted model of the wavelengths, represented in the upper vertical gradient portion, loosely visualized along the edge of the chromaticity diagram.

As you can see in **FIGURE OMFG NON-PERCEPTUAL SCALE**, the line of the visible spectrum wavelengths is not equally and uniformly distributed around the perimeter of the spectral locus; a standard observer does not sense all wavelengths in equal measures, and instead a complex relationship exists between the electromagnetic radiation and the sensation in “standard” perceptual systems. And again, it needs to be stressed that the distances measured along x and y are also not uniform with respect to how we’d perceive the differences in terms of *relative perceptual sensations*. Everything is warped!

---

If we recall back to our last question,  [[The Hitchhiker's Guide#Question 15 What the F *ck is “Perceptually Uniform”?|Question #15]], we presented a more useful variation of the original CIE 1931 chromaticity diagram that warps and scales the x and y axes. Let’s snap our fingers and see the above image, with the exact same arrows, warped, skewed, and bent to the perceptually uniform 1976 diagram variant.

![](https://hg2dc.com/wp-content/uploads/2020/01/1976-recap.png?w=512)

**FIGURE WARPED PERCEPTUAL SCALE 1976**: A perceptually uniform-ish-kinda-sorta scale variant of the diagram above. Note that while the wavelengths move around a bit, they still aren’t distributed uniformly.

As we can see in **FIGURE WARPED PERCEPTUAL SCALE**, the visible light spectra are *still* not uniformly distributed around the perimeter of the spectral locus but the chromaticity coordinates on the inside however, are distributed in a roughly perceptually uniform manner. Because this is a modified variation of the **$xy$** diagram, the measurements have their labels changed to **$u$** and **$v$**. They are a different coordinate model.

So now, what about that damn triangle? Something like this one…

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-1976-1.png?w=640)

**FIGURE WTF IS THE TRIANGLE**: We can see that the triangle represents three specific chromaticities with a fourth towards the middle of it, but what are they exactly?

In **FIGURE WTF IS THE TRIANGLE**, we can see that the red dots at the tips of the triangle, and that off-centre dot inside the triangle, plot four chromaticities. But what exactly are they? The four chromaticities of course, as you may likely have inferred, represent the chromaticities of the three primaries and white chromaticity outlined in the sRGB specification!

That is, if you are staring at a reasonably decent sRGB display, the tips of the triangle represent each of the [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|three colours]] of the three little teeny lights in each pixel of your sRGB display! The off-centre dot is the chromaticity that an ideal sRGB display outputs when you set the sliders to equal R=G=B values. This chromaticity is sometimes [called the ](http://eilv.cie.co.at/term/1430)["white point”](http://cie.co.at/eilvterm/17-23-070). As we discovered in [[The Hitchhiker's Guide#Question 14 What the F *ck is “White”?|Question #14]], “white” is just another chromaticity.

The straight lines of the triangle depict the line of chromaticities that can be mixed between the two outside primary lights at the tips, [[The Hitchhiker's Guide#^c81990|2]] while everything *inside* the triangle is the footprint of the entire area of chromaticities that can be mixed with the specific colours of three RGB lights. sRGB, and all other types of displays, are limited by chromaticities of their three lights, and *no chromaticity can be mixed beyond the limits of the triangle they form on the chromaticity diagrams*! ^abeb66

So let’s move onto that iPad Pro…

![](https://hg2dc.com/wp-content/uploads/2020/01/display-p3-1976.png?w=797)

**FIGURE DISPLAY-WHAT**: The CIE 1976 perceptually uniform chromaticity diagram featuring the relative positions of the iPad Pro’s Display P3 primaries.

Remember back in [[The Hitchhiker's Guide#Question 4 What the F *ck are the Colours of the Three Lights?|Question #4]] where I told you that the “colours” of the three lights in your display are sRGB? Well, I hope our relationship is strong enough now that I can tell you that I lied. At least a little bit.

For the sake of clarity and simplicity, we introduced the complex subject using the generic sRGB standard, as that type of display is extremely common. If you happen to own an iPad Pro or MacBook Pro from 2015 onwards, the colours of the three RGB pixel lights in *those* particular pieces of hardware are not the same as sRGB!

---

The image **FIGURE DISPLAY-WHAT** shows us a similar triangle as **FIGURE WTF IS THE TRIANGLE**, but with different coordinates. The chromaticity coordinates in **FIGURE DISPLAY-WHAT** represents the *Display P3 primaries* that are found in most of Apple’s products from 2015 onward, and more and more displays from different vendors. While Display P3 features the identical white point as sRGB, the primaries are more saturated and of different “hue angles”. That is, two of the three primary lights are further out toward the purest spectral locus region, while the blue light is reasonably similar to sRGB’s blue light. They also plot at slightly different angles from the white point as compared to the sRGB primaries. Draw a straight line from the white point to the tip of the respective primary, and you can see how the angle is slightly different.

To get a better sense of these differences in colorimetry, let’s compare them together in one image using the useful perceptually uniform scale.

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-display-p3-1976.png?w=712)

**FIGURE TWO DISPLAYS**: The above image shows the relative positions of the primaries for both Display P3 and sRGB. Note how the white points are identical, despite the base primary lights being different.

Recall back to [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|Question #3]] where we learned that the chromaticities of each of the three lights in our displays never changes, and only the intensity of emission? The reason that the hardware in a Display P3 device can display more saturated colour mixtures of a wider range is because the chromaticities of the three lights in each of the RGB pixels are *quite different* from sRGB! To really hammer this home, I’d strongly encourage you to go back and review [[The Hitchhiker's Guide#Question 3 Does the F *cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?|Question #3]] and [[The Hitchhiker's Guide#Question 4 What the F *ck are the Colours of the Three Lights?|Question #4]] as the answers provided will be more meaningful now with what we have put into place.

And with that, we can answer our question…

**Answer #16: The triangles commonly found on chromaticity diagrams plot the chromaticities of the three basis primary lights in a display or other three light RGB standard.**

“But wait a minute… what the hell is a gamut?” “Can we deduce the spectral compositions from a single chromaticity?” “How do the sliders behave with different pieces of display hardware?” “I’m a photographer, I shoot real scenes not displays, how does this all relate?” “How does offset and spot printing relate to all of this?”

All terrific questions [that will just have to wait a little bit more…](https://hg2dc.com/question-17/)

---

1 I’d like to give full credit to [a very large cranium visual effects supervisor slash talented image maker Erik Nordby](https://www.imdb.com/name/nm0634969/) for coining that turn of phrase. While he has used it as a derogatory term, I feel it adequately describes what many folks who deal with digital content creation do, and have actively repurposed it here as a badge of honour. [[The Hitchhiker's Guide#^4e9306|↩︎]]  ^5eecef

2 It might be helpful to think of lights as being points on the chromaticity diagram that “pull” towards themselves like gravity as their emissions grow. At equal energy between two lights on the chromaticity diagrams, the resulting mixture is somewhere between the two. As one of the light’s emission grows, it “pulls” the chromaticity away from the other light, towards itself. If the light has no other light “pulling” away from it, the light is the purest and most heavily saturated it can get. This logic carries on to even the spectral laser-like wavelengths represented around the perimeter of the spectral locus! The wavelength composition of D65 daylight, for example, could be though of existing as a bunch of visible spectra under tension between each other, with the relative power “pulling” toward the spectral locus curve to greater or lesser degrees. [[The Hitchhiker's Guide#^abeb66|↩︎]]  ^c81990

![](https://hg2dc.com/wp-content/uploads/2020/01/d65-spectral-power-distribution.png?w=640)

The spectral composition of one particular mixture of D65, which has an x and y coordinate of roughly x 0.3127 and y 0.3290. The heights represent the relative power of the given visible light spectra, and how they pull each other from the outside perimeter of the spectral locus towards the middle region.



 
# Question #17: What the F\*ck is a Colour Space?

Sixteen questions! It has taken us sixteen questions to even begin to describe the term “Colour Space” with any degree of useful communication. We can hop right in to our question…

**Question #17: What is an RGB colour space?**

Careful before you scream out “YOU JUST SAID RGB IS A COLOUR SPACE!!111!!”. See the article “an” in front of “RGB”? That is an important “an”. RGB is [a colour encoding model](http://eilv.cie.co.at/term/208) that transports a colour space. Unto itself, it’s just a hollow container.

---

This question is going to bore you, because frankly, you already have the individual pieces of what composes a colour space. That is, [the CIE defines a colour space loosely](http://eilv.cie.co.at/term/226) as:

> \[a\] geometric representation of colour in space, usually of 3 dimensions
> 
> [The CIE definition of the term “colour space”](https://cie.co.at/eilvterm/17-23-041)

For pixel pushers though, that typically refers to one specific three dimensional [encoding](http://eilv.cie.co.at/term/227) representation. Pixel pushers *usually are dealing with RGB encodings*, of course1

In the [International Standard discussing photographic and graphic technology, the glossary includes a description of an RGB colour space must define three critical aspects](https://www.iso.org/standard/68761.html):

1.  [A set of three primaries](https://hg2dc.com/question-4/) that detail the [chromaticities of the three primary lights](https://hg2dc.com/question-13/) individually.
2.  A chromaticity detailing [the white point of the RGB encoding](https://hg2dc.com/question-14/), which is typically when R=G=B.
3.  [A set of transfer functions or a transfer function](https://hg2dc.com/question-6/) that describes the [relationship between the encoding and the ground truth of linear tristimulus](https://hg2dc.com/question-7/) .

That is, if anyone ever utters the infernal words *colour space* in your vicinity, take it upon yourself to make sure they aren’t barfing up garbage. I assure you that [people throw around the term “sRGB” without understanding what it is, what it represents, and very rarely understanding what the specification encapsulates relating to the above three extremely important bullet points](https://www.colour-science.org/posts/the-importance-of-terminology-and-srgb-uncertainty/).

Always remember that colour spaces almost always refer to something. [sRGB](https://webstore.iec.ch/publication/6169) and [ITU-R BT.1886](https://www.itu.int/rec/R-REC-BT.1886-0-201103-I/en) for example, refers to display devices. [ITU-R BT.709](https://www.itu.int/rec/R-REC-BT.709-6-201506-I/en) refers to a camera encoding.

---

Let’s now take a moment to shame the clusterf\*ck of stupidity out there by being very clear on several crucial things that you should take away from this question:

> RGB is not a f\*cking colour space
> 
> Linear is not a f\*cking colour space
> 
> Log is not a f\*cking colour space
> 
> CMYK is not a f\*cking colour space

Hopefully you can pass that along to prevent more idiots spreading idiocy.

**Answer #17: An RGB colour space, as outlined in the international standard ISO 22028-1:2016 must specify:**

1.  **A transfer function or a set of transfer functions2**
2.  **Three chromaticities for each of the three primary lights**
3.  **The chromaticity of the white point**

Phew.

---

I hope this is a very clear answer. You’ll have to appreciate that the folks who understand this stuff very likely want to use the colourful language above that typical raunchy pixel f\*ckers might use, but can’t for reasons of professionalism or otherwise.

I just checked my pocket and have zero f\*cks left, so I’m giving you this information using the language required to hammer the point home. Don’t let some dipsh\*t developer, or StackExchange idiot, or random YouTube buffoon, or donkey blog post tell you otherwise. You have the links… hammer them over the head with it. Eventually, my grizzled and grumpy pixel pusher friend, they will cease spreading their horses\*it, and the next crop of pixel pushers won’t be as confused as we were when we started.

With that out of the way, [there are bigger fish to fry](https://hg2dc.com/question-18/)…

---

1 Some of you poor, poor people may also be dealing with CMYK encoding models of course, and I feel for you. Sometimes it might be a hybrid output, or even be the primary output! We will get into the nuances of print CMYK encoding models soon enough, but you have already probably deduced that they are not entirely dissimilar to the complexities around RGB, and in fact, the majority of the questions already covered are directly related to the contextual nature of CMYK encoding models!

2 Remember folks, friends don’t let friends say that wretchedly useless word “gamma”. Always remember that the actual specification of sRGB itself, [which is referenced in Question #6](https://hg2dc.com/question-6/), written over **two decades** ago, has a very important annex **solely** dedicated to destroying the term. The last sentence from that annex is:

> Furthermore, it appears that the usefulness of the term \[gamma\] in unambiguous, constructive standard terminology is *zero* and its continued use is *detrimental* to consistent cross-reference between standards and unambiguous communication.
> 
> [The sRGB specification, IEC 61966-2-1:1999](https://webstore.iec.ch/publication/6169)



 
# Question #18: What the  F\*ck is the Missing Axis in a Chromaticity Diagram?

We’ve touched on the importance of the CIE’s chromaticity model, and its relationship to visible light spectra as **the** single most important framework for pixel pushers to get a firm grasp on to understand all of colour. Some folks may also likely have come to realize that the two dimensional representation is missing some important information.

That’s because that as wonderful as the CIE chromaticity two dimensional diagram is, it’s missing one crucial axis that should be made more apparent.

**Question #18: What is the missing axis in the CIE chromaticity diagram?**

---

So we’ve established that the chromaticity diagram is an absolute, two dimensional map of mixtures of visible light1. The terrific part of this is that we can express any mixture and get a resultant absolute coordinate that no one on the planet can muddle up. And it works pretty damn good, plus or minus some more complex details.

The downside? It’s not exactly useful for expressing how a mixture relates to overall radiometric or perceptual quantities of light. That is, for any given chromaticity coordinate, there are an *infinite number of mixtures of intensities that can produce it*.

Whoa that was quite a mouthful. Let’s backtrack a little bit…

---

We know that much like a conventional map, we have two dimensions that we can move in. For a conventional map we have one axis along north to south, and another axis along east to west. Even if we have an absolute map coordinate that tells us we are standing on Mount Everest, we don’t quite have enough information to tell us how high up we are, do we? In theory, with a big enough shovel, we could be standing at the exact same latitude and longitude, but at *any* altitude.

If we go back to our ever crucial CIE 1931 chromaticity diagram, we have our north and south axis via the *y* coordinate, and we have our east and west axis via our *x*. But what about that… “altitude”?

---

The xy chromaticity diagram is in fact a top down view of chromaticities, and if we were creative, we could use some tools to visualize how our view of the map is in fact hiding the “altitude”, to use our Mount Everest analogy above.

Let’s quickly return to the basic two dimensional CIE 1931 chromaticity diagram. We’ll start super simple, and slice up the visible spectrum up into 1nm increments. Think of it as 471 laser pointers of different wavelengths that you might buy from Amazon. That long straight line remember, cannot be expressed using any single visible light Amazon laser, and instead we need to mix the lowest and highest visible wavelength to achieve any of the chromaticities along that edge. If we needed a purple laser pointer along that edge, we’d need to mix two lasers, not one!

![](https://hg2dc.com/wp-content/uploads/2020/01/happy-little-locus-xyy.jpg)

471 increments of visible wavelengths between 360nm and 830nm, plotted in the CIE 1931 chromaticity diagram

Enough of that boring bulls\*it… you’ve been staring at [those sorts of diagrams since Question #13](https://hg2dc.com/question-13/), and all the plot represents is a model that allows us to connect visible wavelength mixtures of light to a model in an absolute way. In our above case, the horseshoe has a representation of the lasers using sRGB colours.

But what if we kick it up a notch, [look back to Question #12](https://hg2dc.com/question-12/), and talk briefly about intensities? [We know from Question #12](https://hg2dc.com/question-12/) that each visible light wavelength carries different perceptual energy levels at equal radiant energy levels. So what would that look like? Funny you should ask…

Visible light divided into 1 nanometer increments and plotted in 3D

Et voila! All we have done is simply expressed our visible laser increments at constant radiometric energy. That shape should now connect directly back to illustrating why those blasted sRGB squares [we covered in Question #12](https://hg2dc.com/question-12/) appear brighter or less bright perceptually, despite being at equal emission intensities! That is, again, the *perceptual* intensity is quite different from the *radiometric* intensity.

You probably aren’t wondering what the lasers might look like if we plotted them relative to our peak fully-adapted set2? F\*ck it, you get to see the 471 laser-like wavelength increments at 100%, 75%, 50%, 25%, and close to 0% anyways…

Visible light divided into 1 nanometer increments, at adapted 100%, 75%, 50%, 25% and close to zero.

---

Now back to pixel pushing on your sRGB display…

Let’s take a small smattering of pixels in an sRGB image. For the sake of clarity, we’ll pretend our image is ridiculously uh… limited, and only features seven mixtures of sRGB light. That is, we can pretend our image has seven pixels of sRGB light mixtures in a row. We can of course visualize what that might look like on our CIE 1931 chromaticity diagram. You’ll be familiar with [the damn triangle from Question #16](https://hg2dc.com/question-16/), where we drew them out for an iPad Pro and an sRGB display.

The following plots the most saturated combinations of sRGB red, green and blue. That means that in the case of the “colour” mixtures, there are only one or two lights mixed.

The outer tips of the triangle, as we know, represent the pure primaries, with no complimentary light channel. The middle points are the mixtures of the two primaries at the tips. And of course our old friend maximum intensity R=G=B is in here too, aka sRGB primaries at 100% for each. Let’s have a look…

![](https://hg2dc.com/wp-content/uploads/2020/01/happy-little-srgb-xyy.jpg?w=1000)

The snoring sRGB specification chromaticities of the three primary lights, expressed in the boring triangle format. Notice the equal mixtures between the two primaries at the tips don’t land smack dab in the middle of the lines!

The tips of our triangle have small colour coded sRGB red, green, and blue dots, we introduce the other three members of the Notorious Six, being sRGB cyan, magenta, and yellow.

For a bit of a mental game, let’s pretend we are dealing with only sets of five intensity increments for our sRGB display linear light output. That is, let’s set those lights in the above combinations to 100%, 75%, 50%, 25%, and a low value near absolute 0%. For this purpose, we are going to remove the sRGB transfer function so we are dealing with linear energy ratios only. Any idea what they might look like if we were to plot them in 3D? Wait no longer!

sRGB, with the transfer function “undone” to illustrate the display linear output at common mixtures and purely saturated primary lights

Of particular note is that within the confines of sRGB, the Notorious Six member sRGB purely saturated “yellow” happens to also have the highest level of perceptual energy. The reason why is that the chromaticity coordinate for the equal energy mixture of green and red results in the highest luminous efficacy, being closest to the magic wavelength 555nm, which packs the most perceptual energy punch!

Also notice the perfectly vertical “legs” for each of the purely saturated Notorious Six members. The vertical “height” is maxed out at a certain point, and the purely saturated primaries and mixtures between *cannot become more luminous*, as they are expressed at 100% relative to the others! That means that again, [rehashing what was covered in Question #12](https://hg2dc.com/question-12/), the chromaticities do not output the same amount of perceptual energy at equivalent radiant energy.

If you have forgotten any of the yawn inducing concepts around intensity, feel free [to revisit Question #12](https://hg2dc.com/question-12/).

---

Alright… that’s a large enough of a dose of colour science for one day, I’d say. Let’s tidy this question up with an answer…

**Answer #18: The missing axis when looking at the CIE 1931 chromaticity diagram is luminance, expressed as an uppercase Y.**

So there you have it. Remember that in colour science, terms and little details such as uppercase or lowercase often carry additional meaning. In this case, the CIE 1931 chromaticity diagram uses the lowercase *x* and *y* to represent *normalized*, or scaled from 0% to 100%, values. If they were not scaled, you would read uppercase *X* and *Y*! And that brings one more puzzle piece to the table with clarity; the three dimensional models we have been plotting are in *xy***Y**, where *Y* represents the unscaled version of *y*. *Y* is also the bass player in the death metal act known as *XYZ*, and occasionally plays in his drill rap act offshoot known as *xyY*. He’s the same band member, and lowercase *y* is his little sibling.

Hopefully by examining the non-uniform perceptual energy vertical axis and the non-perceptually-distributed chromaticities in conjunction with the spectral locus itself has helped cement some of the previous concepts covered.

What’s interesting is that all of the above work is curiously plotted using a 0% to 100% framework though, and for you rendering wonks and photographers out there, you probably may have yet more questions that have become aware to you. But those [will have to wait for a while…](https://hg2dc.com/question-19)

---

1 There are indeed several versions of the Colour Matching Functions, and it’s worth noting so here now that you have a firm understanding of the groundbreaking 1931 version. There have been iterations since then that have attempted to more accurately model the standard observer response to visible light spectra, and “fix” certain problems with the 1931 model. |↩︎]] 

2 *[Adapted](http://cie.co.at/eilvterm/17-23-081)* is an absolutely critical idea here that we will explore later. The reason that adapted is crucial, is that it allows us to discuss our psychophysical response in terms of a ratio from the darkest to the lightest value we have adapted to. Otherwise our scale will change. And yes, rendering wonks or photographers might be generating more questions right now because of that, and rightfully so! |↩︎]] 



 
# Question #19: What the F\*ck is a “Gamut”?

Phew. It’s been a long time coming, but the time we have invested is starting to pay off! We can actually discuss colour in a meaningful way, and with [the introduction of perceptually uniform maps with Question #15](https://hg2dc.com/question-15/), we can even compare colours or get a sense as to “how different” chromaticities are! And we’ve just [started scratching the surface of how different displays behave with Question #16](https://hg2dc.com/question-16/).

Hopefully, with the sorts of questions answered since then you are beginning to appreciate why understanding the various chromaticity diagrams and their relationship to visible light are **the** most important set of concepts a digital artist needs to know; *it allows us to discuss colour in a meaningful way*. As a set of core concepts they are, in no uncertain terms, the ground truth for all things creative from print to display to rendering to photography to motion graphics to whatever little unique domain has found you here, reading this crap.

So you’ve heard about gamuts. You might even be staring at something someone or some marketer described as a “wide gamut” display right now! As is a familiar in this series, *we are here to figure out and investigate exactly what “gamut” means*…

**Question #19: What is a gamut?**

---

By focusing on physical things like displays and lights, we are able to give meaning to the nebulous concepts and keep the meaning out of the abstract bulls\*it quagmire of “colour spaces”. While a typical image hustler has no problem understanding that one of the three tiny and specific coloured lights in their display increases or decreases in emission, the ideas around transfer functions and chromaticities are tricky things to expect someone to “grab on to”.

Why are we rehashing these two darn things again? Because for the answer to our question, we are going to need to hyper focus on transfer functions and chromaticities. Let’s keep the following concepts fresh in our heads:

> **Transfer function*s** are the Rosetta Stone between encoded RGB code values and physical quantities of light.
> 
> **A chromaticity** is a strict and absolute definition of a mixture of the most pure, laser-like wavelengths of visible light relative to a standard observer.

---

Let’s look at what the experts in the field of colours science have to say about [the term gamut](http://cie.co.at/eilvterm/17-32-007). It is the first few words that we are going to focus on:

> volume, area, or solid in a colour space
> 
> [Colour gamut definition from the CIE term list](http://cie.co.at/eilvterm/17-32-007)

For our purposes, we can get a sense of the “area” portion of this definition having covered a couple of very useful models and their respective diagrams. While we will keep our discussion grounded in something that pixel pushers all over are familiar with – a piece of display hardware – the general principles apply for the larger umbrella of colour spaces across different mediums, including print and other reflective media.

We already have discussed two reliable methods to discuss and plot “colour”1 via either [the non-perceptually uniform chromaticity diagram from Question #13](https://hg2dc.com/question-13/) or [the perceptually uniformly scaled variant in Question #15](https://hg2dc.com/question-15/). Let’s look at the *area* differences when comparing an sRGB display versus an iPad Pro again:

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-display-p3-1976.png?w=580)

**FIGURE STUPID AREA COMPARISON**: A comparison of the areas formed between the three lights of an iPad Pro (Display P3) and a typical display (sRGB). Remember, the specification that sRGB uses to describe the chromaticities of the three primary lights is taken directly from another standard in BT.709.

As useful as this diagram is in comforting you that your two thousand dollar display is “better” than your friend’s cheaper display, we can also see that it has limitations. While this variant shows us a two dimensional plot of colour mixtures, [we explored in Question #18](https://hg2dc.com/question-18) that it leaves out one crucial and vastly important aspect. We are missing *the range of intensity that visible light mixtures can be displayed at*!

---

First, let’s knock the answer out. The CIE seems to have a very clear and useful summary solution, so let’s roll with that…

**Answer #19: A gamut is a volume, area, or solid in a colour space.**

But what does that really mean? What does it look like? To answer that, let’s take a peek at a generic image.

![](https://hg2dc.com/wp-content/uploads/2020/02/rgb-does-not-mean.jpg?w=545)

**FIGURE SAMPLE RGB**: Seems fitting enough

Given we’ve spent more than enough time diving into chromaticity diagrams, let’s see what the above image, including the “white” text, looks like as a volume of colours expressed in the CIE 1931 xyY model…

Plot of the sRGB triplet values using the familiar xyY chromaticity diagram. This stupid thing took about three hours to render using the completely unoptimized plotting tools of MatPlotLib.

So what exactly are we looking at?

The above 3D plot maps every single pixel in the above sRGB **FIGURE SAMPLE IMAGE** and transforms the sRGB values properly to xyY. That means several hundred thousand pixels are plopped into the xyY model, and the above animation shows us the volume of colours in the 3D chromaticity diagram. The upper most white circle in the plot? That is the position of the white text pixels, all crammed into the exact same 3D xyY plot position, because… well… they are all the same chromaticity. The darker scattering near the sRGB triangle footprint? Those would be the extremely low intensity emissions near black in the image. If we were able to see through the cluster of points near the bottom, we’d find a single value representing the sRGB chromaticity point for `[0.0, 0.0, 0.0]`. The rest, as you can see, are quite orange-y to red-y to brown-ish looking, and map according to intensity along the vertical axis.

So if that oddly mountainous looking stack of chromaticity positions is indicative of the **FIGURE SAMPLE IMAGE**‘s pixels, what might the extremes of the sRGB gamut look like? Wait no further for the question that you never wanted to know the answer to!

The question you never asked nor cared about! The entire exterior solid hull shape of the sRGB gamut volume expressed using the CIE 1931 xyY model.

---

And that brings another installment to a close. Although there are several useful representations of gamut available as per the CIE defintion, we have highlighted the idea of gamut as a volume here. To appreciate why we have focused on gamut as a volume of values however, will have to wait for [some further questions…](https://hg2dc.com/question-20)

---

1 Always remember that the chromaticity plot only plots a direct connection between visible wavelengths of light and the limited experience of “colour” for a standard observer. While we might be loosey goosey with our terms at times, it is always important to draw a distinction between a *chromaticity* as a useful coordinate mapping and the more complex sensation of *colour*. We can use the former to reference loose ideas of the latter, but there is a nuanced and complex differentiation between the two terms. *Colour*, in the larger psychophysical sense, is hugely complex and contextual.



 
# Question #20: What the F\*ck is a Quantity of Light?

We’ve been talking about radiometric light ratios here for the most part, specifically regarding the final output from a display. In an effort to understand the subsequent questions that follow this one, we are going to need to fill in some further details about what “a quantity of light” means in a way that will visually make sense for a typical image maker.

**Question #20: What is a quantity of light?**

Why on Earth is this even a question in a discussion about digital colour and digital content creation? Just as with the previous questions discussing chromaticity, there’s nuance in them there hills!

The folks who spend time in 3D DCCs or photography types might have a sense as to why this is a crucial bit of understanding already. For the rest, the following relationship is key to understanding what some of the fundamental pixel manipulations *represent*. Smudging, blending, stretching, warping, rotating, or even just drawing an angled line? Yep, you have found yourself smack dab in the middle of this exact subject!

Be forewarned, plenty of crappy images follow. And don’t worry, this won’t turn into a discussion of watts per second or steradians or any things that would get [Euclid](https://en.wikipedia.org/wiki/Euclidean_geometry) excited. In fact, we are not even going to talk about light at all. Let’s talk about sand…

---

Imagine two square holes cut into a slab of material. Like this poorly, half-baked illustration…

![](https://hg2dc.com/wp-content/uploads/2020/04/area-flow-two-holes-no-flow-1.png?w=750)

**FIGURE TWO HOLES** Two extremely poorly illustrated square holes cut into a material, with a slight 3D tilt perspective.

Now imagine that we have a constant flow of sand coming from above such that the sand flows through the two holes…

![](https://hg2dc.com/wp-content/uploads/2020/04/area-flow-two-holes-2.png?w=750)

**FIGURE DUAL HOLES** **FLOWING** The equally crap illustration, with some red arrows that illustrate where the sand would be flowing from.

It is worth noting at this point that we have *two* facets that determine how much sand would be on the ground at any given point in time. The first is our “flow” of the sand, which could be increased or decreased as we wish with some sort of huge sand blower thingy. The second is the “cutout” size.

That is, we have a *rate of flow* and an *area* component. Now what happens if we cut off half of the area?

![](https://hg2dc.com/wp-content/uploads/2020/04/area-flow-single-hole-1.png?w=750)

**FIGURE HALF AREA SAND** Rate of flow of the sand remains the same, with one of the square holes completely blocked off.

It should be evident that we have halved the quantity of sand at a given slice of time here. Of course, to end up with the *exact same quantity* of sand in **FIGURE HALF AREA SAND**, we could have *instead* dialed down the flow of the sand and left the area of both holes uncovered…

![](https://hg2dc.com/wp-content/uploads/2020/04/area-half-flow-two-holes.png?w=750)

**FIGURE HALF RATE SAND** Rate of flow of the sand is halved, with the full areas of pass through open.

Presto! We’ve achieved exactly half the sand again, using a different control knob.

---

So why is this seemingly silly sand side-bar important? Because if we understand the sand demonstration above, we’ve also just understood enough about radiometric light units to discuss fundamental pixel manipulations!

To recap, we have focused on two interconnected ideas to increase or decrease the overall quantity of light:

1.  *Rate*. We can increase or decrease the overall *quantity of light* at an identical area of projection by increasing or decreasing the intensity, or rate of flow, of the emission.
2.  *Area*. We can increase or decrease the overall *quantity of light* at a constant intensity by increasing or decreasing the area that the light projects through or out of or bounces off of.

Way back [at Question #1 we discussed how the sliders typically related to intensity](https://hg2dc.com/question-1) in ancient digital content creation applications. As we can see, this attribute specifically relates to the first point above, as we were dealing with single pixel window units. To head further down into the pixel mine though, including blending, smudging, rotating, and other things, we need to keep a keen eye on relationship that intensity shares with geometric area as well.

For the astute observer who may have dabbled in photography, we also just revealed exactly how your aperture F-Stop numbers relate to the quantity of light landing on the image plane of your camera1.

---

**Answer #20: The result of both area and intensity determines the overall quantity of light.**

Some of you may get a sense as to where this is heading, and some may have found yourselves lost with this seeming completely unrelated question. We will get both folks back on the same path in the next questions, but it will [just have to wait for a stop over to sliders and code values…](https://hg2dc.com/question-21)

---

1 Earlier I mentioned that photography enthusiasts may have a sense of the relationship between intensity and area simply from their experience shooting. What’s even more interesting for those who weren’t aware, is that the aperture value of your lens expresses the exact relationship to area outlined in this answer. What photography nerd doesn’t know that, though? What is not so obvious is that the F-Stop value *is literally a radius ratio*. That is, if we use a selection of the F-Stop series such as `0.5`, `0.7`, `1.0`, `1.4`, `2.0`, `2.8`, `4.0`, etc. we can calculate the light quantity ratios between them. Area of a circle is Pi multiplied by the radius, or half the diameter, squared. To make it more clear, Pi remains constant here, so we could pretend the aperture was a square like our sand illustrations above, and ignore it. So let’s look at that F-Stop series above if we calculate the area of the square by multiply the value by itself? `0.25`, `0.49`, `1.0`, `1.96`, `4.0`, `7.84`, `16.0`, etc. See how if we round the values the total quantity of potential light hitting the image plane double with each increment? `0.25`, `0.5`, `1.0`, `2.0`, `4.0`, `8.0`, `16.0`? Bingo. Exactly the relationship between intensity and area covered in this post. Thinking of F-Stop increments as radius ratios is a handy mental trick, too. Finally, this example also gives us a nice example that further fleshes out the idea that the [radiometrically linear light we discussed in Question #7](https://hg2dc.com/question-7) is **much** simpler and comprehensible math than goofy nonlinear sRGB code values! |↩︎]] 



 
# Question #21: How the F\*ck do we Put a Red Pixel on the Screen?

If you’ve been following this series of questions, you are probably genuinely wondering why the hell we have taken an apparently massive departure from CIE chromaticity diagrams that map visible light to a stupid model, over to [fundamental and equally dumb light intensity and geometry with Question #20](https://hg2dc.com/question-20). We have one more question before we can glue the two halves together.

---

This is essentially inspired by [Jim Blinn’s](https://en.wikipedia.org/wiki/Jim_Blinn) [A Trip Down the Graphics Pipeline](https://bookshop.org/books/jim-blinn-s-corner-a-trip-down-the-graphics-pipeline/9781558603875). We are going to take a trip down the pixel input to output chain, from slider to light output. It won’t answer all of the questions you will have, but it will at least get you asking the right things about what your stupid software might be doing.

WARNING: There’s a small bit of math involved, with the answers provided. Feel free to punch the math into a calculator if you so desire, or just punch a wall if it is already stressing you out.

The point isn’t to confuse you with math, because frankly, math is boring as f\*ck and stinks. With that said, it is critical to understand the conversion between an encoded and decoded value sent to a display and what happens. There’s no other way to really understand the mechanism than to swallow a tiny bit of bitter math. What’s more troubling for this question is that there are plenty of horrible illustrations. The illustrations are far worse than the math.

So let’s hunker down and do a little pixel f\*cking…

**Question #21: How do we display a red pixel at a certain intensity on a display?**

---

Being airy fairy butterfly “creatives”, everyone does plenty of imagining. We are going to carry that trend forward and imagine a display with exactly two pixels. For our purposes, we will assume that it’s a commodity sRGB-like display. Tada…

![](https://hg2dc.com/wp-content/uploads/2020/04/two-pixels-off.png?w=600)

**FIGURE PIXELS OFF** Our virtual display, with a colossal two pixels turned off. Outlined here in dotted cyan to make the individual pixels clearer.

Now imagine if we turned on each pixel to full intensity. If we were to take a peek at the three little lights within each pixel, we’d see something possibly like…

![](https://hg2dc.com/wp-content/uploads/2020/04/two-pixels-full-intensity-led.png?w=600)

**FIGURE NOT REALLY LEDS** Here’s our two pixels, with each of the three sRGB lights turned up to 100% emission.

While it’s extremely useful to remind ourselves that there are indeed three lights that comprise an individual pixel, the more common way we see pixels is as though we are far away from that tiny geometry, and we perceive the three lights as a cumulative sample of their projected wavelengths. In this case, the result is sRGB’s D65 white point chromaticity, which looks like this if you are on something actually displaying sRGB’s D65 chromaticity correctly…

![](https://hg2dc.com/wp-content/uploads/2020/04/two-pixels-100-effective.png?w=600)

**FIGURE WELL DUH FULL** The groundbreaking image of our two pixel display, with both upper and lower pixels emitting 100%.

Whoops! We skipped the part where we are dialing our DCC’s application slider to control the lights. Why is this important? Because until we peek into what is happening between a typical RGB slider and the output from a display, we won’t be able to solve the Riddle of [Question #9](https://hg2dc.com/question-9).

So let’s make this a little more clear. Let’s slide only the red slider on the upper pixel to 100% code value, and we will leave the lower pixel set to code value 0%…

![](https://hg2dc.com/wp-content/uploads/2020/04/dcc-sliders-red-100.png?w=800)

**FIGURE SLIDERS FULL** Adjusting the red slider to 100% code value range for the upper pixel of our two pixel display. It’s worth pointing out that it is valuable to always consider what the slider is referring to, as we will explore further in this entry.

The slider means 100% emission right? Hold your horses! Remember that we are always dealing with relative values and that we have to connect the values to meaning. This is an absolutely crucial thing to work through in our minds. Granted, it’s tiresome as hell, but hang in there…

---

In the above example, we are imagining that our application has the sliders connected directly to our sRGB-like commodity display. That display, as we learned back in [Question #6](https://hg2dc.com/question-6), has a hardware decoder built into it! Before it converts the *code value* into an electronic signal and emits the *radiometric-like linear quantities of light*, it always *decodes* the *encoded value* it receives. It’s not smart and is closer to a sausage machine; it does not care what meat you put into it, it treats all meat the same.

In this case, our sliders communicate to us, the creators, in those code value labels. That is, the value of `1.0`, or 100%, is does **not** quite mean 100% display emission light! It’s a code value. The code value will get decoded by our display’s hardware in some kooky math manner. Let’s step into that process…

---

In this case, our sRGB-like commodity display takes all values it receives and *decodes* them via its specific transfer function, just like the sausage machine. That is, if we send a code value of `1.0` to this particular display, it will take that value and decode it to via a math formula of some sort. For commodity sRGB displays, that formula is:

`encoded_value2.2`

So how to decode our slider’s code value of `1.0`? Just plug it into that formula.

`1.02.2 = 1.0`

Well that was a bit of a let down right? Our input code value of `1.0` comes out as a display linear light ratio of `1.0`. That means that our code value of 100% of the code value range *happens* to end up 100% display linear light output.

But wait, isn’t that the same f\*cking thing?

**No**. No it’s not.

It is *very* important to realize that even though the values end up *identical*, they mean *radically different things*. Even code value `0.0` does not mean 0% display linear light output, but rather it too must be decoded first!

![](https://hg2dc.com/wp-content/uploads/2020/04/one-of-these-kids.png?w=800)

**FIGURE ONE OF THESE KIDS IS NOT LIKE THE OTHER** The numerical values `1.0` are the same, but the meaning is *completely* different. Don’t let identical numerical values seduce you into thinking they hold the same meaning!

With the hope that we will never conflate two identical values with identical meaning again, let’s look at the result…

![](https://hg2dc.com/wp-content/uploads/2020/04/two-pixels-100-red.png?w=600)

**FIGURE RED FULL INTENSITY** Presto. Brain melting magic of taking a known code value ratio and getting it to the display, which decodes it into a linear light ratio for output!

What a huge amount of waffle to hammer a point home when the result is pretty damn expected, right?

---

So let’s do a slightly more tricky value. Let’s say that we want the sRGB-like display to pump out 50% of the overall light level from the display. What does that look like? First we adjust our slider to 50%, right? Right? Right?

![](https://hg2dc.com/wp-content/uploads/2020/04/dcc-sliders-red-50.png?w=800)

**FIGURE TOTALLY WRONG** Why are we being pedantic here? Remember, ask yourself what is the math behind the slider? Is it the transfer function, some random formula that someone dreamt up, or something altogether different?

Wrong!

Remember that the slider represents the encoded value range of our display’s transfer function. That means that the values do *not* represent display linear light ratios of emission, and the values do not even attempt to represent an idealized perceptually uniform distribution as per [Question #15](https://hg2dc.com/question-15). They are simply encoded values. That encoded value in turn will get decoded by the display, and turned into display linear light ratios.

How then, do we figure out to control the display’s linear light ratios directly? We have to flip the display’s output transfer function around!

We want a display emission that is 50% of our maximum emission of the display light range. How do we get that? We need to flip the transfer function of the display backwards. So if our display’s transfer function for output is:

`encoded_value2.2 = display_linear_light_output`

We need to invert that transfer function to get it flipped around the other way. “Invert” here, by way of boring math, means we will divide `1.0` by the exponent:

\-

That probably looks a little scary, but don’t let it freak you out.

The important part to understand is that we have two sides to this problem. One side is the encoded value, the other side is the decoded value. This happens in the hardware of the display itself, and all displays have some sort of hardware decoding thingy. In our case, the encoding is not too complex and is a simple power function of a simple value. Again, for those whose eyeballs rolled back into a glazed donut drooling automaton state the first time…

![](https://hg2dc.com/wp-content/uploads/2020/04/one-of-these-kids.png?w=580)

So let’s plug our desired linear light ratio into our function above and see what encoded value we get back…

`0.5(1.0/2.2) = 0.73`

Don’t let the math scare you. On the left side we put our desired 50% value, or `0.5` in geeky math, into that flipped around backwards version of the display’s decoding function exponent formula thingy.

The result is the magic encoded value of `0.73` we need to send to the display1. The display in turn will do exactly the thing it did in our first example, and push it through it’s hardware decoder sausage maker:

`0.732.2 = 0.5`

If you want, give it a shot using a calculator. Even if you don’t, hopefully you can get a sense of the encoding to decoding that is **always** happening with hardware displays. Your iPad Pro? Yep. Your sRGB display? Yep. Your Adobe RGB display? Yep. Your HDR television? Yep. There’s always a unique transfer function buried in that hardware that is responsible for decoding the magically encoded code value it is handed! Let’s set our slider…

![](https://hg2dc.com/wp-content/uploads/2020/04/dcc-sliders-red-73.png?w=800)

**FIGURE CORRECT SLIDER VALUE FOR 50% DISPLAY LIGHT** Here we have correctly set the slider for 50% display light emission via the math of the display’s transfer function.

So, as per our example, what does that 50% total display emission output, aka sRGB-like code value 0.73, look like for only the red pure sRGB primary light? Here it is…

![](https://hg2dc.com/wp-content/uploads/2020/04/two-pixels-50-red.png?w=600)

**FIGURE HALF INTENSITY** Code value `0.73`, decodes to exactly 50% of the overall emission strength for the red light in our two pixel display. Phew.

Well that was a f\*ck of a lot of work to get our minds around display linear light output, wasn’t it? You might be skeptical that this will have a visual impact on your creative work, and rightfully so.

Would you believe it if someone told you that, despite the rather simple connection between display encodings and their respective meanings in linear light quantities, that a vast majority of software absolutely sh\*ts the bed here? The software sh\*ts the bed so hard that we see nasty-ass looking fringes that we were introduced to in [Question #9](https://hg2dc.com/question-9), gaudy looking transitions in motion picture dissolving, gnarly fringing when we paint, completely incorrect light colour mixing, and wildly crazy incorrect interpretations of code values that leave the output completely broken. [Some woefully informed folks at companies are even treating mishandling of colour as a marketing upside](https://www.benq.com/en-au/knowledge-center/knowledge/is-dci-p3-better-than-srgb-for-gaming.html).

---

So why did we take this pedantic trip from sliders to display output? The important thing to remember here is that there isn’t some magical universal standard for what some random application developer decides to make their sliders do. There’s also no magical operating system that will insulate you from application developers from completely screwing things up. Typically, the developers don’t really have a clue, and those that do have a clue are probably helpless and as frustrated as we are. That means that we, as airy fairy creative butterflies, need to constantly keep our wits about us and prevent the hostile software from bungling our work.

For our purposes, digital colour is related to slippery concepts, and the only way to make them not-so-slippery is through a series of overly simplistic examples. In most cases, RGB sliders are directly related to the code value range of some transfer function, or worse, some random computer formula.

With that said, rightly or completely and absolutely wrongly, it’s extremely common that the slider values are the sRGB transfer function, which differs slightly from the commodity example exponent formula we used here2. Practically, in real-world scenarios, there are many complex things that might happen, including stuff that happens under the umbrella of [colour management](http://cie.co.at/eilvterm/17-32-014). In the end though, whatever the path is, the value will always be converted to an RGB code value for the display3, which in turn will decode it to display linear light ratios. *Always*.

So let’s answer our question and get the hell out of this math bog…

**Answer #21: In order to get display linear light out of a display, the display linear light ratio is encoded to a code value range according to the unique transfer function of the display hardware encoding.**

The code values are frequently *not* ideally perceptually uniform, meaning `0.5` in your slider isn’t some sort of useful metric in most cases, but rather often a ballpark approximation. In addition to the problematic reality of no such idealized perceptually uniform model existing, the reason the encoded values are not perceptually uniform is because they are a compression scheme based on the design of the display characteristics with respect to its intended usage. They typically are sort-of-kind-of close to being sort-of-kind-of-perceptually-uniform-ish-y, but it is a nuance worth distinguishing.

So why did this whole damn question have two pixels instead of just one? That’s a great question that will carry over to the magical gluing of many concepts together. Go grab a quarantine coffee before moving along to [the next question…](https://hg2dc.com/question-22)

---

1 Nope, there won’t be any WANKer conversion to eight bit code values here. Remember? They stink and make things way less comprehensible than they already are. If you are hell bent on doing so, feel free to multiply the code value given by `28 - 1`. But honestly… do yourself a favour and think in terms of ratios and good, old fashioned, sane decimal representations.

2 Many folks and software screw this up all over. The canonized transfer function in the sRGB specification defines a two part *encoding* formula that is close to being the pure 2.2 power function described here. It is important to note that not only is 2.2 the **not** the canonized sRGB output transfer function (EOTF) in some discussion circles, but also that many displays aren’t technically sRGB because of this. In short, as a digital pixel pusher, it’s important to realize that your work will appear subtly different in the shadows if something screws this detail up. For more information, [the official sRGB specification can be purchased here](https://webstore.iec.ch/publication/6169). [The clarification as to the intention of the sRGB EOTF is provided via the excellent Colour-Science website link here](https://www.colour-science.org/posts/srgb-eotf-pure-gamma-22-or-piece-wise-function/). The specification could certainly use some clarity to carry us forward into the future, as the specification’s intention is subject to debate and discourse.

3 A million WANKers just screamed out that some displays use HDMI cables and that in turn, it isn’t RGB signals going down the pipe. The bad news for the WANKers is that displays will almost always have those little RGB lights in them, and that means no matter what is shoved down the cable, be it YCbCr or otherwise, it begins and ends its life as RGB ratios. Keep screaming, no one can hear you…



 
# Question #22: How the F\*ck do we Move a Red Pixel?

In the last post, we took a very high level peek at what might happen in a code value to display output chain. Let’s take a quick look at a recap…

![](https://hg2dc.com/wp-content/uploads/2020/04/general-high-level-overview-2.png?w=800)

**FIGURE HIGH LEVEL BULLS\*IT** This gives a very high level overview of a code value / slider representation to display output chain.

Without further ado…

**Question #22: What happens when we “move” a pixel?**

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

**Answer #22: We can move pixels around by treating them as small geometry that represent emissions using super simple math.**

But wait… there must be a catch, right? Surely there’s something here that we are missing? The answer is sadly, yes.

Many pieces of DCC software are absolute sh\*t. Instead of doing the math on the display’s linear light ratios as we did above, they use some bungled up mess of ideas that some random idiot thought was a good idea. Typically, software folks will conflate the *encoded value* with its *decoded* meaning. You can probably guess where this is going.

Instead of doing the *proper* thing and calculating the math on light ratios, the math is often *wrongly* applied to the encoded values. That’s right, some poor soul never bothered to ask the question way back in [Question #1](https://hg2dc.com/question-1), and as a result, they completely screw up the most fundamental math. Imagine doing the math for audio processing on an encoded MP3 signal and you can guess just how wrong the results would be. This leads to all sorts of broken software ideas all over the damn place!

Stupid software comes back to kick you, the lowly pixel crafter, right in the teeth with garbage broken output when all you wanted to do was blur the sun or smudge a tree line.

*“But aren’t there different types of displays?” “What about different RGB colour spaces with different transfer functions?” “Don’t we need to take the colour spaces into account before doing math?”*

These are all terrific questions. Perhaps you are even starting to understand why some software breaks on even simple things like those outlined in [Question #9](https://hg2dc.com/question-9). But let’s take a break from this and leave the subsequent excellent questions [for another question or two…](https://hg2dc.com/question-23)



 
# Question #23: How the F\*ck Do We Move a Red Pixel Down Over Another Colour?

We’ve been talking about “pixels” in terms of little squares that can emit light. I’d like to point out that [Alvy Ray Smith, one of the key explorers of the alpha channel, has had a rather solid push back about leaning on the concept of “little squares” geometry exclusively](http://alvyray.com/Sprite/SpriteTheory_v4.2.pdf). [Mr. Blinn, who we introduced previously, also has written a wonderful exploration of the meaning of a pixel](https://dl.acm.org/doi/10.1109/MCG.2005.119).

Loosely, there are a number of ways to interpret what a pixel *is*. For our purposes, as mere mortals and not members of the pantheon of imaging deities, we are going to carry on focusing on the idea of discrete little squares, or *sampled geometry* and light1. Sorry Mr. Blinn and Mr. Smith, it’s probably too much too soon to depart from discrete samples just yet…

**Question #23: How do we move an emitting pixel over another emitting pixel?**

---

Let’s pick up from [the movement of the red pixel in Question #22](https://hg2dc.com/question-22) , and rewind just a bit, back to theoretical red pixel tuned to 50% emission…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-on-1.png?w=800)

**FIGURE FAMILIAR** The familiar “single” pixel, at 50% display emission.

In our example, we suggested that our pixel had moved down slightly, straddling the lower pixel window that was turned off…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-moved-down-grid-off-1.png?w=800)

**FIGURE MOVED ME** Here the pixel has been “moved” in a small increment down.

And now for a twist! What if, instead of moving over a pixel window with *no* emission, that the pixel it was moving into were “on” to some level of emission? So rewind and place the two pixels one over the other…

![](https://hg2dc.com/wp-content/uploads/2021/12/add-in-green-pixel-1.png?w=800)

[Now let’s take the exact same movement of the red pixel from Question #22](https://hg2dc.com/question-22). Let’s see what the result would be…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-moved-no-grid.png?w=800)

**FIGURE EMISSION MIX** Here we shifted down the emission of the red light at 50% such that it “overlaps” with the green light at 60%.

Here, our red emission of 50% has been mixed with our green emission of 60%. The result? That yellow looking band. What’s happened here? The three channels have been added together, which is exactly what we’d expect with a reddish and greenish light!

`GREEN_PIXEL_EMISSION[0%, 60%, 0%] + RED_PIXEL_EMISSION[50%, 0%, 0%] = RED_AND_GREEN_PIXEL_EMISSIONS[50%, 60%, 0%]`

As you know, when we mix red and green light, we get a yellowy mixture of the wavelengths from the sRGB diodes.

---

We know that we are not finished, of course, as we have not *encoded* the linear light emissions for our output display device yet. To do so, if you recall back to [Question #22](https://hg2dc.com/question-22), we need to consider both the **geometry** of the pixel windows *and* the **emission** of the pixel we moved to get the overall quantity of light. If this is a slippery idea, refresh by going back to [Question #20](https://hg2dc.com/question-20) and covering the core fundamentals of the idea of geometry and it’s relationship with quantities of light.

Given we are talking about two pixel windows with our example having 100 units of coverage in each, let’s see how the geometry breaks down…

![](https://hg2dc.com/wp-content/uploads/2021/12/red-pixel-moved-grid-on.png?w=800)

**FIGURE GEOMETRY MIX** Here we can see the overlay that illustrates the total area of coverage of the pixel window that the emission is producing.

We know our geometry is conveniently based on the 100 unit divisions, and we’ve moved the pixel down 30% into the destination, or three rows. We also know the emission strength of our starting red pixel of 50%. We have enough information to manually calculate the proper result for our mixing.

Our upper pixel window consists of 100 geometric units, and now our red emission of 50% total display light is only covering 70% of the remaining upper window. The result?

**UPPER PIXEL**: `0.70 * 0.50 = 0.35 == 35%`

---

And our lower window? That’s a little more complex isn’t it? First we have two regions, the yellow and the green region. We are going to calculate each individually, then add them together to get a proper mixture.

First the mixed yellow portion. We can see that it is covering 30% of the pixel window where the red and green emissions overlap, and our emission was originally 50% red.

**LOWER PIXEL**: `0.30 * 0.50 = 0.15 == 15%`

Surprise! Nothing has changed from [Question #22](https://hg2dc.com/question-22) here! The values are *exactly* the same for the red pixel. What *has* changed? Now the red portion covers 30% of the window that is emitting 60% green underneath. To that green pixel, we need to add our small 30% portion, which is emitting the original 50% emission red.

---

So what’s the final pixel emission components? Let’s add the two together.

**LOWER RED** `[0.15, 0.00, 0.00]`

**LOWER GREEN** `[0.00, 0.60, 0.00]`

**SUM** `[0.15, 0.60, 0.00]`

And then we encode the values according to the particular display’s transfer function. Again, for a commodity sRGB display, that’s a pure power function of 2.2 for the output, so we inversely encode the values.

**LOWER RED** `0.15^(1.0/2.2) == CODE 0.42`

And our green portion is encoded as the following.

**LOWER GREEN** `0.60^(1.0/2.2) == CODE 0.79`

And our blue portion is encoded as the… ah right… it’s zero. Zero is zero when we roll it through the magical encoder.

**LOWER BLUE** `0.00^(1.0/2.2) == CODE 0.00`

Final sRGB-like triplet?

**LOWER RGB CODE** `[0.42, 0.79, 0.00]`

And recall back that our upper pixel window has 70% of the coverage with a 50% emission red, which is as follows.

**UPPER PIXEL** `0.70 * 0.50 = 0.35^(1.0/2.2) = 0.62`

**UPPER RGB CODE** `[0.62, 0.00, 0.00]`

What does it look like? Glad you asked…

![](https://hg2dc.com/wp-content/uploads/2021/12/final-mixed-yellow-ish-pixel.png?w=800)

**FIGURE FINALLY** The final output of the mixtures of emission geometry, converted to sRGB-like code values.

---

As slow and tedious this has been, hopefully you have seen that adding the emissions of the two pixels is *extremely* straightforward. It’s clear, simple math, with a clear and simple encoding to the display’s inverted transfer function. Much wow. Much simple.

**Answer #23: To move one emitting pixel over another, we simply calculate the relative geometry and add or remove as required.**

Our calculations are nothing more than extending the exact same ideas that started with [geometry of emission in Question #20](https://hg2dc.com/question-20), as [applied to pixel encodings in Question #21](https://hg2dc.com/question-21), and [pixels moving geometry as in Question #22](https://hg2dc.com/question-22). It’s that simple.

---

And with that we have expanded our understanding of light mixture by building on top of the three previous questions.

You are probably wondering if this is getting darn close to that slippery subject called “alpha”, and you’d be quite right. In fact, [we are now able to discuss what happens under the hood…](https://hg2dc.com/question-24)

---

1 For those interested, the two titles at the top of this post are wonderful entries into the rabbit hole. It should be noted that the rabbit hole got plenty more deep, literally, with the advent of “deep pixels”. [None other than Mr. Duff himself, at Pixar, has been responsible for fleshing out our conceptual models further](https://graphics.pixar.com/library/DeepCompositing/paper.pdf).



 
# Question #24: How the F\*ck Do We Move a Red Pixel Down and Block Another Pixel’s Emission?

**Question #24: How can we move the red pixel from [Question #23](https://hg2dc.com/question-23) down and block the green pixel?**

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

That is, much like the gas, the region is *still* emitting light as when it was a gas, but in this case, Brother Red’s geometry is **also** blocking Sister Green’s geometry and emission! Another way of thinking about “blocking light” is *occluding*. And specifically here, Brother Red is occluding the light emission behind him not only in his own pixel window, but also over a portion of Sister Green’s window.

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

**Answer #24: To move a pixel down and simulate blocking light, we consider the geometry and scale the background emission accordingly.**

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

1 To stress, the Colour Component Transfer Function here corresponds to the output from the particular assumed display we are using. The colour-sciencey lingo for a display’s output is Electro-Optical Transfer Function, or EOTF. Note that every display may use a different specification EOTF! Also note that for a vast majority of “sRGB” displays, the hardware EOTF is *not* the specification’s sRGB EOTF, but rather a likely more inexpensive hardware based 2.2 power function. As such, the code values used here are *not* the canonized sRGB inverse EOTF encoding. They are representing a typical sRGB-like display. The article uses this simplified result for both accuracy of the common case, and clarity of the math. [This footnote is here to shut the WANKers up.](https://hg2dc.com/question-1) |↩︎]] 



 
# Question #25: What the F\*ck is Alpha?

**Question #25: What is alpha?**

**Answer #25: Yet another dumb f\*cking Greek glyph label that a math nerd arbitrarily decided to use.**

Done.

---

As with all things related to digital image making it seems, there are way too many horrible labels based on completely unrelated names for glyphs from the Greek alphabet. Math nerds, we love you, but your choice of placeholder terms absolutely f\*cking sucks.

We need to drill past terrible Greek glyph labels such as “gamma” and “alpha” to get to something meaningful. Let’s re-lens our question into something much more useful.

**Question #25: What does an alpha encoded pixel represent?**

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

**Answer #25: In a properly encoded image, the red, green, and blue channels represent the precalculated emission, and the alpha represents the geometry of occlusion.**

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



 
# Question #26: What the F\*ck is Stimulus Colour?

Phew… it’s been a while dear friend. And with that repose away from the insanity of digital colour, it seems fitting to do a bit of revisionist history tour and look back to what we’ve covered. Why? Because I’ve totally f\*cking lied to you.

Remember way, way, way back where we first started trying to peel off the layers of confusion and outright bullsh\*t? Remember back to Question #1 where I said we were manipulating light emissions? That was only a half truth.

So let’s kick this question out and get down to business.

**Question #26: What is stimulus (encoding) of colour?**

---

Although it is likely a bit of an alien term, “stimulus”1 has a very real impact on the things we are discussing. During our accumulation of concepts across [Question #22](https://hg2dc.com/question-22), [Question #23](https://hg2dc.com/question-23), [Question #24](https://hg2dc.com/question-24), and [Question #25](https://hg2dc.com/question-25) we were getting into the nitty gritty details of manipulating light. Well dear reader, this is where the confession begins…

The basics of the RGB encoding model, as we learned in [Question #13](https://hg2dc.com/question-13), are tied intimately to [the CIE’s XYZ model](https://cie.co.at/eilvterm/17-23-042). This model is the single most important foundational system for an empiricist definition of colour. If you read the footnote from that post in [Question #13](https://hg2dc.com/question-13), there’s a wonderful quotation that needs to be focused on here…

> The chromaticity diagram is a [stimulus](https://cie.co.at/eilvterm/17-23-002) specification. A given color *perception* can be elicited by a [stimulus](https://cie.co.at/eilvterm/17-23-002) represented by just about any point on the chromaticity diagram, depending on the nature of the visual field and the viewer’s state of adaptation.
> 
> [Digital Color Management: Encoding Solutions](https://www.wiley.com/en-ca/Digital+Color+Management:+Encoding+Solutions,+2nd+Edition-p-9780470512449)

Without getting too deep here, [the CIE XYZ model](https://cie.co.at/eilvterm/17-23-042) is a mere breath away from the [tristimulus](https://cie.co.at/eilvterm/17-23-038) RGB model. In fact, it is so closely adjacent to the RGB model that we can refer to the RGB model also as a stimulus encoding model, because the RGB model builds atop of [the CIE XYZ model](https://cie.co.at/eilvterm/17-23-042). So what is the difference between [a stimulus encoding](https://cie.co.at/eilvterm/17-23-002) and actual radiometric light?

---

![](https://hg2dc.com/wp-content/uploads/2022/01/60vn01.jpg?w=504)

**FIGURE CONDESCENDING WONKA** Yeah… I lied…

We might slip into the philosophical a bit here, but it is worth noting that we are dealing with models of something us dumbass humans observe. We observe something, we fart around with some numbers, and derive some model that hopefully represents some aspect of the thing that we are trying to create an empiricist model around. How deeply we flesh out those models is subject to the designed needs of the model in question.

With respect to radiometric light, we could break it down into measurements of electromagnetic radiation, focusing specifically on a thin slice of that entire electromagnetic spectrum that is “visible to a standard observer”. Given that we aren’t inputting actual slices of energy and wavelengths into our digital content creation applications, it should be rather self-evident that our digital RGB model most certainly is not electromagnetic radiation values. That’s where I lied… the values simply do not represent light! Not directly, anyways…

So if we know that electromagnetic radiation is something different to our tristimulus digital RGB encoding model, what exactly is our digital RGB tristimulus encoding model? The first clue is to break down the word tristimulus into it’s two parts; “tri” and “stimulus”. “Tri” meaning three, and “stimulus” being that thing we are trying to flesh out.

So that tells us that it is in fact three whatever-the-f\*ck stimulus encoding thingys are. And of course if we loop back to [Qu](https://hg2dc.com/question-23)[estion #13](https://hg2dc.com/question-13), we know that [the CIE XYZ](https://cie.co.at/eilvterm/17-23-042) [chromaticity](https://cie.co.at/eilvterm/17-23-052) model is a specific model that allows us to discuss “colour”. Further, we can probably guess that the three independent stimulus encoded channels of “red”, “green”, and “blue” do *not* exist out in the wild world of physics… There’s no “Sal, go get a measurement of Universal Blue Lights for me.”

In fact, [the CIE XYZ tristimulus model](https://cie.co.at/eilvterm/17-23-042) is the glue between the electromagnetic visible light radiation and how that energy *stimulates* our receptors. It’s sort of the first order of business that connects uniform with respect to radiometric slivers of visible light energy to uniform with respect to biological cellular mumbo jumbo *stimulation*. Think of it as a Rosetta Stone that bonds the physical world model to the standard observer human model.

---

So why the f\*ck are we bothering with this seemingly pedantic difference here? Well dear reader, it is worth hammering the point home that the values in a stimulus encoding *is not* electromagnetic radiation. Sure, [the CIE XYZ model](https://cie.co.at/eilvterm/17-23-042) and electromagnetic visible light energy typically march lock stepped with each other for a standard observer, it is *absolutely critical* to appreciate that the two different concepts mean very different things. One is a ruler modelled after physical “real world” energy units, and the other is an abstract ruler modelled after cellular response to [stimulus-in-the-electromagnetic-sense](https://cie.co.at/eilvterm/17-23-002), derived from colour matching experiments.

How does this relate to your work as a digital pixel f\*cker?

---

If you are a 3D rendering peep, you’ve probably thought that you were pushing beams of light around inside your RGB “ray tracer” renderer, but of course you were never doing so. You were actually leaning on the fact that digital RGB tristimulus code values march in the aforementioned “lock step” with light energy. The RGB rendering engines are in fact *stimulus encoding renderers*. It’s exactly why they break down, because the two models despite being “locked” together with how the numbers and ratios work, are in fact radically different things.

If you are a graphic designer using Adobe Photoshop or Affinity Designer, this is also why you can’t input spectral quantities of electromagnetic radiation, and instead use that weird stimulus encoding “proxy” of digital RGB values.

Electromagnetic energy *is* indeed a stimulating energy for our biological sensors, but the resulting encoding / empiricist measurement system we use *is not* electromagnetic energy.

So… let’s hammer out the answer on this longwinded pile of crap post and answer what specifically our understanding of “stimulus” is in relation to numbers and models…

**Answer #26: The stimulus specification, or specifically a colour stimulus encoding, is a human created model that connects quantities of the visible range of electromagnetic radiation to the stimulation response of a standard observer.**

---

Phew. That was a janky yet mandatory thing we had to cross over.

The key takeaway at this juncture is that the description of numbers and ratios and all of the rubbish we’ve covered thus far is in fact *not* direct measurements of light, but rather communicated using a colour stimulus encoding value, as specified in [that CIE XYZ model from way back in Question #13](https://hg2dc.com/question-13).

Why is this so damn important to cover now that you had to read this airbag post? Well, dearest reader, we’ve hopefully expanded our understanding enough to get into some sticky yet familiar terms that require this distinction for moving forward. That means we will be able to glue together the previous four posts and some pretty important and commonly misunderstood concepts. [But that will just have to wait a bit longer…](https://hg2dc.com/question-27)

---

1 Given that the official [CIE term list identifies “stimulus” directly as electromagnetic radiation](https://cie.co.at/eilvterm/17-23-002), it’s worth noting that this post tries to address the fact that we are dealing with a stimulus or tristimulus *encoding* when dealing with imagery etc. When you read the word “stimulus” in this context, it’s worth noting that it’s referring to a singular stimulus *encoding*, or a tristimulus *encoding*. For the sake of identifying the differences between actual electromagnetic radiation and the way we specify its impact on a standard observer in terms of encodings, it seems a reasonable term to harness. Note even [the CIE term definition for “Reference Colour Stimuli”](https://cie.co.at/eilvterm/17-23-037) uses the term “theoretical stimuli”, which could be considered ambiguous where a strict interpretation of stimuli with respect to electromagnetic radiation were to be enforced. “Theoretical stimuli” in terms of the theoretical numerical encoding of XYZ become somewhat nonsensical if we are forced to think rigidly in terms of electromagnetic radiation. TL;DR: Consider the use of “stimulus” used here to refer to the nature of the theoretical stimuli encodings we manipulate, and that those theoretical stimuli encoding values are somewhat detached from broader electromagnetic radiation mechanics. If someone feels that the strictest definition of “stimulus encoding” must be adhered to, it should be easy to replace the shorthand use of the term “stimulus” with something like “The R in RGB in this instance means the numerical value in relation to it’s meaning relative to the chromaticity encoding diagram, that is a stimulus specification” in a text editor for their own private reading. The more important point here is to give a person a useful construct to build further inferences upon. |↩︎]] 



 
# Question #27: What the F\*ck is Perceptual Colour?

Remember how I promised years ago that this series would supply the typical digital image maker with fundamental concepts to get a grasp on the complex world of digital colour? This post is the second half of bolting down two important distinctions that cascade into many other insights.

[Question #26 probably feels like a massive departure](https://hg2dc.com/question-26) from the four questions prior that [culminated in Question #25’s discussion of what is alpha](https://hg2dc.com/question-25). In many ways, each question attempts to add a piece of understanding that can be re-assembled into useful weaponry, and this post is precisely such a piece. In fact, it’s the [other half to Question #26’s question about stimulus encoding values](https://hg2dc.com/question-26)1.

First, let’s barf out that question…

**Question #27: What is a perceptual sensation when discussing digital colour?**

It’s a broad stroke question, but we are going to first differentiate ourselves from this question’s twin sibling of [Question #26’s tristimulus encoding model](https://hg2dc.com/question-26). As with all things colour, it can be extremely helpful to *see* an example of what the hell something might be…

![](https://hg2dc.com/wp-content/uploads/2022/01/question-27-abney-effect.jpg?w=1024)

**FIGURE F BLUE** Notice how the “Perceptual” sensation of blue shifts as we move along the gradient?

See how the perceptual sensation of blue seems to drift to a purple mauve? Have a peek at that for a while, and come back after the break to break down what is commonly referred to [as the Abney Effect](https://cie.co.at/eilvterm/17-22-070)…

---

So what are we f\*cking looking at in **FIGURE F BLUE**? Here we see a basic gradient, which consists of a “pure” primary light, without any complimentary light. That is, it’s BT.709 / sRGB blue, at full intensity. Gradually, we add some “achromatic” digital R=G=B light in terms of the respective tristimulus encoding. Except as we do this… the perceptual appearance of hue twists into a… purple-ish!

Let’s analyze this using some of the quantitative means to discuss colour we [covered in Question #13](https://hg2dc.com/question-13) and [Question #15](https://hg2dc.com/question-15). First, let’s generate a simple “sweep” of the above values.

![](https://hg2dc.com/wp-content/uploads/2022/01/abney-sweep-start.jpg?w=1024)

**FIGURE ABNEY START** Here’s the result of adding achromatic tristimulus encoding values, aka less nerd term “achromatic light”.

Now let’s plot the above sweep, as a line in a “Perceptually Uniform Colourspace” such [as the model from Question #15](https://hg2dc.com/question-15), CIE 1976. Here each of the swatches march from “more pure” to “less pure”, and form a line from the absolute purest spectral locus position, through our starting sRGB blue value, to the achromatic adapted D65 white point.

![](https://hg2dc.com/wp-content/uploads/2022/01/abney-sweep-start-plot.jpg?w=595)

FIGURE UNSURPRISING STRAIGHT LINE Notice how the plot of values is a straight line toward the white point.

Notice how in this “Perceptually Uniform” plot, we have a straight line. One might be wondering that if the damn plot is actually “Perceptually Uniform” and whether or not a “uniform” straight line should be… “Perceptually Uniform”. Fair question. Before covering that… let’s generate a sweep of an attempt at a perceptually uniform “hue” version.

![](https://hg2dc.com/wp-content/uploads/2022/01/abney-sweep-corrected.jpg?w=1024)

**FIGURE PLUS OR MINUS** Plus or minus the underlying model, some nuances on encoding clipping, and a bunch of other sh\*t, here’s something a little closer to “Perceptually Uniform”. Note: The model used tends to cleave a little too far to bluey cyan.

The **FIGURE PLUS OR MINUS** is a sort of guesswork based on a model2 that attempts to be a little more “Perceptually Uniform” with respect to “hue”. Let’s have a peek at how that plot looks. Again, we draw a line connecting each of the swatches from left to right above, as they march toward the achromatic white point.

![](https://hg2dc.com/wp-content/uploads/2022/01/abney-sweep-corrected-plot.jpg?w=595)

FIGURE F\*CKING CURVES As we can see… an actual “Perceptually Uniform” hue sweep isn’t straight here! It’s curved!

Oh gosh. The damn line is *curved* in a “Perceptually Uniform” plot. From just beneath us, we can hear the blood curdling screams of “WHAT THE F\*CK IS GOING ON!?!”

As the above question hinted, if the model is supposed to be perceptually uniform, then a uniform straight line should be representative of a uniform step distance in perceptual appearance. And of course we can clearly see that CIE 1976 sure as hell does not seem to abide by this rule, and therefore we’d have to place a caveat on the idea that the CIE 1976 model, or *any* model for that matter, lines up with a perceptual appearance metric.

A general rule of thumb, try to remember that models are models; Human crafted things that try to represent something for serving some distinct purpose. [The map is not the territory](https://en.wikipedia.org/wiki/Map%E2%80%93territory_relation) however, and we must be very careful in how we read models! Caveat Emptor. In this specific case, the CIE 1976 plot is a distorted plot of CIE 1931 tristimulus values, massaged in such a way that “distance” holds a little more validity with respect to how we’d sense them on the perceptual side. And we can clearly see that it’s not without some deeper issues…

---

So where does this leave us? The reason we went romping across Abney is to show that there’s a fundamental disconnect between the tristimulus encoding side, the side that *sort of, kind of, almost* aligns uniformly with electromagnetic radiation, and the perceptual sensation and appearance side. Remember Dr. Jekyll and Mr. Hyde? It’s almost like colour is composed of a Dr. Jekyll and Mr. Hyde; two different perspectives on the “same” thing!

Let’s see what the CIE has to say for defining “colour”. Perhaps in an entirely unsurprising turn of events, there are two definitions listed.

> **colour**, <psychophysical>  
> specification of a [colour stimulus](https://cie.co.at/eilvterm/17-23-002) in terms of operationally defined values, such as three [tristimulus values](https://cie.co.at/eilvterm/17-23-038)
> 
> [CIE Termlist for colour](https://cie.co.at/eilvterm/17-23-001)

But wait… there’s more!

> **colour**, <perceptual>  
> characteristic of [visual perception](https://cie.co.at/eilvterm/17-22-082) that can be described by attributes of [hue](https://cie.co.at/eilvterm/17-22-067), [brightness](https://cie.co.at/eilvterm/17-22-059) (or [lightness](https://cie.co.at/eilvterm/17-22-063)) and [colourfulness](https://cie.co.at/eilvterm/17-22-072) (or [saturation](https://cie.co.at/eilvterm/17-22-073) or [chroma](https://cie.co.at/eilvterm/17-22-074))
> 
> [CIE Termlist for the other colour](https://cie.co.at/eilvterm/17-22-040)

---

Let’s try to get to an answer that can work for us…

**Answer #27: Perceptual sensation of colour is a cumulative appearance based on a number of contextual3 facets.**

---

After seeing our demonstration above, we can probably hear the screams from the depths of the abyss of the poor shadows of former even more poorly informed graphic designers who painstakingly and meticulously copied the f\*cking hex codes into their work, only to have the client lose their minds that the “Colour looks different!”. So many layers of really bad and broken ideas stack together into one gargantuan sh\*t sandwich.

Imagine being the unfortunate 3D rendering wonk who models a car with glossy BT.709 blue paint, and renders it under a nice soft achromatic cloud cover. The blue paint appears as a graduation from the blue to white cloud reflectively mixed from the glossy coating, just like the above demos… and the client? They sh\*t their pants screaming at the poor 3D rendering wonk that their brand identity blue car paint is f\*cking blue, not mauve! The 3D rendering wonk goes and yells at the poor 3D rendering lighter and, they go and yell at the… you get the idea.

So what is in this for the digital RGB surgeon or… digital RGB serial killer? It is with hope dear reader, that by equipping oneself with a dual Dr. Jekyll / Mr. Hyde notion of colour, one is more informed to try and break down problems and *hopefully* solve them.

---

We can, building on top of the conceptual framework outlined between [this Question #27](https://hg2dc.com/question-27) and [the previous Question #26](https://hg2dc.com/question-26), loosely describe a sort of cylindrical model for *both* of the CIE term definitions of “colour” above. A cylindrical model has a height, an angle about some origin, and a distance from the origin. If we assume that our adapted white point is our origin, we have two parallel models we can weaponize. While familiar ideas, it can be helpful to bolt them down into a more concrete form:

CIE Tristimulus Cylinder Model:

1.  CIE xyY Height == Luminance / Y
2.  CIE xyY Angle == Chromaticity angle
3.  CIE xyY Distance == Chromaticity purity

And as a corollary we now have a Perceptual Cylinder Model4 version of the above!

1.  Perceptual Sensation Height == Brightness
2.  Perceptual Sensation Angle == Hue
3.  Perceptual Sensation Distance == Chroma

And we can see a relation breakdown of each parallel model…

-   Tristimulus xyY Luminance is associated with but has a nonuniform relationship to Perceptual Brightness.
-   Tristimulus xyY Angle is associated with but has a nonuniform relationship to Perceptual Hue.
-   Tristimulus xyY Purity is associated with but has a nonuniform relationship to Perceptual Chroma.

And from that loose sort of a breakdown, we can sort of see some interesting connections between the two models! It is a good rule of thumb to remember that in terms of the two parallel models, while each facet is *associated with* the other, much like Dr. Jekyll and Mr. Hyde, *each pair of facets hold a non-uniform relationship to the other*!

As we explored above, the CIE xyY angle and distance in a straight line hold a nonuniform relationship to the Perceptually Uniform Sensation of hue! Conversely, a Perceptually Uniform Sensation of hue is going to hold a nonuniform relationship to the CIE xyY angle between the achromatic point and the spectrally purest point.

As per [Peter Engeldrum](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.104.5669&rep=rep1&type=pdf), a general rule of thumb to identify when one is in the perceptual appearance domain is to look to the words used to describe whatever is being described. [If a term ends in “ness”](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.104.5669&rep=rep1&type=pdf), there’s a good chance we are talking about Mr. Hyde’s perceptual appearance sensation! “Colourfulness”, “Brightness”, etc. are all good examples.

To connect the dots further, we should be also able to look back to the idea of a compressing transfer function, [as with Question #6](https://hg2dc.com/question-6), and know that because it is a compression function based on the *perceptual sensation of brightness*, that the relationship will be nonuniform with respect to the CIE xyY luminance component, and indeed it is! The same goes for ideas of chromaticity purity versus a perceptual sensation of chroma, too!

Every poor graphic designer is probably out there revisiting their thoughts on brand identity guidelines right now…

So let’s wrap this up, and remember to keep this duality of “colour” at the front of our minds for what [is going to follow…](https://hg2dc.com/question-29)

---

1 As with most things colour related, it’s worth pointing out a bit of pedantry. The goal of this series has always been to provide useful groundwork and concepts to digital image surgeons, or digital image serial killers, to help them perform surgery in the first case or… uh… work their craft in the second. Some of that comes with a totally-unscientific-guesswork trade off of strict adherence to CIE terminology versus “useful” and selective corner-cutting. The previous post gets so close down to the metal of discussing colour, that we are in the domain of terms that colour people will bicker and argue about for a very long time. It is with hope that a PhD colour scientist foolishly reading these posts would see that sometimes, in the interest of nudging a specific audience’s progression towards a greater understanding, that a corner or two is cut. The author begs forgiveness from those colour science PhD types…

2 The model used here was Dr. Fairchild and Dr. Ebner’s IPT, for those nerds out there interested. It’s a mathematically fit model to some datasets, which also generally means everything falls to crap pretty quickly.

3 Does the colour of the paint surrounding what we are looking at impact our sensation of colour? Yes. Does the brightness of the light lighting the paint impact our sensation of colour? Yes. Does the white thingy [as per Question #14](https://hg2dc.com/question-14) we’ve adapted to impact us? Yes. Don’t despair! The point isn’t to throw our hands up in the air and give up. The point is to be aware that no amount of code value computer gobbly math nerd slop can insulate us from the nuances of perceptual colour consumption. The more aware we are about the potential compounding contexts that influence the perceptual sensation of a particular stimulus, the more well equipped we are to deal with those differences out in the dirty trenches of image making.

4 Don’t get the idea that this simple division is an endpoint! Colour science and vision researchers have some agreement on the idea that there are “layers” or “orders” to this complex stack. For the purposes of this post, we could say that the twin Dr. Jekyll and Mr. Hyde models are of a lower level order. Closer to the metal, with all sorts of complex things potentially happening in the layers above. All we are trying to do here is derive two basic concepts as a tool for ways to consider colour.



 
# Question #28: What the F\*ck is the Difference Between Affect and Effect? (And What the F\*ck is Rashomon?)

[Rashomon](https://www.imdb.com/title/tt0042876/) was a film that offered a unique multiple recounting of a horrible incident. Why am I bringing it up here? It seems fitting.

In order for us to fully appreciate the depths to which we have plunged, it is critically important for us to pay close attention to the two most recent posts. In [Question #26](https://hg2dc.com/2021/12/03/question-26/), we’ve seen that there’s a metric for describing a relationship to tristimulus with respect to the Standard Observer. In [Question #27](https://hg2dc.com/2022/01/14/question-27/), we’ve seen that there is a parallel, upside down universe that can describe our sensation of appearance of the aforementioned tristimulus using some other metric.

For a long while, there was a plan to dive into things like photographic exposure, contrast, chroma, and saturation. But sadly, the explanations kept returning to the complexity of fully embracing the contextual nature of colour appearance, while simultaneously understanding the representation of that appearance utilizing some tristimulus metrics. So how would we move forward?

It became clear that there was a unique way to retell understanding uncovered in [Question #26](https://hg2dc.com/2021/12/03/question-26/) and [Question #27](https://hg2dc.com/2022/01/14/question-27/) by revisiting the old posts, one by one, and seeing how the author totally lied to us.

**Question #28: How does the difference between affect and effect relate to our use of digital colour?**

This comes complete with our Rashomon inspired sub-question…

**Subquestion #28: How did the author lie to us when they asked “What the F\*ck Happens When We Change an RGB Slider Value?”?**

---

> **Answer #1: You are increasing or decreasing the emission intensity of one of the three RGB lights.**
> 
> – Idiot Author

In fairness to our idiot author, this isn’t entirely incorrect. The point that we should focus on is trying to diagnose which domain this falls into.

We know that RGB is a tristimulus specification related metric, and that all three values uniquely identify a chromaticity coordinate, as well as being intimately interwound with luminance.

That is, we can already identify that the RGB encoding itself is a tristimulus specification, which clearly locates it in the [Question #26](https://hg2dc.com/2021/12/03/question-26/) category of “stimulus”. Further to this, we should be able to use our rule of thumb that tristimulus relates non uniformly with sensation of appearance to glean further insight.

---

When we said that we are simply increasing or decreasing the emission strength of a given channel by adjusting a slider, this comes with some typical inferences that are, in fact, frequently *wrong*. Things like “We are increasing the brightness!” or “We are making it more chroma laden!” or “We are changing the hue!” are all incredibly useful ideas, and they are all completely wrong in this context.

Why are they wrong?

Take note of the terms used. “[Brightness](https://cie.co.at/eilvterm/17-22-059)“, “[Chroma](https://cie.co.at/eilvterm/17-22-074)“, and “[Hue](https://cie.co.at/eilvterm/17-22-067)” are perceptual appearance percepts! This means that they are marching along to some uniform metric that we’d associate with [Question #27](https://hg2dc.com/2022/01/14/question-27/), not [Question #26](https://hg2dc.com/2021/12/03/question-26/)!

So while our author didn’t quite *entirely* lie to you, they did indeed subtly leave the door open here for misleading information.

First, there’s no such thing as “RGB emission”. No really, go down to your local hardware store and ask them for a lamp that is fifteen units of Red channel. The hospitality of the greeter will be tested as the bulb just doesn’t exist! In order to translate the amplitude of RGB tristimulus coordinates to an actual radiometric emission from some specific spectral source, we’d need to transform the amplitudes of the RGB tristimulus values into a quantity of emission, based on some specific spectral composition.

But enough about that… let’s move onto a more important difference that may have been subtly, and incorrectly, inferred. The difference between *affect* and *effect*.

---

In order to try and make this point clear, let’s think about audio signals for a moment. We can wire up a speaker to an amplifier, and control the voltage on the amplifier with a big knob. We can route the output of the amplifier current to a speaker. Now we can turn the knob, and our music goes up and down.

But if the knob is directly controlling current, do we say that it is *affecting* the volume, or *effecting* it?

That is, when we change the current via the knob, the knob moves 1:1 with the current, and indeed the volume *changes*. This is a subtle difference worth pondering, because we can ask ourselves if the knob is doing us a utility as a design if it is controlling current, or controlling the volume. We turn the knob and over some range, it seems to behave as we would like, but then it is also simultaneously hard to control the volume, or more specifically, we are *effecting* the volume where we’d like to *affect* the volume. We are *affecting* the current, and *effecting* the volume.

---

Looping back to digital colour, when we *affect* the amplitude of tristimulus values, we are always *effecting* the sensation of appearance. When we turn the knobs on the tristimulus, we are indeed *effecting* the hue, chroma, and brightness. But in terms of control? We are not directly *affecting* any of those percepts! We could even say labelling the channels as “red”, “green”, and “blue” is part of the problem here1!

We know that in order to affect the hue, value, and chroma we’d need to exert a non-uniform distortion on the tristimulus, and that’s likely never going to happen by essentially *affecting* something closely related to a current knob. Indeed, to *affect* the sensation of appearance, we should be operating in a domain that is more closely aligned with appearance percepts2, and not tristimulus.

And with that, we’ve pulled a Rashomon and retold an answer to our very first question!

**Answer #28: To properly affect digital “colour”, it requires close attention to the desired domain of stimulus or appearance, and choosing an appropriate model to achieve such. Changes in one domain effect the other, not affect!**

Both stimulus domain manipulations and appearance domain manipulations are useful, and we ought to pay attention to just what we are attempting to achieve.

[Moving onto the next bucket of lies from the idiot author…](https://hg2dc.com/question-29)

---

1 Why is labelling the channels according to “red”, “green”, and “blue” part of the misdirection here? Take a look at the following image from [the famous Akiyoshi Kitaoka](http://www.psy.ritsumei.ac.jp/~akitaoka/histogram_compression-ECVP2021-ShowTime.html). See the UK flag red? It is a wonderful demonstration of the sensation of appearance of red, yet there is no tristimulus indication of red. The red channel lies! It helps to think about how we’d increase the sensation of appearance of redness in this sort of context, or more specifically, *affect* the appearance of redness. *Affecting* the tristimulus channel of “Red” is going to yield underwhelming results. Give it a try if you are in disbelief. Always remember that the appearance of colour is purely constructed in our perceptual system. |↩︎]] 

![](https://hg2dc.com/wp-content/uploads/2022/08/akiyoshi-kitaoka-demo.png?w=1024)

**Totally Red Appearance Sensation But Totally No Red**

2 Good luck finding this model. Chasing appearance models is less fruitful than looking for that Fifteen Unit Redness bulb at the hardware store, and probably a thousand times easier chasing down a unicorn or a leprechaun. Or a leprechaun riding a unicorn. This mythical perceptual model simply doesn’t exist. Most of them are fit models, based on some random set of research, and some underlying heuristic assumptions. They may be more or less useful in some specific niche, and smash like peanut brittle when extended for usage beyond. They can of course be useful in some limited contexts, but the wise reader exerts tremendous caution. We simply do not understand perceptual systems enough to develop robust models yet. If anyone is selling you on some perceptual mumbo jumbo, there’s a good chance they are selling you a bucket of rubbish. This is why the CIE pursues [Colour Appearance Model](https://cie.co.at/eilvterm/17-23-027) research to this day, with many explorations and variations on the themes. |↩︎]] 



 
# Question #29: What the F\*ck is Intensity, Again?

Following on from [Question #28’s Rashomon inspired retelling](https://hg2dc.com/2022/08/11/question-28-what-the-fck-is-the-difference-between-affect-and-effect-and-what-the-fck-is-rashomon/), we are going to look again at what [Question #2](https://hg2dc.com/2019/03/24/question-2/) brought to the table, and pick it apart.

[Question #2](https://hg2dc.com/2019/03/24/question-2/) asked:

> **Question #2: What does** `**0.6**` **represent in a typical DCC context?**
> 
> – Idiot Author

The answer to [Question #2](https://hg2dc.com/2019/03/24/question-2/):

> **Answer #2: In an RGB DCC application,** `**0.6**` **is a ratio between a minimum and maximum, representing some ratio of light intensity.**
> 
> – Also Idiot Author

**Question #29: What did the author really mean with “intensity” when they described the numerical value?**

So was the Idiot Author totally and utterly misleading the reader? In a way, yes, and to appreciate how, it is worth taking a slightly closer pass at investigating *intensity* a bit more…

---

When we throw around numbers, it is easy to conflate the number metric with the meaning of what the unit of measurement represents. The same subtle misdirection is happening in the question and answer.

We discussed how the typical usage case relates to the sRGB *encoded* value. What we weren’t quite explicitly clear about, nor at a juncture where we could discuss the nuance in depth, was a focus on the metric. As with [Question #28, we know that the author fibbed a little when they said “light” intensity](https://hg2dc.com/2021/12/03/question-26/).

Most digital craftsfolk can toss out a random smattering of encoding metrics that, in the case of digital colour, frequently amount to amplitudes of some triplet. Adobe RGB, sRGB, BT.709, ARRI LogC version 3, etc. are all such examples. Each of these has accompanying definitions that identify how the *encoding* relates to the broader model of colourimetry defined within the CIE Standard Observer model, frequently the 1924/1931 Illuminant E Standard Observer.

It is worth noting however, that relative to some encoding metric, we are often not quite in the proximity of a Standard Observer tristimulus projection. That is, the *numerical value of the encoding* carries no essential colourimetric meaning in its *encoded* state. The *encodings* provide us with a mechanism to get to this colourimetric definition, through careful decoding.

But even if we have properly *decoded* the *encoding* to a relative tristimulus amplitude, what exactly is the base unit of “intensity” here? What is the incremental unit from 0.1 to 0.2 for example?

---

To answer this, we will need to answer a deeper question about the CIE XYZ colourimetric model. We know that the XYZ model indicates something about a stimulus specification, but when we say “0.1 units of X” what exactly is that increment in relation to?

When we say something like “The Standard Observer Model” we generally mean a specific year and date of the model, which will include a “degree” in terms of the field of view tested during the stimulus matching experiment. In the classic 1931 Standard Observer model, there is another specification that was used to derive the most famous Standard Observer. [This specification comes from 1924](https://cie.co.at/publications/cie-10-degree-photopic-photometric-observer), and is known as the CIE 1924 photopic photometric observer. So what, you ask?

In order to answer what the 0.1 units are above, we need to realize that the entire “scale” of the model is based on that 1924 research. That is, the model was distorted and projected with the luminous efficacy scale as the central spine. It’s the Y component after all! So what are the implications? All three channels in the resultant CIE 1931 Standard Observer Illuminant E XYZ model are gained lock step with that CIE 1924 photopic photometric observer. The most fundamental base unit “distance” measurement, in all three directions, is effectively based off of relative luminance!

---

**Answer #29: When discussing encodings of tristimulus chromaticity coordinates, it is probably wiser to avoid the term intensity, and consider them strictly as encoded ratios of tristimulus, and these ratios are anchored in the CIE 1924 photopic photometric observer as the base unit of the metric.**

As a general guideline, it is worthwhile to accept that a digital *encoding*, be it from a camera, an EXR, an image, or anything else in the world of digital colour, is often times an *encoded* value. We risk grave confusion when we start loosely tossing terms around in the deep end of the pool, which in turn, might pile up and form an incorrect vantage of the surface in question, leading to us drowning in the aforementioned pool.

When a tristimulus value goes upward, it is probably makes good sense to ask what that shift in amplitude means. For our purposes, when discussing colourimetry and the tristimulus values used to communicate colourimetry, the base unit stands in relation to relative luminance, and a straight line to notions of energy in the radiometric sense. |↩︎]] 

[And now, onward…](https://hg2dc.com/question-30)



 
# Question #30: What is the F\*cking “Colour” of Light?

Hello. I just wanted to let you know that the dimwitted author set their password to “password”. This left a glaring security hole in their website.

I’ve just read over all of this nonsense, and I’d like to tell you all that you’ve wasted your time. The author is a *complete* idiot. See, they’ve led you to this ridiculous blog, in an attempt to sell you something or gain clout or some other reason. The whole premise of all of this nonsense is f\*cking absurd.

I’ve read this question that asks:

**Question #3: Does changing the intensity of a single RGB light change its colour?**

The answer the author of this horrible site gave is so completely ridiculous, so completely out to lunch, that I can’t even begin to know where to start. Look… I don’t have long here as they might flip their password over to “Gretzky” or something and lock me out. So let me try to be very quick…

---

The idea that “colour” in the usage of “colour matching” experiments, or “the colour of light” is nonsense. Straight up, pure, unadulterated horsesh\*t. Why? Because colour doesn’t exist outside of our cognition. Colour, as much as it is familiar to all of us in an intimate way, is actually a relationship. We might think of the simplest form of this as a relationship of A to B.

Let’s look at a simple example…

The “diamonds” in the interior regions are of equal tristimulus. The percept of the diamonds, however, is one of significantly different “lightness”. Generally folks will perceive the lower diamonds as “darker”. If we change the arrangement, or, to use [David Katz’s terminology from his 1935 book *The World of Color*, the **articulation**](https://psycnet.apa.org/record/1935-04031-000), of the picture tristimulus, we end up with a very different cognition endpoint. This also happens when we change the field size by zooming in or away from the picture!

“This is just illusory!” I can hear the idiot author shouting. Sorry, this is not illusory. To suggest these are “illusions” is to undermine the very foundations of our visual cognition. We don’t “see”, we *cognize*.

Another incredibly striking example is the glare and halo effect. Take note how the following showcases that despite identical tristimulus values, the “interiors” of the petals are cognized vastly differently. Simultaneously, albeit more subtly, note how the “exterior” of the petals are also subject to this spatio-temporal visual mechanic.

So why show these simple examples? Aside from being wonderfully economical in their ability to showcase how the spatio-temporal articulation of signals play the lead role in our visual cognition of all things, they pose a question unto themselves. Are these sorts of striking visual cognition mechanics somehow isolated, or infrequent in nature?

---

If we flip our entire world-view upside down, and dig a little deeper beyond the hallowed halls of CIE Colourimetry with respect to our discussions of colour, we rapidly realize that colourimetry, as explored in the previous 29 questions from the idiot author, is nothing more than a niche slice of a hotly contested surface.

We can go all the way back to [Helmholtz and Hering who apparently engaged in sh\*tposting of each other’s work](https://journals.sagepub.com/doi/pdf/10.1068/p2805ed) to see that the tenets and concepts of visual mechanics have been at least as territorially complex as modern day geopolitics. Today, the landscape of vision studies fractures into many different fields, and these fields *do not agree* on much of anything. In fact, to get a generalized idea of the landscape, it would require crossing over disparate fields such as computational vision, lighting, art, design, neurology, neurophysiology, biology, and many, *many* other fields.

The idiot author of this blog has done a disservice to you all by suggesting that colourimetry is the bog standard, uncontested world view of all of colour, and therefore digital colour. It is nonsense.

If we are to anneal our understanding in the pursuit of making our art and design work in these sloppy computers and mediums more stable, we have to explore the formulation of colour in our visual cognition systems, and separate the visual cognition of the term *colour* from the “outside” world.

---

Looping back to the Adelson Snake demonstrations, we can ask ourselves whether or not the spatio-temporal articulation impacts our sensation of colour. And the answer is of course provided by none other than [Dr. Akiyoshi Kitaoka, who did some riffing on the original Adelson demonstrations above](http://www.psy.ritsumei.ac.jp/~akitaoka/color11e.html). Dr. Kitaoka has provided us with compelling evidence that, as broadly hinted above, the spatio-temporal articulation impacts all of our visual cognizing of colour.

![](https://hg2dc.com/wp-content/uploads/2023/03/colorsnakeillusion.jpg?w=1000)

Here the spatio-temporal articulation of the picture’s field influences our visual cognition of the interior diamonds. Depending on your genetics in relation to your visual cognition pathways, some of the the R=G=B tristimulus in the diamonds will appear coloured. [Demonstration from Dr. Akiyoshi Kitaoka](http://www.psy.ritsumei.ac.jp/~akitaoka/color11e.html).

The above Dr. Kitaoka demonstrations are compelling examples as to how neglectful the basic measurement comprehension, usually in tristimulus units, of “colour” is. We can clearly see how a global frame of the stasis of R=G=B in our lower order systems can lead to percepts of colour in the visual cognition chain.

We ought to be able to [revisit the idiot author’s third question](https://hg2dc.com/2019/03/24/question-3/) and begin to paint a completely different framework for discussing “colour”.

In terms of *ratios*, changing the magnitude of the channels in an additive RGB system *uniformly* does *not* change the “measurement” in terms of colourimetric chromaticity. But *colour*? The colour as formed in the visual cognition pathways *does* change. Why? Because the above examples should at least hint toward the idea that colour is a broader cognitive activity, and part of the cognition relates to the spatio-temporal relationship in the articulated field.

Why do I keep hammering “spatio-temporal”? Why not just “spatial frequency”? Because the two are the same thing. Our visual cognition is tremendously reliant on the *temporal* relationship. Some colour might look a certain way and, given unique spatio-temporal relationships, shift! In fact, our visual field is ever changing based upon the biological feedback loop from the higher order processing.

First up… the classic [Troxler’s fading](https://en.wikipedia.org/wiki/Troxler%27s_fading) demonstration. Hold your visual field firm and fixate on the cross. One should find that the spatio-temporal articulation of the “colour” dissolves.

And of course, the temporal side is made more evident with this variation of the Troxler Fading effect. Here, as we fixate on the cross, we cognize a similar spatio-temporal colour as present in the above Dr. Kitaoka demonstrations.

Perhaps the most mind numbing part of our visual cognition, and how time is intimately related to visual cognition, is nicely demonstrated through contrast asynchrony. As the *relationship* between values shifts, our sensation of timing shifts. [There is a wonderful demonstration of contrast asynchrony given at Michael Bach’s website](https://michaelbach.de/ot/lum-inducedContrastAsym/). Mark Wexler has posted a video demonstrating fixed rings that induce similar temporal strangeness.

It is difficult to discuss spatio-temporal articulation effects without [Dr. Arthur Shapiro](https://en.wikipedia.org/wiki/Arthur_Shapiro_(vision_scientist))‘s name making an appearance. He too has [some wonderful interactive demonstrations on contrast asynchrony over on his website](http://illusionscience.com/contrast-asynchrony/). He is also a profound force in understanding the complexities of articulation, having written dozens of papers on the subject1.

---

I think the idiot author has just logged in, so I should be going. If you remember one piece of this guest post, it is to pay close attention to terms such as “colour”, “lightness”, “darkness”, and any number of the other terms floating around out there. No one understands visual cognition, and you shouldn’t feel too bad if you cross over conflicting use of terms and phrases. Even the folks with PhDs after their names do not necessarily agree on fundamental definitions!

**Answer #30: Uniformly changing the ratios of tristimulus in an additive RGB system does not change the “measured” colourimetry, however the colour \*does\* change!**

This statement might seem contradictory, but if we keep a separation between the idea that colour is psychological internal visual cognition, and [that the human made measurement of tristimulus is separate from such](https://hg2dc.com/2022/01/14/question-27/), we can probably get a better handle on things. We could go further and hammer home the general idea that *light doesn’t have a f\*cking colour*!

A critical building block in this post is to begin to think about colour, in the psychological visual cognition sense, as a construct predicated on *articulation*. Knowing how absolutely fundamental articulation is in visual cognition can help us to spot nonsense before it takes root.

Oh crap… here he comes… let’s hope he doesn’t carry on [misleading you in the next question…](https://hg2dc.com/question-31)

---

1 [Dr. David Eagleman has written numerous papers on the perception of time, and some have explored the timing of perception of visual signals in relation to cognition](https://eagleman.com/time-and-the-brain-or-what-s-happening-in-the-eagleman-lab/). Truly mind expanding for those interested in the relationship between visual cognition and time. |↩︎]] 



 
# Question #31: What the F\*ck is Colour?

There’s a lurking question sitting atop the pile of these posts, which hopefully has been emerging up and out of the swamp. The shambling shibboleth ultimately is one that we are going to need to tackle in order to revisit some of the previously answered questions in a much more valid manner.

I know that I promised that this would be focused on “Getting Sh\*t Done”, and that this romp man initially appear as a sidebar. Sadly though, when the client screams at you about colour being “different”, or when you carefully match a swatch using the proper colour space and test a soft proof and the print comes back seemingly “weird”, or when you go out and shoot your moving picture project and lean into some grand “colour management” system only to discover none of it worked… it’s a cold awareness that something is not well in the discussion of “colour”.

**Question #31: Just what exactly is colour?**

To answer this in any useful way that allows us to walk away with that sort of deeper “intuitive” understanding, we would do well to do a brief jaunt down the neurophysiological chain. Hopefully this won’t hurt too much, and perhaps instead begin a bit of fascination with what we call “vision”.

This is a longer post. In order to tackle the broad ideas, breaking the following out into smaller bite sized pieces would probably end up less than optimal. I hope you will forgive the length…

---

If we start with the retina itself, we can begin to flesh out a high level understanding of colour in terms of where we immediately begin to get things wrong. For example, few folks realize that our retinal assemblies that are capable of sensing radiation are *inverted*! Here’s a great diagram from Nathan Lents[1](https://hg2dc.com/2023/11/21/question-31/#8d2bcaea-c91b-4493-84a2-b69b0c85e54d).

![](https://hg2dc.com/wp-content/uploads/2023/11/img_0720-1.jpg?w=1024)

The black sensitive assemblies are “inverted” with respect to “conventional” logic in vertebrates!

Now immediately it might seem completely strange that we do not cognize the layers of veins, cells, and other assemblies that are in front of our radiation sensitive layers. This terrific little video might work to let one see the veins that are all over the surface of the retina.

A fun little experiment folks can try to reveal the mass of retinal veins in the path of the radiation that enters their eyes.

The hint as to the *why* we don’t see our veins and other bits has a research trail that goes back at least as far as 1952 in terms of controlled experiments. Ditchburn and Ginsborg[2](https://hg2dc.com/2023/11/21/question-31/#2eaec71d-6747-4c7c-8cc3-57462e4726a7), Riggs[3](https://hg2dc.com/2023/11/21/question-31/#73aa9999-5183-417c-9d3a-4e2e2adfa237), and later Yarbus[4](https://hg2dc.com/2023/11/21/question-31/#49655143-e3e2-4b04-8142-05f131659704) were all exploring this phenomena around the same time.

Through a series of incredibly clever setups, the researchers revealed that if the incoming stimulus was fully fixated to the observer’s eye, that the cognition of vision would completely cease to manifest! If we manage to remove the eye movement out of the equation, and keep the stimulus constant, our biological systems remove all cognition of vision!

To appreciate the mechanics of this strange “no difference – no vision!” engine, we briefly must romp down the primate vision chain. Remember, the following diagram, which is from *Retinal Connectivity and Primate Vision*[5](https://hg2dc.com/2023/11/21/question-31/#671f30fd-00dd-465b-b9ec-19f2a499d408), should be visualized as “inverted”; the radiation enters the retina and passes from bottom to up in the diagram!

![](https://hg2dc.com/wp-content/uploads/2023/11/img_0721-1.jpg?w=1024)

High level breakout of the human retinal tissue.

Now at this point, everyone around these parts is familiar with the whole broad understanding of [trichromancy](https://cie.co.at/eilvterm/17-23-036); three signals blah blah. Sadly, this is also exactly where our understanding of human colour goes off the rails.

Note those bipolar cells in the diagram above? These cells are responsible for differencing the basic electrostatic signals generated at the cones, against each other. This differential is achieved via what is commonly referred to as an inhibitory mechanism. Key takeaway however, is that the all too familiar “Long”, “Medium”, and “Short” (sometime labelled “Protan”, “Deutan”, and “Tritan”) absorptive profiles *never make it out of the retina as an “optic signal”*, a term borrowed from D. B. Judd[6](https://hg2dc.com/2023/11/21/question-31/#b258638b-c3be-44da-bafb-90fc41c09b0f). To be more forceful in an explanation, the idea that the Protan, Deutan, and Tritan absorptive profiles that generate electrostatic signals *appear to never*[7](https://hg2dc.com/2023/11/21/question-31/#12c54d87-3fbd-492f-9857-e8b9070d5e4b) *be propagated beyond the cone cells to the differential inhibitory mechanisms of the On-Off and Off-On assemblies*!

---

So what then is something closer to what the “optic signal” may be? The “truth” is much slipperier and murkier than some would have us believe. There’s no clear demarcation line in the messy world of biology, and this is doubly so with respect to visual cognitive pathways. What is *generally* accepted is that the differenced signal follows three broad assemblies:

1.  **P+D**: The Protan is combined with the Deutan absorptive profile signals.
2.  **P-D**: The Protan is inhibited by the Deutan absorptive profile signals.
3.  **(P+D)-T**: The Protan is combined with the Deutan absorptive profile signals, and inhibited by the Tritan absorptive profile signal.

I’ve chosen to use the Protan, Deutan, and Tritan terms here to avoid a typical over-ontologizing by way of the terms “Long”, “Medium”, and “Short”. The reason is that if we hear “Long”, we lose sight of the fact that the absorptive sensitivities of all of the cellular assemblies wrap the entire visible radiation range, to varying or lesser degrees. If one assumes that the “Long” only detects “Long”, it’s a precarious entry point toward “understanding” if there is any “understanding” to be had at all.

Worse, it’s also worth noting that the Protan and Deutan absorptive characteristics differ only by approximately 30 nanometers! That is, the absorptive profiles are more or less similar, “offset” from each other. Think of it as a “stereo” signal version of the attenuated radiation. I did up this somewhat clunky animation to showcase how the attenuation of energy profiles are “wrapped” around the spectral locus. This animation abuses the CIE xy diagram “map”, which in and of itself is an abuse of the actual “territory” of human visual cognition.

The idiot author’s attempt to provide a little bit of insight into the sensitivity arrangement via the CIE xy projection.

Phew… so where does this leave us? The reason that an understanding of how this differentiation mechanic may arise echoes back to the Yarbus work; the totality of what we call “vision” is utterly dependent upon the manifestations of differences of signals. That is, Judd’s “optic signal” term is not at all “quantities” of attenuated radiation as many folks erroneously infer!

---

At this point dear reader, I want to stress that if you hear someone say “The human eye is like a camera” they are talking directly out of the hole that exists just after their colon. It’s pure, unadulterated farm animal excrement. Alan Gilchrist has coined this construct *The Photometer Metaphor*[8](https://hg2dc.com/2023/11/21/question-31/#61905f02-429e-4c5a-b04a-b4d2bd91d6c6):

> Implicit in most theory and research on the perception of surface lightness is a conception we would call the photometer metaphor. This term refers to the assumption that, fundamentally, the visual system measures the intensity of light reflected by each point in a visual scene.
> 
> Gilchrist, Delman, and Jacobsen – “The Classification and Integration of Edges as Critical to the Perception of Reflectance and Illumination”

If we follow the basic anatomy of the retinal tissue in our primate systems, we can get a high level understanding as to just how wrong this metaphor is, and why it inhibits, no pun intended, deeper understanding. How we ontologize and break down our metaphors influences our inferences and subsequent understanding. From the rather unfortunate “Long”, “Medium”, and “Short” terminology, to the even worse “Red”, “Green”, and “Blue” leap which projects centuries old false ideas of the locus of “colour” existing in the radiation, to the Photometer “The eye is just a camera” noodling nonsense, we see structures of knowledge that undermine a much more nuanced, and likely more tenable, model.

The differentiation that happens somewhere along this signal chain can be broadly broken down into what is generally regarded as ON and OFF signal chains. That is, not only is there a complex web of inhibitory mechanisms at work to differentiate between the absorptive profiles of the first stage radiation sensitive cells, there’s also a distinction in terms of an increment versus decrement signals[9](https://hg2dc.com/2023/11/21/question-31/#026fb748-4a94-410e-a710-b739b90820a9). The types of assemblies that formulate these distinct increment versus decrement signals are varied. Some are considered “simple” cells; which respond strictly to a full assembly increment versus a decrement signal, and others are considered “complex”, which have a central region that differentiates spatially from the outer region, as well as orient specific assemblies that perform similar differentiation. It should go without saying that the mechanics of the visual system are *ridiculously* complex!

---

At this point, a simplified understanding of the system as a “Differencing Machine” that smashes up and discretizes the visual arrangement of the retinal array into overlapping and differenced spatiotemporal arrangements is useful. The majority of the research leans toward a model that doesn’t “measure” light as a camera sensor does, providing signal “quantities” to our higher orders of brain activity. Instead, the basic research done by cat and monkey ~torture~ experiments, indicates that the totality of the signals are differential in nature. To appreciate this, the canonized work of Hubel and Wiesel[10](https://hg2dc.com/2023/11/21/question-31/#7531ef29-fbd3-406e-b110-a98d696fc650) is elegantly summarized in this terrific short video:

A terrific video that summarizes the Hubel and Wiesel work.

To wrap this massive romp up, let’s consider how the receptive fields of the differencing machine are arranged. There is evidence to suggest that the various cells are “pooled” and differenced against each other. This pooling happens at various levels of the system, from the ON-OFF / OFF-ON assemblies, to the amacrine and horizontal cell influence, to the ganglion cell assemblies, among other regions not well understood or even potentially known. To give us an idea as to just how complex the receptive field layout is, this diagram from Das and Gilbert[11](https://hg2dc.com/2023/11/21/question-31/#49383dac-788b-4455-8d44-f668ea013e97) illustrates the overlapping of various receptive fields in panels d, e, and f:

![](https://hg2dc.com/wp-content/uploads/2023/11/img_0722-1.jpg?w=1024)

An example of the overlapping receptive fields in V1 cat cortical analysis.

---

Let’s try to give ourselves a summary of the impossibly complex biological insights we have reason to believe are broadly useful:

-   The retinal assemblies that are able to respond to radiation are arranged backwards with respect to the incoming radiation, and underneath layers of veins and what not. The mechanic that renders these veins invisible is critical to note.
-   The retinal absorptive signals are differenced against each other in complex ways, in varying sized receptive field constellations. Following the above, without a difference, visual cognition ceases. Fixed veins and other points of stasis cannot be easily identified if at all.
-   The retina is not at all like a camera or photoreceptor. Again, this follows due to the biological nature of the ON-OFF and OFF-ON basic mechanics.
-   The differenced signals traverse up the stream and somehow, break apart the signals into notions of “boundaries” and “fills”[12](https://hg2dc.com/2023/11/21/question-31/#b56918f2-d874-4307-bcb6-5a4054af3aa1), involving some degree of resonance / diffusion-like mechanics[13](https://hg2dc.com/2023/11/21/question-31/#73fe898f-096e-422b-9eef-98e096e8c4b9).

All of this is to say that even though we have a bit of a better than poorly informed grasp on the physiology, we still haven’t identified the locus of colour. It would be erroneous and utterly foolish to suggest:

-   The absorptive profiles of the lowest order assemblies are “red”, “green”, and “blue”. The signals are just that, signals. Notions of colour are not yet formed.
-   Following this, the idea of any fixed colour orientation in relation to the neurophysiological signals is equally foolish; colour exists as an active, cognitive process from higher order interactions.
-   That colour is a fluid dynamic of cognitive analysis of *relationships*. Colour is much closer to a cognitive compass-like heuristic, than a fixed ground truth relationship.

We can get a sense pretty quickly that every time someone utters the damn word “colour”, they are probably using it wrong, despite it being an intimately understood thing to everyone reading this. Why?

As has been repeated for nearly two hundred years of more or less “rigorous” attempts to define “colour”, the locus of colour has all-too-often been placed in the extremely limited range of external energy we can “detect”. This is likely the ground zero of the contemporary comprehension disaster around “colour”.

Why? Because the differencing system appears to use a plethora of parallel mechanics to assemble “colour”. This passage from the foreword to Alan Gilchrist’s *Seeing Black and White*[14](https://hg2dc.com/2023/11/21/question-31/#abbb38dd-9e30-463f-b44e-6d570d63b9a8) is a great summation:

> The second reason for using multiple parallel heuristics is that it buys you tolerance for noisy images. It’s a bit like two drunks striving to reach a goal. Each will stumble if he tries on his own (“illusions”), but by leaning on each other they can stagger toward the goal. That’s perception in a nutshell.
> 
> V. S. Ramachandran in the foreword from Alan Gilchrist’s *Seeing Black and White*

That is, we know that the neurophysiological signals are divided into an increment and decrement direction, and therefore we can at least leave the door open that the *relationship* between differences seems to be of incredible importance heuristically, **not** the energy “quantities”. Part of this mechanic is likely helpful to deducing boundaries, but there are other mind boggling examples of how an increment versus decrement signal can provide us with further meaning. A “glint”, “glare”, “reflection”? Increment vs decrement. A “haze” where the differences are gradually collapsed together? Increment vs decrement. Analysis of what is a “figure” and what is a “ground”? Increment vs decrement. And on and on…

One of the more striking series of examples of how this increment and decrement polarity shifts our entire cognition comes from Anderson and Winawer[15](https://hg2dc.com/2023/11/21/question-31/#99b696c6-6a9a-487e-b020-2cff229325b6), and Anderson and Khang[16](https://hg2dc.com/2023/11/21/question-31/#fca15677-62d7-47fc-b0b2-babfc109765d). In the following picture, the “shapes” are identical tristimulus. But note that our cognition of what is what shifts wildly between the variations, where only the “ground” is adjusted to shift the polarity.

![](https://hg2dc.com/wp-content/uploads/2023/11/anderson-and-winawer.png?w=672)

The colour and “meaning” of the forms changes based on their increment or decrement relationship to the adjacent fields.

The effect is even more pronounced when we consider something that generates a chromatic response. This from Anderson and Khang:

![](https://hg2dc.com/wp-content/uploads/2023/11/anderson-and-khang.png?w=941)

The colour of the disc changes based on polarity of the “ground”.

Finally, note that these orientations of articulations shift the cognitive *meaning* that forms. Not only are the above “circles” cognized as different colours, the articulations of colour and increment versus decrement signals seems to arrange our understandings of “transparency”. Again, another from Anderson and Khang:

![](https://hg2dc.com/wp-content/uploads/2023/11/anderson-and-khang-2.png?w=600)

A mind bender where the colour of the disc changes and informs us of some notion of “where”.

One could make a case that entire generation has become so seduced by the century old idea that stimulus carries the colour so as to be deemed entirely blind to the more deep mechanics of cognition. Here is one final example from Ekroll and Faul[17](https://hg2dc.com/2023/11/21/question-31/#e4a367ac-07c6-4089-8779-0586ddbd07ad). The “discs” are identical tristimulus, and have varied only in their orientation of rotation. Yet in one case, we cognize not only a subtly different hue, value, and chroma, but also a very different cognition of transparency versus occlusion. Pay attention to the increment versus decrement polarity of the tristimulus relationships for a hint that might elucidate intriguing patterns!

![](https://hg2dc.com/wp-content/uploads/2023/11/ekroll-faul-discs-transparency.png?w=1024)

Ekroll and Faul exploding our brains with a tristimulus reorientation that changes the “meaning”. Colour is more than just colour.

---

Hopefully we can, by way of negation, arrive at a semblance of what *colour* can be adequately described as, via a tear down of what we know *colour* **can not be**. From the latter demonstrations above, we can get a keen insight that colour is not some “sensing” of stimulus, as the articulations of the tristimulus seem to be arranged into higher order cognitions. Nor is it “capturing”, as we know from the biological differential signals via the high level understanding of the physiology. In fact, our visual system is so ridiculously focused on such a tremendously small range of electromagnetic radiation that it is almost absurd.

Under a wider lens, we can begin to carve out an idea that *colour* is an active biological, organism-centric mechanism. So…

**Answer #31: Colour is not in the spectral radiation of the articulations, but rather an incredibly complex active cognition mechanic.**

That is, here at Question #31, we’ve managed to totally torpedo a sizeable number of the prior answers in no small way. But in doing so, we are able to look down and kick away the ladder that allowed us to get to where we are now, and [tackle further concepts ahead of us…](https://hg2dc.com/question-32)

---

1.  Lents, Nathan H. *Human Errors: A Panorama of Our Glitches, from Pointless Bones to Broken Genes*. Boston: Houghton Mifflin Harcourt, 2018. [↩︎](https://hg2dc.com/2023/11/21/question-31/#8d2bcaea-c91b-4493-84a2-b69b0c85e54d-link)
2.  Ditchburn, R. W., and B. L. Ginsborg. “Vision with a Stabilized Retinal Image.” *Nature* 170, no. 4314 (July 1952): 36–37. [https://doi.org/10.1038/170036a0](https://doi.org/10.1038/170036a0). [↩︎](https://hg2dc.com/2023/11/21/question-31/#2eaec71d-6747-4c7c-8cc3-57462e4726a7-link)
3.  Riggs, Lorrin A., Floyd Ratliff, Janet C. Cornsweet, and Tom N. Cornsweet. “The Disappearance of Steadily Fixated Visual Test Objects\*.” *Journal of the Optical Society of America* 43, no. 6 (June 1, 1953): 495. [https://doi.org/10.1364/JOSA.43.000495](https://doi.org/10.1364/JOSA.43.000495). [↩︎](https://hg2dc.com/2023/11/21/question-31/#73aa9999-5183-417c-9d3a-4e2e2adfa237-link)
4.  Yarbus, Alfred L. *Eye Movements and Vision*. Boston, MA: Springer US, 1967. [https://doi.org/10.1007/978-1-4899-5379-7](https://doi.org/10.1007/978-1-4899-5379-7). [↩︎](https://hg2dc.com/2023/11/21/question-31/#49655143-e3e2-4b04-8142-05f131659704-link)
5.  Lee, Barry B., Paul R. Martin, and Ulrike Grünert. “Retinal Connectivity and Primate Vision.” *Progress in Retinal and Eye Research* 29, no. 6 (November 2010): 622–39. [https://doi.org/10.1016/j.preteyeres.2010.08.004](https://doi.org/10.1016/j.preteyeres.2010.08.004). [↩︎](https://hg2dc.com/2023/11/21/question-31/#671f30fd-00dd-465b-b9ec-19f2a499d408-link)
6.  Judd, Deane B. “Response Functions for Types of Vision According to the Muller Theory.” *Journal of Research of the National Bureau of Standards* 42, no. 1 (January 1949): 1. [https://doi.org/10.6028/jres.042.001](https://doi.org/10.6028/jres.042.001). [↩︎](https://hg2dc.com/2023/11/21/question-31/#b258638b-c3be-44da-bafb-90fc41c09b0f-link)
7.  Barlow, H. B., and W. R. Levick. “Changes in the Maintained Discharge with Adaptation Level in the Cat Retina.” *The Journal of Physiology* 202, no. 3 (June 1969): 699–718. [https://doi.org/10.1113/jphysiol.1969.sp008836](https://doi.org/10.1113/jphysiol.1969.sp008836).  
    [↩︎](https://hg2dc.com/2023/11/21/question-31/#12c54d87-3fbd-492f-9857-e8b9070d5e4b-link)
8.  Gilchrist, Alan, Stanley Delman, and Alan Jacobsen. “The Classification and Integration of Edges as Critical to the Perception of Reflectance and Illumination.” *Perception & Psychophysics* 33, no. 5 (September 1983): 425–36. [https://doi.org/10.3758/BF03202893](https://doi.org/10.3758/BF03202893). [↩︎](https://hg2dc.com/2023/11/21/question-31/#61905f02-429e-4c5a-b04a-b4d2bd91d6c6-link)
9.  Whittle, Paul. “Increments and Decrements: Luminance Discrimination.” *Vision Research* 26, no. 10 (January 1986): 1677–91. [https://doi.org/10.1016/0042-6989(86)90055-6](https://doi.org/10.1016/0042-6989(86)90055-6). [↩︎](https://hg2dc.com/2023/11/21/question-31/#026fb748-4a94-410e-a710-b739b90820a9-link)
10.  Hubel, D. H., and T. N. Wiesel. “Receptive Fields of Single Neurones in the Cat’s Striate Cortex.” *The Journal of Physiology* 148, no. 3 (October 1, 1959): 574–91. [https://doi.org/10.1113/jphysiol.1959.sp006308](https://doi.org/10.1113/jphysiol.1959.sp006308). [↩︎](https://hg2dc.com/2023/11/21/question-31/#7531ef29-fbd3-406e-b110-a98d696fc650-link)
11.  Das, Aniruddha, and Charles D. Gilbert. “Distortions of Visuotopic Map Match Orientation Singularities in Primary Visual Cortex.” *Nature* 387, no. 6633 (June 1997): 594–98. [https://doi.org/10.1038/42461](https://doi.org/10.1038/42461). [↩︎](https://hg2dc.com/2023/11/21/question-31/#49383dac-788b-4455-8d44-f668ea013e97-link)
12.  Grossberg, Stephen, and Dejan Todorovic. “Neural Dynamics of 1-D and 2-D Brightness Perception: A Unified Model of Classical and Recent Phenomena.” *Perception & Psychophysics* 43, no. 3 (May 1988): 241–77. [https://doi.org/10.3758/BF03207869](https://doi.org/10.3758/BF03207869). [↩︎](https://hg2dc.com/2023/11/21/question-31/#b56918f2-d874-4307-bcb6-5a4054af3aa1-link)
13.  Cohen, Michael A., and Stephen Grossberg. “Neural Dynamics of Brightness Perception: Features, Boundaries, Diffusion, and Resonance.” *Perception & Psychophysics* 36, no. 5 (September 1984): 428–56. [https://doi.org/10.3758/BF03207497](https://doi.org/10.3758/BF03207497). [↩︎](https://hg2dc.com/2023/11/21/question-31/#73fe898f-096e-422b-9eef-98e096e8c4b9-link)
14.  Gilchrist, Alan. *Seeing Black and White*. Oxford University Press, 2006. [https://doi.org/10.1093/acprof:oso/9780195187168.001.0001](https://doi.org/10.1093/acprof:oso/9780195187168.001.0001). [↩︎](https://hg2dc.com/2023/11/21/question-31/#abbb38dd-9e30-463f-b44e-6d570d63b9a8-link)
15.  Anderson, Barton L., and Jonathan Winawer. “Image Segmentation and Lightness Perception.” *Nature* 434, no. 7029 (March 2005): 79–83. [https://doi.org/10.1038/nature03271](https://doi.org/10.1038/nature03271). [↩︎](https://hg2dc.com/2023/11/21/question-31/#99b696c6-6a9a-487e-b020-2cff229325b6-link)
16.  Anderson, B. L., and B.-G. Khang. “The Role of Scission in the Perception of Color and Opacity.” *Journal of Vision* 10, no. 5 (May 1, 2010): 26–26. [https://doi.org/10.1167/10.5.26](https://doi.org/10.1167/10.5.26). [↩︎](https://hg2dc.com/2023/11/21/question-31/#fca15677-62d7-47fc-b0b2-babfc109765d-link)
17.  Faul, F., and V. Ekroll. “On the Filter Approach to Perceptual Transparency.” *Journal of Vision* 11, no. 7 (June 9, 2011): 7–7. [https://doi.org/10.1167/11.7.7](https://doi.org/10.1167/11.7.7). [↩︎](https://hg2dc.com/2023/11/21/question-31/#e4a367ac-07c6-4089-8779-0586ddbd07ad-link)



 
# Question #32:  Does the F\*cking “Colour” of the Light Change When We Increase or Decrease the Quantity of Light?

As we look back to the past two questions, it is hopefully more evident that no simple path as forwarded by “stimulus-as-colour” can aid in charting us successfully through the perils of the colour iceberg laden waters. The worst part is that the USS Colourimetry vessel is chocker full of flesh eating obsessed Colourimetric Stimulus Zombies on a hunt for brains to eat. In order to survive these perilous waters, we are going to need to finally jump off the ship, and swim to the USS Computational Neuroscience.

This post marks that moment where we plunge into the waters. It is with hope that the cold waters don’t claim the reader, but after all, anything is better than having one’s brain eaten alive in the Colourimetry Zombie Apocalypse horde.

Grab onto the life jacket…

So let’s revisit [Question](https://hg2dc.com/question-3) [#3](http://hg2dc/question-3), and reframe it…

**Question #32: Does changing the intensity of a single RGB light change the cognition of colour?**

This question has many colourimetric-oriented (Hint: Stimulus) non-answers that are common “orthodox” knowledge, and in turn totally bunko nonsense from the lens of actual colour cognition. Even if a Colourimetry Zombie acknowledges the complexity, it tends to cease with a short non-answer grunt being “Changing the intensity of the stimulus changes the colour!” and the zombie lumbers on their way, clamouring to eat your brain. They might cite numerous “effects” or “illusions” such as the [Bezold-Brücke shift](https://cie.co.at/eilvterm/17-22-071), the [Purkinje effect](https://cie.co.at/eilvterm/17-22-036), or any of another dozen or so peculiarities around “intensity” and the cognition of colour.

Let’s smack open some of those Zombie heads, and in doing so perhaps also learn some Computational Neuroscience self-defence to even manage to repel the Brand Identity Stimulus obsessed animated corporate corpses…

---

First… we would do well to contextualize the prior questions and discussions around “intensity” as a unit of stimulus. Under the lens of what we discussed in [Question #31](https://hg2dc.com/question-31). A few piece of relevant information are worth reframing our discussion to one of *colour*, or the cognitive interpretation of colour [qualia](https://plato.stanford.edu/entries/qualia/):

-   The bulk of the processing in the retina appears to be *differential* in nature[1](https://hg2dc.com/2024/02/03/question-32/#c4b5fee9-f8d1-4a37-ab06-37014637062e)[2](https://hg2dc.com/2024/02/03/question-32/#7fbbc86b-72ce-4cbd-967c-bae9fcdb5fbf). That is, we can’t discuss “scalar” values as “magnitudes” from “zero”.
-   Only an extremely limited, somewhere near 1% of cells appear to provide a local mean scalar value of luminance[3](https://hg2dc.com/2024/02/03/question-32/#24c74a4e-40d7-47ae-9653-8132ae8df09f).

This understanding means that we can’t specifically say that “intensity” is this common and misleading notion of “scalar” value in our colour cognition. Rather, it is more grounded to suggest that “intensity” is *something else*, and is *relational* in nature.

An emergent facet of this slippery “intensity” means we must take care to understand that “intensity” cannot possibly exist along some fictional polemical ruler if the ruler anchor point keeps moving! Rather, this paints a more fluid dynamic that emerges out of the spatiotemporal articulation. As organisms, we are literally ill equipped to “measure” “intensity” along a scalar ruler the way stimulus is all too frequently quantified, and conflated with colour! To this end, the specific *intensity* we are referring to is a notion around *lighter* and *darker*. Emphasis on the suffix.

What does this mean in a practical sense? Usually when the subject of a relational / differential foundation around visual cognition pops up, the common response is to nod one’s head and carry on. To really affix this mind blowing concept in a visceral manner, I typically refer folks to one specific effect that is so jaw dropping it needs to be experienced. The effect is known as [Induced Contrast Asynchrony](https://michaelbach.de/ot/lum-inducedContrastAsym/), and is best experienced in real-time.

With that nightmare demonstration experienced and in the memory bank, we can explore the idea of relational differentials in some very simple still pictures, which echo the same brain pop as the Induced Contrast Asynchrony effect[4](https://hg2dc.com/2024/02/03/question-32/#e263c8eb-5563-460f-aff2-d45749b60de6). So go grab a couple of litres of LSD and hop on board the train…

---

First… let’s provide some stimulus. Here, we have “a disc”.

![](https://hg2dc.com/wp-content/uploads/2024/02/one-disc.png?w=1024)

At the moment we have some spatiotemporal articulation, our meatware goes into overdrive of meaning-making. Even though we could say “This is a disc”, we should at least realize that identifying the boundary conditions has to happen at some mechanical level in our neurophysiology. From the web page assembly, we are identifying the “This is a boundary of the picture” and then a meta decomposition into “I cognize[5](https://hg2dc.com/2024/02/03/question-32/#37513b5f-1d04-4253-b125-1bb1ebd275a3) further boundaries, and now I think I cognize a single form as a disc.”

---

I can already hear the screeching Colourimetry Zombies jumble mutter “Why are you bothering to ramble on about something so trivially obviousszzzz!!11!??” Someone, quick… grab the chainsaw!

What is interesting is that with even a small degree of questioning, we could make a case that our disc is fundamentally *unstable*. That is, our differential inference meat engine is always engaged, and in a constant state of flux in terms of the underlying interpretations of meaning. Is the disc figure[6](https://hg2dc.com/2024/02/03/question-32/#34250f73-f6d3-422c-a60f-30b06c590b91) “in front of” the ground? Is the disc figure “behind” some form, such that the surround is “on top of” the disc? None of these inferences as information units are present in the stale bread stimuli presented in front of us; we must *form* these information units.

Take a moment to look back at the disc and try to cognize the disc in these sorts of orientations…

![](https://hg2dc.com/wp-content/uploads/2024/02/one-disc.png?w=1024)

---

Did you notice anything peculiar happen?

If one successfully focuses on the picture for a moment, it is quite possible that a [Necker’s Cube](https://michaelbach.de/ot/sze-Necker/index.html)\-like modulation of state will occur, by which the disc might flow into and out of “lighter” or “darker” depending on the phase of our cognitive modulations. And of course this *might not* appear to happen immediately for someone, as we all approach our inference formation by way of learned experiential biases.

The following picture is an attempt to describe the possible topmost level of a scission decomposition processing that our meatware inference engine might be able to dream up probabilistically.

![](https://hg2dc.com/wp-content/uploads/2024/02/implicit-bistability.png?w=1024)

Note that if our probability starts at two “highly probable” configurations, we end up with very different ideas of the colour of the “disc” form.

In the left hand case, the disc could be considered “on top” of the “ground”, and therefore in one configuration, it could be occluding the “ground” in some way. This leads to an interception where we might consider the disc “as is” in terms of “lightness”.

In the right hand viable inference, the disc is “under” the “ground”. In this inferential context, the “disc” is “occluded” by the “ground” in some way, and as a result of the interception of probability, the disc *must* be “lighter than” the inference of the prior “on top” configuration. I tried to match the disc tristimulus in both examples to the resulting picture.

It is reasonable to suggest that these implicit instabilities *are* omnipresent however, as hopefully the following demonstrations will show.

---

With this under our experience belts, let’s try to examine the picture again and see if we can discern a peculiar sense of “lightness” that may be incredibly elusive and unstable.

![](https://hg2dc.com/wp-content/uploads/2024/02/one-disc.png?w=580)

And with that, let’s return to Dr. Tse’s completely unstable discs. These discs add a little more statistical probability ingredients that our meatware inference engine can form information from. Are we able to discern the instability of which disc is “lighter” versus which disc is “darker”? Remember, the “forms” of the “discs” are identical tristimulus with respect to the “other disc” form.

![](https://hg2dc.com/wp-content/uploads/2024/02/tse-darker-3.png?w=1024)

And here is a slightly different variation, with the polarity flipped on the “discs”. Can we modulate the “lightness” of the “separate” discs?

![](https://hg2dc.com/wp-content/uploads/2024/02/tse-lighter.png?w=1024)

---

Already our discussion of “intensity” has at least hinted that all is not well in terms of potential “matching”. Within the prior demonstration, the disc “exists” as the cognitively inferred state of the form, not as the stimulus as measured scalar value. That is, we cognize the qualia of the disc, “outside” of the context of the direct stimuli.

Let’s make that situation worse…

![](https://hg2dc.com/wp-content/uploads/2024/01/two-discs-gradient.png?w=1024)

Here, we have “two” discs now, on a slightly graduated “ground”.

Notice how even though this is a rather low spatiotemporal articulation, the “lightness” complexity of instability of *each* disc can cascade down the probability inference chain. As such, we end up with *two* unstable disc lightnesses, each modulating based on cognitive inference state.

And what might we expect to happen if we try to “match” one disc to the other?

What is *absolutely incredible* about this configuration is that if one makes this in their content creation application of choice, and varies the magnitude of the stimulus of one of the discs to “match” the other disc, no magnitude will likely be satisfactory[7](https://hg2dc.com/2024/02/03/question-32/#56770932-ec39-4243-b473-0674a09c9cef)[8](https://hg2dc.com/2024/02/03/question-32/#27bcda1a-b9d2-4554-a4d5-bd6c00a65131)[9](https://hg2dc.com/2024/02/03/question-32/#f3d783d8-bd4d-45b5-809d-0459cfc17cf4)[10](https://hg2dc.com/2024/02/03/question-32/#01f068fd-8dfe-418e-8ab0-0e64b1b238a1). This is an incredibly little known phenomena, so please… share it around when someone discusses the idea of “colour matching”. More importantly, try it yourself!

---

This is arguably the first and most challenging entry session at the Visual Cognition Dojo. I know personally it was one of the most gargantuan leaps I had to make from the sinking cruise liner littered with Colourimetry Zombies hunting for more brains to eat. I hope that the basic premise, that of visual cognition instability, has been presented here in a way that is digestible. With a little luck, it will take hold, and more potential victims of the Colourimetric Zombie Apocalypse can be rescued by way of a thrown life line.

So where do we go from here?

Well first up, we have to answer the question. Note that we are going to answer the question with respect to “lightness” and “darkness” as a subset of the broader idea of “colour” in terms of qualia.

---

If one experiments with the above articulation, and concedes the point that the disc lightness or darkness is impossible to match to the other disc configuration, we will immediately have way more questions than what we started with.

A key question here is *why* does the articulation possibly lead to this completely unstable set of interpretations? Why does the cognitive processing of such a “simple” spatiotemporal articulation lead to such a confounding result? No one knows for certain, although the research around these things has been going on for at least two centuries. This research falls squarely in the field of computational neuroscience, which likely saw a sizeable chunk of the field begin in earnest with folks like Horn[11](https://hg2dc.com/2024/02/03/question-32/#a686b787-b184-42a4-b18f-18edc68e1b13)[12](https://hg2dc.com/2024/02/03/question-32/#cdf70e3d-187e-4ce7-b5d2-36bcd80ee403)[13](https://hg2dc.com/2024/02/03/question-32/#49ee373a-ac1b-4b8d-a93f-2d430221e0ed).

Some things that are worth identifying patterns of might be:

-   The “interiors” of the discs are propagated from the boundary conditions[14](https://hg2dc.com/2024/02/03/question-32/#720ca7e2-43d8-43cc-87c5-751e907f9268), likely resulting in something akin to a “cognitive buffer”.
-   The top-down processing works relentlessly to scise or fission the “cognitive buffer” into forms, and their cascading respective underlying “meaning”[15](https://hg2dc.com/2024/02/03/question-32/#1989f866-0e17-4de2-9fac-c8f1f425b205)[16](https://hg2dc.com/2024/02/03/question-32/#9dd9718d-e665-436d-a89f-61a392732a45)[17](https://hg2dc.com/2024/02/03/question-32/#a414b14f-3fdb-4e28-9d22-58e1d62c74ae)[18](https://hg2dc.com/2024/02/03/question-32/#97816769-bbde-4f95-966b-e51604789ade)[19](https://hg2dc.com/2024/02/03/question-32/#0387c02f-5af8-4641-8adc-b3078513f8ce).

If we *do* engage in a cognitive scission / fission mechanic, decomposing the forms into their cognized qualia “outside” of the contextual information of the stimuli, there is a dilemma! There are multiple potential interpretations of the low articulation of “disc” and “ground”, and that depending on the inferential frame, *there are no absolute “solutions”*. Anyone who tries to offer us Cartesian “model” implying a stimulus to colour qualia “appearance” or “uniformity” is *outright lying to us*. In their defence, they were sadly probably infected through casual contact, but equally sadly, will soon likely evolve into full blown brain eaters.

These models are not “approximate”. They are not “good enough”. They don’t “work”. They are nothing more than flat out lies and nonsense.

---

The following answer is going to appear false in that it relates “colour” to “without colour”. How can an answer follow a series of demonstrations that don’t have “colour” in the classic “ZOMFG RED?!?!!” It will hopefully become clear that we can’t discuss “without colour” without, ironically, discussing “colour”. And in turn, we cannot discuss “lightness” or “darkness” without also simultaneously discussing “colour”. That is a long winded way of saying that we have indeed been discussing colour, even by way of demonstrations that appear to be “without colour”. More on that later, but for now, here’s an answer…

**Answer #32: Changing the intensity of a single sample of RGB light will have echoing changes across the entire cognitive inferential field. As such, even a slight shift of a stimulus energy intensity will indeed change the inference of the colour qualia.**

Phew. A helluva daunting point to get into the books, but one which will [allow us to make far more intuitive steps further, as well as all sorts of conjectures.](https://hg2dc.com/question-33)

---

1.  Ichinose T, Habib S. On and off signaling pathways in the retina and the visual system. *Front Ophthalmol*. 2022;2:989002. doi:[10.3389/fopht.2022.989002](https://doi.org/10.3389/fopht.2022.989002) [↩︎](https://hg2dc.com/2024/02/03/question-32/#c4b5fee9-f8d1-4a37-ab06-37014637062e-link)
2.  Schiller PH. The ON and OFF channels of the visual system. *Trends in Neurosciences*. 1992;15(3):86-92. doi:[10.1016/0166-2236(92)90017-3](https://doi.org/10.1016/0166-2236(92)90017-3) [↩︎](https://hg2dc.com/2024/02/03/question-32/#7fbbc86b-72ce-4cbd-967c-bae9fcdb5fbf-link)
3.  Barlow HB, Levick WR. Changes in the maintained discharge with adaptation level in the cat retina. *The Journal of Physiology*. 1969;202(3):699-718. doi:[10.1113/jphysiol.1969.sp008836](https://doi.org/10.1113/jphysiol.1969.sp008836)  [↩︎](https://hg2dc.com/2024/02/03/question-32/#24c74a4e-40d7-47ae-9653-8132ae8df09f-link)
4.  Shapiro AG, D’Antona AD, Charles JP, Belano LA, Smith JB, Shear-Heyman M. Induced contrast asynchronies. *Journal of Vision*. 2004;4(6):5-5. doi:[10.1167/4.6.5](https://doi.org/10.1167/4.6.5) [↩︎](https://hg2dc.com/2024/02/03/question-32/#e263c8eb-5563-460f-aff2-d45749b60de6-link)
5.  I have been chastised by an unnamed computational neuroscience PhD for using the term “cognition”, who shall remain nameless to avoid any incrimination with the imbecile author. I have chosen this term to impress the incredible importance of treating visual perception as incredibly active, as opposed to the normative passive intake of stimulus. The critique stems from a redundancy among neuroscience types who would suggest that perception is entirely active, therefore using cognition is not normative. I hope any neuroscience PhDs who happen to stumble across this pile of nonsense written here forgive the author for abusing the term cognition in the name of smashing the casually normative notions around perception as a passive activity. [↩︎](https://hg2dc.com/2024/02/03/question-32/#37513b5f-1d04-4253-b125-1bb1ebd275a3-link)
6.  The astute reader would note that it is also a computation to determine the figure from the ground, and that indeed is an incredibly complex computational problem in and of itself! [↩︎](https://hg2dc.com/2024/02/03/question-32/#34250f73-f6d3-422c-a60f-30b06c590b91-link)
7.  Vladusich T. Simultaneous contrast and gamut relativity in achromatic color perception. *Vision Research*. 2012;69:49-63. doi:[10.1016/j.visres.2012.07.022](https://doi.org/10.1016/j.visres.2012.07.022) [↩︎](https://hg2dc.com/2024/02/03/question-32/#56770932-ec39-4243-b473-0674a09c9cef-link)
8.  Heggelund P. Achromatic color vision-I: Perceptive variables of achromatic colors. *Vision Research*. 1974;14(11):1071-1079. doi:[10.1016/0042-6989(74)90203-X](https://doi.org/10.1016/0042-6989(74)90203-X) [↩︎](https://hg2dc.com/2024/02/03/question-32/#27bcda1a-b9d2-4554-a4d5-bd6c00a65131-link)
9.  Heggelund P. Achromatic color vision-II: Measurement of simultaneous achromatic contrast within a bidimensional system. *Vision Research*. 1974;14(11):1081-1088. doi:[10.1016/0042-6989(74)90204-1](https://doi.org/10.1016/0042-6989(74)90204-1) [↩︎](https://hg2dc.com/2024/02/03/question-32/#f3d783d8-bd4d-45b5-809d-0459cfc17cf4-link)
10.  Heggelund P. A bidimensional theory of achromatic color vision. *Vision Research*. 1992;32(11):2107-2119. doi:[10.1016/0042-6989(92)90072-Q](https://doi.org/10.1016/0042-6989(92)90072-Q) [↩︎](https://hg2dc.com/2024/02/03/question-32/#01f068fd-8dfe-418e-8ab0-0e64b1b238a1-link)
11.  Horn BKP. Image Intensity Understanding. Published online August 1, 1975. Accessed July 29, 2023. [https://dspace.mit.edu/handle/1721.1/6236](https://dspace.mit.edu/handle/1721.1/6236) [↩︎](https://hg2dc.com/2024/02/03/question-32/#a686b787-b184-42a4-b18f-18edc68e1b13-link)
12.  Horn BKP. Understanding image intensities. *Artificial Intelligence*. 1977;8(2):201-231. doi:[10.1016/0004-3702(77)90020-0](https://doi.org/10.1016/0004-3702(77)90020-0) [↩︎](https://hg2dc.com/2024/02/03/question-32/#cdf70e3d-187e-4ce7-b5d2-36bcd80ee403-link)
13.  Horn BKP. Determining lightness from an image. *Computer Graphics and Image Processing*. 1974;3(4):277-299. doi:[10.1016/0146-664X(74)90022-7](https://doi.org/10.1016/0146-664X(74)90022-7) [↩︎](https://hg2dc.com/2024/02/03/question-32/#49ee373a-ac1b-4b8d-a93f-2d430221e0ed-link)
14.  Grossberg S, Todorović D. Neural dynamics of 1-D and 2-D brightness perception: A unified model of classical and recent phenomena. *Perception & Psychophysics*. 1988;43(3):241-277. doi:[10.3758/BF03207869](https://doi.org/10.3758/BF03207869) [↩︎](https://hg2dc.com/2024/02/03/question-32/#720ca7e2-43d8-43cc-87c5-751e907f9268-link)
15.  Anderson BL, Winawer J. Layered image representations and the computation of surface lightness. *Journal of Vision*. 2008;8(7):18. doi:[10.1167/8.7.18](https://doi.org/10.1167/8.7.18) [↩︎](https://hg2dc.com/2024/02/03/question-32/#1989f866-0e17-4de2-9fac-c8f1f425b205-link)
16.  Wollschläger D, Anderson BL. The role of layered scene representations in color appearance. *Curr Biol*. 2009;19(5):430-435. doi:[10.1016/j.cub.2009.01.053](https://doi.org/10.1016/j.cub.2009.01.053) [↩︎](https://hg2dc.com/2024/02/03/question-32/#9dd9718d-e665-436d-a89f-61a392732a45-link)
17.  Faul F, Ekroll V. Transparent layer constancy. *Journal of Vision*. 2012;12(12):7-7. doi:[10.1167/12.12.7](https://doi.org/10.1167/12.12.7) [↩︎](https://hg2dc.com/2024/02/03/question-32/#a414b14f-3fdb-4e28-9d22-58e1d62c74ae-link)
18.  Kozaki A, Noguchi K. The relationship between perceived surface-lightness and perceived illumination: A manifestation of perceptual scission. *Psychol Res*. 1976;39(1):1-16. doi:[10.1007/BF00308942](https://doi.org/10.1007/BF00308942) [↩︎](https://hg2dc.com/2024/02/03/question-32/#97816769-bbde-4f95-966b-e51604789ade-link)
19.  Anderson BL, Khang BG. The role of scission in the perception of color and opacity. *Journal of Vision*. 2010;10(5):26-26. doi:[10.1167/10.5.26](https://doi.org/10.1167/10.5.26) [↩︎](https://hg2dc.com/2024/02/03/question-32/#0387c02f-5af8-4641-8adc-b3078513f8ce-link)



 
# Question #33: What the F\*ck are the Colours of the Three Lights?

With the past several posts, the astute mind will have already arrived at the answer to the headline question here, so in an effort to add some value to the short answer of “There is no colour in the discrete scalar samples of stimuli”, let’s try to explore the surface of the problem with a degree of curiosity, and in doing so, perhaps elucidate something crucially important to visual cognition.

**Question #33: What are the actual colours of the three RGB lights?**

We already know that it would be a complete fallacy to discuss “colour of light” being “in” the energy outside of our meatware calculation engine. What we *can* discuss then, are the implications of the stimuli with respect to the display medium’s spectral energy output. If the notions around “colour” are not in the spectral energy, how does the spatiotemporal relationship play a significant role in this cognition of “colour”?

In this brief romp, we should think deeply about what a “gamut” is from the stimuli vantage, and more importantly, from the cognitive colour inference engine vantage.

---

Way back in [Question #4](https://hg2dc.com/question-4) we were presented with the idea that the RGB normalized wattage values were typically connected to a “colour” of the radiometric energy by way of a display standard known as sRGB.

However, in the latter chapters starting around [Question #30](https://hg2dc.com/question-30), we began to construct a mental model of the human visual cognition system as something more of a differential inference engine, where the colour is an inferred computation that emerges from an analysis of the spatiotemporal articulation of the energy fields; how the neurophysiological gradients lead to calculated and inferred “meaning”.

Why am I bringing this discussion up in what apparently should be a discussion around colourimetric stimuli definitions of “gamut”? The answer has to do with what we have slowly been building toward. In the form of a question, we might ask…

**Question #33: How can a “gamut” of colours exist if our neurophysiological mechanisms are broadly differential, comparative, and modulating at the biological level?**

The answer is one that I suspect most readers are already likely finding hints of inconvenient “truths”. If our visual assemblies *are* differential[1](https://hg2dc.com/2024/07/25/question-33/#4ed591ee-ecd2-4698-8816-8b7bea215fa5), the implication is that there’s some sort of mediating regulation and “orienting” system at work. The “absolute” values of radiant energy hold little sway over our cognition if our systems are keenly adapting on the fly to the presented articulations, or the spatiotemporal “arrangement” of the signal energy.

Do we have any evidence to hammer this point home? The answer is of course a resounding yes!

In a canonical piece of research, Brown and MacLeod noted that the appearance of a colour’s “chroma” or “saturation” was predicated upon the articulation of the field the form is embedded in.[2](https://hg2dc.com/2024/07/25/question-33/#767120f6-2ae7-47c8-a4b5-f66c2404960a) Later, minds such as Ekroll, Faul, Wendt, Anderson, Ratnasingam, and many, many others have explored this territory with a greater degree of scrutiny.

Here I have replicated one of the Ekroll and Faul demonstrations[3](https://hg2dc.com/2024/07/25/question-33/#d1fa6a97-98f1-4a6d-a93e-fd7aeeddc9bc) of the *Gamut Expansion and Contraction* effect[4](https://hg2dc.com/2024/07/25/question-33/#7944a6ff-0cdb-4f8d-b19d-f93184578d39). The tristimuli of the “discs” is identical between the two pictures, yet our cognition of the computed and inferred “colourfulness” of the discs vary[5](https://hg2dc.com/2024/07/25/question-33/#863f7570-9ebb-41d9-a159-ec2d7348c6d8). In the first low spatial variegated version, the discs appear more “colourful”. In the highly articulated picture, the discs are less “colourful”. Some may cognize that there may appear subtle variations in their cognition of “hue” and “value” as well.

![](https://hg2dc.com/wp-content/uploads/2024/07/gamut-expansion-low-articulation.jpg?w=1024)

The “disc” forms are more “colourful” in the low spatially variegated case.

![](https://hg2dc.com/wp-content/uploads/2024/07/gamut-expansion-high-articulation.jpg?w=1024)

The “disc” forms are less “colourful” in the higher spatially variegated case.

---

Most of the readership at this point is probably interested in this cognitive effect, and perhaps are wondering how such a mechanic may work in the meatware world of biology. Is there a broad and reasonably simplistic handle that we can employ to hold a thread of understanding here?

One line of reasoning is that we have a dynamic “gain regulation” that operates across many regions of our cognition, from the retinal assemblies on up to the higher order mechanisms of our Lateral Geniculate Nucleus and onward to the Visual Cortex. That is, that somehow our visual cognition system “discounts” or “separates” varying “contrast” neurophysiological gradients via a broader gain regulation system[6](https://hg2dc.com/2024/07/25/question-33/#3c8c5878-2494-4146-894a-6b51f9ac9f0c). Carandini, Heeger, Movshon, and Tolhurst, via ~torture~ research on cats and primates, have located a normalization at work[7](https://hg2dc.com/2024/07/25/question-33/#1471da64-807d-4e33-9075-9f43fcc695c4)[8](https://hg2dc.com/2024/07/25/question-33/#a285d43e-9666-4316-b3c2-ff49405dc33a). Carandini and Heeger go on to call this sort of gain regulation leading to normalization as a “canonical neural computation”[9](https://hg2dc.com/2024/07/25/question-33/#c9d415e6-a73a-43c8-8c9e-54f8197e370f):

> There is increasing evidence that the brain relies on a set of canonical neural computations, repeating them across brain regions and modalities to apply similar operations to different problems. A promising candidate for such a computation is normalization, in which the responses of neurons are divided by a common factor that typically includes the summed activity of a pool of neurons. Normalization was developed to explain responses in the primary visual cortex and is now thought to operate throughout the visual system, and in many other sensory modalities and brain regions. Normalization may underlie operations such as the representation of odours, the modulatory effects of visual attention, the encoding of value and the integration of multisensory information. Its presence in such a diversity of neural systems in multiple species, from invertebrates to mammals, suggests that it serves as a canonical neural computation.

Thus, yet again, we are faced with the cold hard reality that *colour*, in terms of the Munsell inspired constructs[10](https://hg2dc.com/2024/07/25/question-33/#da1a8a95-5221-4bae-9c74-0cf3ff58ead5) of *Hue*, *Value*, and *Chroma*, nor more abstract notions around “contrast”[11](https://hg2dc.com/2024/07/25/question-33/#3ba9c92c-1016-4093-99b0-83af98ef590f), cannot be understood nor communicated using a stimuli wattage unit specification!

---

“But… but… but… these are *edge cases*!111!!!” I can hear the zombies of the USS Colourimetric Titanic WANKers screeching…

In fact, one can make a case that this cognitive machination of a dynamic gain regulation is so prevalent, so omnipresent, that even our casual perusal of social media pictures engages our frictionless colour cognition at every waking moment. In fact it seems that this dynamic gain regulatory system could be incredibly important in the decomposition[12](https://hg2dc.com/2024/07/25/question-33/#3994d68b-a020-42fc-97a4-b1827f75d789) of forms.

Here’s [a very simple picture found on social media](https://pixelfed.social/p/bogat23k/676415682625788345), from [bogat23k](https://pixelfed.social/bogat23k). Using your “mind’s eye”, take a moment to estimate what the door colour is.

![](https://hg2dc.com/wp-content/uploads/2024/07/the-blue-door-base.jpg?w=580)

The Blue Door. What colour do we cognize when effortlessly reading and parsing this pictorial depiction?

Of course, very few folks are pathological, and likely aren’t going to pixel scrub the discrete scalar samples of stimuli. Most folks, including authors very much like you would adjust the picture, settle on “It’s a pale blue”, and move on.

But what if we *did* sample the discretized stimuli and pull them out of the articulation? Would we be able to find this colour we cognized?

![](https://hg2dc.com/wp-content/uploads/2024/07/the-blue-door-door-samples.png?w=580)

Discrete samples of stimuli, arranged in an increment orientation, in isolation of the broader spatiotemporal articulation reveals the *colour* is not in the stimuli.

Here I’ve sampled a good smattering of discrete pixel stimuli intensities, and isolated them in an increment orientation toward the sides of the depiction. We can get a sense that the colour we effortlessly thought we passively “saw” in the stimuli, is simply nowhere to be found! It turns out that for most folks no satisfactory “match” can be derived, regardless of which stimuli sample we choose. For many folks, *none* of the swatches carry the cognition of “blueness” that is present in the articulation of the door.

Xing et al[13](https://hg2dc.com/2024/07/25/question-33/#c84c24e5-426c-48c7-b5a3-826c5986da9d) noted a strong correlation between the “surrounding” stimuli in terms of luminance variegation polarity and the cognition of colour.

> The interaction between brightness and color causes there to be different color appearance when one and the same object is viewed against surroundings of different brightness. Brightness contrast causes color to be desaturated, as has been found in perceptual experiments on color induction and color-gamut expansion in human vision.

![](https://hg2dc.com/wp-content/uploads/2024/07/shapley.png?w=580)

Dynamic gain regulation could very well be one of the forces at work here, scaling our neurophysiological signals, stretching and contracting the cognitive [“sense datum”](https://iep.utm.edu/sense-da/) into what we ultimately analyze to compute and infer form colour from!

---

You might be wondering where all of this leaves sRGB, BT.709, BT.2020, “wide gamut”, “HDR”, and the rest of the acronyms and buzzwords around pictures. If the research shows a trend toward some sort of gain regulation and / or normalization around visual cognition, how then is colour cognition related to the differential neurophysiological gradients of these mediums? It’s an open question that I hope more people begin to ask themselves, as it is quite possible that the hype and marketing overreach of vendors and companies selling products and services is a disservice to a biologically tenable framing of visual cognition. Caveat Emptor; *be vigilant in one’s wariness about what is being sold*.

---

We originally answered [Question #4](https://hg2dc.com/question-4) with a degree of shallow insight:

**Answer #4: There is a good chance that the colours of the three primary lights in your display are darn close to the REC.709 red, green, and blue chromaticities.**

At this point in our discussions, with our understanding of colour having been fleshed out into a more nuanced understanding based on top of biologically plausible mechanisms, we need to update that answer.

**Answer #33: There is a good chance that the spectral composition of the three primary emitters in your display are darn close to the REC.709 red, green, and blue colourimetric stimuli specification standard. However, suggesting that there is colour, or a “colour gamut” within the stimuli volume of the three lights is a grave overreach of terminology when framed from a biologically untenable vantage.**

[In the coming posts](https://hg2dc.com/just-wait/), we will hopefully explore these general ideas further with a hope of gaining a stronger grasp on the fluidity of the visual cognition system, and the implications on the common vernacular of “gamut”, “primaries”, and other orthodox ideas central to picture making for the digital picture author.

---

1.  Westheimer G. The ON–OFF dichotomy in visual processing: From receptors to perception. *Progress in Retinal and Eye Research*. 2007;26(6):636-648. doi:[10.1016/j.preteyeres.2007.07.003](https://doi.org/10.1016/j.preteyeres.2007.07.003) [↩︎](https://hg2dc.com/2024/07/25/question-33/#4ed591ee-ecd2-4698-8816-8b7bea215fa5-link)
2.  Brown RO, MacLeod DIA. Color appearance depends on the variance of surround colors. *Current Biology*. 1997;7(11):844-849. doi:[10.1016/S0960-9822(06)00372-1](https://doi.org/10.1016/S0960-9822(06)00372-1) [↩︎](https://hg2dc.com/2024/07/25/question-33/#767120f6-2ae7-47c8-a4b5-f66c2404960a-link)
3.  Faul F, Ekroll V, Wendt G. Color appearance: The limited role of chromatic surround variance in the “gamut expansion effect.” *Journal of Vision*. 2008;8(3):30. doi:[10.1167/8.3.30](https://doi.org/10.1167/8.3.30) [↩︎](https://hg2dc.com/2024/07/25/question-33/#d1fa6a97-98f1-4a6d-a93e-fd7aeeddc9bc-link)
4.  Ekroll V, Faul F, Wendt G. The strengths of simultaneous colour contrast and the gamut expansion effect correlate across observers: Evidence for a common mechanism. *Vision Research*. 2011;51(3):311-322. doi:[10.1016/j.visres.2010.11.009](https://doi.org/10.1016/j.visres.2010.11.009) [↩︎](https://hg2dc.com/2024/07/25/question-33/#7944a6ff-0cdb-4f8d-b19d-f93184578d39-link)
5.  Ratnasingam S, Anderson BL. The role of chromatic variance in modulating color appearance. *Journal of Vision*. 2015;15(5):19. doi:[10.1167/15.5.19](https://doi.org/10.1167/15.5.19) [↩︎](https://hg2dc.com/2024/07/25/question-33/#863f7570-9ebb-41d9-a159-ec2d7348c6d8-link)
6.  Gardner JL, Sun P, Waggoner RA, Ueno K, Tanaka K, Cheng K. Contrast Adaptation and Representation in Human Early Visual Cortex. *Neuron*. 2005;47(4):607-620. doi:[10.1016/j.neuron.2005.07.016](https://doi.org/10.1016/j.neuron.2005.07.016) [↩︎](https://hg2dc.com/2024/07/25/question-33/#3c8c5878-2494-4146-894a-6b51f9ac9f0c-link)
7.  Carandini M, Heeger DJ, Movshon JA. Linearity and Normalization in Simple Cells of the Macaque Primary Visual Cortex. *J Neurosci*. 1997;17(21):8621-8644. doi:[10.1523/JNEUROSCI.17-21-08621.1997](https://doi.org/10.1523/JNEUROSCI.17-21-08621.1997) [↩︎](https://hg2dc.com/2024/07/25/question-33/#1471da64-807d-4e33-9075-9f43fcc695c4-link)
8.  Tolhurst DJ, Heeger DJ. Comparison of contrast-normalization and threshold models of the responses of simple cells in cat striate cortex. *Vis Neurosci*. 1997;14(2):293-309. doi:[10.1017/S0952523800011433](https://doi.org/10.1017/S0952523800011433) [↩︎](https://hg2dc.com/2024/07/25/question-33/#a285d43e-9666-4316-b3c2-ff49405dc33a-link)
9.  Carandini M, Heeger DJ. Normalization as a canonical neural computation. *Nat Rev Neurosci*. 2012;13(1):51-62. doi:[10.1038/nrn3136](https://doi.org/10.1038/nrn3136) [↩︎](https://hg2dc.com/2024/07/25/question-33/#c9d415e6-a73a-43c8-8c9e-54f8197e370f-link)
10.  Munsell AH. *A Color Notation*. G. H. Ellis co.; 1907. Accessed July 29, 2023. [https://catalog.hathitrust.org/Record/000349968](https://catalog.hathitrust.org/Record/000349968) [↩︎](https://hg2dc.com/2024/07/25/question-33/#da1a8a95-5221-4bae-9c74-0cf3ff58ead5-link)
11.  Burr DC, Ross J, Morrone MC. Local regulation of luminance gain. *Vision Research*. 1985;25(5):717-727. doi:[10.1016/0042-6989(85)90178-6](https://doi.org/10.1016/0042-6989(85)90178-6) [↩︎](https://hg2dc.com/2024/07/25/question-33/#3ba9c92c-1016-4093-99b0-83af98ef590f-link)
12.  Anderson BL, Khang BG. The role of scission in the perception of color and opacity. *Journal of Vision*. 2010;10(5):26-26. doi:[10.1167/10.5.26](https://doi.org/10.1167/10.5.26) [↩︎](https://hg2dc.com/2024/07/25/question-33/#3994d68b-a020-42fc-97a4-b1827f75d789-link)
13.  Xing D, Ouni A, Chen S, Sahmoud H, Gordon J, Shapley R. Brightness–Color Interactions in Human Early Visual Cortex. *J Neurosci*. 2015;35(5):2226-2232. doi:[10.1523/JNEUROSCI.3740-14.2015](https://doi.org/10.1523/JNEUROSCI.3740-14.2015) [↩︎](https://hg2dc.com/2024/07/25/question-33/#c84c24e5-426c-48c7-b5a3-826c5986da9d-link)

