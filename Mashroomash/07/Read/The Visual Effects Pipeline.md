---
URL: http://www.andrew-whitehurst.net/pipeline.html
thumbnail: 
site: "[[]]"
date: 2024-09-20T11:45:08
duration: 14
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[../../01 Maps/Themes/Article|Article]] 
# The Visual Effects Pipeline

I get asked a lot of questions about how a VFX studio is structured and what each department does. This not entirely surprising as there are many departments with a great deal of interdependence and they often have names which are unhelpful to the layperson. What I'm going to try and do in this article is to go through the stages of production, what they mean and then look at each department in a facility, where they fit into the schedule, what they do and who they deal with. Let's get started:

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0001.jpg)  
### An empty slate

This blank canvas represents the cycle of a film, from earliest days on the project on the left to final output on the right. There are three key phases of any film's production so let's get them blocked in first.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0002.jpg)  
#### Pre-production

Pre-production is the first stage of getting a film made and is characterised by all the work that is done before the shoot on set or location occurs. This can vary from a few weeks to over a year depending on the show.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0003.jpg)  
#### Production

Production is the actual shooting of the film. Much work is done by VFX on-set and back at the studio whilst the film is actually being shot. Shoots can last from a couple of months to over a year.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0004.jpg)  
#### Post-production

After the project has finished being filmed it enters post-production. This is the phase where the majority of the VFX work happens and when there is the majority of contact with the client. It is also during this time that the edit, music and sound are added.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0005.jpg)  
### Research and Development

R and D is one of the key departments in any large visual effects house. Most projects will require tools to be written that either make something that's already possible go faster or more efficiently or tools for things that did not previously exist. It is in the nature of visual effects to always push the boundaries of what is possible with the technology and audiences crave more and bigger effects year on year. There is no way for a piece of off the shelf software like Maya or Nuke to be able to handle all these requirements and so it is down to an R and D department, made up of programmers, scientists and mathematicians to realise those new tools. The tools are either written as plug-ins for exisiting software, like Maya for example, or as stand-alone programs. There may be a small R and D department assigned to each show but in general it is a resource shared by the whole company as a tool written for one show will often prove useful on another.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0006.jpg)  
### Tests

Part of the process of convincing clients to place work with a facility is through the production of tests demonstrating either a potential look, style or piece of technology that they may want to use in the production of actual sequences on the film. Tests are done as proof-of-concept pieces to give the client confidence that what they want to achieve is possible. Tests are generally done by very experienced artists as they are often highly experimental and complicated with tools needing to be written on the fly by the team doing the test. Once the work is won the process of building the models can begin.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0007.jpg)  
### Modelling

Modelling will generally begin in pre-production because often low-res models will be needed for pre-visualisation and tests. It is also possible that the client will supply drawings or clay models of elements they want to be created in CG. These models and sketches are used to build totally faithful CG reproductions that can be used in shots. As you can see the modelling phase continues through into the start of post-production but most shows will aim to have built everything they need by the time they start actually producing finished shots. Models will be produced at several quality levels, very high resolution models for final renders, medium quality for animation and low quality for pre-visualisation:

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0008.jpg)  
### Pre-visualisation

Pre-vis is a process of taking the story-boards or script description of a scene and then blocking out the action in 3D using low-resolution models and textures. The idea is to take the story-board into 3D so that the director can get a better idea of how the sequence will work and so that camera moves and set-ups can be experiemented with before committing to an expensive on-set shoot. The pre-vis will usually be done by animators and will be rendered at low quality. Several versions will be produced and presented to the clients before the final flow of the sequence is established. Often the pre-vis will be used only as a guide on set so the shots as filmed may differ greatly from the inital pre-vis although sometimes it will match shot for shot, framing for framing, action for action.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0009.jpg)  
### Reference photography

Once the actual shoot begins it is usually the case that a representative of the VFX company will be on-set when any sequence they will eventually be working on is shot. Usually it will be the VFX supervisor, CG supe or 2D supe who will go on set as they will have the best overall view of how the project is to be run back at the studio. As well as offering advice on VFX set-up when it is asked for, the on-set representative will take as many photographs as possible. These will be used for modelling reference, texture reference, lighting reference and possibly elements for matte paintings. The idea is capture as much visual information about the shoot so that anything can be reconstructed later in CG if needed.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0010.jpg)  
### LIDAR or cyberscan

