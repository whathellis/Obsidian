---
URL: https://hg2dc.com/2019/06/23/question-8/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/06/40268-1w8o68p7-xvli2qccmjggug.png
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-09-09
duration: 5
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #8: What the F*ck Type of “Linear” Have We Been Assuming?

I’m going to spoil our trend of not answering questions with an actual answer, that is somewhat not-too-secretly buried it the question itself. That is, this isn’t even a question, but more of a pit stop in the glossary. Specifically, the four previous questions culminate in the term we are going to Achievement Unlock:

1.  [Back at Question #2](https://hg2dc.com/question-2/), we were able to discover the arbitrary nature of RGB code value triplets. We focused on the idea that in some instances, the code values represent a ratio, and specifically, a ratio between some minimum and some maximum.
2.  [At Question #5](https://hg2dc.com/question-5/), we dug a little deeper. We revealed that code values could be ratios, and hinted that the nature of the ratios could be related to a whole, such as with a percentage, or with regards to ratios between each code value.
3.  [Question #6](https://hg2dc.com/question-6/) began to lay the structure in place to connect the dots between code values and meaning. We learned the crucial concept of a colour component transfer function, and how it decodes code values to something.
4.  Finally, with [Question #7](https://hg2dc.com/question-7/), we established what exactly the something is from above, and bolted it down to a concept around linear light and how our psychophysical perceptual system is nonlinear.

And with those four questions…

***Question #8: What type of “linear” have we been assuming the RGB code values are in reference to?***

---

“What a stupid question! Linear is linear right? Linear light energy is linear light energy. We’ve covered this sh\*t…”

The issue is that like all things colour and code value related, the confusion comes out of the bog of nightmare terms. Up to this point, we haven’t managed to find a term that gives this meaning specific context, and it’s clear we need one. It’s also an extremely crucial bit of terminology to keep in sight when discussing code value decoding as we have been.

---

***Answer #8: Up to now the “linear” have we been talking about stands in reference to a particular type of display, or more generally as output referred encodings.***

“WAIT A MINUTE. WE KNOW THIS ALREADY FROM QUESTION F\*CKING #1!!1! THIS IS A CONTENT SCRAPE!!11!!”

Yup. As mentioned, this is a cheated question. Why the cheat?

The specific term in question, [*output referred*](http://cie.co.at/eilvterm/17-32-052), is useful alone. More useful though, is that we can’t break down things further without it. We can now speak about the relationship of the intensity output of a code value in relation to a specific context, and concretely and accurately connect light emission of a particular code value in an output referred context.

Extending this, when we are discussing displays, we are speaking of the [display’s input / output characteristics](http://cie.co.at/eilvterm/17-32-022), which as we know from [Question #6](https://hg2dc.com/question-6/), is the mathematical function known as a [colour component transfer function](http://cie.co.at/eilvterm/17-32-004). We also get to add another term to our toolbox, and discuss code values related to displays as *display referred encodings*.

---

“Display referred, OK… but there are other things that aren’t displays… How do the digital code values in a photograph work? They can’t be in relationship to a display in the camera. What about a printer? That clearly isn’t in relationship to a display. A scanner?!? This is completely unuseful!”

You’d be 100% correct if you have these sorts of questions swirling around in your head. That’s a good thing! Better, you’ve hopefully grown bored of the idea that code values are always in *reference* to *something*, and that *something* isn’t always a damn display! In some instances, the code values refer to other contexts, and only take their meaning from that context. Hence, output referred is the umbrella under which many other references live, and the umbrella that display referred lives under.

So is there a commonality here? Is there something further we can add to our general output referred understanding? Yes. The key point to understand is that when discussing output referred encodings such as devices, printers, etc. is that their code values exist as a ratio of values from some minimum to some maximum, and that the *absolute* meaning is defined *solely* by that reference. A ratio of light from a display, a ratio of light that a sensor can detect, a ratio of reflectance off of an object, a ratio of values scanned into an image, or even a ratio of ink applied to a particular type of paper, etc.

In all cases, remove the referred device and RGB or CMYK or any other bogus code value, no matter how precise, utterly loses its meaning. So much for the sh\*t-f\*ck-metric-tonne of garbage articles that discuss RGB and CMYK as a *colour space*, eh? Hopefully you are beginning to see the horrible confusion between a [colour encoding model](http://cie.co.at/eilvterm/17-32-006) and a [colour space encoding](http://cie.co.at/eilvterm/17-32-018); the former’s code values hold no meaning without the details of the latter. In most cases, that meaning is derived from some specific reference².

---

I’m going to hope you found this question sleight-of-hand completely unsatisfactory and underwhelming. I’m also going to hope you found it somewhat obvious, and even hope further that this felt like a rehashing of things we’ve been tracing back and forth over. In fact, I’m going to hope this was a boring repeat of information you already fully understand and were simply lacking the appropriate term.

Armed with a new term, we can slip back to connecting the dots. There’s one specific question that frequently comes up, and that is, why do we bother with linear and nonlinear encodings at all? [That seems like a good question to dig into over the next couple of questions…](https://hg2dc.com/question-9/)

---

¹ The wise reader probably already knows or remembers that colour displays haven’t always had code values that represented intensity. In fact, the original colour displays weren’t terribly colourful, and had limited, specific colours they could represent. Those display encodings became known as [palettized](https://en.wikipedia.org/wiki/Palette_%28computing%29), and their semantics were basically like picking spot colours out from a given list. This post has left behind that era in the hope of removing some of that confusing history, not that you won’t see it come up time and time again as one confused idiot “explains” colour in a verbal diarrhea potpourri from time to time on those ever-awesome answer sites…

² In some rare cases, the colour encoding model comes with a specific colour space encoding series of characteristics. They are few and far between, and it’s best to think of a colour encoding model as something separate from a colour space encoding.

