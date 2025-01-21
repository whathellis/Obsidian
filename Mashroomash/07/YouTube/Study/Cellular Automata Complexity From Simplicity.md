---
URL: https://www.youtube.com/watch?v=t_HcBAO_Yas
thumbnail: https://i.ytimg.com/vi/t_HcBAO_Yas/default.jpg
channel: "[[Acerola]]"
date: 2024-07-22T15:49:17
published: 2021-09-25T03:56:16
duration: 783
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [time:: "13m 3s"]
# Cellular Automata: Complexity From Simplicity
`````col
````col-md
flexGrow=1
===
![[Pasted image 20240722154940.jpg]]
````
````col-md
flexGrow=1
===
https://www.youtube.com/watch?v=t_HcBAO_Yas
<iframe width="400" height="210" src="https://www.youtube-nocookie.com/embed/t_HcBAO_Yas" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
````
`````
Description:: A brief history and explanation of Cellular Automata and their many applications.

Twitter: https://twitter.com/Acerola_t
Twitch: https://www.twitch.tv/acerola_t
Discord: https://discord.gg/FxGQvbfm6Y
Code: https://github.com/GarrettGunnell/Cellular-Automata

The opening animation is the Seeds cellular automaton.

References:
https://softology.com.au/ACellularAutomatonDescribingTheFormationOfSpatiallyOrderedStructures.pdf
https://web.archive.org/web/20081223050254/http://llk.media.mit.edu/projects/emergence/mutants.html
https://books.google.com/books?id=HBlJzrBKUTEC&pg=PA27#v=onepage&q&f=false

NileRed video: https://youtu.be/LL3kVtc-4vY

Music:
Old Friends - Transistor OST
Stained Glass - Transistor OST
Tommy Dorsey - Stardust On The Moon
Kid Ory - High Society
Jimmy Noone - Sweet Georgia Brown

00:00 Intro
00:25 Background
1:15 How They Work
1:50 Rule 110
4:25 Two Dimensions
5:05 Brian's Brain
7:09 Applications
8:38 Belousov-Zhabotinsky
10:37 Conclusion
11:13 Post Credits Scene

Thanks for watching!

This video is dedicated to my friend, Alotryx.

also please subscribe haha please man please just subscribe dude please just like one sub I swear I'm not addicted please man please just one sub please