As well as reference photos, 3D digital scans will also often be made of key sets, props and actors. LIDAR is a laser-based 3D scanning device that can create highly detailed models of buildings or environments. Samller objects will be scanned using a similar device. The models produced by these machines are usually incredibly dense and often quite artifact heavy; they may have many millions of polygons. A modeller will always build the render, animation and pre-vis model from scratch using the LIDAR as reference. Having an accurate scanned 3D model to base the render-geometry on ensures that CG objects will always line up perfectly with their on-set counterpart.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0011.jpg)  
### High dynamic range environment photographs

As well as taking general reference pictures the on-set representative of the VFX house will take high-dynamic range photographs of each environment to enable the lighting TDs to use image-based lighting techniques when lighting the shots. These photos will generally be taken in the form of two sets of 180 degree apart fish-eye photographs of the scene. Each view will probably be photographed about five times at different shutter speeds to get as much of both the shadow and highlight detail as possible. These sets will be combined into a single, floating point lat-long style map for use by lighting and look-development artists back at the VFX facility.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0012.jpg)  
### Film scans

Once the shoot has finished and the edit begins the actual takes of each shot that will be used in the film are selected and then scanned by the client. Most film is scanned at 2K, or 2048x1556 pixels if the film is shot on Super 35mm. Each frame is scanned as a separate high dynamic range image to preserve as much detail from the original negative as possible.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0013.jpg)  
### Technical grade

Once the scans are delivered to the VFX house a technical grade is often done. Grading is a process whereby colour and exposure changes are made to the scanned frames. The purpose of a technical grade is to get all shots in a sequence to have the same overall look and feel so that there are no noticeable jumps in brightness or colour changes when the shots are viewed together as a sequence. Creative grades where the finished "look" of the film is established will be done by the director of photgraphy in colaboration with a colourist in a DI (Digital Intermediate) suite, not by the visual effects house. The technical grade is not creative, it's just there to get everything looking similar before work begins on the shots.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0014.jpg)  
### Plate preparation

Because most movies are still shot on film it is usual for dust spots and developing chemical patches to be present in the scanned frames. It is pretty much impossible to keep a piece of negative completely clean and so a team of compositors will paint out any scratches or dust that appears in the scans. This process is often called dust-busting.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0015.jpg)  
### Rigging

Once models are completed they need to be rigged. Rigging is a very technical task requiring an engineer's understanding of how objects move and interact. Creature rigging is especially difficult as layers of bone, flesh and skin need to be simulated by the rigging process. Once a rig has been created it is tested by animators who try and break it, then a new, revised, rig is created based on the results of the testing phase. Rigging may well continue throughout the animation cycle as better and more refined rigs enable ever greater results from the animators. As well as animators requiring rigged elements, they are also required when match moves are needed in a project.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0016.jpg)  
### Camera tracking and match-moving

Once the scanned film has been delivered and rigged models of all the elements exist it is time for the tracking department to go to work. The first thing to be done will be the production of a camera track. This will be done with a piece of 3D tracking software like Boujou, 3DE or PFTrack. On set, the lens measurements will have been taken so that the correct focal length can applied to the CG camera. Often it will require manual tweaking of the output of the tracker to finesse the camera move into something which locks perfectly with what the real camera did on set.

Once an accurate camera track exists any match moving or body tracking will be done. A body track is an animated CG character or object which perfectly mimics what the on set equivalent did. You may want a body track if you need to stick a CG element to an on-set character, for example adding a digital tail to Hellboy. In order to do this, a CG model of Hellboy will be animated so that he perfectly lines up with the photographed actor on every frame. It is then possible to create the digital rendered tail element and stick it to the body-track knowing that when it is composited it will appear to be stick to the real actor. Juniors who aspire to be TDs or animators often start out in camera and match-moving.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0017.jpg)  
### Animation

Animation is the process of taking the modelled, rigged elements and bringing them to life. Usually this means creatures or characters but it could be a vehicle or anything else that moves. Animators will tend to work with medium-resolution models, they need to be detailed enough that they can be positioned accurately but not so dense that the animators work-station slows down while they're trying to work. Keeping a loose, light workflow enables an animator to craft a natural looking performance. Animation versions will be presented to the client as grey-shaded playblasts for critique and further revision will be made based on these comments.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0018.jpg)  
### Effects animation

