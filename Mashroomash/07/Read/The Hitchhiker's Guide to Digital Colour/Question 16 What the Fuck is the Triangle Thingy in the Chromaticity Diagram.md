---
URL: https://hg2dc.com/2020/01/07/question-16/
thumbnail: https://hg2dc.com/wp-content/uploads/2020/01/srgb-display-p3-1976.png
site: "[[The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-22T18:18:21
duration: 7
done: false
playlist: "[[The Hitchhiker's Guide to Digital Colour]]"
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Question #16: What the F*ck is the Triangle Thingy in the Chromaticity Diagram?

Recall back to [Question #13 where we explored how chromaticities are discussed](https://hg2dc.com/question-13/). You may have wondered where that triangle went, and [why I removed it in the subsequent diagrams in Question #15](https://hg2dc.com/question-15/).

Why did we have to learn about chromaticities instead of RGB values? Because, as you have hopefully learned from the preceding batch of questions, RGB is a *relative encoding model*, which means making comparisons becomes extremely confusing! How can we evaluate the Display P3 “green” value on your iPad Pro at 100% emission strength to the “green” value on one of your sRGB device, when the two values expressed in RGB are identical? We can’t!

Guess what? That leads us directly to the subject of our current question…

***Question #16: What is the triangle that appears commonly on a chromaticity diagram?***

---

The goal here in this back alley of the interwebs of colour debauchery, is for you, the pixel f\*cker1, to *completely* and *utterly* comprehend what is presented to you. So, let’s quickly recap a few important details about the CIE 1931 xy chromaticity diagram:

-   The diagram is an invented model that lets us connect visible spectral light energy and mixtures to numbers.
-   The xy chromaticity diagram uses a warped scale that is disconnected from how we perceive differences in the visible wavelengths of light.
-   The diagram’s peculiar curved portion of the shape represents the visible light spectra in nanometers.
-   The region outside the spectral locus does not exist in any physically meaningful way. It is only even given a shape due to the artificial model and the representations you have seen.

Let’s have a peek at the above summary on the diagram to reinforce understanding…

![](https://hg2dc.com/wp-content/uploads/2020/01/1931-recap.png?w=512)

**FIGURE OMFG NON-PERCEPTUAL SCALE**: A non perceptually uniform scale human crafted model of the wavelengths, represented in the upper vertical gradient portion, loosely visualized along the edge of the chromaticity diagram.

As you can see in **FIGURE OMFG NON-PERCEPTUAL SCALE**, the line of the visible spectrum wavelengths is not equally and uniformly distributed around the perimeter of the spectral locus; a standard observer does not sense all wavelengths in equal measures, and instead a complex relationship exists between the electromagnetic radiation and the sensation in “standard” perceptual systems. And again, it needs to be stressed that the distances measured along x and y are also not uniform with respect to how we’d perceive the differences in terms of *relative perceptual sensations*. Everything is warped!

---

[If we recall back to our last question, Question #15](https://hg2dc.com/question-15/), we presented a more useful variation of the original CIE 1931 chromaticity diagram that warps and scales the x and y axes. Let’s snap our fingers and see the above image, with the exact same arrows, warped, skewed, and bent to the perceptually uniform 1976 diagram variant.

![](https://hg2dc.com/wp-content/uploads/2020/01/1976-recap.png?w=512)

**FIGURE WARPED PERCEPTUAL SCALE 1976**: A perceptually uniform-ish-kinda-sorta scale variant of the diagram above. Note that while the wavelengths move around a bit, they still aren’t distributed uniformly.

As we can see in **FIGURE WARPED PERCEPTUAL SCALE**, the visible light spectra are *still* not uniformly distributed around the perimeter of the spectral locus but the chromaticity coordinates on the inside however, are distributed in a roughly perceptually uniform manner. Because this is a modified variation of the xy diagram, the measurements have their labels changed to u’ and v’. They are a different coordinate model.

So now, what about that damn triangle? Something like this one…

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-1976-1.png?w=640)

**FIGURE WTF IS THE TRIANGLE**: We can see that the triangle represents three specific chromaticities with a fourth towards the middle of it, but what are they exactly?

In **FIGURE WTF IS THE TRIANGLE**, we can see that the red dots at the tips of the triangle, and that off-centre dot inside the triangle, plot four chromaticities. But what exactly are they? The four chromaticities of course, as you may likely have inferred, represent the chromaticities of the three primaries and white chromaticity outlined in the sRGB specification!

That is, if you are staring at a reasonably decent sRGB display, the [tips of the triangle represent each of the three colours of the three little teeny lights in each pixel of your sRGB display](https://hg2dc.com/question-3/)! The off-centre dot is the chromaticity that an ideal sRGB display outputs when you set the sliders to equal R=G=B values. This chromaticity is sometimes [called the “](http://eilv.cie.co.at/term/1430)[white](http://cie.co.at/eilvterm/17-23-070) [point”](http://eilv.cie.co.at/term/1430). As [we discovered in Question #14, “white” is just another chromaticity.](https://hg2dc.com/question-14/)

The straight lines of the triangle depict the line of chromaticities that can be mixed between the two outside primary lights at the tips2, while everything *inside* the triangle is the footprint of the entire area of chromaticities that can be mixed with the specific colours of three RGB lights. sRGB, and all other types of displays, are limited by chromaticities of their three lights, and *no chromaticity can be mixed beyond the limits of the triangle they form on the chromaticity diagrams*!

So let’s move onto that iPad Pro…

![](https://hg2dc.com/wp-content/uploads/2020/01/display-p3-1976.png?w=797)

**FIGURE DISPLAY-WHAT**: The CIE 1976 perceptually uniform chromaticity diagram featuring the relative positions of the iPad Pro’s Display P3 primaries.

Remember [back in Question #4](https://hg2dc.com/question-4/) where I told you that the “colours” of the three lights in your display are sRGB? Well, I hope our relationship is strong enough now that I can tell you that I lied. At least a little bit.

For the sake of clarity and simplicity, we introduced the complex subject using the generic sRGB standard, as that type of display is extremely common. If you happen to own an iPad Pro or MacBook Pro from 2015 onwards, the colours of the three RGB pixel lights in *those* particular pieces of hardware are not the same as sRGB!

---

The image **FIGURE DISPLAY-WHAT** shows us a similar triangle as **FIGURE WTF IS THE TRIANGLE**, but with different coordinates. The chromaticity coordinates in **FIGURE DISPLAY-WHAT** represents the *Display P3 primaries* that are found in most of Apple’s products from 2015 onward, and more and more displays from different vendors. While Display P3 features the identical white point as sRGB, the primaries are more saturated and of different “hue angles”. That is, two of the three primary lights are further out toward the purest spectral locus region, while the blue light is reasonably similar to sRGB’s blue light. They also plot at slightly different angles from the white point as compared to the sRGB primaries. Draw a straight line from the white point to the tip of the respective primary, and you can see how the angle is slightly different.

To get a better sense of these differences in colorimetry, let’s compare them together in one image using the useful perceptually uniform scale.

![](https://hg2dc.com/wp-content/uploads/2020/01/srgb-display-p3-1976.png?w=712)

**FIGURE TWO DISPLAYS**: The above image shows the relative positions of the primaries for both Display P3 and sRGB. Note how the white points are identical, despite the base primary lights being different.

Recall [back to Question #3 where we learned that the chromaticities of each of the three lights in our displays never changes, and only the intensity of emission](https://hg2dc.com/question-3/)? The reason that the hardware in a Display P3 device can display more saturated colour mixtures of a wider range is because the chromaticities of the three lights in each of the RGB pixels are *quite different* from sRGB! To really hammer this home, I’d strongly encourage you to go back and [review Question #3](https://hg2dc.com/question-3/) and [Question #4](https://hg2dc.com/question-4/) as the answers provided will be more meaningful now with what we have put into place.

And with that, we can answer our question…

***Answer #16: The triangles commonly found on chromaticity diagrams plot the chromaticities of the three basis primary lights in a display or other three light RGB standard.***

“But wait a minute… what the hell is a gamut?” “Can we deduce the spectral compositions from a single chromaticity?” “How do the sliders behave with different pieces of display hardware?” “I’m a photographer, I shoot real scenes not displays, how does this all relate?” “How does offset and spot printing relate to all of this?”

All terrific questions [that will just have to wait a little bit more…](https://hg2dc.com/question-17/)

---

1 I’d like to give full credit to [a very large cranium visual effects supervisor slash talented image maker Erik Nordby](https://www.imdb.com/name/nm0634969/) for coining that turn of phrase. While he has used it as a derogatory term, I feel it adequately describes what many folks who deal with digital content creation do, and have actively repurposed it here as a badge of honour.

2 It might be helpful to think of lights as being points on the chromaticity diagram that “pull” towards themselves like gravity as their emissions grow. At equal energy between two lights on the chromaticity diagrams, the resulting mixture is somewhere between the two. As one of the light’s emission grows, it “pulls” the chromaticity away from the other light, towards itself. If the light has no other light “pulling” away from it, the light is the purest and most heavily saturated it can get. This logic carries on to even the spectral laser-like wavelengths represented around the perimeter of the spectral locus! The wavelength composition of D65 daylight, for example, could be though of existing as a bunch of visible spectra under tension between each other, with the relative power “pulling” toward the spectral locus curve to greater or lesser degrees.

![](https://hg2dc.com/wp-content/uploads/2020/01/d65-spectral-power-distribution.png?w=640)

The spectral composition of one particular mixture of D65, which has an x and y coordinate of roughly x 0.3127 and y 0.3290. The heights represent the relative power of the given visible light spectra, and how they pull each other from the outside perimeter of the spectral locus towards the middle region.

