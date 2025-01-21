- [Overview](Dataview.md##Overview)
	- [How to Use Dataview](Dataview.md##How%2520to%2520Use%2520Dataview)
		- [Data Indexing](Dataview.md##Data%2520Indexing)
		- [Data Querying](Dataview.md##Data%2520Querying)
	- [Resources and Help](Dataview.md##Resources%2520and%2520Help)

# Overview

Dataview is a live index and query engine over your personal knowledge base. You can [[Adding Metadata|Adding Metadata]] to your notes and **query** them with the [[Dataview Query Language|Dataview Query Language]] to list, filter, sort or group your data. Dataview keeps your queries always up to date and makes data aggregation a breeze.

You could

- Track your sleep by recording it in daily notes, and automatically create weekly tables of your sleep schedule.
- Automatically collect links to books in your notes, and render them all sorted by rating.
- Automatically collect pages associated with today's date and show them in your daily note.
- Find pages with no tags for follow-up, or show pretty views of specifically-tagged pages.
- Create dynamic views which show upcoming birthdays or events recorded in your notes

and many more things.

Dataview gives you a fast way to search, display and operate on indexed data in your vault!

Dataview is highly generic and high performance, scaling up to hundreds of thousands of annotated notes without issue.

If the built in [query language](https://blacksmithgu.github.io/obsidian-dataview/query/queries/) is insufficient for your purpose, you can run arbitrary JavaScript against the [dataview API](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) and build whatever utility you might need yourself, right in your notes.

Dataview is about displaying, not editing

Dataview is meant for displaying and calculating data. It is not meant to edit your notes/metadata and will always leave them untouched (... except if you're checking a [Task](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#task-queries) through Dataview.)

## How to Use Dataview

Dataview consists of two big building blocks: **Data Indexing** and **Data Querying**.

More details on the linked documentation pages

The following sections should give you a general overview about what you can do with dataview and how. Be sure to visit the linked pages to find out more about the individual parts.

### Data Indexing

Dataview operates on metadata in your Markdown files. It cannot read everything in your vault, but only specific data. Some of your content, like tags and bullet points (including tasks), are [available automatically](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#implicit-fields) in Dataview. You can add other data through **fields**, either on top of your file [per YAML Frontmatter](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#frontmatter) or in the middle of your content with [Inline Fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#inline-fields) via the `[key:: value]` syntax. Dataview _indexes_ these data to make it available for you to query.

Dataview indexes [certain information](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#implicit-fields) like tags and list items and the data you add via fields. Only indexed data is available in a Dataview query!

For example, a file might look like this:

`--- author: "Edgar Allan Poe" published: 1845 tags: poems ---  # The Raven  Once upon a midnight dreary, while I pondered, weak and weary, Over many a quaint and curious volume of forgotten lore—`

Or like this:

`#poems  # The Raven  From [author:: Edgar Allan Poe], written in (published:: 1845)  Once upon a midnight dreary, while I pondered, weak and weary, Over many a quaint and curious volume of forgotten lore—`

In terms of indexed metadata (or what you can query), they are identical, and only differ in their annotation style. How you want to [annotate your metadata](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) is up to you and your personal preference. With this file, you'd have the **metadata field** `author` available and everything Dataview provides you [automatically as implicit fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/), like the tag or note title.

Data needs to be indexed

In the above example, you _do not_ have the poem itself available in Dataview: It is a paragraph, not a metadata field and not something Dataview indexes automatically. It is not part of Dataviews index, so you won't be able to query it.

### Data Querying

You can access **indexed data** with the help of **Queries**.

There are **three different ways** you can write a Query: With help of the [Dataview Query Language](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline/#dataview-query-language-dql), as an [inline statement](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) or in the most flexible but most complex way: as a [Javascript Query](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#dataview-js).

The **Dataview Query Language** (**DQL**) gives you a broad and powerful toolbelt to query, display and operate on your data. An [**inline query**](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) gives you the possibility to display exactly one indexed value anywhere in your note. You can also do calculations this way. With **DQL** at your hands, you'll be probably fine without any Javascript through your data journey.

A DQL Query consists of several parts:

- Exactly one [**Query Type**](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) that determines what your Query Output looks like
- None or one [**FROM statement**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands#from) to pick a specific tag or folder (or another [source](https://blacksmithgu.github.io/obsidian-dataview/reference/sources/)) to look at
- None to multiple [**other Data Commands**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) that help you filter, group and sort your wanted output

For example, a Query can look like this:

` - [[00 Daily/05/24.05.21.md|24.05.21]]
- [[00 Daily/05/24.05.22.md|24.05.22]]
- [[00 Daily/06/24.06.01.md|24.06.01]]
- [[00 Daily/06/24.06.02.md|24.06.02]]
- [[00 Daily/06/24.06.03.md|24.06.03]]
- [[00 Daily/06/24.06.04.md|24.06.04]]
- [[00 Daily/06/24.06.05.md|24.06.05]]
- [[00 Daily/06/24.06.06.md|24.06.06]]
- [[00 Daily/06/24.06.09.md|24.06.09]]
- [[00 Daily/06/24.06.07.md|24.06.07]]
- [[00 Daily/06/24.06.08.md|24.06.08]]
- [[00 Daily/06/24.06.10.md|24.06.10]]
- [[00 Daily/06/24.06.13.md|24.06.13]]
- [[00 Daily/06/24.06.14.md|24.06.14]]
- [[00 Daily/06/24.06.15.md|24.06.15]]
- [[00 Daily/06/24.06.12.md|24.06.12]]
- [[00 Daily/06/24.06.11.md|24.06.11]]
- [[00 Daily/06/24.06.18.md|24.06.18]]
- [[00 Daily/06/24.06.20.md|24.06.20]]
- [[00 Daily/06/24.06.21.md|24.06.21]]
- [[00 Daily/06/24.06.22.md|24.06.22]]
- [[00 Daily/06/24.06.23.md|24.06.23]]
- [[00 Daily/06/24.06.16.md|24.06.16]]
- [[00 Daily/06/24.06.17.md|24.06.17]]
- [[00 Daily/06/24.06.19.md|24.06.19]]
- [[00 Daily/06/24.06.24.md|24.06.24]]
- [[00 Daily/06/24.06.28.md|24.06.28]]
- [[00 Daily/06/24.06.25.md|24.06.25]]
- [[00 Daily/06/24.06.26.md|24.06.26]]
- [[00 Daily/06/24.06.27.md|24.06.27]]
- [[00 Daily/06/24.06.29.md|24.06.29]]
- [[00 Daily/06/24.06.30.md|24.06.30]]
- [[00 Daily/total.md|total]]
- [[00 Daily/24.07.01.md|24.07.01]]
- [[00 Daily/may.md|may]]
- [[01/Activity History.md|Activity History]]
- [[01/Gallery.md|Gallery]]
- [[01/Diet.md|Diet]]
- [[01/Post.md|Post]]
- [[01/Food table.md|Food table]]
- [[01/Food.md|Food]]
- [[01/Tasks.md|Tasks]]
- [[01/Table.md|Table]]
- [[01/Task Table.md|Task Table]]
- [[02 Projects/Womp.md|Womp]]
- [[02 Projects/Animated character.md|Animated character]]
- [[03/Cara.md|Cara]]
- [[03/Instagram.md|Instagram]]
- [[03/YouTube.md|YouTube]]
- [[04/Code blocks.md|Code blocks]]
- [[04/index.html.md|index.html]]
- [[04/Portfolio.html.md|Portfolio.html]]
- [[08/Plugins/Heatmap Calendar.md|Heatmap Calendar]]
- [[08/Plugins/Note gallery.md|Note gallery]]
- [[08/Plugins/Obsidian Dataview.md|Obsidian Dataview]]
- [[08/Plugins/Obsidian Page Gallery.md|Obsidian Page Gallery]]
- [[08/Plugins/Obsidian Style Settings Plugin.md|Obsidian Style Settings Plugin]]
- [[08/Syntax/Advanced formatting syntax.md|Advanced formatting syntax]]
- [[08/Syntax/Basic formatting syntax.md|Basic formatting syntax]]
- [[08/Syntax/Markdown.md|Markdown]]
- [[08/Syntax/Adding Metadata.md|Adding Metadata]]
- [[08/Syntax/Dataview.md|Dataview]]
- [[08/Syntax/Metadata on pages.md|Metadata on pages]]
- [[08/Syntax/Metadata on Tasks and Lists.md|Metadata on Tasks and Lists]]
- [[08/Syntax/Dataview Query Language.md|Dataview Query Language]]
- [[08/Syntax/DQL, JS and Inlines.md|DQL, JS and Inlines]]
- [[08/Syntax/Data Types.md|Data Types]]
- [[08/Themes/Chime.md|Chime]]
- [[08/Themes/Blue Topaz.md|Blue Topaz]]
- [[08/Themes/Light & Bright.md|Light & Bright]]
- [[08/Themes/PLN.md|PLN]]
- [[08/Themes/README.md|README]]
- [[08/Themes/Vicious.md|Vicious]]
- [[08/Themes/Royal Velvet Obsidian Theme.md|Royal Velvet Obsidian Theme]]
- [[08/Template/Cssclasses.md|Cssclasses]]
- [[08/Template/Daily.md|Daily]]
- [[08/Template/Editing Checklist.md|Editing Checklist]]
- [[06 Skincare/Art&Fact.md|Art&Fact]]
- [[06 Skincare/Icon Skin.md|Icon Skin]]
- [[06 Skincare/New.md|New]]
- [[06 Skincare/Skincare products.md|Skincare products]]
- [[06 Skincare/Onme.md|Onme]]
- [[06 Skincare/Other.md|Other]]
- [[Untitled 1.md|Untitled 1]]
- [[07 YouTube/Random color palette generator  Gradient color palette - Blender 3D Animation.md|Random color palette generator  Gradient color palette - Blender 3D Animation]]
- [[07 YouTube/Scales - Short Blender 3D Animation.md|Scales - Short Blender 3D Animation]]
- [[07 YouTube/Verdant Gecko - Short Blender 3D Animation.md|Verdant Gecko - Short Blender 3D Animation]]
- [[07 YouTube/Birthday Cake Speed Modeling in Blender 3D 🎂 I didn't got the real cake so I modeled one.md|Birthday Cake Speed Modeling in Blender 3D 🎂 I didn't got the real cake so I modeled one]]
- [[07 YouTube/Cute Little Snake Speed Modeling in Blender 3D 🐍 Scales simple particle system.md|Cute Little Snake Speed Modeling in Blender 3D 🐍 Scales simple particle system]]
- [[07 YouTube/Stylized Illustration Speed Modeling in Blender 3D ✏️ Silly doodles drawing process.md|Stylized Illustration Speed Modeling in Blender 3D ✏️ Silly doodles drawing process]]
- [[07 YouTube/Under the ground - Short Blender 3D Animation.md|Under the ground - Short Blender 3D Animation]]
- [[07 YouTube/Isometric Floating Island Speed Modeling in Blender 3D.md|Isometric Floating Island Speed Modeling in Blender 3D]]
- [[07 YouTube/Ground Layers Speed Modeling In Blender 3D 💀 Buried dinosaur skull.md|Ground Layers Speed Modeling In Blender 3D 💀 Buried dinosaur skull]]
- [[99/js table.md|js table]]
- [[99/jsp.md|jsp]]
- [[99/linksjs.md|linksjs]]
- [[99/ReadItLater Plugin for Obsidian.md|ReadItLater Plugin for Obsidian]]
 `

which list all files in your vault.

Everything but the Query Type is optional

The only thing you need for a valid DQL Query is the Query Type (and on [CALENDAR](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types#calendar-queries)s, a date field.)

A more restricted Query might look like this:

`  `

which lists all files in your vault that have the tag `#poems` and a [field](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) named `author` with the value `Edgar Allan Poe`. This query would find our example page from above.

`LIST` is only one out of four [Query Types](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) you can use. For example, with a `TABLE`, we could add some more information to our output:

` | File | author | published | Mentions |
| ---- | ------ | --------- | -------- |
 `

This'll give you back a result like:

|File (3)|author|published|Mentions|
|---|---|---|---|
|The Bells|Edgar Allan Poe|1849||
|The New Colossus|Emma Lazarus|1883|- [[Favorite Poems|Favorite Poems]]|
|The Raven|Edgar Allan Poe|1845|- [[Favorite Poems|Favorite Poems]]|

That's not where the capabilities of dataview end, though. You can also **operate on your data** with help of [**functions**](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/). Mind that these operations are only made inside your query - your **data in your files stays untouched**.

` | File | author | Age in Yrs | Counts of Mentions |
| ---- | ------ | ---------- | ------------------ |
 `

gives you back

|File (3)|author|Age in Yrs|Count of Mentions|
|---|---|---|---|
|The Bells|Edgar Allan Poe|173|0|
|The New Colossus|Emma Lazarus|139|1|
|The Raven|Edgar Allan Poe|177|1|

Find more examples [here](https://blacksmithgu.github.io/obsidian-dataview/resources/examples/).

As you can see, dataview doesn't only allow you to aggregate your data swiftly and always up to date, it also can help you with operations to give you new insights on your dataset. Browse through the documentation to find out more on how to interact with your data.

Have fun exploring your vault in new ways!

## Resources and Help

This documentation is not the only place that can help you out on your data journey. Take a look at [Resources and Support](https://blacksmithgu.github.io/obsidian-dataview/resources/resources-and-support/) for a list of helpful pages and videos.

Made with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)