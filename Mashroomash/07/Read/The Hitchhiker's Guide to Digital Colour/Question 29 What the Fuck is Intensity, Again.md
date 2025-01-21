---
URL: https://hg2dc.com/2022/11/07/question-29/
thumbnail: https://hg2dc.com/wp-content/uploads/2022/11/6zwk7s.jpg
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:28:36
duration: 4
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #29: What the F*ck is Intensity, Again?

Following on from [Question #28’s Rashomon inspired retelling](https://hg2dc.com/2022/08/11/question-28-what-the-fck-is-the-difference-between-affect-and-effect-and-what-the-fck-is-rashomon/), we are going to look again at what [Question #2](https://hg2dc.com/2019/03/24/question-2/) brought to the table, and pick it apart.

[Question #2](https://hg2dc.com/2019/03/24/question-2/) asked:

> ***Question #2: What does*** `***0.6***` ***represent in a typical DCC context?***
> 
> – Idiot Author

The answer to [Question #2](https://hg2dc.com/2019/03/24/question-2/):

> ***Answer #2: In an RGB DCC application,*** `***0.6***` ***is a ratio between a minimum and maximum, representing some ratio of light intensity.***
> 
> – Also Idiot Author

***Question #29: What did the author really mean with “intensity” when they described the numerical value?***

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

***Answer #29: When discussing encodings of tristimulus chromaticity coordinates, it is probably wiser to avoid the term intensity, and consider them strictly as encoded ratios of tristimulus, and these ratios are anchored in the CIE 1924 photopic photometric observer as the base unit of the metric.***

As a general guideline, it is worthwhile to accept that a digital *encoding*, be it from a camera, an EXR, an image, or anything else in the world of digital colour, is often times an *encoded* value. We risk grave confusion when we start loosely tossing terms around in the deep end of the pool, which in turn, might pile up and form an incorrect vantage of the surface in question, leading to us drowning in the aforementioned pool.

When a tristimulus value goes upward, it is probably makes good sense to ask what that shift in amplitude means. For our purposes, when discussing colourimetry and the tristimulus values used to communicate colourimetry, the base unit stands in relation to relative luminance, and a straight line to notions of energy in the radiometric sense.

[And now, onward…](https://hg2dc.com/question-30)

