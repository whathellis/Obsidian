---
URL: https://hg2dc.com/2019/06/19/question-7/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/06/eb077-1q5b2r_r312diag5okuycng.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-04
duration: 7
topics: 
done: false
cover: 
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
word-goal: 2500
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Question #7: What the F*ck Does “Linear” Mean?

Description:: This is perhaps one of the most ugly questions we are going to tackle, and I’ll warn you up front, it’s *very* ugly. The good news is that we are going to smash up a bunch of bogus misinformation in this question. The bad news is, much like all of these damn questions, is that there will be more questions left in the rubble.

[The previous Question #6](https://hg2dc.com/question-6/), we started chipping away at what a transfer function is. Let’s recap a little bit:

1.  [Back at Question #2](https://hg2dc.com/question-2/), we first posed the question as to what a code value represents in a typical DCC application. We learned that it relates to some intensity of light coming out of a display on some scale from minimum to maximum. Unlike what we thought as a “colour”, we learned that it is some *code* to be *decoded*.
2.  [Back at Question #5](https://hg2dc.com/question-5/), we learned that while we have connected the dots to some sort of emission from a display, we haven’t really pondered what the measurement system is. That is, in learning that a particular value doesn’t mean anything, we learned that we need some means of defining a frame of reference, or *ground truth*.
3.  [Back in Question #6](https://hg2dc.com/question-6/), we learned that the math formula that defines our measurement system is called a transfer function. This function is the glue between the *code values* and something to do with a *physical quantity of light*.

The last point is a doozy. If you thought folks are driving their digital colour cars into the ditch via the revelations accumulated over the previous six questions, the third point above is a canyon. We can’t discuss code values and their relationship to quantities of light until we bridge the canyon with a bit about how light works…

---

Hopefully at this point you’ve come to the conclusion that the misunderstandings you may have had regarding colour come from the lack of a frame of reference. “Linear” is just such a term. So let’s keep things in the commerce of the Attention Economy and get our question front and centre:

***Question #7: What does “linear” mean and what does it relate to?***

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

Sadly, not even this rule of thumb really describes lightness¹ very well. Remember how we said human perceptual systems are nonlinear? They are so nonlinear and strange that there’s no real perfect, idealized formula for it, and new research is being done even today. At a certain level, once we are adapted to a given range of light, light behaves one way, then above a certain level, it behaves slightly differently. It’s a sloppy mess. For our purposes, it’s great that it’s sloppy as we can simply accept wholeheartedly that our perception is a *nonlinear phenomena*.

![](https://hg2dc.com/wp-content/uploads/2019/06/eb077-1q5b2r_r312diag5okuycng.png)

A rough approximation of perceived lightness along the vertical axis against a known linear model variable known as luminance along the horizontal axis

---

We’ve just about hit our time allocation here, which indicates that our question is about as fleshed out as we can be at this point. So, let’s answer the question…

***Answer #7: “Linear”, when used in the context of digital colour, is referring to how radiometric light energy behaves, and how ratios can be described with respect to that radiometric energy ground truth via the physics and math of light energy.***

---

We can’t discuss digital colour without understanding that there is a need to subdivide our dive into different domains. In discovering that light is physical and that colour is psychological, it helps us to understand why colour exists as a [*psychophysical*](http://cie.co.at/eilvterm/17-21-012) phenomena; the experience of colour is tightly wound between physical stimuli and complex human psychological and organic reactions.

Specifically though, we need to understand that “linear” is a crucial aspect to how we are going to be describing light energy; it’s a foundational concept that connects all of the moving parts. With that understanding, we also must note that using a term like “linear” alone isn’t quite enough information to make meaningful inferences.

We know that we are referring to some sort of linear radiometric quantity of light, but we can clearly see that there’s many different contexts that could result in quite different interpretations of “linear” here, and yield different meanings from our code values in our precious RGB encoding model. And with that… take another break, and rest your RGB grey matter before we [move onto our next question](https://hg2dc.com/question-8/)…

---

¹ It is easy to be a bit sloppy in using the terms [lightness](http://cie.co.at/eilvterm/17-22-063) and [brightness](http://cie.co.at/eilvterm/17-22-059) somewhat interchangeably. In terms of colour science and colour appearance models, it should be noted that there are strict definitions and differences between the two.

