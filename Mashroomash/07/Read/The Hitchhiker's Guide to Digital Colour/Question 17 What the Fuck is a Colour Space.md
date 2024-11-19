---
URL: https://hg2dc.com/2020/01/08/question-17/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/01/rgb-is-not-a-colour-space.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:18:42
duration: 4
topics: 
done: false
cover: 
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
word-goal: 2500
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Question #17: What the F*ck is a Colour Space?

Description:: Sixteen questions! It has taken us sixteen questions to even begin to describe the term “Colour Space” with any degree of useful communication. We can hop right in to our question…

***Question #17: What is an RGB colour space?***

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

***Answer #17: An RGB colour space, as outlined in the international standard ISO 22028-1:2016 must specify:***

1.  ***A transfer function or a set of transfer functions2***
2.  ***Three chromaticities for each of the three primary lights***
3.  ***The chromaticity of the white point***

Phew.

---

I hope this is a very clear answer. You’ll have to appreciate that the folks who understand this stuff very likely want to use the colourful language above that typical raunchy pixel f\*ckers might use, but can’t for reasons of professionalism or otherwise.

I just checked my pocket and have zero f\*cks left, so I’m giving you this information using the language required to hammer the point home. Don’t let some dipsh\*t developer, or StackExchange idiot, or random YouTube buffoon, or donkey blog post tell you otherwise. You have the links… hammer them over the head with it. Eventually, my grizzled and grumpy pixel pusher friend, they will cease spreading their horses\*it, and the next crop of pixel pushers won’t be as confused as we were when we started.

With that out of the way, [there are bigger fish to fry](https://hg2dc.com/question-18/)…

---

1 Some of you poor, poor people may also be dealing with CMYK encoding models of course, and I feel for you. Sometimes it might be a hybrid output, or even be the primary output! We will get into the nuances of print CMYK encoding models soon enough, but you have already probably deduced that they are not entirely dissimilar to the complexities around RGB, and in fact, the majority of the questions already covered are directly related to the contextual nature of CMYK encoding models!

2 Remember folks, friends don’t let friends say that wretchedly useless word “gamma”. Always remember that the actual specification of sRGB itself, [which is referenced in Question #6](https://hg2dc.com/question-6/), written over ***two decades*** ago, has a very important annex ***solely*** dedicated to destroying the term. The last sentence from that annex is:

> Furthermore, it appears that the usefulness of the term \[gamma\] in unambiguous, constructive standard terminology is *zero* and its continued use is *detrimental* to consistent cross-reference between standards and unambiguous communication.
> 
> [The sRGB specification, IEC 61966-2-1:1999](https://webstore.iec.ch/publication/6169)

