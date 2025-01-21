---
cssclasses:
  - daily
  - page-black
  - Wednesday
date: 2024-07-20
topics:
  - "[[BRDF|BRDF]]"
  - "[[BSDF|BSDF]]"
  - "[[PBR|PBR]]"
q-type: article
q-data:
  leech-count: 1
  due-at: 2024-07-24T18:00:00.000Z
---
[[../../07/YouTube/Study/The Secret Behind Photorealistic And Stylized Graphics|The Secret Behind Photorealistic And Stylized Graphics]][^1]

[^1]: ![[../../07/YouTube/Study/The Secret Behind Photorealistic And Stylized Graphics#^546845|The Secret Behind Photorealistic And Stylized Graphics > ^546845]]

![[../../07/YouTube/Study/The Secret Behind Photorealistic And Stylized Graphics#^012a40|The Secret Behind Photorealistic And Stylized Graphics > ^012a40]]
#### The rendering equation

# The main problem

> How do you determine how much light is going out in a specific direction - This is the fundamental problem of computer graphics, as the resulting light ray from this process becomes the color of a pixel in the final image render.

While we can model each surface individually, there is one thing that connects them all - *the fact that light goes in and light goes out*.

#### The rendering equation:
> The amount of **outgoing light** at a point on a surface is equal to the **emitted light** plus the **reflected light**.[^2]

[^2]: 1986, David Immel and James Kajiya introduced a general equation to describe the expected behavior of light surface interactions

The part we mostly care about is the **reflected light** portion, because **emissive light** is usually just an additive constant when we want to model something like a light bulb or anything else that produces light.
If we wanted to make that fancier, then we would make modifications to that portion of the equation, but otherwise we can kind of just ignore it, since most surfaces are not emissive anyways.

> Without emission, the equation reduces to just the **outgoing light** being equal to the **reflected incoming light**.

Now we need to convert this abstract idea into math.
#### Variables:
##### X - position in space
##### Wo - the direction of outgoing light (towards the camera)
##### Wi - the direction of incoming light ^18dc42
##### Li - color of that incoming light
##### Lo - outgoing light
##### Li - incoming light

> Now we have *Lo = Li*
`````col
````col-md
flexGrow=1
===
![[05 Notes/Excalidraw/The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^area=O-2X4bw-k-ugrG-AY76cg]]
````
````col-md
flexGrow=2
===
![[Screenshot_20240720_192538_com.huawei.himovie.overseas.jpg]]
````
`````
- Imagine a sphere in a black void with absolutely no light except a single directional light source colored white. Well  obviously not right. We are getting what we asked for though. Each point of the sphere is outputting the **color** of the light source without  regard to anything else. 
- If we look at the real world though we can see that a directly lit sphere looks a bit different, it's bright as where the surface can see the light and slowly gets darker, until the surface faces away from the light. Clearly there is a relationship between the *direction* the surface faces and the *amount of light* reflected at that point. So we need a new variable.

##### n - surface normal
- The vector that points orthogonal to the surface - . 
- For a flat plane this Vector points directly up. 
- If it's directly overhead the **normal**, then we should expect a full strength **reflection**, but as the [[The Secret Behind Photorealistic And Stylized Graphics.Note#^18dc42|light vector]] moves away from the normal below a ° angle, clearly the light should no longer be able to reach that point and there should be no reflection as the surface itself is blocking the view.
`````col
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=U2hlG8bu|surface normal]] 
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=aEOJbf1L]]
````
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=mhy7fom2| the normal vector|220]]
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=p8sSFw1Y]]
````
`````
##### θi (cos) - function that takes in an angle and returns 1 when the angle is 0 and 0 when the angle is 90°.
- So what we need is the angle between the [[The Secret Behind Photorealistic And Stylized Graphics.Note#n - surface normal|normal]]  and the [[The Secret Behind Photorealistic And Stylized Graphics.Note#^18dc42|light direction]] which we call the *incident angle* to put into cosine.
- But we can skip that entirely by making use of a linear algebra operation *The dot product*. There are two ways to calculate *The dot product*:
	- By multiplying each component of the vectors and adding them up
	 - By multiplying the magnitudes (*|V1||V2|*) of the vectors by the cosine of the angle between them




Since our [[The Secret Behind Photorealistic And Stylized Graphics.Note#^18dc42|light]] and [[The Secret Behind Photorealistic And Stylized Graphics.Note#n - surface normal|normal]] vector are normalized, their magnitudes are equal to 1 and any number multiplied by 1 is the same number.

Which means *The dot product* will be equal to just the cosine of the angle.
So if we use this , then through the equivalence of the two definitions we get what we need - *cos θi* 
> Lo = Li cos θi

We can write this as either *The dot product* of the two vectors or as the *cosine of the incident angle*. It depends on who's writing the equation. Wikipedia uses *the do product* but Disney uses the *cosine*.

##### BRDF - bidirectional reflectance distribution function 
- Placeholder function that describes how much light is reflected at a specific point.
For instance  we're only taking into account one [[The Secret Behind Photorealistic And Stylized Graphics.Note#^18dc42|light direction]], but if we wanted to get the true amount of incoming light out of point, we would need to check every single possible incoming direction in the surrounding hemisphere.
- Which is how we would get *Global illumination* and soft shadows.

- We model this using an *indefinite integral* because there are technically an infinite amount of incoming directions. In real-time rendering though, we're just going to compute one or two light directions and ignore the integral. 
- Lastly we bring back our *emissive light* term from earlier and we have derived the actual rendering equation.


This version is a bit outdated as it doesn't account for a number of other aspects of light behavior those fall under **BSDF** ([[The Secret Behind Photorealistic And Stylized Graphics.Note#BRDF - bidirectional reflectance distribution function|BRDF]] is a part of it too)[^3]:

[^3]: It's called bidirectional because the output should be the same if the incoming and outgoing directions are swapped. This is known as the *Helmholtz Reciprocity Principle*.
#### BSDF - Bidirectional Scattering Distribution Function:
- **Transmission** of light - observed in translucent surfaces like glass or water
- **Subsurface scattering** of light - observed in surfaces like Jade or foliage
- **Polarization** of light - which is hard to explain
- **Phosphorescence** - which is when a surface slowly releases light it absorbed earlier. Like glow-in-the-dark  stars
- **Light interference** - which is when the wave of light is interfered with, just like other waves can be interfered with 
- **Fluorescence** - which is like phosphorescence but the glow ceases immediately after radiation exposure stops 
- **Non linear light** effects - such as two photon absorption
- **Doppler effect** - also applies to light but only when objects are traveling close to the speed of light, so we can probably just ignore this one

##### BRDF rules:
1. Law of conservation of energy
2. Helmholtz Reciprocity Principle[^3]
`````col
````col-md
flexGrow=1
===
![[Screenshot_20240720_211812_com.huawei.himovie.overseas.jpg]]
````
````col-md
flexGrow=1
===


````
`````

#### The simplest BRDF in the industry
From theory we know that when a light ray collides with a surface it's going to penetrate it and then get scattered at many angles. For simplicity's sake we assume that the entry and and exit point of the light ray are the same.
`````col
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=zrrJZ_lLL7hAU8Np1ZkfD|Diffuse reflection|310]]
````
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=K8u17Ty5I8b2JAYNcglQx|Lambertian reflectance]]
````
`````
######  -  when light is scattered all around from the point of intersection.
######  - is when the surface diffusely reflects equally in all directions.
##### Lambertian Diffuse BRDF
When a light ray penetrates a surface a certain amount of it is going to be absorbed, while the  light remains. 
For instance, if a light ray representing the color white collide with an Apple, the Apple surface will absorb a large portion of the green and blue light of that ray while  the remaining red, giving the Apple its red appearance after the reflected light enters our eyes.
`````col
````col-md
flexGrow=1
===
- The **RGB** color model allows us to represent this mathematically - if the color of the surface is red then multiplying it against white gives us red, as the green and blue were reduced to zero per the multiplication. 
- Replacing the red with a very variable that describes the base color of the surface - we have derived the most basic of BRDFs - **the Lambertian Diffuse**.
- Technically there should be a divide by pi here but that's usually omitted in most game engine software
> But if we try to model something shiny like plastic or polished wood we clearly can't, so we need to add more functionality to our BRDF
````
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=Ir8iv6SP|apple]]
![[Screenshot_20240720_212502_com.huawei.himovie.overseas.jpg]]
````
`````
##### Phong Reflection BRDF
###### 

- diffuse reflections are just half of the equation when a light Ray hits a surface not all of it will be absorbed and Scattered a certain amount of it will be directly reflected.
- specular highlights are a bit different from diffuse, while diffuse reflectance scatters at many angles, specular reflectance scatters in a much smaller range, so the direction we view the object from actually matters when it comes to seeing these, as well as the light direction.
- We should only really see specular highlights when the direction of the reflection aligns closely with the view direction, as that's when the reflected light would be mostly bouncing into our eyes.
`````col
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=cLlKUWepq_WA5gQy46Uca|Specular reflection]]
````
````col-md
flexGrow=1
===
![[Screenshot_20240720_212850_com.huawei.himovie.overseas.jpg]]
````
`````
Not all specular highlights are  created equal:
- Very shiny objects have tiny pinpoint highlights, requiring a more perfect reflection alignment to be visible 
- While other more rough objects have a wider range of specular  scattering angles
So we can model this by adding an exponent variable that controls how wide the specular lobe is. This specular BRDF is known as the Phong Reflection BRDF.
##### Blinn-Phong specular BRDF
If we take a look at our vector diagram, the [[The Secret Behind Photorealistic And Stylized Graphics.Note#n - surface normal|normal]]  vector is also the halfway vector between the [[The Secret Behind Photorealistic And Stylized Graphics.Note#Wi - the direction of incoming light 18dc42|light]] and *reflection* vectors, so we can optimize the [[The Secret Behind Photorealistic And Stylized Graphics.Note#Phong Reflection BRDF|Phong Reflection BRDF]] model by calculating the *halfway vector* between the [[The Secret Behind Photorealistic And Stylized Graphics.Note#Wo - the direction of outgoing light (towards the camera)|view]] and [[The Secret Behind Photorealistic And Stylized Graphics.Note#Wi - the direction of incoming light 18dc42|light]] vectors and taking *the dot product*  between the *half* vector and the **normal** vector, removing the need to compute the reflection.[^4]

[^4]: This optimization was derived by Jim Blinn in 1977 and the resulting BRDF is known as the Blinn-Phong specular model
-  Combining Blinn-Phong with the [[The Secret Behind Photorealistic And Stylized Graphics.Note#Lambertian Diffuse BRDF|Lambertian Diffuse BRDF]] by adding them together gives us what used to be the most common lighting model in video games and other real-time rendering pursuits.
`````col
````col-md
flexGrow=1
===
- It enables us to model a very wide variety of materials in a way that feels  physically plausible. Smooth plastic has the expected specular highlights now, the polished wood actually looks polished and we could model numerous other materials from shiny to matte. No longer limited to just diffuse reflectors.
> But *Lo = 1.42* is greater than *Li = 1*
````
````col-md
flexGrow=1
===
![[Screenshot_20240720_212940_com.huawei.himovie.overseas.jpg]]
````
`````
- It breaks the [[The Secret Behind Photorealistic And Stylized Graphics.Note#BRDF rules|laws of physics]] and generates more energy than was received 
- It's also not  bidirectional[^3]  so it's not correct to refer to it as a  BRDF.
## Physically based rendering
Light operates and reflects at a microscopic level, so if we want to be physically accurate with our light predictions, we're going to have to think at that scale. 
##### Microfasets
Physics has found it easier to think about the *roughness* of a surface rather than the *shininess* metric that we've been using so far.
- A perfectly smooth surface like a mirror is going to look like a flat plane at the microscopic level.
`````col
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=VbFVQYN583VZG7CgHKLCD]]
````
````col-md
flexGrow=1
===
![[The Secret Behind Photorealistic And Stylized Graphics.excalidraw.md#^group=2CTeaZIjhi9XakqdaE-lC|Microfasets]]
````
`````
- But a very rough surface like a concrete - is going to be composed of microscopic grooves of varying slope and height.
- The greater the variety - the rougher the surface.
- These little microscopic surfaces are called microfacets and they average out to the surface [[The Secret Behind Photorealistic And Stylized Graphics.Note#n - surface normal|normal]] we've been using thus far.
- It's these microfacets that light actually reflects off.

- We can model the roughness of our surface as the probability that the light hits a microfaset that points in the direction of perfect reflectance.
###### Fresnel Equations
A phenomenon in which surfaces demonstrate greater reflectivity when viewed at grazing angles. For instance: the hallway floor becomes more mirrorlike towards the distance, as the angle of incidence decreases and another popular example is the ocean specular abstractly.
> The Fresnel Equations term describes how  much light is reflected based off the view angle.
###### Geometric Attenuation
The scenario in which microfacets can block each other, reducing the chance of a reflection and causing a phenomenon known as *Off Specular Peak* 
- Where the peak reflectance is achieved at a lower angle than otherwise predicted by the *Fresnel* term.
> The *Geometric Attenuation* term counteracts the *Fresnel* for very rough surfaces.
#### Microfacet BRDF
These three abstract terms are multiplied with each other and divided by the denominator. This completes the Microfacet BRDF for specular highlights
`````col
````col-md
flexGrow=1
===
![[Screenshot_20240720_213540_com.huawei.himovie.overseas.jpg]]
> When we say something is physically based that means it's derived from [[#Microfasets]] theory
````
````col-md
flexGrow=1
===
![[Screenshot_20240720_213118_com.huawei.himovie.overseas.jpg|200]]
````
`````
# Disney's BRDF 
`````col
````col-md
flexGrow=2
===
![[Screenshot_20240720_213646_com.huawei.himovie.overseas.jpg]]
````
````col-md
flexGrow=2
===
![[Screenshot_20240720_213844_com.huawei.himovie.overseas.jpg]]
````
````col-md
flexGrow=1
===
![[Screenshot_20240720_214630_com.huawei.himovie.overseas.jpg]]
````
`````
#### Diffuse
1. Color of the surface - they use Burly[^5] Diffuse or the Disney Diffuse. It is an extension of the [[The Secret Behind Photorealistic And Stylized Graphics.Note#Lambertian Diffuse BRDF|Lambertian]] model that takes into account [[The Secret Behind Photorealistic And Stylized Graphics.Note#Fresnel Equations|Fresnel reflectance]] which is dependent on the second  parameter.
	> But *1.0022* is greater than *1* 
	> It breaks the ==[[The Secret Behind Photorealistic And Stylized Graphics.Note#BRDF rules|laws of physics]]== and generates more energy than was received
2. Surface roughness - Schlick Fresnel approximation[^6]
3. Subsurface scattering - the Disney BRDF provides a secondary diffuse lobe for artists that is an approximation of the Hanrahan-Krueger's subsurface BRDF . But it is not a replacement for genuine subsurface scattering. The diffuse does not blend into and illuminate shaded areas like genuine subsurface scattering. Subsurface parameter Blends between the Disney diffuse and the subsurface scattering approximation allowing for more artistic control.
4. Sheen strength- which is an  additive lobe based on the angle between the light and *half vector* such that when the light is at very grazing angles, there is a slight sheen to the surface observed on materials like cloth .There is no physical basis for this, it's just an additional artistic parameter which is accompanied by the next parameter 
5. Sheen tint -  tints the sheen towards the color of the surface. 
#### Specular
6. Anisotropic
7. Specular strength 
8. Metallic
9. Specular tint
10. Clearcoat
11. Clearcoat gloss




[^5]: Invented by Brent Burley
[^6]: Invented by Christophe Schlick in 1994







