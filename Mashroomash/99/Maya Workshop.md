# July 13, 2020 Workshop 1 Notes

## INTRODUCTION T0 MAYA

### PART I: SIMPLE OBJECT CREATION

1. Open Maya
2. Make a simple nurbs object

Create/nurbsprimitives/sphere

Drag to create size interactive/or single click for default values

#### VIEW CONTROLS

1. Mouse button forward/back – zoom in/out
2. Alt left mouse button – rotate up and over, left to right
3. Alt-right mouse button/move left right – zoom in/out
4. Alt-middle mouse buttom – pan left/right
5. Ctl-alt – low left/up right box – zoom in
6. Clt-alt – up right/low left box – zoom out

#### MODIFY SPHERE USING CHANNEL BOX

1. Select sphere.
2. Select channel box
3. Modify scale, rotation, translation by entering values
4. Note coordinate system z forward, x to right, y is up.
5. Translate x-3
6. Scale y – 1

#### CREATE BOX USING HOT BOX

1. Hold space bar
2. Select Create/nurbsprimitives/cube

#### CREATE CONE USING SHELF

1. Display UIElements/Shelf (go into modeling mode)
2. Surfaces/nurbsprimitives/select icon for cone
3. change channel box attribute for cone to -4.

#### CHANGING ATTRIBUTES OF OBJECT WHILE CREATING IT

1. Select create/nurbsprimitives/cone and the check-box in cone selection menu.
2. Change height to 3.
3. Click with the left mouse button in the view window to place the cone in the model.

#### CHANGING ATTRIBUTES OF EXISTING OJECT

1. Select a cone primitive with arrow selection icon
2. Select “Inputs” tab from channels box
3. Change value (height ratio to 4 on cone.
4. Hit enter to complete.

#### ATTRIBUTES OF SURFACE TORUS

1. **Radius** (half-diameter)
2. **Start sweep** (begin angle of sweep clockwise)
3. **End sweep** (end angle of sweep clockwise)
4. **Minor sweep** – unfolds torus
5. degree **linear**/**planar** or **cubic**/**curved** – less or more smooth.
6. **sections** – divisions in U (horizontal) direction
7. **spans** – division in the V (vertical direction)
8. **height ratio** – ratio height to depth

#### POLYGONS

1. Less data needed than nurbs (will not have radical geometry)
2. Composed of **faces**, **edges** and **vertices**
3. subdivisions = smoothness
4. six types: sphere, cube, cylinder, cone, plane and torus
5. create/polygonprimtives/torus
6. use menu or hotbox (spacebar) or shelf

#### CHANGING POLYGON PRIMITIVE ATTRIBUTES (Varies per object type, not all attributes appear on all objects)

1. In options box during creation/channels input box after creation
2. Subdivisions height = # times surface divided
3. subdivisions height/width/depth = divisions height/width/depth
4. subdivisions axis = divisions of surface along central axis
5. cap subdivisions = divisions of cap – concentric (cone, cylinder only)
6. radius = half diameter
7. section radius = torus section radius
8. width, height, depth = overall width, height, depth
9. twist = rotates facesaround tube of torus (vertically)

#### TEXT {SKIPPED DURING ACTUAL WORKSHOP}

1. curves, trim or poly = (no surface, trimmed surfaces, modifiable surface, poly is surface with more modifiable options)
2. create/text/box pick type, font, text -> placement by origin.
3. Try making planar surface from cuves type object  (poly not selected)

#### NAMING OBJECTS 

1. Select object
2. Click on name to Change it at top of channels box (or do this during creation)
3. or change name with attributes editor select object/control a (icon next to IPR symbol)

#### PIVOT POINT

1. Pivot point is origin of object
2. hit “insert” (“home” key on Apple_and select move to move pivot point (then try a rotation)
3. center a pivot point; select object – modify menu/center pivot

### PART II: SETTING UP A PROJECT FOLDER

1. File/Project/Window allows you to more interactively establish the project folder.  
    2a. Under images type “images’ – subfolder where animations are kept.  
    2b. Under “scenes” type scenes – subfolder where all scenes are kept  
    2c. Or, rather than steps 2 and 3, use "default" option.
2. File/project/set …. Establishes name (folder) and directory location and can be used to open  
    an existing project and file.
3. save scene at end.

### PART III: SIMPLE KEYFRAME ANIMATION 

1. Create sphere, go to frame 1, type “s”
2. go to frame 48, move sphere, type “s”
3. hit play button
4. see in   wireframe and shader mode (hit #4 and #5 keys)
5. select rendering panel (display uielements/shelf/rendering)/ select globals
6. Change rendering to low quality raytrace and image type to jpg.
7. batch render

# July 21, 2020 Workshop 7 Notes

## LIGHTING AND MATERIALS, RENDER FARMING  
  
This workshop is developed after techniques described in the Robinson text,. it contains examples that are reinforced by background concepts in Chapters Chapter 14 + Chapter 15 (part), pages 349 402 

#### 1. Shaders in Maya are based upon standard rendering algorithms and include the following types:    

- Lambert – flat – cosine shading (Lambert’s law)
- Phong – typical phong (spectral highlight)
- Phong E – spectral highlight in white
- Blinn – metallic objects
- Anistropic – good for material with grooves
- Layered Shader – more than one material
- Ramp Shader – ramp color (eye ball)
- Shadows …. Map of shadow lines from viewpoint of light sources (geo calculation)

These types of shaders are acessible through the hypershade dialog box or Window/Rendering Editors/Hypershade

![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/hypershademenu2016.jpg)

#### 2. Lighting types & 3 point lighting  - Chapter 14

Lighting types commonly used are 1) Ambient, 2) Distant/Directional, 3) Point and 4) Spot Light which appear from left to right in the Rendering Shelf tab in Maya. Ambient light provides general background illumination. A Distant/Directional light provides parallel light rays from a specific angular orientation, and may be used to mimic such distant lights as sunlight or moonlight. A point light is an omni-directional light that sends light out in all directions from a single location. A directional light sends light in a specific direction at a specific angle from a source location to a target location. 

 ![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/renderingTab2016.jpg)

