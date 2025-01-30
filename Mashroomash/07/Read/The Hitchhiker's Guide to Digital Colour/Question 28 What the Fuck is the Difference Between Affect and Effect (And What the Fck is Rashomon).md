---
URL: https://hg2dc.com/2022/08/11/question-28-what-the-fck-is-the-difference-between-affect-and-effect-and-what-the-fck-is-rashomon/
thumbnail: https://hg2dc.com/wp-content/uploads/2022/08/rashomon_poster_3-e1660265559465.jpg?w=1200
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:27:57
duration: 6
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #28: What the F*ck is the Difference Between Affect and Effect? (And What the F*ck is Rashomon?)

[Rashomon](https://www.imdb.com/title/tt0042876/) was a film that offered a unique multiple recounting of a horrible incident. Why am I bringing it up here? It seems fitting.

In order for us to fully appreciate the depths to which we have plunged, it is critically important for us to pay close attention to the two most recent posts. In [Question #26](https://hg2dc.com/2021/12/03/question-26/), we’ve seen that there’s a metric for describing a relationship to tristimulus with respect to the Standard Observer. In [Question #27](https://hg2dc.com/2022/01/14/question-27/), we’ve seen that there is a parallel, upside down universe that can describe our sensation of appearance of the aforementioned tristimulus using some other metric.

For a long while, there was a plan to dive into things like photographic exposure, contrast, chroma, and saturation. But sadly, the explanations kept returning to the complexity of fully embracing the contextual nature of colour appearance, while simultaneously understanding the representation of that appearance utilizing some tristimulus metrics. So how would we move forward?

It became clear that there was a unique way to retell understanding uncovered in [Question #26](https://hg2dc.com/2021/12/03/question-26/) and [Question #27](https://hg2dc.com/2022/01/14/question-27/) by revisiting the old posts, one by one, and seeing how the author totally lied to us.

***Question #28: How does the difference between affect and effect relate to our use of digital colour?***

This comes complete with our Rashomon inspired sub-question…

***Subquestion #28: How did the author lie to us when they asked “What the F\*ck Happens When We Change an RGB Slider Value?”?***

---

> ***Answer #1: You are increasing or decreasing the emission intensity of one of the three RGB lights.***
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

***Answer #28: To properly affect digital “colour”, it requires close attention to the desired domain of stimulus or appearance, and choosing an appropriate model to achieve such. Changes in one domain effect the other, not affect!***

Both stimulus domain manipulations and appearance domain manipulations are useful, and we ought to pay attention to just what we are attempting to achieve.

[Moving onto the next bucket of lies from the idiot author…](https://hg2dc.com/question-29)

---

1 Why is labelling the channels according to “red”, “green”, and “blue” part of the misdirection here? Take a look at the following image from [the famous Akiyoshi Kitaoka](http://www.psy.ritsumei.ac.jp/~akitaoka/histogram_compression-ECVP2021-ShowTime.html). See the UK flag red? It is a wonderful demonstration of the sensation of appearance of red, yet there is no tristimulus indication of red. The red channel lies! It helps to think about how we’d increase the sensation of appearance of redness in this sort of context, or more specifically, *affect* the appearance of redness. *Affecting* the tristimulus channel of “Red” is going to yield underwhelming results. Give it a try if you are in disbelief. Always remember that the appearance of colour is purely constructed in our perceptual system.

![](https://hg2dc.com/wp-content/uploads/2022/08/akiyoshi-kitaoka-demo.png?w=1024)

**Totally Red Appearance Sensation But Totally No Red**

2 Good luck finding this model. Chasing appearance models is less fruitful than looking for that Fifteen Unit Redness bulb at the hardware store, and probably a thousand times easier chasing down a unicorn or a leprechaun. Or a leprechaun riding a unicorn. This mythical perceptual model simply doesn’t exist. Most of them are fit models, based on some random set of research, and some underlying heuristic assumptions. They may be more or less useful in some specific niche, and smash like peanut brittle when extended for usage beyond. They can of course be useful in some limited contexts, but the wise reader exerts tremendous caution. We simply do not understand perceptual systems enough to develop robust models yet. If anyone is selling you on some perceptual mumbo jumbo, there’s a good chance they are selling you a bucket of rubbish. This is why the CIE pursues [Colour Appearance Model](https://cie.co.at/eilvterm/17-23-027) research to this day, with many explorations and variations on the themes.