# Transcript
[00:00](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=0) [Music] hey everyone and welcome to a new video or a not so new video if you're watching this in the future today's topic is cellular automata or how simple rules 
[00:21](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=21) can produce complex and unpredictable behavior like most computer science concepts cellular automata was discovered by john von neumann while he was fantasizing 
[00:34](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=34) about self-reproducing robots and his colleague stanislaw ulam studying something kind of completely unrelated in the 1950s ulam and von neumann worked together to 
[00:45](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=45) create a method of fluid simulation modeling an area as a collection of cells that contain fluid with the motion of the fluid dependent on its neighbors as behavior 
[00:56](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=56) thus was born the first cellular automata and absolutely no one cared it wasn't until the year 1970 when john conway invented the very famous game of life that cellular automata as a concept 
[01:11](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=71) broke into the mainstream and wasn't exclusive to academia so how do they work let's start with the simple one-dimensional automaton an automaton 
[01:24](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=84) consists of a grid of cells each cell exists in any number of states but it's usually two on or off each individual cell is only concerned 
[01:35](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=95) with itself and its neighbors and each advancement of the automaton is referred to as a generation a new generation is created according to rules defined by the creator of the 
[01:47](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=107) automaton and is usually the same for every cell to demonstrate let's go through one generation of the one-dimensional automaton known as rule 110. the rules for this are as follows 
[02:00](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=120) if the cell and both its neighbors are on the cell turns off if the cell in both its neighbors are off it stays off if the cell and its right side neighbor are off but its left side neighbor is on 
[02:13](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=133) the cell stays off otherwise the cell turns on let's look at one state of a 6 cell rule 110 automaton and draw its next generation 
[02:25](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=145) this grid has two active cells the third and the fifth from the left to find the next generation let's start with the first cell this cell is off its left neighbor is 
[02:37](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=157) the cell on the other end which is also off and its right neighbor is off this means that by rule 2 the cell will remain off moving on to the next cell it and its 
[02:48](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=168) left neighbor are off but its right neighbor is on therefore it turns on the next cell is on its left and right neighbors are off so it turns on the next cell is the opposite but it still 
[03:00](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=180) turns on the next cell is the same as the third so it turns on the last cell is off its left neighbor is on but its right neighbor is off so it stays off per rule number three we 
[03:13](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=193) have now created the next generation of this automaton the original generation could be referred to as generation t and this new one can be referred to as t plus one 
[03:25](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=205) now you might be thinking this seems kind of stupid but let's look at it on a much larger scale isn't that neat from such simple rules emerge complex seemingly random 
[03:56](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=236) structures but it isn't completely random it's consistent enough that a man named matthew cook proved in 1994 that this automaton is turing complete meaning it can be used to simulate any 
[04:09](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=249) computation or computer program not all cellular automata are created equal though as most rule sets result in completely repetitive behavior or absolute chaos with few standing above 
[04:21](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=261) the rest like rule 110 or conway's game of life speaking of conway's game of life let's move into two dimensions things change a little bit when we add 
[04:32](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=272) the new axis and it introduces a new question what is considered a neighbor of the cell there are two types of cell neighborhoods the moore neighborhood and 
[04:42](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=282) the von neumann neighborhood the more neighborhood includes diagonals whereas the von neumann neighborhood does not other than that the concept is the same a cell has a state and it changes based 
[04:54](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=294) on the behavior of its neighbors according to a set of rules you've seen conway's game of life before assuredly so i won't show you that instead i'll show you a less popular 
[05:04](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=304) variant of it called brian's brain invented by brian silverman the rules for it are as follows a cell may be in three states on dying or off each cell has eight neighbors 
[05:18](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=318) a cell turns on if it was off but had exactly two neighbors that were on all cells that are on go into the dying state all cells in the dying state turn off 
[05:30](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=330) anyways without further ado let's run the simulation [Music] wow you know i just think that people when 
[06:11](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=371) they say that they you know hate cellular automata they just they don't have context they don't know where it comes from cellular automata was born in a little room at los alamos national 
[06:24](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=384) laboratory just because von neumann couldn't stop thinking about self-replicating robots no one could understand him or talk to him the only way they could communicate 
[06:35](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=395) was with algorithms i think part of the problem is that you can't hear it you have to see it you have to see what's at stake i mean look at these 
[06:44](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=404) fellas look at this spaceship right here he just hijacked the grid he's on his own trip every one of these guys is turning off on or dying and now look this other spaceship he's got his own 
[06:56](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=416) idea and so it's conflict and it's compromise and it's just it's new every time it's brand new every cycle and it's very very exciting [Music] 
[07:10](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=430) unlike my last video cellular automata has applications in many fields most notably chemistry physics and computer science due to their application in physics many 
[07:22](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=442) video games use cellular automata to simulate physics like water a specific example being terraria another popular example is noida which the entire pixel simulation is at its 
[07:36](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=456) core a cellular automaton with each pixel being a cell in cryptography cellular automata can be used as a one-way function since it's nearly impossible to inverse some rule 
[07:48](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=468) sets one example is this pattern in conway's game of life this square is stable meaning it will stay that way for every generation in 
[07:57](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=477) the future as long as it is left alone but this pattern can also be formed by this pattern and its next generation so how can you tell given a generation if this pattern was formed in the last 
[08:09](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=489) generation or has remained stable for thousands of generations you unfortunately can't in chemistry cellular automata has been used to model the bellusov zabutinski 
[08:21](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=501) reaction which if you haven't seen it looks like this and nile red has a cool video on it which you should definitely watch i have actually gone through the trouble 
[08:31](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=511) of implementing this cellular automaton and it looks really really cool so as a reward for those still watching you get to see it the rules for this automaton are as follows a cell exists in n states 
[08:44](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=524) this represents how infected a cell is an example would be 100 where zero is healthy and 100 is completely infected if a cell is completely infected it magically becomes healthy again 
[08:58](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=538) if a cell is between 0 and n then it becomes the average of the values of its neighbors plus a constant g where g is the rate at which the infection spreads 
[09:09](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=549) if a cell is healthy it becomes a weighted average of the number of infected and ill neighbors and that's it i do have to give an epilepsy warning though as it flashes a 
[09:19](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=559) lot so please skip ahead to the time shown if that's a concern stardust on the moon what a night [Music] 
[10:21](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=621) all right isn't that the coolest you've ever seen there are so many more patterns that this automaton produces that i'd love to show you but i unfortunately can't put them all in one 
[10:30](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=630) video so if you'd like to play with it yourself the unity project code is in the description anyways that's all for this video this was originally going to be another 
[10:41](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=641) paltry programming installment but the topic was a little too big for that so it is its own thing now unfortunately my main project has been delayed two weeks due to hardware issues so i put this out 
[10:53](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=653) in the meantime make sure to subscribe below so you know when that video comes out and check out my other socials for updates but i gotta go now so have a great rest of your day 
[11:03](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=663) and i'll see you next time all right all right all right here's one more for the fans [Music] [Applause] 
[11:39](https://www.youtube.com/watch?v=t_HcBAO_Yas&t=699) [Music] uh ah [Music] bye 