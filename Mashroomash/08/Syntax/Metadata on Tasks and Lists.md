Just like pages, you can also add **fields** on list item and task level to bind it to a specific task as context. For this you need to use the [inline field syntax](Metadata%2520on%2520Tasks%2520and%2520Lists.md##Inline%2520Fields):

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
- `due`: The date a task is due, if it has one.
- `created`: The date a task was created.
- `start`: The date a task can be started.
- `scheduled`: The date a task is scheduled to work on.

### Accessing Implicit Fields in Queries

If you're using a [TASK](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#task-queries) Query, your tasks are the top level information and can be used without any prefix:

` - [ ] Buy vinegar
- [x] Log meals to **필라이즈**
    - [-] Post on Twitter
- [x] Log meals to **필라이즈**
    - [-] Post on Twitter
- [ ] [do not binge](Daily.md)
- [ ] Breakfast
- [ ] Log meals to **필라이즈**
- [ ] [Morning skincare](AM.png)
- [ ] Work on a #3D/project
- [ ] [Evening skincare](PM.png)
- [ ] #post/3D on [[Cara]]
- [ ] #post/3D on [[Instagram]]
- [ ] render props / outfits
- [ ] #post/3D props render
- [ ] #post/3D turnaround
- [-] Add rigg
    - [-] change the pose
    - [-] make walking animation
- [ ] This is an incomplete task.
- [ ] Task item 1
    - [ ] Subtask 1
- [ ] Task item 2
    - [ ] Subtask 1
- [ ] Todo
- [-] Cancelled
- [r] r Important
- [l] l Info
- [n] n Noinfo
- [o] o Other
- [k] k Kancelled
- [U] U Unchecked
- [)] ) Good
- [:] : Pin
- [(] ( Bad
- [}] } High
- [=] = Normal
- [{] { Low
- [?] ? Question
- [*] ** Star
- [!] ! Important
- [>] Forward
- [<] Backward
- [/] / Pause
- [+] +Upward
- [_] _ Downward
- [%] % Recurring
- [&] & Trash
- [.] . Lock
- [@] @ At
- [#] Hashtag
- ['] ' Quote
- [a] a Archive
- [A] A Alarm
- [b] b Bookmark
- [B] B Birthday
- [c] c Comment
- [C] C Clip
- [d] d Diamond
- [D] D Document
- [e] e Envelope
- [E] E Eye
- [f] f Flame
- [F] F Financial
- [g] g Gaming
- [G] G GYM
- [h] h Home
- [H] H Heart
- [i] i info
- [I] I Idea
- [m] m Music
- [M] M Medical
- [p] p Person
- [P] P Plane
- [s] s Sport
- [S] S Search
- [u] u URL
- [v] v Video
- [w] w World
- [W] W Work
- [z] z Moon
- [Z] Z Sun
- [0] 0 Text Highlight 0
- [1] 1 Text Highlight 1
- [2] 2 Text Highlight 2
- [3] 3 Text Highlight 3
- [4] 4 Text Highlight 4
- [5] 5 Text Highlight 5
- [6] 6 Text Highlight 6
- [7] 7 Text Highlight 7
- [8] 8 Text Highlight 8
- [9] 9 Text Highlight 9
- [§] § Text Highlight §
- [ ] Due this Saturday 🗓️2021-08-29
- [ ] I made this on ➕1990-06-14
- [ ] Task I can start this weekend 🛫2021-08-29
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
- [ ] [do not binge](Daily.md)
- [ ] Breakfast
- [ ] Log meals to **필라이즈**
- [ ] [Morning skincare](AM.png)
- [ ] Work on a #3D/project
- [ ] [Evening skincare](PM.png)
- [ ] #post/3D on [[Cara]]
- [ ] #post/3D on [[Instagram]]
- [ ] Add footage to Premiere and wait for ingest
- [ ] Ensure audio is on Track 1 and sound similar to previous published video
- [ ] Cut A-Roll
- [ ] Watch through video to check for good flow
- [ ] Add color-graded adjustment layer
- [ ] Upload A-Cut to [Frame.io](http://frame.io) for review
- [ ] Watch through A-Cut and note any needed fixes
- [ ] Create chronological list of B-Roll with descriptions
- [ ] Tag B-Roll ideas with Gather types
- [ ] Acquire all needed B-Roll
- [ ] Add all B-Roll items to Premiere and wait for ingest
- [ ] Rename all B-Roll items in Premiere to be more descriptive
- [ ] Add all Premiere B-Roll to main sequence
- [ ] Export medium-bitrate 1080p Animation Cut for AE Animations
- [ ] Create Animations.aep in project Drive folder using AE template project
- [ ] Add Animation Cut to AE and create a master composition from it
- [ ] Add all graphics and animations in AE
- [ ] Import AE project into Premiere and put on top layer of main sequence
- [ ] Add any needed transitions
- [ ] Add any needed SFX
- [ ] Add music
- [ ] Watch through video to check for errors (including spelling errors)
- [ ] Export video - H.264, YouTube 1080p preset
- [ ] Upload final video to Rev and order captions
- [ ] When captions arrive, save to project folder
- [ ] Salicylic Acid 2% +Urea 2% + Panthenol 2%
- [k] Art&Fact Lactobionic Acid 1% + Lactic Acid 2% + Hyaluronic Acid 0.1%
- [ ] Salicylic Acid 2% + Licorice Root Extract 3%
- [ ] Probiotic Complex + Ceramide NG
- [ ] Niacinamid 10% + Zink 1%
- [ ] Niacinamide 5% + Retinol ,4% + Lactic Acid + Complex Of Amino Acids
- [ ] Vitamin C 15% + Rosmarinus Officinalis Water 1% + Argireline 0,5% + Aloe Barbadensis Leaf Juice 0,5%
- [ ] Matmarine 4% + Niacinamide 2% + Urea 2%
- [ ] 3D Hyaluronic Acid
- [ ] Azelaic Acid Derivative
- [ ] Caffeine 3%
- [ ] Retinol o,3% + Retinyl Palmitate o,3% + Caffeine 0,5%
- [r] Salicylic Acid 2% + Zinc Oxide 0.5% + Hemisqualane 0.5% + Allantoin 0.2%
- [n] SPF 5O+
- [n] SPF 30+
- [r] Blue Retinol 3% + Shea Butter 2% + Retinol 1.5%
- [ ] Propolis Extract 10% + Shea Butter 3% + Urea 1% + Niacinamide 0.5%
- [ ] Kaolin 5% + Lactic Acid 10% + Glycolic Acid 1%+ Tea Tree Essential Oil 0,1%
- [k] Kaolin 11,5% + Niacinamide 2% + Sulfur 1,5% + Mandelic Acid + Lactic Acid
- [k] Retinol 1% + Collagen 1% + Beeswax 3%
- [r] Mandelic Acid 10%
- [k] Papain 5% + Allantoin 0.5%
- [ ] Herbal Power Balancing Tonic
- [ ] Aqua Recovery Hyaluronic Mineral Serum
- [ ] Aqua Balance Moisturizing Fluid
- [n] Aqua Eccence Hyaluronic & Peptide Fluid
- [k] Aqua Recovery Hyaluronic Mineral Cream
- [ ] 12% AHA+BHA Smart Peel System
- [k] 7 Herbs Enzyme Cleansing Powder
- [k] Vitamin C Shine Enzyme Cleansing Powder
- [ ] Пенка Бергамот + Мята
- [n] Флюил Для Снятия Макияжа
- [k] Гидрофильный Гель
- [k] Тоник Увлажняющий Роза + Алоэ
- [ ] Обновляющая Маска Койевая Кислота + Ниацинамид
- [o] Востанавливающая Маска Сквалан + Церамиды
- [k] Тонизирующая Маска Лайм + Мята
- [r] Тонизирующее Молочко Для Тела Апельсян + Грейпфрут
- [ ] Shine Is Niacinamide 10% + Retinol o.1%
- [ ] Tretinoin Gel UPS o.1%
- [k] Laboratorium Ceramides Mask
- [k] Aravia Anti-Acne Corrective Essence
- [k] Aravia Anti-Acne Intensive
- [k] Aravia Post-Acne Balance Mask
- [k] Shades Of You
 `

For every other Query type, you first need to access the implicit field `file.lists` or `file.tasks` to check for these list item specific implicit fields:

` - [[00 Daily/06/24.06.03.md|24.06.03]]
- [[00 Daily/06/24.06.18.md|24.06.18]]
- [[00 Daily/06/24.06.19.md|24.06.19]]
- [[00 Daily/24.07.01.md|24.07.01]]
- [[02 Projects/Animated character.md|Animated character]]
- [[08/Syntax/Basic formatting syntax.md|Basic formatting syntax]]
- [[08/Syntax/Markdown.md|Markdown]]
- [[08/Syntax/Metadata on Tasks and Lists.md|Metadata on Tasks and Lists]]
- [[08/Syntax/Dataview Query Language.md|Dataview Query Language]]
- [[08/Template/Daily.md|Daily]]
- [[08/Template/Editing Checklist.md|Editing Checklist]]
- [[06 Skincare/Art&Fact.md|Art&Fact]]
- [[06 Skincare/Icon Skin.md|Icon Skin]]
- [[06 Skincare/Onme.md|Onme]]
- [[06 Skincare/Other.md|Other]]
 `

This will give you back all the file links that have unfinished tasks inside. We get back a list of tasks on page level and thus need to use a [list function](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/) to look at each element.