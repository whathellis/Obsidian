---
URL: https://hg2dc.com/2019/03/23/question-1/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/01/picker-question.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-31
duration: 5
done: true
---
# Question #1: What the F\*ck Happens When We Change an RGB Slider Value?

For reasons that are still somewhat alien and strange to me, I get weekly emails reaching out from digital image makers in smaller studios to independent one-person-army types. Every single post is unique, yet at their core, the foundational concepts remain extremely similar. *“What the hell can I do to fix my pixel pushing in Random Digital Content Creation Application.”* I try my best to give a leg up and help out the folks asking to the best of my abilities. Frequently, I’m looping over a path that I’ve slowly refined over the years.

This post is essentially a means for me to link to and avoid copy pasting over and over again. I’m not going to make any grandiose claims or promises that there will even be a follow up post. Take from it what you will. Every entry is an attempt at a simple, short, and concise question.

As of writing, I can think of no better entry point to pixel pusher clarity than what I’m going to present in this post. I hope you find it as fascinating as I have…

Pushing pixels for anyone who has done it for any length of time appears to be such a mundane concept that discussing sliders isn’t even worth bothering with. Pick a colour, slap it down. It’s sadly so mundane that many seasoned veterans haven’t bothered to stop to ask themselves just what the hell is going on at the simplest level. Nevertheless, the following is the most informative entry point question I’ve arrived at:

**Question #1: What the hell happens when you slide or adjust one of the RGB values in your favourite digital content creation painting application?**

For those of you who can’t answer it clearly, and become somewhat shocked at how nebulous and slippery developing an answer seems, congratulations! The question is designed to not only reveal one of those hidden blind spots in your vision, but also to fork off into the crucial concepts behind colour for you as a pixel pusher.

Any ideas? Take your time, or better still, crack open your favourite DCC and give those sliders a whirl with the question firmly in front of you. I’ll wait…

Welcome back.

If you thought a bit about the answer, or perhaps even mucked about with a colour picker for a while, and arrived at the correct solution, congratulations, you are in a minority! I’ve posed that question to over a hundred well-seasoned, veteran image makers, and the response is always the same; one part confusion, one part surprise, and one part curiosity.

*“It makes the colour redder.”*
*“It makes the colour less greeny.”*
*“It changes the colour to make it different.”*

All of which are of course descriptive effects of the answer here, but none of which describe what is the affecting force. The answer is that, when you are picking a colour in a majority of DCCs, you are doing precisely one thing and one thing only. I’m going to make a bit of an oversimplification for some edge case readers here and provide you a working answer that *hopefully* makes clear sense for the intended audience[^1].

[^1]: It should be made clear that this short post is for anyone who has ever had to push a pixel around on a computer in their life and experience nausea when someone utters the words Colour Management openly. This isn’t a f\*cking article about Colour Management per se. It’s about colour, and more specifically at times, RGB, for the poor pixel crafters out there who quietly want some clarity in their work. If [Leonardo Da F\*cking Vinci can cut apart cadavers to hone his craft](https://www.telegraph.co.uk/culture/art/leonardo-da-vinci/10202124/Leonardo-da-Vinci-Anatomy-of-an-artist.html), it seems reasonable that someone getting paid to push pixels around should be able to cultivate a sense of pride in their craft enough to research and understand just what the hell they are doing. This site is for them, and not the ever wise group of folks I typically discuss and bicker about colour with. If you are pushing pixels around for free, self inflicting a horrible sense of imposter syndrome on some personal project, this series is perhaps even *more* for you…

**Answer #1: You are increasing or decreasing the emission intensity of one of the three RGB lights.**

How simple was that?

If we are sliding a slider in Photoshop or Procreate or any of the other popular mainstream DCCs, we are connecting the slider up to the little diodes in our display[^2].

[^2]: For those of you wise ass *“Well actually…”* Number Kids (WANKs henceforth) that want to dissect what is happening in the reference space versus what is output to the display, and the role of a colour management system, and the potential for gamut mapping transformations and the… just shut the f\*ck up and sit down for a moment. You are part of the problem. You aren’t helping the intended audience of this piece by diving so f\*cking deep so quickly that you are drowning them.

As you are already likely well aware, most displays are composed of an array of pixels, which in turn are composed of a series of three extremely small lights of three particular colours, or RGB *primaries*. We so frequently refer to the RGB model that we sometimes forget that there are three physical little lights per pixel in our displays that are increasing or decreasing in emission strength.

When a slider is increased, it increases the intensity of the given channel based on a ratio. That is, if we slide the green slider upwards, we are increasing the quantity of the light emitted from the little green diode in the pixel(s) in question toward the maximum intensity output of the little green diode. This leads us to [[Question 2 What the Fck Does 0.6 Mean|our next crucial question…]]