Effects animation refers to anything involving simulation. These will generally fall into one of three catergories, particles, rigid-body dynamics and fluids. The effects TD will pick up the camera and any hand animated elements plus a CG version of the environment. They will use this scene to provide the basis for their simulations. For example the fire on Liz Sherman in Hellboy 2 is a fluid simulation. As well as a camera track, Selma Blair's performance was recreated in a rough form by a match move artist so that there was a CG representation of her in the scene. The effects TD can then emit fire fluid sims from the Liz geometry and use the same geometry as a 3D matte when rendering out the finshed fire simulation. This ensures that we cannot see fire that would be behind her and helps the compositor sit the flame into the shot over the real actor's performance.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0019.jpg)  
### Texturing

Once the models are finshed they need to have texture maps both for colour and for fine detail and texture that it isn't sensible to try and model like pores, wrinkles and so on. Using the reference photographed on set a texture painter can create maps for diffuse colour, specularity as well as displacement and bump maps. These maps are often extremely detailed, sometimes 8K in resolution if the digital camera is to get very close to the model.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0020.jpg)  
### Look Development

Look development is the phase where the texture maps are used with shaders and lights to determine the final look of the finished model, Shininess, reflectivity, roughness and so on will be tweaked by the look-dev artist until a perfect match with the on-set version (if one exists is achieved). For objects where no real version exists for comparison it will be down to the VFX supervisor and the director to decide what is correct. Look developers will often work with R and D if a new specific shader is required for a particular effect. Some look-dev artists write their own shaders.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0021.jpg)  
### Lighting and Rendering

Once the animation and look-dev has been approved the lighting artists can begin rendering the finished CG. They will use the shader settings supplied by look-dev and the HDR lighting maps that were shot on set but will often add more CG lights to add accents or enhancements as each shot requires, e.g. a little rim light or eye glint light. Lighters will render the CG passes and then do a basic composite of their CG over the scanned film plate to test that their lighting enables the CG object to feel like it is in the filmed environment. Once the supervisor agrees that the lighting works the CG can be passed onto a compositor for proper integration.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0022.jpg)  
### Rotoscoping

It will often be necessary to put a digital element behind a real filmed element in the plate photography. For example imagine a character on set walking in front of a background and the visual effect is to be added so that it appears to be between the background and the character. In order to cut out the real character a roto artist will have to draw around the character on every frame to make a matte that the compositor can use to put the real element back over the top of the CG part of the shot so that everything appears to be layered in the correct order. Some shots will be filmed in front of a blue or green screen, in which case it may be possible to pull a key and create a matte that way. For circumstances where the key cannot be pulled, or there is no greenscreen, rotoscoping is the only way to create the mattes that the compositor will need to finish the shot. Juniors who want to be compositors often start out as roto artists.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0023.jpg)  
### Element shoots

As well as using fully CG passes it is often a good idea, especially for natural phenomena like smoke, splashes or dust, to shoot real examples of these effects against a black, blue or green screen. These isolated shots are called elements and there will usually be an element shoot as part of a film production. VFX houses keep large libraries of elements from previous shows so that compositors have a range of explosions, blood spurts and so on to choose from when trying to add all the pieces needed to finish a shot.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0024.jpg)  
### Compositing

Compositing is the last process in the chain and it is where all the CG, elements and the scanned plates are brought together to create a seamless finished image. Matte paintings may also be produced at this stage to serve as the backdrop to green screen elements or CG. A compositor will use a variety of techniques to integrate all the elements together so that the shot looks as if it had been filmed and no trickery has been used. Compositors must have an excellent grasp of lens properties and film as well as a good artistic eye to achieve this. Once the composite for the shot has been done it is sent to the supervisors and then the director for approval.

![](http://www.andrew-whitehurst.net/pipeline/VFX_flowChart.0025.jpg)  
### Film out

Once the composite has been approved it is supplied back to the client in the same form as the original scan was received, usually as a series of digital image files. The client uses these finished composited frames for creative grading and eventually to be shot out onto film or DCP for release in cinemas.

  

## Conclusion

As you can see from the final diagram above the whole VFX pipeline is very complex with many departments who are all interdepenedent to a greater or lesser degree. Whilst there will be differences in organisation from facility to facility the above represents a good general guide to all the places I've worked and know of second hand. In every department company-wide there will be a range of senior artists, mid-level artists and juniors. Also be aware that a small project may have one person fulfilling many of these roles alone and larger shows many have tens of people in every position. Whatever the size of the show, the basic flow and order in which things get done is pretty much the same.

I hope this has proved useful to you.

[![Creative Commons License](http://i.creativecommons.org/l/by-nc-nd/3.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/3.0/)  
This work is licensed under a [Creative Commons Attribution-Noncommercial-No Derivative Works 3.0 Unported License](http://creativecommons.org/licenses/by-nc-nd/3.0/).

