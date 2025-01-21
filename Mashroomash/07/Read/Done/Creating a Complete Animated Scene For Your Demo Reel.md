---
URL: https://discover.therookies.co/2024/08/12/creating-animated-scene-demo-reel/
thumbnail: https://discover.therookies.co/content/images/size/w1000/2024/07/scene00-1.jpg
site: "[[The Rookies]]"
date: 2024-09-20
duration: 9
done: true
cover: ""
topics:
  - "[[Characters|Characters]]"
  - "[[Complete scene|Complete scene]]"
---
[[../../../01 Maps/Themes/Article|Article]]
!
# Creating a Complete Animated Scene For Your Demo Reel

In this article, SF Film School student Nayon Park presents "Pinocchio," a demo reel inspired by the 2022 film.

---

In this article, [SF Film School](https://www.therookies.co/schools/sf-film-school?ref=discover-the-rookies) student, Nayon Park, introduces his latest project, "Pinocchio," a demo reel inspired by the 2022 film. Drawing from the heartfelt themes of the film, Nayon's work showcases a detailed process, from sculpting and modeling to texturing and animation. The article delves into the challenges Nayon faced, including achieving a lifelike representation of Geppetto and animating Pinocchio and his companions. If you are looking to create a scene for your VFX and Animation reel, this article may just inspire you to get started!

---

## **Introduction**

I created this demo reel, titled ‘**_Pinocchio_**’, Inspired by the 2022 film of Pinocchio. Before falling asleep, Geppetto wishes upon the moonlight for the wooden puppet, Pinocchio, to become a real boy. While he sleeps, the blue fairy pays a visit. The next morning, Geppetto finds a himself face to face with a living, moving and breathing child Pinocchio. Overwhelmed with joy, they embrace and share their newfound reality and stories.

## **Inspiration**

While looking at the movie poster for ‘Pinocchio’, I imagined how the story would unfold, even though I already knew it. The heartfelt emotions of innocence and earnestness from Pinocchio and Geppetto inspired me to choose this theme. Particularly, Pinocchio’s earnest desire to become human and Geppetto’s endless fatherly love deeply moved me. To express this emotion, I created a portfolio using various character designs, hard surfaces and textures references from the movie. I hope my work conveys the heartfelt message of this beautiful story.

## **Workflow**

I completed this project in the order of modeling, texturing, look development, rigging, layout, animation, lighting, rendering, and final output.

## Geppetto

### Sculpting & Modeling

I started by sculpting this character in [ZBrush](https://www.maxon.net/en/zbrush?ref=discover-the-rookies), beginning with a sphere with references. Then, I used Wrap 4D to transfer topology and texture maps from 3D scan data to my sculpt for the head details. After that, I used Quad draw in [Maya](https://www.autodesk.com.au/products/maya/overview?ref=discover-the-rookies) to adjust the topology to fit the flow of this character's face.



Every step was challenging for me, but the most challenging part was creating Geppetto to look exactly like a real one. Tom Hanks is so famous that people recognise his face very well. Because of this, I made extra efforts to capture his features in detail.

I searched for various reference photos from different angles of the ages when he actually acted and tried to find some unique features. And then, I added all the skin, wrinkles, moles, eye dots, iris colour’s details that only he has to the texture maps, making him more realistic.

The hands of this character were depicted according to the setting of being a woodcarver, with calluses, short nails, and thick finger joints.

### Groom & Clothing

Once I completed the modeling, I started creating the hair. Using the X-gen interactive groom in Maya, I placed guides in the general shape of each part(hair, eyebrows, eyelashes, beard, mustache, peach fuzz, hands) and then adjusted using the modifiers such as noise and sculpt to adjust width, length etc. To make the peach fuzz translucent, I used the ramp texture feature in VrayHairSampler in Hypershade. After connecting Distance along the stand node with the ramp texture node, I applied this to transparency and adjusted the ramp graph.

The clothes were initially created in [Marvelous Designer](https://www.marvelousdesigner.com/?ref=discover-the-rookies) and then finalised in ZBrush for the details. Then, I exported displacement maps and texturing was done in [Substance 3D Painter](https://www.adobe.com/creativecloud/3d-ar.html?ref=discover-the-rookies).

I also created his shoes, accessories, belts in ZBrush and used Quad draw in Maya for topology. Then, I used ZBrush to add details for modeling and textured in Substance 3D Painter and [Photoshop](https://www.adobe.com/au/products/photoshop.html?ref=discover-the-rookies). I mostly used baked maps, masks, and alphas from downloaded textures to depict the effects of time and usage, considering their purpose. Any additional alpha maps or metallic texture maps needed were created in Photoshop or Substance 3D Painter.



### Rigging & Animation

Next, I set up the rigging using Advanced Skeleton in Maya, and then, I used the paint mode in ‘Painted skin weight tool’ to paint the weights on the relevant areas, making the movements appear more natural. Afterwards, I positioned the cameras to set up the layouts for animation.

Following the reference shots that I acted, I created the characters animation using Stepped tangents for blocking, Auto/Weighted Tangents for splines, and I also used Blend shapes for additional animation. I then exported the alembic animation cache for clothing simulation. After finishing the clothing simulation in Marvelous Designer, I exported the Alembic (Ogawa) animation cache and attached his accessories to the clothes using rivet constraint in Maya.

To enhance the detailing of Geppetto's surprised expression, I used layered textures in Maya. Additionally, I emphasised wrinkles using ZBrush and Substance 3D Painter. Afterwards, I exported texture maps to blend with the base textures of the default expression. Using a set driven key, I adjusted the amount in the surprised expression to seamlessly integrate the textures.

## Pinocchio

### Sculpting & Modeling

I began by sculpting the character in ZBrush starting from a basic sphere, then refined the modeling's topology in Maya using a quad draw. Returning to ZBrush, I added some details and also made accessories like stitches, buttons, an IMM brush for the details on his vest.



Using Maya and ZBrush, I created a gloves base mesh for this character. I used curves to shape the knit stitches, then converted them into curved polygons and added a noise texture to make the yarn appear layered in Maya. Next, I used the MASH option in Maya to create the knitting for the gloves. To achieve a natural weave, I added MASH Random in the editor. I also added fine hairs by creating maps in Photoshop and using MASH for the placement.

To achieve detailed representation of the wood texture on Pinocchio, I mainly used the Wrap projection in Substance 3D Painter.

### Rigging & Animation

Rigging was done using Advanced Skeleton.

Based on the reference shots I acted out, I animated this character using stepped tangents for blocking, auto/weighted tangents for the spline animation, and blend shapes for additional animation details. Specifically, I used a V-ray Decal in Maya to make the eyes move according to the basic shape of Pinocchio's eyes.

## Jiminy Cricket

### Sculpting & Modeling

I began by sculpting this character in ZBrush starting from a basic sphere and also used Maya for the all topology using a quad draw.

I added details and textures using ZBrush and Substance 3D Painter. I also created the hair of his hat using the X-gen interactive groom.

### Rigging & Animation

I proceeded with Jimmy's rigging and animation using the same process as Pinocchio.

I created a low-poly cage modeling for character's rigging, then used 'bind skin' with joints. I painted the skin weights afterward. Next, I connected the original clothes I made with the joints using ‘bind skin’, and transferred the skin weights from the previously painted cage to the clothes using 'copy skin weight' for each. For buttons or accessories, I added joints and used parent constraint, then used 'copy skin weights' from the cage to each again.

## Lighting and Cameras  

I aimed to create an overall warm and cozy lighting ambiance, referencing appropriate sources to achieve this. I arranged cameras for night and morning scenes to set up the layout.

Then, using [V-Ray](https://www.chaos.com/?ref=discover-the-rookies) Dome, Rect light, and Fog, I set up the basic lighting. I gradually added lights to each scene, adjusting them to find colors and angles that would effectively highlight the characters as I rendered each scene. In V-Ray Frame Buffer, I set OCIO and adjusted white balance and filmic tonemap. In addition, I selected 'ACEScg' in Tone mapping space to create warm and cozy lighting ambiance.

I positioned the camera and in each scenes and adjusted Focal length. To achieve the desired depth of field, I set it as a physical camera. Afterwards, I adjusted the F-number and ISO for the physical light settings. During the character's animation, the focus changed, but I resolved this by using the V-Ray Camera Physical Focus Distance to keep the focus fixed on the center of the character's eyes.

## Props

I made all props to real-life scale based on references in Maya and used ZBrush to add details for modeling, textured in Substance 3D Painter and Photoshop. I mostly avoided using brushes for props in Substance 3D Painter, instead layering baked maps, masks, and alphas from downloaded textures to depict the effects of time and usage, considering their purpose. Any additional opacity or metallic texture maps needed were created in Photoshop or Substance 3D Painter.
`````col
````col-md
flexGrow=1
===
![[prop1-2.jpg]]
![[prop3-1.jpg]]
````
````col-md
flexGrow=1
===
![[prop2-1.jpg]]
![[prop4-1.jpg]]
````
`````

## Rendering and Final

I rendered a representative frame for each scene using both ‘progressive’ and ‘bucket’ settings using V-Ray in Maya, taking time to find the settings that best suited my project.




Lastly, I worked on path compositing in [Nuke](https://www.foundry.com/products/nuke-family/nukex?ref=discover-the-rookies). I composited animations of the flying fairy by blending various downloaded sources in Nuke. After extracting camera animation caches and plane OBJ from each scene, I adjusted the speed, size, intensity, and defocus of floating dust particles. Then, I integrated these dust particles into the final composite. Additionally, the spreading effect of fairy dust utilised Optical effects in After Effects, and finally, I adjusted the overall colour scheme in After Effects to complete this project.

### Prop References

## **Final Thoughts**

My journey in creating this project inspired by the story of Pinocchio has been a deeply rewarding experience. Every step, from story development to video editing, was a great challenge. I feel like I learned and grew a lot during this time.

Thank you for taking the time to read through this article. I also want to thank the Rookie Awards for giving me the opportunity to feature the process of my work in an article.

Feel free to reach out if you’d like to connect, and check out more of my work via my Rookies profile [here](https://www.therookies.co/u/annpark?ref=discover-the-rookies), where all my additional social channels are linked.