Key and Fill Lighting: A typical three point lighting setup has a Spot light (also known as a Key light) to the upper right of model at full intensity to provide high contrast shadows, a Point light (also known as a fill light) to the upper left of the model at lower intensity filling in middle gray values, and a back spot light (also known as a back key light) at lower intensity than the front spot light and that provides some three-dimensional depth to the rendering.   

![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/setkeylight2016.jpg)

Key light set at full intenstity and positioned using the show manipulator tool (selected tool on left-hand side of Application window).

|   |   |
|---|---|
|![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/threepointlighting2016.jpg)|![rendering](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/threepointlightrendering2016.jpg)|

  
Full three point lighting setup and rendering. Back key light (spot light) being set into place on left. Rendering on right.

#### 3. Materials Some Definition of Textures and Methods

Materials reference attribute nodes that determine look of an object. This includes  

Texture – an material  that is mapped to object  
      Types:  procedural (based on an algorithm) and  
                    image (based on a photograph).

Bump Map – image read for its gray scale value that makes a material have the appearance of a surface relief

#### 4. Menu items in Hypershade window (Left to Right)

![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/hypershademenu2_2016.jpg)

From left to right the icons above the work area window (see above) have the following functions . Ignore for now those functions which are grayed out:

Clear Graph bar – clears out any nodes in work area  
Add selected nodes to graph  
Remove selected nodes from graph  
Rearrange graph  
Clear graph materials on selected objects  
Hide attributes on selected nodes  
Show connected attributes on selected nodes  
Show primary attributes on selected nodes  
Show attributes from custom attribute view  
Toggle the display of attribute filter field  
Toggle the icon swatch size  
Turn on grid in graph window  
Turn on gravity grid in graph windows  

#### 5. Basic material properties:

![material properties](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/materialproperties2016.jpg)

Color – RGB or HSV selection model color  
Transparency – degree to which material is transparent  
Ambient Color – brightness or darkness of whole material  
Incandescence – create appearance of giving light  
Bump mapping – makes a surface appear bumpy

#### 6. Example of use of simple material definition and assignment

Change color of an object

1. from Windows menu select Rendering Editors -> Hypershade  
      
      
    ![create yellow lambergt](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/creatyellowlambert_2016.jpg)  
    
2. Select create materials
3. Click Lambert (cosine shaded object)
4. Double click the new material to invoke attribute editor 
5. Select field next to color on right-hand side of screen.
6. Choose color from rgb or hsv model/accept  
      
    ![select yellow](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/selectyellow_2016.jpg)  
      
      
    
7. Drag material with middle button onto surface from icon in work are to object. Or select surface and select material with right mouse button, select “Assign Material to Selection”

![assign material](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/assignmaterial_2016.jpg)  

#### 6. Texture mapping nurbs surface

Prepare brick.jpg file or somephoto.jpg file. Make a material from a lamber shader. In the color selection area on the right-hand side of  the the screen, select the checkered symbol and follow the dialog box to load the brick.jpg file.

![select image map](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/selectimagemap_2016.jpg)

Once the image map has been loaded into the definition of the material, it is included in the symbolic graph of the material (left-hand side of image below). Double-clicking on the Place2D texture tool activates interactive placement options.

