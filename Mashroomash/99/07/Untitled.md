--- 
cssClass: cover-img 
---

![banner](beach.png)

top and formatted in bold.
Title property: For notes that have the title property in their metadata, the title is written in the index next to the link. This is useful for example when managing citation notes, usually named by their citation key by the Citations plugin. Having the title next to the citation key helps identify the notes in an index.
Index formatting: Sections in the index are derived from their tags. For instance, #deep_learning becomes Deep learning in the index. If you have an acronym then add an additional underscore before the word to make it all-caps. For example, #_ml becomes ML and #comparisons__ml becomes Comparisons ML.
Excluded folders: you can set folders to exclude from indexing, like the templates folder.
Troubleshooting
If indices are not appearing as expected, ensure that:

Tags are correctly spelled and used consistently.
The update interval is appropriately set according to your needs.
If the indices don't seem to update, try view > Force Reload or restart Obsidian.
If the block reference of the index is modified or deleted, the plugin will fail to detect the existing index and append a new index block rather than update it. If this happens, just delete the old block.

**Basic checklists:**
- [ ] normal
- [/] / - incomplete
- [x] x - done
- [-] -  canceled
- [s] s - forwarded
- [<] < - scheduling

**Extras checklists:**
- [?] ? - question
- [!] ! - exclamation
- [*] * - star
- ["] " - quote
- [l] l - location
- [b] b - bookmark
- [i] i - information
- [S] S - savings
- [I] I - idea
- [p] p - thumbs up
- [c] c - thumbs down
- [f] f - fire
- [k] k - key
- [w] w - win
- [u] u - up
- [d] d - down




![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/cover.png)

  

> **Table of Contents**
> 
> 1. [Special Syntax](https://github.com/Bluemoondragon07/obsidian-notation-2/blob/main/README.md#special-syntax)
>     1. [Callout Colors](https://github.com/Bluemoondragon07/obsidian-notation-2#callout-colors)
>     2. [Toggle Blocks](https://github.com/Bluemoondragon07/obsidian-notation-2#callout-toggle-blocks)
>     3. [Heading Callouts](https://github.com/Bluemoondragon07/obsidian-notation-2#heading-callouts)
> 2. [CSS Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#css-classes)
>     1. [Banner Images](https://github.com/Bluemoondragon07/obsidian-notation-2#banner-images)
>     2. [Text Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#text-classes)
>     3. [Other Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#other-classes)
> 3. [Some Other Cool Things](https://github.com/Bluemoondragon07/obsidian-notation-2#some-other-cool-things)
> 4. [Credits](https://github.com/Bluemoondragon07/obsidian-notation-2#credits-)
> 5. [License](https://github.com/Bluemoondragon07/obsidian-notation-2/blob/main/README.md#license)

  

**Notion** has always been one of my favourite apps because of its advanced features, and **Notation** remains one of my favourite Obsidian themes of all time. The original Notation is still a bit broken after 1.0, so I thought I'd make a new theme combining the design elements of Notation with the features of Notion.

With Notation 2, you can experience the power of cover (banner) images, callouts with custom backgrounds, and more (see: **Special Syntax**)

# Special Syntax

## Callout Colors

Callouts are styled to look like Notion callouts by default, with a tranparent background and a faint outline. You can choose the color of any callout with ease: just add the color you want--`red`, `orange`, `yellow`, `green`, `blue`, `purple`, `pink`, `brown`, or `grey`/`gray`--inside the callout type brackets, separated by a `|`.

> Example: `>[!quote|blue]`

![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/Screenshots/callout.png)

![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/Screenshots/blue-callout.png)

## Callout "Toggle Blocks"

When I switched over to Obsidian from Notion, I found it hard to adjust to the absence of toggle blocks. So I added them to this theme.

Any collapsible callout takes on the appearance of a Notion toggle block.

### Regular Toggle Block

```markdown
>[!info]+ I am a toggle block.
>I contain information.
```

![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/Screenshots/toggle-block.png)

Toggle blocks also support background colors.

### Colored Toggle Block

```markdown
>[!info|blue]+ I am a blue toggle block.
>I contain information.
```

![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/Screenshots/blue-toggle.png)

### Just...Don't Create Empty Toggle Blocks

This results in normal text with no collapse icon.

## Heading Callouts

I made this mainly for toggles, but they work with regular callouts, too. Adding `h1`, `h2`, or `h3` inside the callout type brackets will increase the font size without messing up padding.![](https://raw.githubusercontent.com/Bluemoondragon07/obsidian-notation-2/HEAD/cover.png)

  

> **Table of Contents**
> 
> 1. [Special Syntax](https://github.com/Bluemoondragon07/obsidian-notation-2/blob/main/README.md#special-syntax)
>     1. [Callout Colors](https://github.com/Bluemoondragon07/obsidian-notation-2#callout-colors)
>     2. [Toggle Blocks](https://github.com/Bluemoondragon07/obsidian-notation-2#callout-toggle-blocks)
>     3. [Heading Callouts](https://github.com/Bluemoondragon07/obsidian-notation-2#heading-callouts)
> 2. [CSS Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#css-classes)
>     1. [Banner Images](https://github.com/Bluemoondragon07/obsidian-notation-2#banner-images)
>     2. [Text Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#text-classes)
>     3. [Other Classes](https://github.com/Bluemoondragon07/obsidian-notation-2#other-classes)
> 3. [Some Other Cool Things](https://github.com/Bluemoondragon07/obsidian-notation-2#some-other-cool-things)
> 4. [Credits](https://github.com/Bluemoondragon07/obsidian-notation-2#credits-)
> 5. [License](https://github.com/Bluemoondragon07/obsidian-notation-2/blob/main/README.md#license)

  

**Notion** has always been one of my favourite apps because of its advanced features, and **Notation** remains one of my favourite Obsidian themes of all time. The original Notation is still a bit broken after 1.0, so I thought I'd make a new theme combining the design elements of Notation with the features of Notion.

With Notation 2, you can experience the power of cover (banner) images, callouts with custom backgrounds, and more (see: **Special Syntax**)

# Special Syntax

## Callout Colors

Callouts are styled to look like Notion callouts by default, with a tranparent background and a faint outline. You can choose the color of any callout with ease: just add the color you want--`red`, `orange`, `yellow`, `green`, `blue`, `purple`, `pink`, `brown`, or `grey`/`gray`--inside the callout type brackets, separated by a `|`.

> Example: `>[!quote|blue]`

![](https://raw.githubu