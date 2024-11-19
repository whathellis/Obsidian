---
date: 2024-07-19
cssclasses:
  - daily
  - Wednesday
  - page-grid
  - page-gray
topics:
  - "[[Animation Principles|Animation Principles]]"
  - "[[Smears|Smears]]"
q-type: article
q-data:
  leech-count: 1
  due-at: 2024-07-24T18:00:00.000Z
---
[[../../07/YouTube/Animation/What Are Animation Smears REALLY For - Doodley|What Are Animation Smears REALLY For - Doodley]]
## What are Smears

>  Smear - animation equivalent to a motion blur

- Create funny looking frames if you'll pause at the right time
- Can connect 2 key poses without a lot of frames

`````col
````col-md
flexGrow=1
===
![[Videoframe_20240719_120033_com.huawei.himovie.overseas.jpg]]
````
````col-md
flexGrow=1
===
![[Videoframe_20240719_120057_com.huawei.himovie.overseas.jpg]]
````
`````

>  Smears make fast movement more readable and less stiff
### Classic smears
#### If you only have a few frames 
##### You still need:
- anticipation[^1]
- action[^2]
- overlapping action[^3]
- saddle[^4]
`````col
````col-md
flexGrow=1
===
But the movement might bee too big or too fast to include all these poses, so you'll put a **smear** in the middle.
It makes the action *readable*.
````
````col-md
flexGrow=1
===
![[Videoframe_20240719_120248_com.huawei.himovie.overseas.jpg]]
````
`````

[^1]: ![[./Animation Basics in 14 Minutes (6 Big ideas for beginners).Note#4. Anticipation|Animation Basics in 14 Minutes (6 Big ideas for beginners).Note > 4. Anticipation]]
[^2]: 
[^3]: ![[./Animation Basics in 14 Minutes (6 Big ideas for beginners).Note#5. Overshoot|Overshoot]]
[^4]:
#### Even if you have a lot of frames:
- Fighting games are usually 60FPS, but they use smears. 
	Without smears, more frames could be busier and harder to understand.
- When characters move unrealistically fast.
	It would be impossible to animate it normally in few frames.
	This is usually where [[What Are Animation Smears REALLY For - Doodley.Note#Multiples|Multiples]] camming.

### Multiples
>  Multiple smear - drawing extra parts of the character to show a fast rapid action


#### Types:
- **Arc** - to make smth super readable
- **A straight path** - to give a fast action a lot of power
- **Scattered in a bunch of places** - to show lots of quick movements without needing extra frames ^98950d
#### They can be:
- After images like in *motion blur* photography.
- But they can go a step further:
If you need a part of a character visible for just one more frame than you have available, you can create a *fake frame* with a multiple. In motion it'll seem like 2 frames.

> The extra *fake frame* with a **multiple smear** helps viewer see and focus on an important part of the character.
### Drag smears
Smears can also make an animation feel less stiff.
Animation has lots of techniques to keep things loose, those don't distort[^5] the character:
- **Squash and stretch** - maintains the scenes of volume by stretching outwards equal to how much you squash inwards and vice versa. The mass of the character stays consistent. ^f924a5
- **Drag** - can pull parts of the character behind the main action, so they don't feel too stiff or static. ^3422ed

However, you can push both of those principles with very saddle **"drag" smears**[^6]. Which distort the character for just a frame or two, to really extenuate both [[What Are Animation Smears REALLY For - Doodley.Note#^3422ed|drag]] and [[What Are Animation Smears REALLY For - Doodley.Note#^f924a5|squash and stretch]].

.Depending on who you ask: These are not really smears and just very exaggerated extensions of those principles.
.-Doodley: But  they distort the character in the exact same way smears do.
.-Doodley: If you compare these two, they seem like off-model errors.



[^5]: "Distort" as in becoming off-model / looking "incorrect". Squash and stretch exaggerates while staying on-model.
[^6]: Not an "official" term.

## How to implement them

### Classic smears
> Those simulates motion blur (i.e. elongated inbetweens, the most common type)


1. - [8] They should appear only for 1-2 frames maximum
	- Focus more on before and after of the smear:
		1. Use a really strong pose with a lot of anticipation.
		2. Smear for just 1-2 frames.
		3. And then a big reaction afterwards, with every other part of the character following through.
			Hair capes and other body parts can catch up afterwards, to give the smear more weight after it's already gone.
	- Having a smear appear for anything more than 1 or 2 frames makes the smear feel like it's part of the character. Like they are made of liquid. Which can work if that's what you want.
`````col
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (7).jpg]]
````
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (8).jpg]]
````
`````
2. - [8] They should follow very specific A to B path (Ignore these for other types of smears / multiples).
	- It follows the same idea as arcs[^7].
	- You have 2 key poses.
	- The smear links them together in a clear easy to see path.
		- Keep the details and shapes simple.
		- Keep the path clear and obvious.
		- Whether it's an arc or a straight line, make sure they are linked together.
		- Avoid the gap between the smear and the other two frames.
		- If the pas is not clear, the smear ends up being muddled and busy. Kinda worse than nothing at all.

These are classic smears, but the rules apply a little differently for other types of smears

[^7]: Classical animation technic.
### [[What Are Animation Smears REALLY For - Doodley.Note#^98950d|Speed multiples]] 
You can basically ignore these for speed multiples.
- They usually appear for more than a few frames.
- They are often used for a lot of little actions rather than one big action.
- You can use them in the same way you wold classic smears - as an extra frame.

### Anime style smears
- They usually seek to emulate motion blur closely.
- Erasing parts of the line art.
- Adding speed lines for several frames.
- Often the motion is drawn entirely jittery - to give it a sense of uncontrollable speed.

### Common guidelines for 3D
`````col
````col-md
flexGrow=1
===
#### Experiment:
- Roughly draw what you want smear to look like
- See if it feels good
````
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (10).jpg]]
````
`````
#### Smears in the video:
- Lattice Deformer (turning on and off via envelope)
- Flat piece of geometry - Pure black lines for speed lines
- Copy posed character and delete irrelevant geometry - for a [[What Are Animation Smears REALLY For - Doodley.Note#Multiples|multiple]]
- Use blend-shapes and sculpt the geometry the way you want
- Use any geometry forms
`````col
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (6).jpg]]
![[What Are Animation Smears REALLY For (11).jpg]]
````
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (4).jpg]]
![[What Are Animation Smears REALLY For (3).jpg]]
````
````col-md
flexGrow=1
===
![[What Are Animation Smears REALLY For (2).jpg]]
![[What Are Animation Smears REALLY For (1).jpg]]
````
`````




>  You can basically use whatever you want as it's only for one frame. You don't need anything complicated.




