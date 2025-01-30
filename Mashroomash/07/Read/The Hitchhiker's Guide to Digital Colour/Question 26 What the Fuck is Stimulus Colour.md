---
URL: https://hg2dc.com/2021/12/03/question-26/
thumbnail: https://hg2dc.com/wp-content/uploads/2022/01/60vn01.jpg
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:22:38
duration: 7
done: false
playlist: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #26: What the F*ck is Stimulus Colour?

Phew… it’s been a while dear friend. And with that repose away from the insanity of digital colour, it seems fitting to do a bit of revisionist history tour and look back to what we’ve covered. Why? Because I’ve totally f\*cking lied to you.

Remember way, way, way back where we first started trying to peel off the layers of confusion and outright bullsh\*t? Remember back to Question #1 where I said we were manipulating light emissions? That was only a half truth.

So let’s kick this question out and get down to business.

***Question #26: What is stimulus (encoding) of colour?***

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

***Answer #26: The stimulus specification, or specifically a colour stimulus encoding, is a human created model that connects quantities of the visible range of electromagnetic radiation to the stimulation response of a standard observer.***

---

Phew. That was a janky yet mandatory thing we had to cross over.

The key takeaway at this juncture is that the description of numbers and ratios and all of the rubbish we’ve covered thus far is in fact *not* direct measurements of light, but rather communicated using a colour stimulus encoding value, as specified in [that CIE XYZ model from way back in Question #13](https://hg2dc.com/question-13).

Why is this so damn important to cover now that you had to read this airbag post? Well, dearest reader, we’ve hopefully expanded our understanding enough to get into some sticky yet familiar terms that require this distinction for moving forward. That means we will be able to glue together the previous four posts and some pretty important and commonly misunderstood concepts. [But that will just have to wait a bit longer…](https://hg2dc.com/question-27)

---

1 Given that the official [CIE term list identifies “stimulus” directly as electromagnetic radiation](https://cie.co.at/eilvterm/17-23-002), it’s worth noting that this post tries to address the fact that we are dealing with a stimulus or tristimulus *encoding* when dealing with imagery etc. When you read the word “stimulus” in this context, it’s worth noting that it’s referring to a singular stimulus *encoding*, or a tristimulus *encoding*. For the sake of identifying the differences between actual electromagnetic radiation and the way we specify its impact on a standard observer in terms of encodings, it seems a reasonable term to harness. Note even [the CIE term definition for “Reference Colour Stimuli”](https://cie.co.at/eilvterm/17-23-037) uses the term “theoretical stimuli”, which could be considered ambiguous where a strict interpretation of stimuli with respect to electromagnetic radiation were to be enforced. “Theoretical stimuli” in terms of the theoretical numerical encoding of XYZ become somewhat nonsensical if we are forced to think rigidly in terms of electromagnetic radiation. TL;DR: Consider the use of “stimulus” used here to refer to the nature of the theoretical stimuli encodings we manipulate, and that those theoretical stimuli encoding values are somewhat detached from broader electromagnetic radiation mechanics. If someone feels that the strictest definition of “stimulus encoding” must be adhered to, it should be easy to replace the shorthand use of the term “stimulus” with something like “The R in RGB in this instance means the numerical value in relation to it’s meaning relative to the chromaticity encoding diagram, that is a stimulus specification” in a text editor for their own private reading. The more important point here is to give a person a useful construct to build further inferences upon.

