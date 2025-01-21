---
share: true
---
Just like pages, you can also add **fields** on list item and task level to bind it to a specific task as context. For this you need to use the inline fields - [[./Adding Metadata|Adding Metadata]]:

`- [ ] Hello, this is some [metadata:: value]! - [X] I finished this on [completion:: 2021-08-15].`

Tasks and list items are the same data wise, so all your bullet points have all the information described here available, too.

## Field Shorthands

The [Tasks](https://publish.obsidian.md/tasks/Introduction) plugin introduced a different [notation by using Emoji](https://publish.obsidian.md/tasks/Reference/Task+Formats/Tasks+Emoji+Format) to configure the different dates related to a task. In the context of Dataview, this notation is called `Field Shorthands`. The current version of Dataview only support the dates shorthands as shown below. The priorities and recurrence shorthands are not supported.

Example

Example

- [ ] Due this Saturday 🗓️2021-08-29
- [x] Completed last Saturday ✅2021-08-22
- [ ] I made this on ➕1990-06-14
- [ ] Task I can start this weekend 🛫2021-08-29
- [x] Task I finished ahead of schedule ⏳2021-08-29 ✅2021-08-22

There are two specifics to these emoji-shorthands. First, they omit the inline field syntax (no `[🗓️:: YYYY-MM-DD]` needed) and secondly, they map to a **textual** field name data-wise:

|Field name|Short hand syntax|
|---|---|
|due|`🗓️YYYY-MM-DD`|
|completion|`✅YYYY-MM-DD`|
|created|`➕YYYY-MM-DD`|
|start|`🛫YYYY-MM-DD`|
|scheduled|`⏳YYYY-MM-DD`|

This means if you want to query for all tasks that are completed 2021-08-22, you'll write:

` - [x] Completed last Saturday ✅2021-08-22
- [x] Task I finished ahead of schedule ⏳2021-08-29 ✅2021-08-22
 `

Which will list both variants - shorthands and textual annotation:

`- [x] Completed last Saturday ✅2021-08-22 - [x] Some Done Task [completion:: 2021-08-22]`

## Implicit Fields

As with pages, Dataview adds a number of implicit fields to each task or list item:

Inheritance of Fields

Tasks inherit _all fields_ from their parent page - so if you have a `rating` field in your page, you can also access it on your task in a `TASK` Query.

|Field name|Data Type|Description|
|---|---|---|
|`status`|Text|The completion status of this task, as determined by the character inside the `[ ]` brackets. Generally a space `" "` for incomplete tasks and an `"x"` for completed tasks, but allows for plugins which support alternative task statuses.|
|`checked`|Boolean|Whether or not this task's status is **not** empty, meaning it has some `status` character (which may or may not be `"x"`) instead of a space in its `[ ]` brackets.|
|`completed`|Boolean|Whether or not this _specific_ task has been completed; this does not consider the completion or non-completion of any child tasks. A task is explicitly considered "completed" if it has been marked with an `"x"`. If you use a custom status, e.g. `[-]`, `checked` will be true, whereas `completed` will be false.|
|`fullyCompleted`|Boolean|Whether or not this task and **all** of its subtasks are completed.|
|`text`|Text|The plain text of this task, including any metadata field annotations.|
|`visual`|Text|The text of this task, which is rendered by Dataview. This field can be overriden in DataviewJS to allow for different task text to be rendered than the regular task text, while still allowing the task to be checked (since Dataview validation logic normally checks the text against the text in-file).|
|`line`|Number|The line of the file this task shows up on.|
|`lineCount`|Number|The number of Markdown lines that this task takes up.|
|`path`|Text|The full path of the file this task is in. Equals to `file.path` for [pages](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/).|
|`section`|Link|Link to the section this task is contained in.|
|`tags`|List|Any tags inside the task text.|
|`outlinks`|List|Any links defined in this task.|
|`link`|Link|Link to the closest linkable block near this task; useful for making links which go to the task.|
|`children`|List|Any subtasks or sublists of this task.|
|`task`|Boolean|If true, this is a task; otherwise, it is a regular list element.|
|`annotated`|Boolean|True if the task text contains any metadata fields, false otherwise.|
|`parent`|Number|The line number of the task above this task, if present; will be null if this is a root-level task.|
|`blockId`|Text|The block ID of this task / list element, if one has been defined with the `^blockId` syntax; otherwise null.|

With usage of the [shorthand syntax](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands), following additional properties may be available:

- `completion`: The date a task was completed.
- : The date a task is due, if it has one.
- `created`: The date a task was created.
- `start`: The date a task can be started.
- `scheduled`: The date a task is scheduled to work on.

### Accessing Implicit Fields in Queries

If you're using a [TASK](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#task-queries) Query, your tasks are the top level information and can be used without any prefix:

` - [-] Buy vinegar
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
    - 0% cottage cheese - 300g
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [x] Install
    - [x] Milanote
    - [x] Rnote
    - [-] Mural
    - [x] tldraw
    - [-] AFFiNE
    - [x] Goodnotes
    - [-] Figma
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Breakfast
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Breakfast
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] [[Blender 4.2 Portals using the Ray Portal node!]]
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [-] Log meals to **필라이즈**
- [8] (27+27+12)/2=33 ^39c68f
- [x] download [[Maya]]
    - [-] install Redshift
- [x] install [[Houdini]]
    - [-] Arnold for Houdini
- [m] A little "poem": > I was playing the piano, Playing guitar, drums, and tennis I was swimming, running, fighting Rode the bike and skateboard.
- [U] [[Salicylic Acid 2% + Urea 2% + Panthenol 2%]]
- [k] [[Art&Fact Lactobionic Acid 1% + Lactic Acid 2% + Hyaluronic Acid 0.1%]]
- [U] [[Salicylic Acid 2% + Licorice Root Extract 3%]]
- [U] [[Probiotic Complex + Ceramide NG]]
- [U] [[Niacinamide 5% + Retinol ,4% + Lactic Acid + Complex Of Amino Acids]]
- [k] [[Vitamin C 15% + Rosmarinus Officinalis Water 1% + Argireline 0,5% + Aloe Barbadensis Leaf Juice 0,5%]]
- [U] [[Matmarine 4% + Niacinamide 2% + Urea 2%]]
- [U] [[Azelaic Acid Derivative]]
- [ ] [[3D Hyaluronic Acid]]
- [ ] [[Caffeine 3%]]
- [ ] [[Retinol o,3% + Retinyl Palmitate o,3% + Caffeine 0,5%]]
- [r] [[Salicylic Acid 2% + Zinc Oxide 0.5% + Hemisqualane 0.5% + Allantoin 0.2%]]
- [n] [[SPF 5O+]]
- [n] [[SPF 30+]]
- [r] [[Blue Retinol 3% + Shea Butter 2% + Retinol 1.5%]]
- [ ] [[Galactomyces Ferment Filtrate 7% + Green Tea Extract 3%]]
- [ ] [[Lactobionic Acid 3% + Lactic Acid 5% + Avocado Oil 0.5%]]
- [ ] [[Glycine Soja Oil 3% + Macadamia Ternifolia Seed Oil 0.8% + Niacinamide 0.5% + Rhodiola Extract]]
- [o] [[Propolis Extract 10% + Shea Butter 3% + Urea 1% + Niacinamide 0.5%]]
- [ ] [[SYN-AKE 3% + Lecithin 3% + Hyaluronic Acid + Plant Extracts]]
- [ ] [[Prebiotic Complex + Niacinamide 1.5%]]
- [k] [[Retinol 1% + Collagen 1% + Beeswax 3%]]
- [ ] [[Collagen + Palmitoyl Tripeptide-1 +Chlorella Extract]]
- [ ] [[Aloe Barbadensis Leaf Gel 4% + Niacinamid 3% + Vitamin C 2% + Lactic Acid 0.3% + Menthol]]
- [ ] [[Amono Acid Complex 2% + Vegetable Carbohydrates 1%]]
- [ ] [[Azulene 0.3% + Extract Complex + D-Pantenol]]
- [ ] [[Kaolin 5% + Lactic Acid 10% + Glycolic Acid 1%+ Tea Tree Essential Oil 0,1%]]
- [ ] [[Kaolin + Curcuma Extract + Calendula Extract]]
- [ ] [[Kaolin + Kojic Acid 1% + Niacinamide 1%]]
- [k] [[Kaolin 11,5% + Niacinamide 2% + Sulfur 1,5% + Mandelic Acid + Lactic Acid]]
- [r] [[Mandelic Acid 10%]]
- [ ] [[Gluconolactone 1% + Niacinamide 1% + Aloe Barbadensis Leaf Juice 1,5%]]
- [ ] [[Glycolic Acid 15% + Gluconolactone 3% + Lactic Acid 3% + Salicylic Acid 2%]]
- [ ] [[Glycolic Acid 10% + Salicylic Acid 0,5% + Lactic Acid]]
- [k] [[Papain 5% + Allantoin 0.5%]]
- [ ] Herbal Power Balancing Tonic ![[IS Toner.webp]]
- [ ] Aqua Recovery Hyaluronic Mineral Serum ![[IS Serum (1).jpg]]
- [ ] Aqua Balance Moisturizing Fluid ![[IS Cream.png]]
- [n] Aqua Eccence Hyaluronic & Peptide Fluid ![[IS (1).jpg]]
- [k] Aqua Recovery Hyaluronic Mineral Cream ![[IS (6).webp]]
- [ ] Glow Skin Exfoliating Enzyme Mask ![[IS (10).jpeg]]
- [ ] 12% AHA+BHA Smart Peel System ![[IS (4).webp]]
- [ ] 15% Acid Mix & Vitamin C Smart Peel System ![[IS (8).webp]]
- [k] 7 Herbs Enzyme Cleansing Powder ![[IS Powder.webp]]
- [k] Vitamin C Shine Enzyme Cleansing Powder ![[IS Powder.jpg]]
- [ ] Пенка Бергамот + Мята ![[OnMe (1).webp]]
- [n] Флюил Для Снятия Макияжа
- [k] Гидрофильный Гель
- [k] Тоник Увлажняющий Роза + Алоэ
- [ ] Обновляющая Маска Койевая Кислота + Ниацинамид ![[OnMe (7).png]]
- [o] Востанавливающая Маска Сквалан + Церамиды ![[OnMe (6).png]]
- [k] Тонизирующая Маска Лайм + Мята ![[OnMe (5).png]]
- [r] Тонизирующее Молочко Для Тела Апельсян + Грейпфрут
- [ ] [[Shine Is Niacinamide 10% + Retinol o.1%]]
- [ ] Tretinoin Gel UPS o.1% ![[Retinol (2).webp]]
- [k] Aravia Anti-Acne Corrective Essence ![[Aravi (7).webp]]
- [k] [[Laboratorium Ceramides Mask]]
- [k] Aravia Anti-Acne Intensive ![[Aravi (4).webp]]
- [k] Aravia Post-Acne Balance Mask ![[Aravi (5).webp]]
- [k] Shades Of You
- [ ] U In use
- [k] k To use
- [r] r Opened
- [n] n Dont use
- [o] o Second Use
- [l] l Fav
- [ ] [[Rigid Body Dynamics]]
- [ ] [[Geometry Nodes For Beginners - Blender 3D]]
- [ ] [[CGI for Product Advertising]]
- [ ] [[Introduction to Show Titles Design - By Crossmind Studio]]
- [ ] [[Animated Content Creation]]
- [ ] [[Mantaflow]]
- [ ] [[Modeling for Animation!]]
- [ ] [[Rigging Characters in Blender]]
- [ ] [[Get Good at Blender 2.8]]
- [ ] [[Stylized Character Bust]]
- [ ] [[Game Ready 3D Enemy Minion]]
- [ ] [[Maya 2024 Course]]
- [ ] timelapse
- [ ] render
- [ ] edited video
- [ ] post on social media - [ ] Instagram - [ ] YouTube - [ ] Twitter - [ ] Cara - [ ] [[Portfolio]] - [ ] [[Artstation]] - [ ] The Rookies [High-Five all the amazing entries to Meet Mat 4!](https://www.therookies.co/contests/groups/meet-mat-4/entries)
- [-] remake lighting
- [-] add animation smears
    - [-] motion blur
- [-] timelapse
- [-] edited video
- [-] The Rookies
- [ ] timelapse
- [ ] render
- [ ] edited video
- [ ] post on social media
    - [ ] IG
    - [ ] YouTube
    - [ ] Twitter
    - [ ] Cara
- [ ] The Rookies
- [8] Meet Mat Animation  ![|200](https://d3stdg5so273ei.cloudfront.net/mashroomash/2024-10-22/770038/1400xAUTO/027-mashroomash.jpg)
- [-] stop mo
- [X] Shadows
    - Rays: 4
    - Steps: 12
    - [ ] Volume Shadows
        - Steps: 16
    - Resolution: 1.000
- [ ] Denoising
- [(] Hard to change smth
- [)] Fluid
- [)] Spontaneous
- [)] Faster method for complicated motion
- [)] Easier to adjust
- [(] Can feel rigid
- [8] We can simplify all the little ideas about animation to the 3 most important ideas:
- [ ] I've always felt that there is something wrong with me.
- [-] I have relationship and intimacy problems.
- [-] I tend to get through things rather than experience and or enjoy them. (Vacations, Holidays, Projects, Shopping, Gatherings)
- [-] Dysfunctional people seek me out.
- [-] Being wrong and or right means too much to me.
- [ ] I can get into certain modes. (survival mode, work mode, rescue mode, emergency mode).
- [-] When things are going well, I don’t trust it.
- [-] Growing up, my parent(s) were rageful, volatile, dominating, depressed, unavailable or neurotic.
- [-] Growing up, there was manipulation and or injustice.
- [-] Growing up, I experienced corporal punishment.
- [-] I get upset when others don’t read what is going on with me.
- [ ] I can overpower or shut down during conflict.
- [ ] I’ve been told I’m intense (too serious), or disengaged (aloof).
- [ ] I anticipate that other people will be upset with me and or that they will let me down.
- [-] I can be greatly affected by other people’s moods.
- [-] Compliments make me uncomfortable and I minimize them.
- [ ] Rejection puts me in a very bad place.
- [-] I can often view myself based on the way people react or respond to me.
- [-] When someone is caring or nurturing I question it and feel uncomfortable.
- [-] I can often feel used or taken advantage of.
- [-] I often do not trust my own feelings or the feelings of others.
- [-] I can be reactive or deeply affected by criticism (any kind).
- [-] I feel that I’m not worthwhile unless I’m a satisfactory lover.
- [ ] Growing up, things were not talked about. (emotions, situations, elephants in the room).
- [-] I’ve felt inadequate about my gender.
- [ ] I don't like being touched.
- [ ] I’ve only ended relationships once things get very bad.
- [-] I’m perfectionistic and or rigid.
- [ ] Growing up I had feelings about killing one or both my parents which caused shame.
- [-] One or both my parents overly confided in me growing up about their problems.
- [ ] Angry people and people in authority freak me out.
- [ ] I tend to think about my feelings v. feeling them fully.
- [-] Speaking up about my needs/preferences or saying no, is difficult for me.
- [ ] [[24.08.August]]
- [ ] ```dataview Task WHERE contains(file.name, "August") group by completed ```
- [ ] [[24.09.September]]
- [ ] ```dataview Task WHERE contains(file.name, "September") group by completed ```
- [ ] [[24.10.October]]
- [ ] ```dataview Task WHERE contains(file.name, "October") group by completed ```
- [ ] [[24.11.November]]
- [ ] ```dataview Task WHERE contains(file.name, "November") group by completed ```
- [ ] [[24.12.December]]
- [ ] ### December ```dataview Task WHERE contains(file.name, "December") group by completed ```
- [ ] [[2024]]: [[24.09.September]]
- [k] [[Maya Statue]]
- [k] read [[The Hitchhiker's Guide to Digital Colour]]
- [ ] [[2024]]: [[24.08.August]] - [[24.10.October]]
- [-] [[Character Design Contest]]
- [ ] Chita Skull - [[2024-W38#24.09.18]]
    - [ ] Retopology [[2024-W38#24.09.21]]  -
    - [-] Sceen
    - [-] Texture
    - [-] Animation
    - [-] Timelapse
- [ ] [[2024-W37#24.09.14]] - [[3D USD Masterclass Scene Assembly and Rendering]]
- [ ] [[2024-W37#24.09.14]] - [[W40]] [[Get Good at Blender 2.8]]
- [ ] [[2024]]: [[24.09.September]] - [[24.11.November]] 
- [ ] [[2024]]: [[24.10.October]] - [[24.12.December]]
- [ ] [[How To Animate in Toon Boom Harmony (Full Class w⧸ Q&A)]]
- [ ] [[Sculptober]]
- [ ] [[Brain threads]]
- [ ] [[2024]]: [[24.11.November]] - [[25.01.January]]
- [ ] [[Brain threads]]
- [ ] [[Sculptober]]
- [ ] [[24.12.December]] -
- [ ] [[Sculptober]]
- [ ] [[Brain threads]]
- [ ] [[Demo reel dash]]
- [ ] [[Easy Vox Infographic Animation (After Effects Tutorial)]]
- [ ] [[How To Animate Infographics Like VOX (After Effects Tutorial)]]
- [ ] [[How To Make A Collage Animation (After Effects Tutorial)]]
- [ ] [[How To Animate in Toon Boom Harmony (Full Class w⧸ Q&A)]]
- [ ] [[How To Animate in Clip Studio Paint - Tutorial for Beginners]]
- [ ] [[2D FX GEOMETRIC SLASH TUTORIAL (ToonBoom)]]
- [ ] [[2D FX STAR EXPLODE TUTORIAL (ToonBoom)]]
- [ ] [[2DFX BUBBLES TUTORIAL ToonBoom]]
- [ ] [[2DFX INFINITE FIGHT TUTORIAL (ToonBoom)]]
- [ ] [[2DFX ORB TUTORIAL (ToonBoom)]]
- [ ] [[Phoerens]] character creation series
    - [ ] Sculpting
    - [ ] Retopology
    - [ ] Texturing
- [ ] [[3D USD Masterclass Scene Assembly and Rendering]]
- [ ] [[Get Good at Blender 2.8]]
- [ ] [[How to Improve Your 3D Presentations]]
- [ ] [[3D USD Masterclass Scene Assembly and Rendering.Note]]
- [ ] [[The Ultimate Guide to Arnold Rendering - InFocus Film School]]
- [ ] [[To Read]]
- [ ] [[Beginners guide to XGen pipeline]]
- [ ] [[ImagineFX]] Latest issue
- [ ] [[The Hitchhiker's Guide to Digital Colour]]
- [ ] [[PBR Guide]]
- [ ] [[The Toolbag Baking Tutorial - Marmoset]]
- [ ] watch [[LuxCore Render for Blender]] playlist
    - [ ] watch 2 [[LuxCore shaders]] tutorials
- [ ] [[Tutorial Cartoon head in Blender (A to Z)]]
- [x] TG
    - [x] Houdini
        - [-] Arnold
    - [x] Maya
        - [-] Redshift
        - [-] Octane
- [x] After effects EXR tutorial
    - [x] compositing tutorial
    - [-] hard surface modeling with substance painter time-lapse
- [x] Install Octane for Blender
    - [-] check if it works without internet
    - [-] download playlist
- [-] find IG accaunts to copy
- [x] upload some projects to The Rookies
    - [-] Find some 3d challenges
- [-] Sort pictures
    - [-] past to Obsidian articles
    - [-] make playlists
- [-] download Motion Beast course
- [x] Download
    - [x] AgX OCIO
        - [x] for Blender
    - [-] Color Picker (Foregrounh Color, 32-bit)
    - [x] ACES tutorial from VFX tutorial guy
    - [-] 2 videos from ACES for Substance Painter
- [-] change Maya mouse battons
- [-] Epicura.com
- [-] pepsi
- [-] shotgrid
- [-] canvas
- [x] edit [[Blender donut]] video
    - [x] fix and render animation
    - [x] make thumbnails
    - [x] write a description
    - [-] render wireframe
- [ ] [[Character Design Contest]]
- [ ] [[Meet Mat 4]]
- [ ] [[Sculptober]]
- [ ] [[Creature]]
- [ ] May 2024
- [ ] 2023 09
- [ ] 296 - 2023
    - [x] Portrait ➕ 2024-09-20
    - [x] Mask ➕ 2024-09-24
- [ ] 299
- [ ] 301
- [ ] 303
- [ ] 305
- [ ] 306 - 2023
    - [ ] Houdini
    - [x] Stylized character ➕ 2024-09-20
    - [x] Modeling portfolio ➕ 2024-09-23
- [ ] 307 - 2024
- [ ] 308
- [ ] 309
    - [ ] Game asset
    - [ ] Reptilian creature
    - [ ] Render engines
- [ ] 310
- [ ] 311 - 05
    - [ ] Animal
    - [x] A character with stylized texturing ➕ 2024-09-23
    - [ ] Still-life
- [ ] 312 - June
- [ ] 313 - July
- [ ] 314 - August
    - [ ] Witch
- [ ] 224
- [ ] 225
- [ ] 226
- [ ] 227
- [ ] 228
- [ ] 229
- [ ] 230
- [ ] 231
- [ ] 232
- [ ] 233 - Xmas
- [ ] 234
- [ ] 235
- [ ] 237
- [ ] 240 - July
- [ ] 241 - [[24.08.August]]
- [ ] 242 - September
- [ ] 243 - October
- [ ] [[Animation exercises]]
- [ ] [[Cinema 4D Free Course – Part 1 Modeling and Rigging]]
- [ ] [[How to Animate in Blender Learning the Basics]]
- [ ] [[01 Maps/YouTube/Playlist/Animation|Animation]]
- [ ] [[Alex on Story]]
- [ ] [[Modeling For Animation 01 - TOP 5 Features of Good Animation Models!]]
- [ ] [[How To Animate in Toon Boom Harmony (Full Class w⧸ Q&A)]] ➕ 2024-11-03
- [ ] [[How To Animate in Clip Studio Paint - Tutorial for Beginners]]
- [ ] [[2D FX GEOMETRIC SLASH TUTORIAL (ToonBoom)]]
- [ ] [[2D FX STAR EXPLODE TUTORIAL (ToonBoom)]]
- [ ] [[2DFX BUBBLES TUTORIAL ToonBoom]]
- [ ] [[2DFX INFINITE FIGHT TUTORIAL (ToonBoom)]]
- [ ] [[2DFX ORB TUTORIAL (ToonBoom)]]
- [ ] [[Introduction to Show Titles Design - By Crossmind Studio]]
- [ ] [[Animated Content Creation]]
- [ ] [[CGI for Product Advertising]]
- [ ] [[Brain threads]]
- [ ] [[Artistic Anatomy of the Skull (Full Course)]]
- [ ] [[Phoerens]] character creation series
    - [ ] Sculpting
    - [ ] Retopology
    - [ ] Texturing
- [ ] [[Phoerens]]  character sculpting series
- [ ] [[The Creature Design Workshop]] series
- [ ] [[Tutorial Cartoon head in Blender (A to Z)]]
- [ ] [[Stylized Character Bust]]
- [ ] [[Modeling for Animation!]]
- [ ] [[The Ultimate Guide to Character Modelling!]]
- [ ] [[Rigging Characters in Blender]]
- [ ] rigging in maya
- [ ] [[Game Ready 3D Enemy Minion]] series
- [ ] [[How to Create a Great 3D Character Artist Portfolio]]
- [x] [[Realistic Character Design - Techniques You Need to Know]]
    - [ ] [[Beginners guide to XGen pipeline]]
- [ ] [[SPACE CADET BLENDER TUTORIAL  AENDOM]]
- [ ] [[Color Management for CGI Artists]] ➕ 2024-08-06
    - [ ] [[The Hitchhiker's Guide to Digital Colour]]
- [ ] [[Get Good at Blender 2.8]] ➕ 2024-08-08
- [ ] [[BLENDER & SUBSTANCE PAINTER MEDICINE CABINET]]
- [ ] [[3D Modeling & Rendering - LOWPOLY ENVIRONMENT in BLENDER]]
- [ ] [[3D  Lowpoly PBR Game Asset Creation (Timelapse) in Blender 3D and Substance Painter]]
- [ ] [[SIMPLE 3D Modeling and Rendering in Blender 3.5 - 3D Lowpoly Modeling]]
- [ ] [[(Timelapse) Simple Day & Night Low Poly Scenes in Blender & Unity - Blender Speed Low Poly Models]]
- [ ] [[Sculptober]]
- [ ] [[Phoerens]]
    - [ ] character sculpting series
    - [ ] creature sculpting series
- [ ] [[Tutorial Sculpting Mouths in ZBrush  Step by Step]]
- [ ] [[Full 3D Modeling Workflow  Autodesk Maya + Substance 3D Painter]]
- [ ] [[Biologic Field Tester  Autodesk Maya + Substance 3D Painter]]
- [ ] [[Command HQ  Autodesk Maya + Substance 3D Painter]]
- [ ] [[Texture a Game Asset in Substance Painter]]
- [ ] [[Blender Beginners Tutorial - Modeling & Unwrapping a game ready Flashbang]]
    - [ ] Blender
    - [ ] Marmoset
- [ ] [[blender hard surface modeling and animation Tutorial  - USB FLASH]]
- [ ] [[blender hard surface modeling - pistol]]
- [ ] [[Blender Hard surface Modeling Tutorial - Wireless Earbuds]]
- [ ] [[Hard Surface Basics  ZBrush Tutorial]]
- [ ] [[Brain threads]]
- [x] [[Texture Baking - Blender 3d vs. Substance Painter vs. Marmoset Toolbag]]
    - [ ] read [[The Toolbag Baking Tutorial - Marmoset]]
- [ ] [[Quick tips Creating displacement from images]]
- [ ] [[PBR Guide]]
- [ ] [[Beginners guide to Procedural shading]]
- [ ] [[LearnOpenGL - Theory]]
- [ ] [[Easy Vox Infographic Animation (After Effects Tutorial)]]
- [ ] [[How To Animate Infographics Like VOX (After Effects Tutorial)]]
- [ ] [[How To Make A Collage Animation (After Effects Tutorial)]]
- [ ] read [[Fusion 18 manual]]
- [x] [[Get good at Blender]] ✅ 2024-07-05
    - [ ] [[Get good at Blender 2.8]] ➕ 2024-08-08
- [ ] [[LuxCore shaders]]
- [ ] [[LuxCore Render for Blender]] playlist
- [ ] [[Rigid Body Dynamics]]
- [ ] [[Mantaflow]]
- [ ] [[3D USD Masterclass Scene Assembly and Rendering]]  2024-09-14
- [ ] [[Full VFX Course - Houdini Is Hip]] playlist
- [ ] [Blender user tries Houdini for the first time, starring Christopher Rutledge](https://www.youtube.com/watch?v=zylBiBqN5jQ)
- [ ] [[Creating a Mega Character]]
- [ ] [[Marmoset Toolbag 4]]
- [ ] [[Marmoset Toolbag 4 Beginners Tutorial - Baking & Texturing a game ready Flashbang!]]
- [ ] [[The Toolbag Baking Tutorial - Marmoset]]
- [ ] LookDev
- [ ] [[Natron Compositor Tutorials]] playlist
- [ ] [[Getting Started with Substance Painter 2021]] playlist
- [ ] [[Zbrush Sculpting  Base Female Face Forms]] ✅ 2024-09-20
- [ ] [[Tutorial Sculpting Mouths in ZBrush  Step by Step]]
- [ ] [[Hard Surface Basics  ZBrush Tutorial]]✅ 2024-09-26
- [ ] 
- [ ] 
- [ ] u
- [ ] 
- [ ] timelapse #todo
- [ ] render #todo
- [ ] edited video #todo
- [ ] [[Instagram]] #todo
- [ ] [[Resting Pieces]] #todo
- [ ] Twitter #todo
- [ ] [[Cara]] #todo
- [ ] [[07/The Rookies]] #todo
- [ ] [[Artstation]] #todo
- [ ] [[Portfolio]] #todo
- [ ] plant house - a complex scene
- [ ] wilder girls
    - [ ] a complex scene
    - [ ] character modeling practise
- [ ] puppets
    - [ ] Don't hug me I'm scared
    - [ ] stop motion
- [ ] brain threads - nodes?
- [ ] resting pieces - logo
- [ ] my room - modeling practise
- [ ] Pokemons
- [ ] Realistic Still Life
- [ ] Hard surface
- [ ] Customize graph colors
- [ ] More chart types
- [ ] Export data
- [ ] Import data
- [ ] This is an incomplete task.
- [ ] Task item 1
    - [ ] Subtask 1
- [ ] Task item 2
    - [ ] Subtask 1
- [ ] Buy new shoes # shopping
- [ ] Mail Paul about training schedule
- [ ] Finish the math assignment
    - [x] Finish Paper 1 [due:: 2022-08-13]
    - [ ] Read again through chapter 3 [due:: 2022-09-01]
    - [x] Write a cheatsheet [due:: 2022-08-02]
    - [ ] Write a summary of chapter 1-4 [due:: 2022-09-12]
- [ ] Get new pillows for mom # shopping
- [ ] Buy new shoes # shopping
- [ ] Get new pillows for mom # shopping
- [ ] Finish the math assignment
    - [ ] Read again through chapter 3 [due:: 2022-09-01]
    - [ ] Write a summary of chapter 1-4 [due:: 2022-09-12]
- [ ] Buy new shoes # shopping
- [ ] Mail Paul about training schedule
- [ ] Get new pillows for mom # shopping
- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]
- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]
- [ ] Call the insurance about the car
- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]
- [ ] Call the insurance about the car
- [ ] Bedroom [urgent:: true]
- [ ] Due this Saturday 🗓️2021-08-29
- [ ] I made this on ➕1990-06-14
- [ ] Task I can start this weekend 🛫2021-08-29
- [ ] 
- [ ] [do not binge](Daily.md)
- [ ] [Morning skincare](AM.png)
- [ ] Work on a #3D/project
- [ ] #post/3D on [[Cara]]
- [ ] #post/3D on [[Instagram]]
- [ ] 
- [ ] 
- [ ] 
- [ ] timelapse
- [ ] render
- [ ] edited video
- [ ] post on social media
    - [ ] Instagram
    - [ ] YouTube
    - [ ] Twitter
    - [ ] Cara
    - [ ] [[Portfolio]]
    - [ ] [[Artstation]]
        - [ ] The Rookies
- [ ] 
 `

For every other Query type, you first need to access the implicit field `file.lists` or `file.tasks` to check for these list item specific implicit fields:

` - [[00 Daily/06/2024-06-03.md|2024-06-03]]
- [[00 Daily/07/2024-07-08.md|2024-07-08]]
- [[00 Daily/07/2024-07-09.md|2024-07-09]]
- [[00 Daily/07/2024-07-10.md|2024-07-10]]
- [[00 Daily/07/2024-07-11.md|2024-07-11]]
- [[00 Daily/07/2024-07-12.md|2024-07-12]]
- [[00 Daily/07/2024-07-13.md|2024-07-13]]
- [[00 Daily/07/2024-07-14.md|2024-07-14]]
- [[00 Daily/07/2024-07-16.md|2024-07-16]]
- [[00 Daily/07/2024-07-15.md|2024-07-15]]
- [[00 Daily/07/2024-07-19.md|2024-07-19]]
- [[00 Daily/07/2024-07-20.md|2024-07-20]]
- [[00 Daily/07/2024-07-18.md|2024-07-18]]
- [[00 Daily/07/2024-07-21.md|2024-07-21]]
- [[00 Daily/07/2024-07-17.md|2024-07-17]]
- [[00 Daily/07/2024-07-22.md|2024-07-22]]
- [[00 Daily/07/2024-07-23.md|2024-07-23]]
- [[00 Daily/07/2024-07-24.md|2024-07-24]]
- [[00 Daily/07/2024-07-25.md|2024-07-25]]
- [[00 Daily/07/2024-07-26.md|2024-07-26]]
- [[00 Daily/07/2024-07-27.md|2024-07-27]]
- [[00 Daily/07/2024-07-29.md|2024-07-29]]
- [[00 Daily/07/2024-07-28.md|2024-07-28]]
- [[00 Daily/07/2024-07-30.md|2024-07-30]]
- [[00 Daily/07/2024-07-31.md|2024-07-31]]
- [[00 Daily/08/2024-08-01.md|2024-08-01]]
- [[00 Daily/08/2024-08-02.md|2024-08-02]]
- [[00 Daily/08/2024-08-05.md|2024-08-05]]
- [[00 Daily/08/2024-08-20.md|2024-08-20]]
- [[00 Daily/11/2024-11-19.md|2024-11-19]]
- [[02 Review/Skincare/Art&Fact.md|Art&Fact]]
- [[02 Review/Skincare/Icon Skin.md|Icon Skin]]
- [[02 Review/Skincare/Onme.md|Onme]]
- [[02 Review/Skincare/Other.md|Other]]
- [[02 Review/Skincare/Skincare products.md|Skincare products]]
- [[01 Maps/YouTube/Channels/CrossMind Studio.md|CrossMind Studio]]
- [[01 Maps/YouTube/Channels/Dikko.md|Dikko]]
- [[01 Maps/YouTube/Channels/Grant Abbitt.md|Grant Abbitt]]
- [[01 Maps/YouTube/Channels/Nexttut.md|Nexttut]]
- [[04 Projects/Brain threads.md|Brain threads]]
- [[04 Projects/Done/Blender Donut.md|Blender Donut]]
- [[04 Projects/Done/Maya Statue.md|Maya Statue]]
- [[04 Projects/To-Do/Demo Reel.md|Demo Reel]]
- [[04 Projects/Portfolio/Meet Meat.md|Meet Meat]]
- [[04 Projects/Portfolio/Talking Head.md|Talking Head]]
- [[05 Notes/3D/Eevee settings.md|Eevee settings]]
- [[05 Notes/Animation/Should you PLAN your animation.Note.md|Should you PLAN your animation.Note]]
- [[05 Notes/Animation/The Three Biggest Ideas in Animation.Note.md|The Three Biggest Ideas in Animation.Note]]
- [[05 Notes/Mental/CHILDHOOD PTSD QUESTIONNAIRE.md|CHILDHOOD PTSD QUESTIONNAIRE]]
- [[06 Plan/01/Months.md|Months]]
- [[06 Plan/02/24.08.August.md|24.08.August]]
- [[06 Plan/02/24.09.September.md|24.09.September]]
- [[06 Plan/02/24.10.October.md|24.10.October]]
- [[06 Plan/02/24.11.November.md|24.11.November]]
- [[06 Plan/02/24.12.December.md|24.12.December]]
- [[06 Plan/02/25.01.January.md|25.01.January]]
- [[06 Plan/03/2024-W34.md|2024-W34]]
- [[06 Plan/03/2024-W35.md|2024-W35]]
- [[06 Plan/03/2024-W36.md|2024-W36]]
- [[06 Plan/03/2024-W37.md|2024-W37]]
- [[06 Plan/04/Contests.md|Contests]]
- [[06 Plan/04/To Read.md|To Read]]
- [[06 Plan/05/00/Animation.md|Animation]]
- [[06 Plan/05/00/Characters.md|Characters]]
- [[06 Plan/05/00/Compositing.md|Compositing]]
- [[06 Plan/05/00/Modeling.md|Modeling]]
- [[06 Plan/05/00/Sculpting.md|Sculpting]]
- [[06 Plan/05/01/Hard Surface.md|Hard Surface]]
- [[06 Plan/05/01/Textures.md|Textures]]
- [[06 Plan/05/02/After Effects.md|After Effects]]
- [[06 Plan/05/02/Blackmagic Fusion.md|Blackmagic Fusion]]
- [[06 Plan/05/02/Blender 3D.md|Blender 3D]]
- [[06 Plan/05/02/Houdini.md|Houdini]]
- [[06 Plan/05/02/Marmoset Toolbag.md|Marmoset Toolbag]]
- [[06 Plan/05/02/Maya.md|Maya]]
- [[06 Plan/05/02/Natron.md|Natron]]
- [[06 Plan/05/02/Substanse painter.md|Substanse painter]]
- [[06 Plan/05/02/ZBrush.md|ZBrush]]
- [[06 Plan/06/Goal.md|Goal]]
- [[06 Plan/06/Kanban.md|Kanban]]
- [[06 Plan/06/Month.md|Month]]
- [[06 Plan/06/Project.md|Project]]
- [[06 Plan/Ideas.md|Ideas]]
- [[08/Plugins/Mood Tracker.md|Mood Tracker]]
- [[08/Syntax/Basic formatting syntax.md|Basic formatting syntax]]
- [[08/Syntax/Dataview Query Language.md|Dataview Query Language]]
- [[08/Syntax/Metadata on Tasks and Lists.md|Metadata on Tasks and Lists]]
- [[99/Template/Channel.md|Channel]]
- [[99/Template/Daily.md|Daily]]
- [[99/Template/Goal.md|Goal]]
- [[99/Template/Plan.md|Plan]]
- [[99/Template/Project.md|Project]]
- [[99/Template/Month.md|Month]]
 `

This will give you back all the file links that have unfinished tasks inside. We get back a list of tasks on page level and thus need to use a [list function](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/) to look at each element.