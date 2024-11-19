---
URL: https://www.youtube.com/watch?v=PDd5GQnjR44
thumbnail: https://i.ytimg.com/vi/PDd5GQnjR44/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:50:46
published: 2021-10-09T03:00:27
duration: 794
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "13m 14s"]
# How Do Computers Produce Random Numbers?
`````col
````col-md
flexGrow=1
===
text
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=PDd5GQnjR44
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/PDd5GQnjR44" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: The first in a series of videos on noise; in this premiere we tackle the idea of white noise and pseudo-random number generators.

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Code: https://github.com/GarrettGunnell/Linear-Congruential-Generator

References:
https://en.wikipedia.org/wiki/Linear_congruential_generator

Music:
Coasting - Transistor OST
Stained Glass - Transistor OST
Beware - Death Grips
Blues In The Velvet Room - Persona 3 OST

Chapters:
00:00 Intro
00:31 Background
03:04 How They Work
06:45 Why Call It Noise?
08:00 Applications
08:31 Outro
08:57 ????

Thanks for watching!

This video is dedicated to my friend, Alotryx.

also please subscribe haha please man please just subscribe dude please just like one sub I swear I'm not addicted please man please just one sub please

# Transcript
[00:08](https://www.youtube.com/watch?v=PDd5GQnjR44&t=8) hey everyone and welcome to a new video or a not so new video if you're watching this in the future today's video is the start of a new series on noise and its many derivatives as well as how it is 
[00:20](https://www.youtube.com/watch?v=PDd5GQnjR44&t=20) used in pretty much everything you have ever used or looked at electronically in this first video we'll be looking at how deterministic machines can fake non-deterministic outcomes 
[00:35](https://www.youtube.com/watch?v=PDd5GQnjR44&t=35) computers are stupid they do only exactly what we tell them to do and only that as it would be rather inconvenient for us if they did anything else or anything more this is known as 
[00:47](https://www.youtube.com/watch?v=PDd5GQnjR44&t=47) deterministic behavior a system in which no randomness or variance is involved this poses a problem when we do want some sense of randomness in our system how can you do that when computers are 
[01:00](https://www.youtube.com/watch?v=PDd5GQnjR44&t=60) completely deterministic enter the pseudo-random number generator pseudo-random number generators or prngs for short are deterministic algorithms 
[01:16](https://www.youtube.com/watch?v=PDd5GQnjR44&t=76) for generating fake random numbers which sounds really weird at first but it'll make sense in a little bit not all prngs are the same but their goal is for the most part 
[01:28](https://www.youtube.com/watch?v=PDd5GQnjR44&t=88) so i'll be going over one prng in this video and then you can pretend they all work that way but first a little bit of history like most computer science concepts the 
[01:38](https://www.youtube.com/watch?v=PDd5GQnjR44&t=98) first prng was invented by the man himself john von neumann in 1949 he proposed the use of the middle square method it starts by taking an initial integer or seed as the tech bros like to 
[01:53](https://www.youtube.com/watch?v=PDd5GQnjR44&t=113) call it you then square this number and use the middle digits of the result as both the random number and the new seed for the next prng output also if the squared number has an odd number 
[02:06](https://www.youtube.com/watch?v=PDd5GQnjR44&t=126) of digits you can just prepend a zero to it for example take the seed eight thousand five hundred and eighty we square that and get the result uh [ __ ] seventy three 
[02:18](https://www.youtube.com/watch?v=PDd5GQnjR44&t=138) million six hundred and sixteen thousand hundred and taking the middle digits we get our random number and the next seed which would be 6165. as another example we can use the seed 
[02:33](https://www.youtube.com/watch?v=PDd5GQnjR44&t=153) 1000 squaring that we get uh one million which has an odd number of digits so we prepend a zero to this and then we take the middle digits to get our random number and next seed which is 
[02:47](https://www.youtube.com/watch?v=PDd5GQnjR44&t=167) zero and now you can realize why this method for generating random numbers [ __ ] sucks von neumann got a lot of things right 
[02:55](https://www.youtube.com/watch?v=PDd5GQnjR44&t=175) but this one ain't it he knew this of course he just didn't care to keep developing prngs as the middle square method was sufficient for his needs 
[03:06](https://www.youtube.com/watch?v=PDd5GQnjR44&t=186) [Music] okay with a little history out of the way we can move on to an actual real modern pseudo-random number generator but first let's establish some aspects 
[03:18](https://www.youtube.com/watch?v=PDd5GQnjR44&t=198) of prngs that we went over with the middle square method prngs taken a seed to set the stage for the resulting random numbers the prng is what operates on this seed and then out 
[03:31](https://www.youtube.com/watch?v=PDd5GQnjR44&t=211) comes a random result this result isn't actually random at all though of course it's entirely deterministic because of the seed the same seed will have the same result 
[03:42](https://www.youtube.com/watch?v=PDd5GQnjR44&t=222) this is actually very useful behavior as interesting results of procedurally generated systems can be completely recreated with the same seed anyways let's take a look at a prng 
[03:54](https://www.youtube.com/watch?v=PDd5GQnjR44&t=234) known as the linear congruential generator or lcg for short the lcg works by utilizing a discontinuous piecewise linear function which sounds really complicated but it just means a line 
[04:07](https://www.youtube.com/watch?v=PDd5GQnjR44&t=247) that is not continuous the generator is defined by the recursive relation x of n plus 1 equals a times x of n plus c mod m where x of n plus 1 is the next random 
[04:22](https://www.youtube.com/watch?v=PDd5GQnjR44&t=262) number a is a multiplier constant of the previous random number or initial seed c is a constant incrementer and m is a constant that modulates the resulting number into a given period 
[04:36](https://www.youtube.com/watch?v=PDd5GQnjR44&t=276) additionally i like my random numbers in the range of 0 to 1 so we can divide this entire result by m to get that range the values you decide to use for each of 
[04:47](https://www.youtube.com/watch?v=PDd5GQnjR44&t=287) these parameters will wildly change the quality of the lcg so i stole the values that fortran and matlab use for their random number generator to illustrate how the lcg works let's 
[04:59](https://www.youtube.com/watch?v=PDd5GQnjR44&t=299) use the seed 2 since it's the coolest number 2 gets put into the lcg as x of 0 multiplied by 8121 incremented by twenty eight thousand 
[05:11](https://www.youtube.com/watch?v=PDd5GQnjR44&t=311) four hundred and eleven and modulated by one hundred and thirty four thousand four hundred and fifty six this result then becomes the new seed for the next iteration of the lcg and 
[05:23](https://www.youtube.com/watch?v=PDd5GQnjR44&t=323) before we return the number to be used we divide it into the zero to one range to demonstrate that this lcg is in fact suitably random i have plotted one hundred thousand generated numbers and 
[05:35](https://www.youtube.com/watch?v=PDd5GQnjR44&t=335) as we can see there is a relatively equal distribution of numbers produced by the lcg with little to no bias and if you'd like to see the code for this 
[05:46](https://www.youtube.com/watch?v=PDd5GQnjR44&t=346) it's in the description below as you can see lcgs are very nice and simple they are extremely fast and use essentially no memory as all they need to maintain state is 32 or 64 bits 
[06:01](https://www.youtube.com/watch?v=PDd5GQnjR44&t=361) depending on implementation but they aren't without their weaknesses lcgs begin to crumble once they are used on a very large scale they are only suitable for about a thousand random numbers and 
[06:13](https://www.youtube.com/watch?v=PDd5GQnjR44&t=373) 32 bits and a little over 2 million for 64 bits and that sounds like a lot of samples but it's really not when you delve into large scale monte carlo simulations 
[06:25](https://www.youtube.com/watch?v=PDd5GQnjR44&t=385) additionally lcgs aren't very suitable for on gpu random number generating as the lcg kind of requires you to maintain state which isn't possible on the gpu and if you care about generating random 
[06:38](https://www.youtube.com/watch?v=PDd5GQnjR44&t=398) numbers on the gpu you should look into hash functions personally i use the the zor shift algorithm now you might be thinking why is this video called noise and not pseudo random 
[06:53](https://www.youtube.com/watch?v=PDd5GQnjR44&t=413) number generators and that's a great question honestly i don't really know the exact answer other than it's just a matter of semantics and context noise is used to refer to variance and 
[07:05](https://www.youtube.com/watch?v=PDd5GQnjR44&t=425) stochasticism in the graphics world as well as data collection this association becomes obvious when we visualize the lcg we created earlier as a texture this image looks like a television 
[07:18](https://www.youtube.com/watch?v=PDd5GQnjR44&t=438) without a signal and that's because a television without a signal is visualizing the full range of frequencies on its screen this is referred to as white noise 
[07:28](https://www.youtube.com/watch?v=PDd5GQnjR44&t=448) because of how color works white light is the combination of all colors and in the case of the television it is visualizing the combination of all frequencies at once 
[07:39](https://www.youtube.com/watch?v=PDd5GQnjR44&t=459) tying this back to our random number generator it is generating the full range of random numbers in the zero to one range without any patterns or direction hence why we could refer to it 
[07:50](https://www.youtube.com/watch?v=PDd5GQnjR44&t=470) as white noise and this relation will become more obvious in future videos in the series okay if you need me to explain to you why 
[08:06](https://www.youtube.com/watch?v=PDd5GQnjR44&t=486) random numbers are impressive or applicable in the real world you may be not the pride of your friend group but here's a quick list of applications for you 
[08:19](https://www.youtube.com/watch?v=PDd5GQnjR44&t=499) [Music] but having this random number generator or white noise is a very important foundation for a lot of amazing techniques and graphics that i will 
[08:29](https://www.youtube.com/watch?v=PDd5GQnjR44&t=509) introduce to you in later videos anyways that's all folks i hope this video and series is as interesting to you as it is to me if you haven't already subscribe below 
[08:41](https://www.youtube.com/watch?v=PDd5GQnjR44&t=521) so you can see when i post new videos and check out my other social media as well but i gotta go now so have a great rest of your day and i'll see you next time 
[09:02](https://www.youtube.com/watch?v=PDd5GQnjR44&t=542) hey everyone uh i don't really know what this is i guess this is like a blog i'm recording this on my laptop so the 
[09:14](https://www.youtube.com/watch?v=PDd5GQnjR44&t=554) the quality is really bad but anyways i'm here staying in the uh mcminnamon's hotel in portland despite everything uh it's actually pretty cool this is the room that the 
[09:28](https://www.youtube.com/watch?v=PDd5GQnjR44&t=568) silver sun pickups stayed in they played the song lazy eye so all of the uh lyrics to this song are like painted on 
[09:39](https://www.youtube.com/watch?v=PDd5GQnjR44&t=579) the walls it's pretty cool i'd play the song for you uh but you know how youtube is i'm here for a concert i'm seeing tennis 
[09:52](https://www.youtube.com/watch?v=PDd5GQnjR44&t=592) the pop band i also went to a uh blazers game it was uh blazers versus golden state it was pretty cool got to see uh steph curry do 
[10:06](https://www.youtube.com/watch?v=PDd5GQnjR44&t=606) some things i don't know i don't play basketball or watch it for that matter i just got invited to the show but i actually just got back from the tennis concert 
[10:17](https://www.youtube.com/watch?v=PDd5GQnjR44&t=617) uh it was pretty good i'll play some uh some clips that i recorded my favorite song by then [Music] 
[10:32](https://www.youtube.com/watch?v=PDd5GQnjR44&t=632) oh [Music] that's a modern women modern woman 
[10:53](https://www.youtube.com/watch?v=PDd5GQnjR44&t=653) excuse me it's pretty good you should listen to it again i'd play it for you but you know how youtube is um 
[11:03](https://www.youtube.com/watch?v=PDd5GQnjR44&t=663) i also got some some like art books and stuff at powell's which is like a really famous bookstore i got uh the first volume of the 
[11:13](https://www.youtube.com/watch?v=PDd5GQnjR44&t=673) bakumanagatari manga which is pretty cool as well as um the art of the last of us too regardless of what you think of the game 
[11:24](https://www.youtube.com/watch?v=PDd5GQnjR44&t=684) it is a very very impressive game visually i also got the art of the the first first game and the art of death stranding which is a very big inspiration for me tech art 
[11:39](https://www.youtube.com/watch?v=PDd5GQnjR44&t=699) wise from the concert i got one of every vinyl which um the lady at the merch stand she actually 
[12:00](https://www.youtube.com/watch?v=PDd5GQnjR44&t=720) gave me a signed copy of of the their newest final because i spent so much money that she felt bad it was really cool 
[12:13](https://www.youtube.com/watch?v=PDd5GQnjR44&t=733) uh she also well she didn't give me this i bought a shirt as well which is it's pretty cool looking i think anyways 
[12:28](https://www.youtube.com/watch?v=PDd5GQnjR44&t=748) i did most of the work for this video here in this hotel room so hopefully it's as good as my other videos i don't know i guess it's like if i was locked in a room and all i could 
[12:41](https://www.youtube.com/watch?v=PDd5GQnjR44&t=761) do was make a video this would be it but i'm headed back tomorrow so hopefully the hardware for 
[12:53](https://www.youtube.com/watch?v=PDd5GQnjR44&t=773) my my main project is in the mail i hope it's there otherwise i guess i'll figure out what to do for another in between video 
[13:04](https://www.youtube.com/watch?v=PDd5GQnjR44&t=784) but anyways thanks for watching this little like blog section i'm just bored so have a great rest of your day thanks for watching 