![map brick](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/mapbrick_2016.jpg)

1. Nurbs surfaces U horizontal – V vertical map from lower left corner to upper right
2. Can map TIF, JPG and Maya’s IFF
3. Create Lambert material
4. In Hypershade panel double click on icon.
5. Add brick file to material
6. Select object, right click on lambert material and assign to object.
7. Double click on pace2dTexture node
8. See red square on object: middle mouse button - drag center to move, drag corners to rotate,
9. Repeat UV … to repeat pattern (do 4 in each of U and V)

#### 7. Ramp texture (eyeball)

![ramp shader](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/rampShader_2016.jpg)

1. Create Phone E shader
2. Double click on the icon (gets attributes window), and then click checkerboard icon on the color.
3. In response to the dialog box to "Select a Render Node", select a "ramp" shader.
4. Change top shader to black by lowering color solider to left.
5. Move middle shader (default color is green) closer to top
6. Click on ramp 1/5th way to bottom, place new position indicator just below 2nd one (above).
7. Click and drag bottom indicator just below new one (3rd one).
8. Click on color swatch for above indicator and select white.
9. Change shader type to U Ramp if needed (rathern than a default V Ramp)and assign to sphere (in Maya 2018 it appears that you may need to try using a Type V Ramp and a type U Ramp before detemining which type is more effective).

#### 8. Layered Shader

![layered shader](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/layeredshader_2016.jpg)

1. Create two blinn shaders red and blue.
2. In blue shade, double clock on icon, and then on transparency color select fractal.
3. Create layered shader
4. Double click on layered shader material.
5. With the middle mouse button drag blue and red materials from the Hypershade into the red square under Layered Shader Attributes. (note blue shader comes before red shader)
6. Click X under original green shader to remove it.
7. On blue blinn shader, use fractal to define transparency
8. Apply the shader to a sphere.
9. In Render view, click on the Redo Previous Render Icon. Red can be seen through the blue due to fractal transparency.

#### 9. Bump Map

![bulge bump map](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/bulgebumpmap_2016.jpg)

1. Create Lambert ahder and assign to plane via MMB.
2. Double-click on Lambert shader
3. Click map button next to bump mapping and select bulge.
4. Select render icon (upper right hand side of screen) to see bump map..
5. To change bump depth/chose graph materials on selected objects icon in hypershade panel and select lambert object.
6. Select bump2d node, increase bump depth , & render (render icon)  
      
    ![render bump map](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/renderBumpMap.jpg)  
    

#### 10. Projection Map

![projection map](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/projectionMap_2016.jpg)

1. Create NURBS plane.
2. Create a lambert material in Hypershade and apply to plane.
3. Double-click on the lambert material in Hypershade
4. In attribute editor, click on map next to color slider.
5. Click the file button (select a file).
6. Click file1 tab at top of attribute editor.
7. Click on folder icon next to Image Name
8. Open your own image.
9. Goto perspective view and select key #6 to render.
10. Select the place2d texture utility in the hypershade window/
11. Experiment with rotate frame, repeat UV and rotate UV options.

[If surface appears to be moving through texture, then in Rendering mode, select the surface, and then from the Texturing menu select “Create Texture Reference Object”]

#### 11. To Improve Quality of Rendering

1. Select object.
2. In hypershade panel, choose Graph Materials on Selected Objects Icon.
3. Double-click on the material in Hypershade.
4. In Attribute editor, under Hardware Texturing, click arrow to expand options.
5. Change “Texture Quality” setting to High. Only do this for temporary viewing since it slows Maya down.  
      
    ![hardware texture](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/hardwareTexture_2016.jpg)  
      
    

#### 12. 3D Paint Tool

