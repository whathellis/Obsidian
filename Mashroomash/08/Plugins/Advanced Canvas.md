### ![Logo](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/logo-light.svg)Logo  
  
Advanced Canvas for [Obsidian.md](https://obsidian.md/)

[![GitHub star count](https://img.shields.io/github/stars/Developer-Mike/obsidian-advanced-canvas?colorA=363a4f&colorB=e0ac00&style=for-the-badge)](https://github.com/Developer-Mike/obsidian-advanced-canvas/stargazers)[![Open issues on GitHub](https://img.shields.io/github/issues/Developer-Mike/obsidian-advanced-canvas?colorA=363a4f&colorB=e93147&style=for-the-badge)](https://github.com/Developer-Mike/obsidian-advanced-canvas/issues)[![List of contributors](https://img.shields.io/github/contributors/Developer-Mike/obsidian-advanced-canvas?colorA=363a4f&colorB=08b94e&style=for-the-badge)](https://github.com/Developer-Mike/obsidian-advanced-canvas/contributors)  
[![](https://img.shields.io/endpoint?url=https://scambier.xyz/obsidian-endpoints/advanced-canvas.json&style=for-the-badge&colorA=363a4f&colorB=d53984)](https://obsidian.md/plugins?id=advanced-canvas)[![GPL-3.0 license](https://img.shields.io/static/v1.svg?style=for-the-badge&label=License&message=GPL-3.0&colorA=363a4f&colorB=b7bdf8)](app://obsidian.md/LICENSE)  
  
**⚡ Supercharge** your canvas experience! Create presentations, flowcharts and more!

## Installation

Open the Community Plugins tab in the settings and search for "Advanced Canvas" (or click [here](https://obsidian.md/plugins?id=advanced-canvas)).

Other installation methods  

- [](https://github.com/TfTHacker/obsidian42-brat)

## Features

All features can be enabled/disabled in the settings.

- Create groups independently of the nodes
- More [canvas commands](app://obsidian.md/index.html#canvas-commands)
- [Node Styles](app://obsidian.md/index.html#node-styles)
    - (Flowchart) [Node Shapes](app://obsidian.md/index.html#node-shapes)
        - Terminal shape
        - Process shape
        - Decision shape
        - Input/Output shape
        - On-page Reference shape
        - Predefined Process shape
        - Document shape
        - Database shape
    - [Border Styles](app://obsidian.md/index.html#border-styles)
        - Dotted
        - Dashed
        - Invisible
    - Text Alignment
        - Left
        - Center
        - Right
- [Edge Styles](app://obsidian.md/index.html#edge-styles)
    - [Path Styles](app://obsidian.md/index.html#path-styles)
        - Dotted
        - Short-dashed
        - Long-dashed
    - [Arrow Styles](app://obsidian.md/index.html#arrow-styles)
        - Triangle Outline
        - Halved Triangle
        - Thin Triangle
        - Diamond
        - Diamond Outline
        - Circle
        - Circle Outline
    - [Pathfinding Methods](app://obsidian.md/index.html#pathfinding-methods)
        - Default
        - Straight
        - Square
        - A*
- [Custom colors](app://obsidian.md/index.html#custom-colors) in the color picker
- [Properties Support](app://obsidian.md/index.html#properties-support)
    - Set properties for the canvas file
- [Presentation mode](app://obsidian.md/index.html#presentation-mode)
    - Create presentations by connecting nodes with arrows
- [Portals](app://obsidian.md/index.html#portals)
    - Embed other canvases inside your canvas
    - Create edges (arrows) to the embedded canvas
- [Collapsible groups](app://obsidian.md/index.html#collapsible-groups)
    - Collapse and expand groups to organize your canvas
- [Better readonly](app://obsidian.md/index.html#better-readonly)
    - Disable node popup menus
    - Lock the canvas' position
    - Lock the canvas' zoom
- [Encapsulate selection](app://obsidian.md/index.html#encapsulate-selection)
    - Create a new canvas from the selected nodes
    - Create a link to the new canvas in the current canvas
- Expose [canvas events](app://obsidian.md/index.html#canvas-events) to use them in other plugins
- Expose node data to style them using CSS

## Support

Please consider supporting the plugin. There are many hours of work and effort behind it. The two easiest ways to support the plugin are either by starring ⭐ the repository or by donating any amount on [Ko-fi](https://ko-fi.com/X8X27IA08) ❤️. Thank you!

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/X8X27IA08)  
![Time Spent](https://img.shields.io/endpoint?url=https://wakapi.dev/api/compat/shields/v1/Developer-Mike/interval:all_time/project:obsidian-advanced-canvas&label=Time%20Spent&style=for-the-badge&colorA=ffffff&colorB=ff5e5b)

## Canvas Commands

- `Advanced Canvas: Create text node`
    - Create a new text node
- `Advanced Canvas: Create file node`
    - Create a new file node
- `Advanced Canvas: Select all edges`
    - Select all edges
- `Advanced Canvas: Zoom to selection`
    - Zoom to the bounding box of the selected nodes
- `Advanced Canvas: Clone node up/down/left/right`
    - Clone the selected node in the direction of the arrow keys
    - The cloned node will have the same dimensions and color as the original node
- `Advanced Canvas: Expand node up/down/left/right`
    - Expand the selected node in the direction of the arrow keys

## Node Styles

### Node Shapes

Flowchart Example![Flowchart Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-flowchart.png)

#### Usage

- Use the updated popup menu set a node's shape

#### Shapes

Terminal Shape![Terminal Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/terminal.png)Process/Center Shape![Process/Center Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/process.png)Decision Shape![Decision Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/decision.png)Input/Output Shape![Input/Output Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/input-output.png)On-page Reference Shape![On-page Reference Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/reference.png)Predefined Process Shape![Predefined Process Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/predefined-process.png)Document Shape![Document Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/document.png)Database Shape![Database Shape](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/flowchart-nodes/database.png)

### Border Styles

Set the style of the border to dotted, dashed or invisible.

Border Styles Example![Border Styles Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/border-styles.png)

## Edge Styles

### Path Styles

Set the style of the edge paths to dotted, short-dashed or long-dashed.

Edge Styles Example![Edge Path Styles Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/edge-path-styles.png)

### Arrow Styles

Set the style of the arrows to triangle outline, halved triangle, thin triangle, diamond, diamond outline, circle or circle outline.

Arrow Styles Example![Edge Arrow Styles Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/edge-arrow-styles.png)

### Pathfinding Methods

Set the pathfinding method of the edges (arrows) to default, straight, squared or A*.

Path Styles Example![Edge Pathfinding Methods Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/edge-pathfinding-methods.png)

## Custom Styles

Custom style attributes for nodes and edges can easily be added.

1. Add a popup menu option
    
    - Open the `<VAULT-PATH>/.obsidian/plugins/obsidian-advanced-canvas/data.json` file
    - If you want to add an option to node popup menu, search for `customNodeStyleAttributes` property, otherwise search for `customEdgeStyleAttributes` property. (Create it if it doesn't exist yet)
    - Add the custom popup menu option (Remove the comments!)
    
    ```json
     "customNodeStyleAttributes": [
         {
             "datasetKey": "exampleStyleAttribute", // Must be unique and written in camelCase
             "label": "Example Style Attribute",
             "options": [
                 {
                     "icon": "cloud-sun", // Choose an icon from lucide.dev
                     "label": "Sunny Appearance",
                     "value": null // Null means default
                 },
                 {
                     "icon": "cloud-rain-wind", // Choose an icon from lucide.dev
                     "label": "Rainy Appearance",
                     "value": "rainy" // The value that gets set
                 }
             ]   
         }
         // You can add more categories here
     ]
    ```
    
2. Create a new CSS snippet in your vault (And enable it in the settings)
    
    ```css
    .canvas-node[data-<DATASET-KEY>="rainy"] { /* The dataset key is now written in kebab-case */
        background-color: #7f7f7f;
    }
    ```
    
3. Reload Obsidian and enjoy your new custom style!  
      
    ![Custom Style Attribute Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/custom-style-attribute-example.png)

## Custom Colors

Add custom colors to the color picker. You can add them using the following css snippet:

```css
:root {
    /* Where X is the index of the color in the palette */
    /* The colors 1-6 are already used by Obsidian */
    --canvas-color-X: 0, 255, 0; /* RGB */
}
```

Custom Colors In Palette![Custom Colors In Palette](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/custom-colors.png)

## Properties Support

Support for properties in canvas files just like in md files. You can edit the properties using the updated control menu.

Supported properties:

- `cssclasses` (Separate multiple classes with a space)

### Custom Background Example (cssclasses)

```css
.canvas-wrapper.<CLASS-NAME> > .canvas-background {
    background-image: url('<IMAGE-URL>');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    
    filter: blur(5px) brightness(0.8);
}
```

## Presentation Mode

In presentation mode, you can navigate through the nodes using the arrow keys or the PageUp/PageDown keys (Compatible with most presentation remotes). The different slides/nodes are connected using arrows. If you want to have multiple arrows pointing from the same node, you can number them in the order you want to navigate through them. While in presentation mode, the canvas is in readonly mode (So [better readonly](app://obsidian.md/index.html#better-readonly) effects the presentation mode as well!). You can exit the presentation mode using the `ESC` key or the corresponding command. If you want to continue the presentation from the last slide you were on, you can use the `Advanced Canvas: Continue presentation` command.

![Presentation mode example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-presentation-simple.gif)Canvas File![Presentation canvas file](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-presentation-simple.png)

### More Complex Example

![Complex presentation mode example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-presentation-complex.gif)Canvas File![Complex presentation canvas file](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-presentation-complex.png)

### Usage

- Create the first slide
    - Create the first slide of the presentation using the updated popup menu
    - OR create a node and mark it as the first slide using the updated card menu
- Add more slides
    - Link the slides using arrows
        - If you want to loop back to a previous slide, you can number the arrows in the order you want to navigate through them
    - **TIP:** Create slides with consistent dimensions by using the updated card menu
- Control the presentation
    - Start the presentation using the command palette (`Advanced Canvas: Start presentation`)
    - Change slides using the arrow keys
    - Exit the presentation using the `ESC` key

## Portals

Embed other canvases inside your canvas and create edges (arrows) to the embedded canvas.

![Portal example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/sample-portal-usage.png)

### Usage

- Embed a canvas file and click on the door icon of the popup menu to open a portal

## Collapsible Groups

Collapse and expand groups to organize your canvas.

Collapsible Groups Example![Collapsible Groups Example](https://raw.githubusercontent.com/Developer-Mike/obsidian-advanced-canvas/HEAD/assets/collapsible-groups.png)

## Better Readonly

- Disable node popup menus
- Lock the canvas' position
- Lock the canvas' zoom
- BUT to retain some interactivity, it allows zooming to a bounding box (e.g. zoom to selection, zoom to fit all)

### Usage

- Use the updated control menu to toggle the new features (Only shown if the canvas is in readonly mode)

## Encapsulate Selection

Move the current selection to a new canvas and create a link in the current canvas.

### Usage

- Select the nodes you want to encapsulate
- Use the context menu (right click) to encapsulate the selection
- OR use the command palette (`Advanced Canvas: Encapsulate selection`)

## Canvas Events

All custom events are prefixed with `advanced-canvas:` and can be listened to using `app.workspace.on` (Just like the default events).

All Events (27)

-   
      
    

## Settings

Every feature can be enabled/disabled in the settings. All features were made to be as customizable as possible.

## Contributing

All contributions are welcome! Here's how you can help:

- Create a fork of the repository
- Create a branch with a descriptive name
- Make your changes
- Debug the plugin using `npm run dev`
- Create a pull request
- Wait for the review

## Known Issues - Create an issue if you find any!

- [ ] Shapes are not shown in the preview
- [ ] Edges from portals can still be dragged