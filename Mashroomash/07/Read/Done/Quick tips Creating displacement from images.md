---
URL: https://www.mikecauchiart.com/single-post/2016/12/11/quick-tips-creating-displacement-from-images
thumbnail: https://static.wixstatic.com/media/2ae9b9_216a01d3f76f493795ff2a2e5ddecce7~mv2_d_3572_1500_s_2.jpg/v1/fill/w_1000,h_420,al_c,q_85,usm_0.66_1.00_0.01/2ae9b9_216a01d3f76f493795ff2a2e5ddecce7~mv2_d_3572_1500_s_2.jpg
site: "[[mikecauchiart]]"
date: 2024-09-03
duration: 5
topics:
  - "[[Texture Map|Texture Map]]"
  - "[[Compositing|Compositing]]"
  - "[[Tutorial|Tutorial]]"
done: true
cover: ""
---
[[../../../01 Maps/Themes/Article|Article]]
# Quick tips: Creating displacement from images

(Description:: **Hey** Hey, I thought for this quick tip tutorial I should cover something involving automation. Since most of my stuff revolves around modelling and shading maybe displacement would be a good place to start.) 
**QUICK DISCLAIMER:** This method may be quick for MOST images but if you want truly accurate displacement than this is not the way to go. Best thing to do would be to sculpt or use photogrammetry to create actual geometry. That said this is a much quicker method and as 3d artists we generally like to be lazy :) Anyways, I hope you find this useful! 
**Note:** As hinted to before, this method works better for some images than others, there's a gallery below where you can see this (The tiles really aren't that great but the skin works really well)

**Credit where it's due** Just thought I should say before I get started that the images used to demonstrate the nuke script are from [](http://www.episcura.com/)[**www.Episcura.com**](http://www.episcura.com/). I would heavily recommend using their site to try out this method just because the images are guaranteed to be good quality. (I'm not sponsored I swear, they're just really good!) Also, the render at the very bottom of the image used a HDR from HDR labs SIBL archive.

**Why nuke?** So, Why use nuke for creating your displacement maps from images. Well there's quite a lot of reasons but for me it's the simple fact that once you have made the node graph you now have a fully automated way to convert any image. If you did this in Photoshop you would have to repeat the same steps again and again for each image. That said, if you really wish to use photoshop than I recommend checking the resources section at the bottom, there will be a link down there for you. (Or use Quixel's NDO)

**Workflow**

#### Step one: desaturate
Ok, time to get to the making of bit that you're here for. So to start off we want to remove all colour from the image using a saturation node since displacement it much easier to calibrate with a monotone image. Of course, if you have ever used texturing xyz you'll know that different displacement maps can be separated into each channel to essentially give the lookdev artist the ability to change the amount of certain details by combining the RBG at different amounts (I won't be going into any detail about this but if you want to learn about it check out the resources at the bottom of the page).



#### Step two: set the value range
Once we have our image in monotone we need to make sure that will are using the full value range so that we can get the best results. To do this we will remap the values using the curve tool and grade nodes. First create a dot node to split the image into two paths, then connect a curve tool node and set it to max luma pixel. Then hit go to analyse the image so that we can access the min an max values of the image. From here all we have to do is copy and paste the values from min/max luminence values into the black point and white point of the image. This should slightly increase the contrast of the image and make sure that we are using the whole value range of the image.



#### Step three: using highpass filters to create displacement
Now that our image is ready to be converted into a displacement map we just have to create three highpass filters. There are a few ways to do this buy my personally prefered method is to use a blur and a merge minus node to seperate details from the image (you could also use a merge difference but this tends to always capture high frequency details which you may not always want!). So, start by splitting the image into multiple paths using a dot node, connect this dot node to a blur and a merge minus. Now use the blur amount to decide the size of the detail you want to capture. in my case I used a blur size of: high frequency = 4, mid frequency = 32 and low frequency = 85. After you have got the details seperated use a merge plus to add them all togeather and then plus this with a constant set to a value of 0.5 to set the middle value of the image. 
**Note:** at the end of the displacement I added a invert node. During writing this tutorial I realised that this was actually not needed and I should have infact changed the order of the a/b inputs for the highpass filters.



#### Step four: Set the range again and blur
At this point we have all we need to use the map for displacement however to get the most out of the map I like to add a small blur and also repeate step two to make sure i'm using the whole value range

!

**So, why didn't you just desaturate it? That can be used for displacement right?** well, technically you're not wrong... You could just use a black and white version of the original image as a displacement however there are a few considerations to make. Firstly, the lighting conditions/shadows will drasticly change the displacement quality. This is why we did highpass filters, as this helps us to seperate the details from the lighting, it obviously isn't perfect but it goes a long way flatten the image.

**Before you go**

I hope this short tutorial has been helpful for you, as I said earlier though, don't use this expecting perfect results from any image. You'll be dissopointed rather quickly. Typically it gives good results on soft surfaces (anything organic really) but if you want perfect displacement, don't get lazy. Just model it or use photogrammetry to get much nicer results.

#### [[../../../01 Maps/Themes/Resources|Resources]]:
**Jeremy Celeste - Combining multichannel displacement maps:** http://texturing.xyz/pages/non-destructive-and-interactive-workflow-using-texturingxyz-maps **Vray world - Creating displacement from images using photoshop** https://vwartclub.com/?section=learning&category=useful+tips&article=useful-tips-vray-world-how-to-create-a-displacement-map-in-photoshop