1. Create Lambert material and assign it to a new NURBS sphere.
2. Select the sphere.
3. From Texturing Menu, select box next to 3D Paint Tool.
4. Scroll down until you see File Textures.
5. Click the Assign Textures button, determine resolution, and click Assign Textures {note project setup must include texture area
6. In perspective view, hold “b” key and move mouse left & right to size brush.
7. Click and drag on surface to paint.
8. Select swatch next to floor color and choose yellow at top of Color Choose.
9. Click “Flood Paint”
10. Change paint color and paint smiley face on surface.
11. Click on the change brush button, scroll down Visor and select hair folder.
12. Choose hair type and paint on to sphere.
13. Clear surface with flood button.
14. Select brush adjacent to Artisan to return to normal brush.
15. Decrease capacity of brush to see color beneath
16. Can edit image in Photoshop directly from directory.
17. [techniques can also be used for Attributes and Transparency, pull-down menu under file textures.

RENDER FARM RENDERING HAS BEEN DELAYED DUE TO A BACKLOG OF IT PROJECTS CAUSED BY THE PANDEMIC  
These notes will be updated once the backlog has been cleared, which is possible but uncertain for this summer.  
In the interim, the Virtual Workstation platform may be the best availble option for higher performance computing for most students.  

#### RENDER FARMING (SKIP FOR NOW)

Rendering farming, distributed rendering to remote computers, is possible in Maya for Mental Ray and Maya Software rendering options. Basic [setup instructions](http://www-2016.arch.virginia.edu/uploads/documentation/Maya_batch.pdf) (requires login) are typically posted on the School of Architecture web site web. Note that these instructions are continually being updated. The rendering is completed in batch processing mode such that once a job is submitted it is not necessary to stay logged in while it is being processed. The following steps illustrate a typical render farming sequence.

1. Create a folder on the School's "ScanTemp" server typically with your name (e.g., wdisney).Typically "ScanTemp" is visible on any public computer with thie School of Architecture.

1a. On a private Mac on grounds or through VPN use the menu item "Go/Connect To Server":

![connect to server](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/goToScantemp.png)

1.b Similarly, on Windows use the "Run" command and enter

\\scantemp.arch.virginia.edu\ScanTemp

2. Within Maya, setup a project directly on "ScanTemp" under your folder (e.g,"wdisney/batchRenderingTest")

3. Create or open a pre-existing scene file and save it to the "scenes" subfolder of the project folder on "ScanTemp" similar to previous workshops.

4. Setup for batch rendering with either "Maya Software" or "V-Ray" in the "Render Settings" tool similar to previous workshops.  

![set for backburner dialog](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/setupBackburnerMaya2019.png)  

5. Go to the "Rendering Module" in Maya and then go to the menu sequence "Render/Create Backburner Job ... ".

![set for backburner dialog](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/setupBackburnerMaya2019.png)

6. Within the next stage, you maybe asked to save the scene one time. Save it to your project's scenes folder on scan temp.

![save scene](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/saveSceneToScanTemp.png)

7. The following backburner settings are typical.

![create backburner job](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop7images/setupBackburnerMaya2019.png)

Note that a number of changes from the default setup are necessary:

7a. Create a "Job Name", such as "myFirstTry".

7b. Set the "Manager Name" to "renderfarm01.arch.virginia.edu" (the address of the render server).

7c. Set the 'Port" to "7347."

7d. NOTE: The "Renderer Path", set by default, will be different on Windows and on the Mac and needs to be as follows on both platforms. There is a blank space " "between "Program" and "Files" in this path address:

C:/Program Files/Autodesk/Maya2019/bin/Render.exe

7e. The backburner path should be set to:

/opt/Autodesk/backburner/cmdjob

Note: the backburner pathway may need to be set to /usr/discreet/backburner/cmdjob on some computers (this is currently being investigated)

8. Choose the "Submit Job" button, and look for the rendered frames in the images folder under your project Folder on ScanTemp. At this point it is no longer necessary to remain logged in for the backburner batch process to proceed.

9. Whe the images are rendered, copy them from ScanTemp to the local desktop and compile them within Quictime Pro as per the method of earlier workshops. Do not attempt to compile the images over the network due to a number of potential errors.

10. The full setup [PDF file](https://www-2016.arch.virginia.edu/uploads/Documentation/Maya_Batch.pdf) (requires access through UVA login / netbadge) also illustrates how to send email to your self notifying when the backburner task is completed. In addition it describes how to monitor the status of the rendering process on a School of Architecture Windows computer.

11. You can monitor render jobs on the web from on grounds on Cavalier (not Wahoo), or via VPN access:

[http://renderfarm01.arch.virginia.edu/backburner](http://renderfarm01.arch.virginia.edu/backburner)

The web page also requires a login:  
sarc  
render  

note: there is one bug in the web monitor that is acknowledged by Autodesk - it only shows the first letter of the job name, owner, and server name.

12. Tutorials on VRay and Maya are published on the Chaos Group Web site. This [primer](https://docs.chaosgroup.com/display/VRAY3MAYA/Tutorials) is the most relevant to our needs.

# July 22, 2020 Workshop 8 Notes

## Introduction To Rendering With V-Ray

V-Ray is an implementation of a Global Ilumination light energy modeling method that is based upon realistic simulation of lights and materials and takes advantage a probabilistic sampling to reduce the level of computation time. The implementation within Maya allows for the continued use of some regular Maya shaders and also provides an additional set of V-Ray shaders with more advanced simulaation properties.

Tutorials on VRay and Maya are published on the Chaos Group web site. The [primer](https://docs.chaosgroup.com/display/VRAY3MAYA/Tutorials) is the most complete reference for our needs. The V-Ray [tutorials](https://docs.chaosgroup.com/display/VRAY3MAYA/Tutorials#Tutorials-Overview) are a good place to begin toexplore different materials and simulation methods.The notes here reflect a shorter and quick set of examples that help to establish a quick introduction, but the Choas Group web site is best for more thorough explanations and details.

As noted on the Chaos Group [overview](https://docs.chaosgroup.com/display/VRAY3MAYA/V-Ray+in+Maya#V-RayinMaya-2Dand3DTextures) web site, the following Maya (non V-Ray) shaders are supported:

- Lambert
- Blinn
- Phong
- Phong Explorer
- Ramp Shader
- Layered Shader *
- Surface shader
- Use background

For these materials, the supported parameters are:

- Diffuse color/texture
- Reflection color/texture
- Glossiness control
- Bump mapping
- Transparency
- Incandescence

In addtion, the following Maya lighting types are also supported:

- Directional light
- Point light
- Spot light
- Rectangle light

See the Chaos Group web site for an overview of [V-Ray material shaders](https://docs.chaosgroup.com/display/VRAY3MAYA/Materials) and [V-Ray lights](https://docs.chaosgroup.com/display/VRAY3MAYA/Lights).

In part I below, a few variations on basic VRay material and their properties are adjusted. The full set of options and range of values for this type material is [expanded in detail](https://docs.chaosgroup.com/display/VRAY3MAYA/V-Ray+Material+%7C+VRayMtl) on on Chaos Group web site.

Part I: Vray Material Shader Example with IES Light

        1. Create a project folder "VRayTest" and save a scene "sc1.mb". Next, create three polygon spheres above a polygon plane as shown below:

        ![three spheres](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/threepolyspheres.png)

        2. Go to the V-Ray tab, right-mouse click on the "V-Ray IES Light" symbol, second one from the the right-hand side of the light types, and add the light to the model space.  
  
            ![light types](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vraylights.jpg)

        3. Use the menu item "Modify/Show Manipulator" too to position the light above and looking down at the center sphere similar to how the technique was use used in previous tutorials with respect the spotlight for Maya Software.  

           ![place IES light](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/placeIESLight.png)

        3. Open the properties window for the light and the tab "VRayLightIESShape1" as illustrated below. Next, open the sub-areas named "Basic parameters" and "Light shape" as also illustrated below. IES refers to Illuminating Engineering Society data that is typically provided by lighting manufacturers. Here we will use an IES data file [CP6RB10830W.ies](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/CP6RB10830W.ies) which holds data for the simulated light intensity and geometry profile for a Core Pro lighting fixture made by Phillips Lightng (see the [original web source](http://www.lightingproducts.philips.com/our-brands/lightolier-usa/corepro-led-downlight.html#!f=%40WithSmartServiceUSA%3a1%2b%40HasRevitFiles%3a1) of the data file for addtional details).

![core pro LED light](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/CP4RB.jpg)  
Core Pro LED Light by made by Phillips Lighting.  

Download the file [CP6RB10830W.ies](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/CP6RB10830W.ies) and place it inside the "data" subfolder of the project folder.

         ![IES light prop](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/attributesForIESlight.png)

Within the "Basic parameters" subarea, and adjacent to the "IES File Name" blank text field, select the yellow folder and then select the IES file CP6RB10830W.ies from the project "data" subfolder.

       ![add ies file](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/addIESFile.png)

Once the IES file has been loaded, the view window in Maya will be changed to match the Core Pro lighting fixture.

      ![ies fixture in model](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/iesLightAddedToModel.png)

4. Now, under the menu item "Windows/Rendering Editors/Hypershade" open the hypershade panel and review the  
"Surface" shaders available for V-Ray.

      ![vray surface shaders](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/VRaySurfaceShaders.png)

4. Select the generic type V-Ray shader named "VRay Mtl".

     ![choose vray mtl](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/chooseVRayMtl.png)

5. Within the property editor change the Material Viewer from "Hardware" to "V-Ray", and change the sliders for the "Diffuse Color", "Opacity Map", "Reflection Color" and "Refraction Color" to light gray (about 1/3rd of the way from left to right). These values 1/3rd the way from black to white in effect make the material less bright, less reflective , and less apparently refractive. Next, assign the shader to the rightmost sphere in the model. Note: The "Opacity Map" is actually a somwhat inappropriate way to control general transparency, but here is used as a quick method to create the appearance some transpanency. (It's actually better used in a different context, which is to map an image where darker colors indicate transparency, but that is beyond the sope of this current introduction). See step 16 for a more appropriate and revised approach where this material's properties are reset. In particular, note in step 16 that the IOR (index of refraction) for glass at IOR = 1.5. is used.

     ![adjust vray shader prop](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjVRayShaderProp.png)

  6. Create a second VRay "VRay "mtl" shader with the same properties, except let the "Diffuse" color have the appearance of "brass" or "shiny copper", and put the "Opacity" slider all the way to the right so that the adjacent color is white. Next, assign the shader to the center sphere in the model and to the planar polygon.

     ![second vray shader](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/V-RayMtl2.png)

7. Create a third VRay "VRay "mtl" shader with the same properties as the first one, except turn on sub-surface scattering. Next, assign the shader to the remaining sphere in the model.

     ![vray third material with higher refraction index](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/V-RayMtl3_topal.png)

8. Next, open the "Render View" window, and go to the menu item"Opens/Render using/V-Ray".

    ![render options selection](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/renderOptionsSelection.png)

9. Select the "Render" icon in the upper left hand corner of the "Render View " window, and note thatt the "Render View " window is replaced by the V-Ray Render Buffer. In the first pass, the rending is likely to be inappropriately exposed.

     ![first VRay rendering](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/firstVRayRendering.png)

10.However, select the first and the sixth icons on the lower left hand corner of frame buffer view window in order to activate the "corrections control" tools on its right hand side.

    ![add corrections control](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/addcorrectionscontrol.png)

11. Next, scroll down the options on the right-hand side of the frame buffer view window until finding the "Levels" graph. Note that the check-box is "on" due to the selecting the "sixth" icon in previous step 10.

    ![pre adjusted levels](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/frameBufferPreAdjustedLevels.png)

12. Next, just below the graph select the rightmost upward triangleand shift it towards the right end of the graph. Simlarly, select the leftmost upward triangleand shift it slightly towards the left end of the graph. Continue to adjust the two triangle until the rendering appears properly exposed. Note that the left-most and right-most sphere appear different due to the sub-surface scattering property being added to the left sphere. However, our rendering itself was completed without adding on the sub-surface scattering option turned on.

       ![frame buffer adjusted levels](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/frameBufferAdjustedLevels.png)

13. Next, go to the render settings for V-Ray. the "GI" tab in the first area labelled "GI" turn the upper check-box to "On" as well as the check-boxes for "Reflective "Cuastics" and for "Refractive Caustics". In the fifts area labelled "Caustics" turn the upper check-box to "On".

       ![turn on GI effects](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/turnOnGiSettings.png)

14. See the scattering of light impacts below the sphere in the rendering that follows.

      ![GI effects rendered](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/GIeffectsRendered.png)

     15. Add a second IES light of the same type.  

     ![second ies light](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/twoIESLights.png)

16. Increase the index of refraction (IOR) to 20 (unusully high, such as very a highly polished metal) and adjust the "reflection" and the "refraction" color sliders to the right be closer to white for the last material,. Also, adjust the "Opacity Map" color to middle gray scale. A source of IOR values is availble at [https://pixelandpoly.com/ior.html](https://pixelandpoly.com/ior.html) well as other web sites.  
  

     ![modify last material](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/modifyThirdMaterial.png)

17. Re-render.

    ![rerender with more lights and adjusted material](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/twoLightsAndAdjMaterial3Ren.png)

18. The sphere to the right still is somewhat unrealistic in that it appears to be more the non-reflective transparency of paper like but less like perhaps the transparency of glass. As solid glass it would bend light in a way that may also not allow full transparency, but it would bend light more and also be more reflective. To clarify this situation we return back to the properties of the material assigned to this object. In this revision to the properties for the matieral, an IOR of1.5 to is assigne to refraction. We also use an IOR of 1.5 for the material's [fresnal effect](http://www.3drender.com/glossary/fresneleffect.htm) (determines reflectivity at different viewing angles). In addtion the opacity map slider is set to full white (no opacity), and the reflection slider is also set to full white (maximum reflectivty). Note that rather lower the intensity of the "Opacity Map", the level of transparency is determined by the IOR value of 1.5 that is assigned to refraction. Here in the "Material Viewer" as in the model itsef the sphere is not self-evidently transparent when the revised material is applied to a solid sphere. However, when the same material is applied to flat box, the transparency of the material is evident.

![vray material 1 redone](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/VRayMtl_1redone.png)

In the following rendering, a flat vertical wall-like box is added. The box and wall are assigned the revised first material.

![glass wall and sphere](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/glassWallandSphere.png)  

19. In one more step, subsurface scattering is added to the first material.

![add subsurface scattering](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/addSubsurfaceScattering.png)

Note that GI and Caustics must be turned on (from step 13 above):

![turn on GI effects](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/turnOnGiSettings.png)

Re-rerendering produces the following result:

![rerender with subsurface scattering](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/renderWithSubsurfaceScattering.png)

Part II. Simulation of Water  
  
        1. Go to the V-Ray tab, right-mouse click on the "Sun" symbol on the right-hand side of the light types, and add a sunlight to the model space.

            ![light types](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vraylights.jpg)

        Once the sun is placed in the Maya model., Set the V-Ray sun position's geographical locations as:

        Latitude = 38       -Mid Atlantic US  
        Longitude = -78

        Time Zone GMT - 5:00 - US East Coast TIme

         Local Hour 15 (3 pm)

         Date: 11.27.2017

        ![sun position settings](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/setVraySunPosition.jpg)

       2. Under the VRaySunShape1/Parameters tab, set the sky model to Preetham et. al. and nder Ray Trace Shadow Attributes, turn on "Shadows" and "Cast Shadows From Environment".

      ![shape attributes](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/sunShapeAttributes.jpg)

4.    Optionally, add a point source light to the model from the light palette, 3rd icon from the left, to help with middle grey scale shading values.

        ![light types](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vraylights.jpg)

5. Now add a polygon surface plane to the X-Z ground plane and subdivide it into 12 x 12 subdivision units in its "width" and "height" through the channels dialog box as done in prior workshops.

       ![subdivide polygon](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/subdividePolygonInGround.jpg)

6. In the "planeShape1" tab for the polygon surface, right click on the "Attributes/VRay" menu at the top of the dialog box and add "displacement control".  
  
      ![](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/planeShape1VrayAttributes.jpg)

7. Within the hypershade panel create a VRay material that is a new, slightly dark gray, and also has a a mid gray reflection value and a light gray refraction value for a small degree of tansparency and refraction. Also, set the IOR (index of refraction) for the material to 1.35,

     ![create darker grey water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/createNeutraltoDarkerGrayMaterial_1.png)

8. Continuing withing the hypershade window , open the bump map tab for the new material, and select the checkered box to the right pf the word "map".

     ![bump map tab](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/creaeNeutraltoDarkerGrayMaterial_2.png)

9. Now, in the dialog that follows, select under VRay 2D textures option a VRay water material.

![vray water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/selectVRayWater.jpg)

10. Applying the water properties as a bump map and adjusting its paramters, the original VRay material is modified as in the following sample.

   [![water applied](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/waterPropertiesApplied_1b.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/waterPropertiesApplied_1b.png)

From Chaos Group's [documentation](https://docs.chaosgroup.com/display/VRAY3MAYA/Water+Map+%7C+VRayWater), the following are the definitions for each parameter:

**Height Multiplier** – Specifies a scale multiplier for the whole texture.

**Wind Direction** – Specifies the wind direction and thus the direction of the waves.

**Wind magnitude** – Specifies the strength of the wind creating the waves. Higher values produce larger waves. 

**Wind Direction Multiplier** – Specifies a multiplier for the importance of the wind direction. Smaller values will produce more variation in the direction of the waves. 

**Choppy Multiplier** – Specifies a multiplier for the choppiness of the waves. Higher values will produce sharper looking waves.

**Rate** – Speeds up or slows down the movement of the waves. This value has effect only in an animation. 

**Seed** – Specifies an integer used to set the starting point for the random generator. Different values produce different waves randomly. 

**Resolution** – Specifies the amount of detail in the generated map. 

**Patch size** – Specifies the real world size of one patch of the VRayWater texture outside of which the surface is perfectly periodic.

11. Add an ellipsoid and two cylinders, render in Vray and adjust the "Levels" according the procedure done in Part I of these notes. Due to sun color temperature the initial rendering of the the ground surface is a bit yellow. However, futher integrating the VRay sky and other environmental features will alleviate this. Moreover, the water material is an animated map that will cause the effects of water movement in the surface when the scene is animated.

    ![vray water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayWaterRendering_1.png)

12. Continuing within the Hypershade Window, connect the output of the material VRay water into the "Displacement" port of the component "VRayMtl1SG" of the original "VRay Mtl" shader, and note that the rendering of the water level appears to change height accordingly.

  ![hyperShadeMaterial Diagram](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/hypershadeWaterDisplacement_1.png)

13. Returning the shader for the water, increase the density of the texture map to "Repeat U V" 4 x 4 times.

   ![texture density increase](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/textureDensityIncreaseB.png)

  [![vray water rendering 2](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayWaterRendering_1c.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayWaterRendering_1c.png)

14. To add a sky, Go to the view menu, camera attribute editor, and select the environment tab.

     ![camera attr editor](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/camattributeEditorEnvTab.jpg)

15. Select the "Create" button shown in the illustration above, and within the dialog box the follows, choose type "texture".

    ![choose type texture](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/chooseTypeTexture.jpg)  
  
16. Select the checkered box adjacent to the word "Texture" and then uder the VRay shader options choose a VRay sky (alternative to the Maya sky).

  ![VRay Env Sky](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayEnvSky.jpg)

17. In the dialog box that follows, we see the VraySky in the attributes editor. Do NOT check the box that says "Overwrite Sun Settings", and the sky will inherit the values of the Sun light created in step 1 above.

  ![sky attribute editro](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/VRaySkyAttributes.jpg)

18. Next, render the scene in the V-Ray Render Buffer. Here the sky appears too bright and the water surface is still brownish reflecting the color temperature of the sun.

  ![render with VR Sky](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/renderWithVRSky_1.png)

19. However, expand the VRay Frame Buffer Window by selecting the icon in its lower left-hand corner. In the expanded dialogue box on the right-side, select on the option for "White Balance" and move the slider to the left (or right) until the color of the columns, which should be white, turns white. This is the equivalent of correcting for color using a "White Balance" on a real camera which is a way to adjust to color temperature of the exposure. For more details on working with the V-Ray Frame Buffer see this link on [V-Ray Color Corrections](https://docs.chaosgroup.com/display/VRAY3MAYA/Color+Corrections). Rendering again will result in a corrected color balance.

 [![white balance](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjWhiteBalance.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjWhiteBalance.png)

20. Change the diffuse color of the water matarial to a darker shade of gray. In addition adjust the refraction IOR to 1.33, the standard value for water.

   ![adjust shader colors](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjustShaderColors_1.png)

Reset the V-Ray sun time to 13 hours (1 pm) on October 27th for a time of day when the sun is higher in the sky.

![reset sun time](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/resetSun.png)

 Re-render from a lower camera angle and see the result.

![reset sun rendering](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/resetSunRendering.png)

Re-adjust white balance and adjustments for "Exposure", "Highlight Burn" and "Contrast" in the dialog box at right in the image below.

[![adj exposure](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjustExposure.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/adjustExposure.png)

Select the following image to see a brief animated video clip.  
  
[![boat on water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/waterTestAPost.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vRayWaterClip.html)

20. The renderings above use a "bump" map approach where water waves are rendered to appear to be 3D though a shading artifice but the underlying 2D geometry of the flat plane isn't changed. Alternatively, a "displacement" map creates more directly a rendered true 3D geometry that occludes other geoemtry and casts real shadows. This is possible by modifying the VRay attributes of the polygon plane such as illustrated in a [tutorial](http://www.grinning-tiger.com/posts/2015/5/16/creating-an-ocean-with-vray-water) posted on the web site http://www.grinning-tiger.com/.

21. Yet another method for a true 3D displacment is described here.

First, create a new V-Ray material with the same settings for Diffuse color, Reflection and Refration used previously, except do not create a Bump map.

![second water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/secondWaterWithoutBumpMat.png)

Apply the new material to the water plane.

[![apply second water waterial](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/applySecondWaterMaterial.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/applySecondWaterMaterial.png)

22. Next, begin by selecting the plane used to represent the water, shift-select the VRay Displacement Node from the VRay palette, right-mouse click on the the node and choose the option to "Appy single VRayDisplacment node to selection".

![apply displacement](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/applyVRayDisplacement.png)

 23. Next, within the " dialog box at the right, select the checkered icon and then the "VRay Water" animated texture utility.

[![VRay Animation Water Utility Texture](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/selectWaterTextureUtil.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/selectWaterTextureUtil.png)

The last step in turn creates a second "VRayWater" texture. We will use this texture to replace the one that had been used for the water wave in the 2D bump map approach used previously.

[![vray second water texture](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/VRayWaterTexture2.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/VRayWaterTexture2.png)

Change the parameters in the new VRayWater2 as indicated below.

![new water texture parameters](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/2ndWaterTextureParameters.png)

24. Within the Attributes dialog box for the vrayDisplacement, turn on "Displacement control".

![vRayDispacement Attributes](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayDisplacementAttributes.png)

The vrayDisplacement displacement feature results in the following more complete 3D water surface that occludes part of the cylingers and the ellipsoid object.

![3d water displacement](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vrayDisplacementWaterRen.png)  
  

Select the following image to see a brief animated video clip for the displacement mapped waves.  
  
[![boat on water](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/waterTestB.png)](https://web.arch.virginia.edu/arch5422/workshops/workshops2020/workshop8images/vRayWaterClip2.html)