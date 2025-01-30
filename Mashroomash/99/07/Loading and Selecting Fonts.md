---
URL: https://p5js.org/tutorials/loading-and-selecting-fonts/
thumbnail: https://p5js.org/_astro/FontsA.DHxppF9H.png
site: 
date: 2025-01-25T16:36:02
duration: 10
tags: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[Article|Article]] 
# Loading and Selecting Fonts

Description:: Welcome to the chapter finale. In the last two tutorials, you have embarked on a journey of building and styling your HTML, crafting responsive buttons, and executing the logic for your snake game. In this closing tutorial, our focus shifts to Fonts and their pivotal role in design. You’ll learn the art of loading and selecting fonts for your sketch, contributing to your game’s visual identity and user experience.

![Bold typography in contrasting white and black against a deep blue background. It features the words "FONTSTYLE" in black at the top. "TYPEFACE" is in white in the middle. "abc" is in white at the bottom. Each is in a different font size. This creates a bold and striking display of font styles and typefaces.](https://p5js.org/_astro/fonts.BwRbgByd_1YmeTy.webp)

Bold typography in contrasting white and black against a deep blue background. It features the words "FONTSTYLE" in black at the top. "TYPEFACE" is in white in the middle. "abc" is in white at the bottom. Each is in a different font size. This creates a bold and striking display of font styles and typefaces.

Fonts are important in design, and we will learn how to load and choose them for your snake game sketch. You will learn practical techniques for seamless integration and as we finish the series, you will have a complete snake game. You will also understand the important role fonts have in digital experiences, delve into typography, and add finishing touches to your digital masterpiece.

## Prerequisites

-   You must have finished the [Creating and Styling HTML](https://p5js.org/tutorials/creating-styling-html/) and [Responding to Inputs tutorials](https://p5js.org/tutorials/responding-to-inputs/).
-   [Complete Responding to inputs code](https://editor.p5js.org/ruthikegah/sketches/TKoGPLJfe/)

### Step 1 – Learn about fonts

Fonts refer to a set of characters, symbols, and styles within a [typeface](https://fonts.google.com/knowledge/glossary/typeface/). They dictate the visual appearance of text, encompassing factors like size, style, and weight.

For best practices, these are some guidelines you should consider while choosing a font to suit your project best:

-   **Consider project requirements:** Understand your project’s goals, audience, and tone. Different projects may require fonts with specific characteristics. For example, you may use a formal serif font to make an interactive version of a vintage newspaper, while you may use a playful sans-serif for a game.
-   **Pairing fonts effectively:** Experiment with font pairings. Effective font pairings contribute to visual hierarchy and readability. For example, you may want to pair a distinctive display font with a legible sans-serif for body text.
-   **Evaluate font properties:** Pay attention to font properties like thickness, slant, and width. Adjust these properties based on the project’s visual requirements and the desired impact.
-   **Readability:** Prioritize readability. Choose clear and legible fonts, especially for large bodies of text and consider factors like letter spacing and line height.
-   **Explore font libraries:** [Google Fonts](https://fonts.google.com/) and [Font Squirrel](https://www.fontsquirrel.com/) offer diverse collections of free and open-source fonts. Use the search and filtering options to narrow your choices based on categories, popularity, and trending fonts. Take advantage of the live preview feature to see how fonts will appear in your design.
-   **Accessibility:** Your sketch may run on a wide range of devices, from phones to large projector installations. Choose fonts that scale well across different screen sizes without sacrificing legibility. Google Fonts and Font Squirrel provide information on each font’s character set, language support, and variability. This information will help you make informed choices for responsive designs.
-   **License:** Be mindful of font licenses. Some fonts are free for commercial use, while others may have restrictions. Adhere to licensing agreements. 

Choosing suitable fonts involves a thoughtful and systematic approach. You can create visually appealing and user-friendly projects by considering factors such as readability, consistency, and responsive design. Remember to explore the font libraries, test fonts in various environments, and seek inspiration to make informed design decisions. With these guidelines, you’ll be well-equipped to enhance your design projects with the perfect typography.

Check out [Google Fonts’ “Choosing type” section](https://fonts.google.com/knowledge/choosing_type/) to learn more about selecting fonts and best practices.

In this case, you will use the fonts to style your text prompts in your game, i.e., the Display message and Game Over prompt. Considering the project is a retro game console, we will use a retro font for our prompts. 

### Step 2 – Style text with web-safe fonts

Before moving to Google custom fonts that fit the project, let’s start with more common web-safe fonts like Arial and Courier New to style your texts. [Web-safe fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals#web_safe_fonts) are available on most computers by default. 

To set the font for your display messages, you will use the p5.js [`textFont()`](https://p5js.org/reference/p5/textFont/) function. This function sets the font for the contents of your [`text()`](https://p5js.org/reference/p5/text/) function. In your \- and \- functions, add your font:

```
// Start message.
function displayStartMessage() {
  textSize(20);
  textAlign(CENTER);

  //Add font
  textFont('Courier New');
  fill(255, 0, 0);
  text('Press ▶ to Start', width / 2, height / 2);
}

// End message.
function displayEndMessage() {
  background(0);
  textSize(40);
  textAlign(CENTER);

  //Add font
  textFont('Courier New');
  fill(255, 0, 0);
  text('Game Over', width / 2, height / 2);
  textSize(14);
  text('Press ▶ to Start', width / 2, height / 2 + 50);
}
```

Next, you change the logo text. It’s an HTML element, so you will be using the [`.style()`](https://p5js.org/reference/p5.Element/style/) method. As stated in the previous chapter, the `.style()` method is used to manipulate HTML elements. In your `gameBoyText` , add your font like this:

```
// Create the game boy text
let gameBoyText = createDiv('GameBoy');
gameBoyText.id('game-boy-text');
gameBoyText.style('margin', '10px 145px');
gameBoyText.style('font-size', '25px');
gameBoyText.style('color', '#fff');
gameBoyText.style('background-color', '#000');
gameBoyText.style('padding', '10px');
gameBoyText.style('border-radius', '5px');

// Add font
gameBoyText.style('font-family', 'Arial');
```

Your fonts should look like this:

![The image features a digital rendition of a Gameboy with a gray body and a dark screen displaying the text "Press > to Start" in a classic Courier font. Below the screen, the word "GameBoy" is presented in a bold, sans-serif font on a blue background, creating a contrast. Red arrow buttons and blue round buttons for play and pause are also visible, adding to the nostalgic gaming theme.](https://p5js.org/_astro/gameboy-fonts.BdNF3dTK_Z1yI3ou.webp)

The image features a digital rendition of a Gameboy with a gray body and a dark screen displaying the text "Press > to Start" in a classic Courier font. Below the screen, the word "GameBoy" is presented in a bold, sans-serif font on a blue background, creating a contrast. Red arrow buttons and blue round buttons for play and pause are also visible, adding to the nostalgic gaming theme.

In this exercise, you can observe the impact of different fonts on your project. The intention is to familiarize yourself with web-safe fonts. We will enhance this style in the following steps. For now, feel free to delete the changes made to the fonts.

##### Try this!

Experiment with the textAlign() and textStyle() functions to see how they modify your fonts.

[Solution.](https://editor.p5js.org/ruthikegah/sketches/w1SZv_0w6/)

### Step 3 – Download a font from Google fonts

Now, it’s time to add a custom font to your project. Go to [Google Fonts](https://fonts.google.com/) and search for PressStart2P, a font with a retro gaming design.

![A screenshot from the Google Fonts website showing a sample of the 'Press Start 2P' font. The font, designed by CodeMan38, has a pixelated, blocky style that is reminiscent of text seen in early computer and video game screens. In the example, the bold letters spell out "Whereas disregard and contempt for human rights have...". This shows the font's retro gaming style and digital type.](https://p5js.org/_astro/PressStart2P.CPGACgRi_oqyg6.webp)

A screenshot from the Google Fonts website showing a sample of the 'Press Start 2P' font. The font, designed by CodeMan38, has a pixelated, blocky style that is reminiscent of text seen in early computer and video game screens. In the example, the bold letters spell out "Whereas disregard and contempt for human rights have...". This shows the font's retro gaming style and digital type.

Click on Download Family to download the font. It usually comes in a zip file; open it and extract the .ttf file.

##### Try this!

Search Google Fonts for other styles that you’d like to use for your game.

### Step 4 – Upload the font file to your project

In your web editor, click on the + icon on the top right corner of your screen and select Create Folder. Name your folder assets, click on the folder, and select upload file. Upload your `.ttf` file to your assets folder.

![A dynamic GIF illustrating how to create a folder on the p5.js web editor. You open the files window on the top left by clicking the “>” icon, click the plus icon and select the “Create Folder" option.](https://p5js.org/_astro/create-folder.BOmUjU4R_Z2hCLbR.webp)

A dynamic GIF illustrating how to create a folder on the p5.js web editor. You open the files window on the top left by clicking the “>” icon, click the plus icon and select the “Create Folder" option.

### Step 5 – Preload your font

p5.js’ [`preload()`](https://p5js.org/reference/p5/preload/)  function loads external assets before the rest of your sketch is executed. The `preload()` function is called directly before `setup()`. It is used to handle asynchronous loading of external files in a blocking way. If the `preload()` function is defined, `setup()` will wait until any load calls within have finished.

For example: 

Inside the `preload()` function, you can use p5.js’s various asset-loading functions such as `loadImage()`, `loadSound()`, and `loadFont()` to load external files. These functions take the path to the asset file as an argument.

At the start of your `sketch.js` file, write the following code:

```
let myFont;
function preload(){
  myFont = loadFont("assets/PressStart2P-Regular.ttf");
}
```

You declare a variable myFont to store your font. The `preload()` function loads your font with the `loadFont()` function, passing your file path as the argument. 

### Step 6 – Use your fonts in your display messages

With your fonts loaded, using them where needed is relatively easy now. Call The p5.js [`textFont()`](https://p5js.org/reference/p5/textFont/) function and pass in your `myFont` variable as its argument. The `textFont()` function sets the font that will be used by your [`text()`](https://p5js.org/reference/p5/text/) function. Syntax:

```
textFont(font);
```

Now use the `textFont()` function to load your font in your \- and \- like this: 

```
// Start message.
function displayStartMessage() {
  textSize(20);
  textAlign(CENTER);
  fill(255, 0, 0);
  // Use your font
  textFont(myFont);
  text('Press ▶ to Start', width / 2, height / 2);
}

// End message.
function displayEndMessage() {
  background(0);
  textSize(40);
  textAlign(CENTER);
  fill(255, 0, 0);
  // Use your font
  textFont(myFont);
  text('Game Over', width / 2, height / 2);
  textSize(14);
  text('Press ▶ to Start', width / 2, height / 2 + 50);
}
```

Your Start message should look like this:

![An image with a gray background and the text “Press ▶ to Start” centered on the image, colored in red. The text is in the retro gaming style font PressStart2P-Regular.](https://p5js.org/_astro/press-start-font.CeMIx8NW_1yLb5T.webp)

An image with a gray background and the text “Press ▶ to Start” centered on the image, colored in red. The text is in the retro gaming style font PressStart2P-Regular.

Your End message:

![An image with a black background and a bold text “Game Over” centered on the image, below it is a smaller centered text “Press ▶ to start”. Both texts are colored red and in the retro gaming font PressStart2P-Regular. On the top right is the text “Score: 0”, colored white and in the retro gaming font PressStart2P-Regular.](https://p5js.org/_astro/game-over-font.DXM7YXjv_Z6npJ4.webp)

An image with a black background and a bold text “Game Over” centered on the image, below it is a smaller centered text “Press ▶ to start”. Both texts are colored red and in the retro gaming font PressStart2P-Regular. On the top right is the text “Score: 0”, colored white and in the retro gaming font PressStart2P-Regular.

Adjust the `textSize()` if the text becomes too big or too small for the screen.

##### Try this!

Make the `textSize()` a fraction of the sketch `height` or `width`.

[Solution.](https://editor.p5js.org/ruthikegah/sketches/_bnQ40m9l/)

### Step 7 – Setting the font for your logo text

We are almost at the end of this project! The final thing to do now is to set a font for your logo text. Since it is an HTML element, you use the `.style()` method to directly manipulate the style of the element.

In your `gameBoyText` div, add another .style() method with the property `'font-family'` and value `'PressStart2P-Regular'` which is the name of the font you are using:

```
// Create the game boy text
let gameBoyText = createDiv('GameBoy');
gameBoyText.id('game-boy-text');
gameBoyText.style('margin', '10px 145px');
gameBoyText.style('font-size', '25px');
gameBoyText.style('color', '#fff');
gameBoyText.style('background-color', '#000');
gameBoyText.style('padding', '10px');
gameBoyText.style('border-radius', '5px');

// Add font for gameBoyText
gameBoyText.style('font-family', 'PressStart2P-Regular');
```

Your logo should now look like this:

![An rectangular image with a light gray background and the text “Gameboy”. The text is wrapped in a small rectangular, black background and is colored white. It is styled with a retro gaming style font.](https://p5js.org/_astro/gameboy-logo-font.CuctgwtG_s0t3C.webp)

An rectangular image with a light gray background and the text “Gameboy”. The text is wrapped in a small rectangular, black background and is colored white. It is styled with a retro gaming style font.

Make sure to adjust the size if the text becomes too large or small in your text area.

##### Try this!

Load and try out other fonts to see which one you feel is best for your game.

Here are some other retro fonts that can give you that retro feel:

-   [Amarante](https://fonts.google.com/specimen/Amarante/)
    
    ![A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Amarante.](https://p5js.org/_astro/amarante-example.CuAMh_GQ_1T4ht1.webp)
    
    A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Amarante.
    
    This font gives an elegant, narrow, serif typeface; it can work as a display face and surprisingly well in texts and headlines.
    
-   [Geostar Fill](https://fonts.google.com/specimen/Geostar+Fill?query=Geos)
    
    ![A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Geostar Fill.](https://p5js.org/_astro/geostar-example.DuDMPDvm_ZqDSXT.webp)
    
    A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Geostar Fill.
    
    Geostar is a great font for large headlines. Its single weight allows for easy legibility and captivates the audience at first glance. Because Geostar is so symmetrical, it is a fantastic option to add charisma and sophistication to your screen.
    
-   [Ewert](https://fonts.google.com/specimen/Ewert?query=Ewert)
    
    ![A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Ewert.](https://p5js.org/_astro/ewert-example.WtxZ7BJ0_Zs1gQ7.webp)
    
    A square image with a dark gray background and a text “Press Play to Start” centered on it. The text is red in color and is styled with a classic font, Ewert.
    
    Ewert is a slab serif wood type inspired by, and loosely based on, the collection of cultural infographic maps by Estonian graphic artist Olev Soans. It gives your screen text a stylish, robust fantasy aesthetic.
    

## Conclusion

Congratulations for making it this far! You have completed your p5.js GameBoy sketch. Throughout this series, you’ve embarked on a comprehensive coding journey, mastering key aspects of web development and creative coding:

-   HTML Crafting: You learned how to structure and style your HTML elements with p5.js, setting the foundation for a visually appealing and responsive interface.
-   Interactive Buttons: Implementing buttons with p5.js, you gained hands-on experience in creating interactive elements for user input, which is crucial for game control.
-   Gameplay Logic: Delving into the core of game development, you implemented gameplay logic for a snake game. You tackled input handling, movement, collision detection, and scoring on the way to building a fully functional game.
-   Font Integration: Understanding the significance of fonts in design, you explored the process of loading and selecting fonts using Google Fonts. Applying this knowledge, you stylized your game’s display messages with a retro font.
-   Design Principles: Beyond coding, you grasped essential design principles, considering factors like readability, consistency, and responsive design to enhance user experience.

With this series, you’ve acquired technical coding and input logic skills and honed your design sensibilities. The journey concludes with a fully functional retro game console and a snake game that reflects your newfound expertise. 

Congratulations again on reaching this milestone!

Here is an [example finished project](https://editor.p5js.org/ruthikegah/sketches/fDU72YAkp/) for reference.

### Next steps

-   [Abracadabra: Speak With Your Hands in p5.js and ml5.js](https://p5js.org/tutorials/speak-with-your-hands/)
-   [Color Gradients](https://p5js.org/tutorials/color-gradients/)

### References

-   [Google fonts](https://fonts.google.com/)
-   [Understanding typography (Canva)](https://www.canva.com/learn/typography-guide/)

