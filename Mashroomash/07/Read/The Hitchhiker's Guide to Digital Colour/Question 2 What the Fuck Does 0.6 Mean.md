---
URL: https://hg2dc.com/2019/03/24/question-2/
thumbnail: https://hg2dc.com/wp-content/uploads/2019/03/bf326-1p_8ere1ahf7t0wcyi36qag.png
site: "[[09 Index/The Hitchhiker's Guide to Digital Colour]]"
date: 2024-08-31
duration: 6
done: true
---
# Question #2: What the F\*ck Does 0.6 Mean?

As we learned through our [entry question #1](https://hg2dc.wordpress.com/2019/03/23/question-1/), changing the value of an RGB slider changes the intensity of light emitted from a single channel of our display. Depending on your DCC of choice, you might see a range of values change from some small value to some larger value. Sometimes, instead of a legible value such as `0.6`, you may see goofy looking values such as `121` or even more confusing cryptic looking codes such as `0x1A`.

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

If we were fleshing out an RGB model, we could say a single bit of information has a range of 2¹, or two, positions just like a coin. That means we could assign the *meaning* of those positions to represent the states of our little lights in our little pixels as being either on or off, or minimum and maximum. If we add a single bit of information, we have 2² positions, or four![^1] That might mean minimum, maximum, and two values in between. Carry on with this, and we hit the magic number eight, which for reasons I won’t go into here, is an historical quantity of information “steps” that we have used to represent colour for a long while. It’s a boring historical romp into computer colour for those who want to dive deeper.

[^1]: A simple way to understand the basic math is to think in terms of coins. A single coin has a number of sides (2), and the number of coins gives us the exponent. If we had 6 coins, the total number of unique positions if we laid them out on a table would be 2⁶, or 64 unique combinations.

Why is eight bit relevant here? Eight bit gives rise to the two latter *encodings* we see above. That is, value `153` and the ridiculous `0x99` are nerdy computer methods of describing the much more legible value `0.6`. At eight bits, we can encode a total of `256` unique combinations. If we were to go a step further in refining the meaning of those combinations, we could interpret them as whole-numbers, or in nerdy-speak *integers*. Under such an interpretation, the values could be thought of as simply a number of steps from the first combination to the last, which would be from `0` to `255`. So what then, is `153/255`? You guessed it! `0.6`! And if we go down the gobbly gook hole of computer history, we discover that `0x99` is *hexadecimal* for the integer whole-number value `153`, which again, is nothing more than a fractional representation of the maximum value, or more simply, the decimal value `0.6`. Seems like a lot of work to make `0.6` *less* legible, agree?[^2]

[^2]: I have some bad news for you WANKs who think you are doing the world a wonderful service by confusing the hell out of everyone using eight bit code values `153` or the ever more super-secret-I-know-what-I-am-doing-and-you-don’t cryptic value `0x99`; you haven’t added any meaning. No really, you haven’t. Feel free to head home with your lunch box and tell your mom I insulted you. To everyone else, let’s wrap this nightmare of nerd-speak up and forge ahead to the next question.

Thankfully, I’ll keep the cryptic WANKer speak to a minimum, and try to refer to the more sane decimal representation where possible.

---

Given we know that RGB sliders impact the intensity of emission of the lower level reddish, greenish, and blueish lights that compose a single pixel, we now can concretely cut through the bulls\*it of the various representations of code values. `0.6` represents a ratio along the way from minimum to maximum. We know it is somehow tied to the lights in our display, but sadly, we aren’t much better off than when we started. What the hell is it `0.6`, or 60%, *of* exactly? Better, if we set it to 100%, does the colour change from when we had the light set at 60%? That seems like [a pretty darn good next question…](https://hg2dc.com/question-3/)


