---
{}
---
[[../../99/Template/Heatmap Year Tracker|Heatmap Year Tracker]]
# Heatmap Tracker plugin for Obsidian

![](https://raw.githubusercontent.com/mokkiebear/heatmap-tracker/refs/heads/main/public/readme-cover.png)

The **Heatmap Tracker plugin for Obsidian** is a powerful and customizable tool designed to help you **track, visualize, and analyze data** over a calendar year. Perfect for habit tracking, project management, personal development, or any kind of data visualization, this plugin enables you to create beautiful, interactive heatmaps directly within Obsidian. Whether you’re **monitoring progress, visualizing trends, or staying on top of daily goals**, the Heatmap Tracker enhances your productivity and organization. Discover its intuitive features, flexible customization options, and seamless integration with Obsidian in the detailed guide below.

>  
> 
> **Tip:** Check [Example Vault](https://github.com/mokkiebear/heatmap-tracker/tree/main/EXAMPLE_VAULT). There're lots of good examples (and I update it often).

## Watch video to start using this plugin in 30 seconds

![](https://raw.githubusercontent.com/mokkiebear/heatmap-tracker/refs/heads/main/public/heatmap-how-to.gif)

## Start with this code example

>  
> 
> **Tip:** Update `trackerData` with your own dataset to visualize custom data points.

>  
> 
> **Tip:** Add  in the beginning of your code block to enable DataviewJS functionality.

```javascript
// Update this object
const trackerData = {
    entries: [],
    separateMonths: true,
    heatmapTitle: "This is the title for your heatmap",
    heatmapSubtitle: "This is the subtitle for your heatmap. You can use it as a description.",
}

// Path to the folder with notes
const PATH_TO_YOUR_FOLDER = "daily notes preview/notes";
// Name of the parameter you want to see on this heatmap
const PARAMETER_NAME = 'steps';

// You need dataviewjs plugin to get information from your pages
for(let page of dv.pages(`"${PATH_TO_YOUR_FOLDER}"`).where((p) => p[PARAMETER_NAME])){
    trackerData.entries.push({
        date: page.file.name,
        intensity: page[PARAMETER_NAME],
        content: await dv.span(`[](${page.file.name})`)
    });
}

renderHeatmapTracker(this.container, trackerData);
```

## Tracker Settings Documentation

### `year`

- **Type:** `number`
- **Default:** Current year (`new Date().getFullYear()`)
- **Description:** Specifies the year for which the heatmap should display data by default.

---

### `colorScheme`

- **Type:** `object`
- **Default:**

```
{
  "paletteName": "default",
  "customColors": []
}
```

- **Description:** Defines the color scale used for representing different intensity levels in the heatmap. Each color corresponds to a specific range of data intensity.

---

### `customColor`

- **Type:** `string`
- **Default:** `undefined`
- **Description:** Entry property. Sets the color for specific entry. If you want some entry (based on the condition) to have a different color, you can set it here.

---

### `entries`

- **Type:** `array`
- **Default:**

```
[
  { "date": "1900-01-01", "customColor": "#7bc96f", "intensity": 5, "content": "" }
]
```

- **Description:** A list of data entries for the heatmap. Each entry includes:
    - : The date of the entry (ISO string format).
    - `customColor`: The color for that entry.
    - `intensity`: The data intensity for that date.
    - `content`: Optional tooltip or note associated with the date.

---

### `showCurrentDayBorder`

- **Type:** `boolean`
- **Default:** `true`
- **Description:** Indicates whether the current day should be highlighted with a border on the heatmap.

---

### 

- **Type:** `number`
- **Default:** `4`
- **Description:** The default intensity assigned to new data entries if no intensity is explicitly specified.

---

### `intensityScaleStart`

- **Type:** `number`
- **Default:** `1`
- **Description:** The minimum value for the intensity scale. Used to determine the color mapping for the lowest intensity values in the heatmap.

---

### `intensityScaleEnd`

- **Type:** `number`
- **Default:** `5`
- **Description:** The maximum value for the intensity scale. Represents the highest possible intensity that can be mapped to the color scale.

---

### `separateMonths`

- **Type:** `boolean`
- **Default:** `false`
- **Description:** Determines whether months should be visually separated within the heatmap layout.

![](https://raw.githubusercontent.com/mokkiebear/heatmap-tracker/refs/heads/main/public/two-mac-mockup.png)

To be used with [Obsidian Dataview](https://blacksmithgu.github.io/obsidian-dataview/), but could be used standalone or with other plugins as well (if you know some javascript).

## 📦 Plugin Features

### ✅ Key Features:

1. **Yearly Heatmap Visualization**  
    Render a dynamic heatmap for the selected year, displaying data intensity for each day.
    
2. **Customizable Colors and Intensity**  
    Define your own color schemes and intensity ranges to match your data's theme.
    
3. **Interactive Navigation**  
    Easily switch between years using left and right navigation arrows.
    
4. **Flexible Data Entries**  
    Add entries with customizable colors, intensity levels, and tooltips for detailed content.
    
5. **Monthly Separation Option**  
    Choose whether to separate months visually within the heatmap.
    
6. **Localization**  
    Plugin supports multiple languages, including English, German and Russian.
    
7. **Statistics View**  
    Statistics view where you can see your progress.
    

![](https://raw.githubusercontent.com/mokkiebear/heatmap-tracker/refs/heads/main/public/mac-mockup-dark.png)![](https://raw.githubusercontent.com/mokkiebear/heatmap-tracker/refs/heads/main/public/tracker-overview.png)

## Roadmap

📍 Check out the [Roadmap](app://obsidian.md/ROADMAP.md) to see what's planned for the future!

## Development (Windows/Mac):

`npm run dev` - will start an automatic TS to JS transpiler and automatically copy the generated JS/CSS/manifest files to the example vault when modified (Remember to run `npm install` first).

After the files have been transpiled, the **hot-reload plugin** ([https://github.com/pjeby/hot-reload](https://github.com/pjeby/hot-reload)) then reloads Obsidian automatically.  
Hot-reload is installed in the example vault by default. its used to avoid restarting obsidian after every change to code.  
_(remember to add an empty_ .hotreload _file to "EXAMPLE_VAULT/.obsidian/plugins/heatmap-tracker/" if not already present, as this tells hot-reload to watch for changes)_

`npm run build` generates the files ready for distribution.

Tip: `ctrl-shift-i` opens the devtools inside Obsidian.

---

## Inspired by:

[https://github.com/Richardsl/heatmap-calendar-obsidian](https://github.com/Richardsl/heatmap-calendar-obsidian)