# Obsidian — The Queue

There is no point in creating notes you never see again!

_The Queue_ is a plugin for [Obsidian.md](app://obsidian.md/index.html) that shows you random notes from your vault, one at a time. You can configure your notes to function as habits, flashcards, iterative reading prompts, to-dos and more.

## What The Queue can help you with

1. Overcoming favorite & forget
2. Gradually building up a genuine Zettelkasten
3. Low-friction iterative reading
4. Spaced Repetition flashcard learning
5. Getting through to-do lists without being overwhelmed
6. Building & tracking habits (a lot of them, if you want)
7. Intersperse boring or unpleasant work with fun and enjoyment
8. Serendipitously discover connections between your notes
9. Improving your PKM in a gradual, natural way

## Installation

_The Queue_ is not yet available through the `Community Plugins` tab in Obsidian (WIP). You must install it manually:

1. Download this repository as a `.zip` file and unzip
2. Locate your Obsidian plugin folder and copy the project folder there
3. Activate `The Queue` in your Community Plugins tab in your Obsidian Settings

If any of these steps cause you trouble, refer to _Method 2_ in [this excellent installation guide](https://www.makeuseof.com/install-obsidian-plugins/).

_Obligatory warning: This plugin works by editing the metadata/frontmatter of your notes. We took steps to avoid interference with existing workflows or settings, but if this sounds scary to you, we recommend you backup of your vault, as well as read this documentation carefully._

## Get Started

1. Select the little die icon in your ribbon. (📝)
2. You are in your queue, have fun!

## Usage, Features and Functionality

(in detail)

### Frontmatter Settings

1. _The Queue_ always shows one of your notes at a time
2. How exactly your note is treated is depending on its _frontmatter_ (also called _metadata_)

If you never heard of frontmatter, I recommend [this excellent introduction](https://notes.nicolevanderhoeven.com/obsidian-playbook/Using+Obsidian/03+Linking+and+organizing/YAML+Frontmatter).

_The Queue_ uses a bunch of frontmatter properties, **all of them optional**. As a rule, they start with `q-`. This is an attempt to avoid clashes with other plugins or workflows that use otherwise similarly named properties.

Below is an example note with all properties that _The Queue_ can interpret.

```
---
q-type: habit
q-interval: 3
q-priority: 5
q-keywords: 
  - at home
  - break
q-topic: Home Exercise
q-data:
  due-at: 2024-02-26T03:00:00.000Z
aliases: 
  - Situp Habit
---

Do (at least) 3 sit-ups. Go!
```

Here is an overview of all properties and what they're used for:

|Frontmatter Property|Possible Values|Usage/Meaning|
|---|---|---|
|`q-type`|_see [Types of notes](app://obsidian.md/index.html#types-of-notes)_|Determines how the note will be treated and which buttons you see. _Most important_.|
|`q-interval`|any positive number (like `3`, or `0.2`)|How often a note will show up, measured in days.|
|`q-priority`|any number|Whether this note will be prioritized compared to other notes due at the same time — the higher the value, the more likely it will be picked.|
|`q-keywords`|text, or an array of text|_see [Filtering](app://obsidian.md/index.html#filter-notes-in-your-queue)_|
|`q-topic`|any text|Additional text that will show up on the top right of the note when it is displayed in the queue. As of now, purely visual.|
|`q-data`|—|An object used to keep track of various values that are internally relevant to _The Queue_. Unless you are transferring notes from another system, you will never have to touch this.|

Again, all of these properties are optional. You can set some, all or none of them. For examples, this is also a completely valid note that will be understood by _The Queue_:

```
---
q-priority: 15
q-topic: being present
---

I like watching the clouds pass by.

```

Which properties you need depends highly on what kind of note you are creating (as determined by `q-note`). In the next chapter, you will learn about all the different types of notes in _The Queue_.

### Types of notes

Setting `q-type` in the frontmatter of a note will tell _The Queue_ how to treat it — is it a habit? A to-do? A learning flashcard?

First of all, here is a list of all `q-type`s that _The Queue_ is aware of:

|`q-type` value|Note Type|Treatment|
|---|---|---|
|`learn`|Learning Flashcard|A Spaced-Repetition flashcard where you initially only see the front side.|
|`todo`|To-Do|A task that you only have to do once. Will be hidden once it's finished.|
|`habit`|Habit Prompt|A recurring habit that you want to establish. Will prompt you to do the task on the note every time it comes up.|
|`check`|Check-In|Like a habit, but phrased as a question and looking back. It's a bit hard to explain but very useful.|
|`article`|Article|Something like a blog post or similar mid-sized content. Will prompt you to read a bit everyday until you are done.|
|`book`|Book|A book on your reading list. Will also prompt you to read daily, but _The Queue_ will limit the books that you read simultaneously.|
|`misc`|Miscellaneous|Just...some kind of note. Basically just shows up and you say 'ok'.|
|value not set, or none of the above|" "|Treated like `misc`. All your notes are of type `misc`, unless you specify otherwise.|
|`exclude`|Excluded Note|This note will not show up in the queue.|

_There are some additional types used internally. See [here](app://obsidian.md/index.html#additional-secret-types) if that interests you._

In the following chapters, you will learn about every type of note in detail. At the end, you can customize how notes will show up in your queue to your heart's desire.

#### Standard notes / Miscellaneous / Default

If a note has no `q-type`, an invalid one, or `misc`, it will be handled as shown here.

##### Useful for...

1. thoughts that you occasionally want to be reminded of
2. quotes that you like but don't want to exactly memorize
3. paintings, memes, silly things
4. photos that you took; memories

##### Examples

1. A valid note with no frontmatter (treated as `misc`)

`The Eruption of Vesuvius.md`

```

![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/I.C.Dahl_Vesuv.jpg/1024px-I.C.Dahl_Vesuv.jpg)
```

2. A valid note with `q-type: misc` said explicitly, no content besides the name, given a [priority value](app://obsidian.md/index.html#priority).

`"Whom the gods wish to destroy, they give unlimited resources".md`

```
---
q-priority: -20
q-type: misc

---
```

When you encounter a `misc` note in your vault, you have the option to select **Show Less Often**, **Ok, Cool** and **Show More Often**. The two outer buttons decrement/increment the note's [priority](app://obsidian.md/index.html#priority) so that it will come up less/more in the future.

#### Learning flashcards

##### Useful for...

1. learning vocabulary
2. memorizing quotes
3. studying for exams

##### Examples

- For simple notes, _The Queue_ will interpret the name of the note as the front (the question) and the note's content as the back side (the solution). See below:

`I like cold pizza.md`

```
---
q-type: learn
---

Mi piace la pizza fredda
```

- It is also possible to define the front and the back side of the flashcard within the note's content
- As you can see below, there is nothing stopping you from putting additional content on a flashcard

`Vienna Secession Period.md`

```
---
q-type: learn
---

The [[Vienna Secession]] started ＿ and ended 1905.

---

1897

- → [[design-periods]], [[Vienna]]
- *remember*: just around the turn of the century
```

##### Functionality

_under construction_. Learning card system was recently switched from ebisu to FSRS.

#### To-Dos

To-dos are marked by setting `q-type: todo` in the frontmatter.

##### Useful for...

1. tasks that you have to do once

#### Example

Here is an example:

`finalize documentation.md`

```
---
q-type: todo
---

→ finish documentation of The Queue
```

Once you select **Completed**, it will not show up again. Whereas if you select **Not today**, you will see the note the next day, while **Later** delays for 10 minutes.

#### Habits

Habits are a lot like to-dos — however, they are recurring. You set them with `q-type: habit`.

##### Useful for...

1. enhancing your productivity (e.g. _plan the rest of your day_)
2. iteratively improving your note-taking system (e.g. _import browser bookmarks to Obsidian_)
3. taking care of your health (e.g. _stand up and roll your shoulders_)
4. staying on top of social obligations and relationships (e.g. _convert at least 1 email in your inbox to a to-do and delete it_)
5. almost any kind of habit that you want to establish, honestly

##### Examples

Here is a habit note that will show up every 3 days:

`Tidy Desk Habit.md`

```
---
q-type: habit
q-interval: 3
---

- clear your desk
	- only laptop, glass of water, notebook and potted plant are allowed on it
```

As you can see, the interval (=how often you are prompted) is set by `q-interval` and measured in days. For habits, setting `q-interval` is recommended, but not required — if it's not set, _The Queue_ will show the habit once a day.

###### Habits with short intervals

You can set `q-interval` to any number larger than zero, even really small ones. For example, the following habit will be due roughly every 20 minutes.

```
---
q-type: habit
q-interval: 0.014
---

Take a deep, slow breath
```

We recommend not having too many habits with really short intervals since they can "clog" your queue. However, it's useful for certain habits, and of course you can adapt the interval at any time.

###### Tracking many habits

Different to many personal productivity systems, _The Queue_ does not require you to actively remember habits, nor to check-off a list of them every day. Because of this, you can put hundreds of habits into your queue at little cost — if you so desire.

Whether this makes sense depends on how long you engage with your queue every day. If you only look at half a dozen notes on an average day but have 50 active daily habits, you will of course not see all of them everyday. Depending on the habit in question, this may be be OK, or ruin the idea. Consider this carefully.

As long as you're consistently checking your queue now and again, it's very convenient to add habits that are only due very rarely and thus easy to forget, like:

```
---
q-type: habit
q-interval: 300
---

call doctor for yearly check-up
```

I have quite a lot of those.

To make sure that important habits are not drowned out, take a look at [setting note priorities](app://obsidian.md/index.html#priority).

##### Set yourself up for success with habits

No matter how many habits you choose to put into your queue, we advice you to design them carefully. Having habits that feel to big, too undefined or too dreadful can quickly take out the fun. Some tips:

1. Set [Smart Goals](https://www.atlassian.com/blog/productivity/how-to-write-smart-goals) on every habit note
2. Set an optional _Minimum Viable Habit_: A tiny action in the right direction that is possible to do even when you are at your worst
3. Specify exceptions: What do you do when it's impossible to do the habit right now?

Take special care when you use `habit` notes for self-change or mental health concerns. It's no win to create a habit to feel better only to then feel worse because you're not up for doing it. Three additional recommendations here:

1. Create `habit` notes for habits you already do anyways; to build trust in your ability to do so.
2. Consider `habit` notes for things that are fun, silly, useless or unrelated to your goals, such as _eat a piece of chocolate and really enjoy it_.
3. For new habits, start tiny. For example, if you want to establish mood tracking, try _draw a smiley about how you feel in your notebook_ instead of _write a 1-page diary entry_.

Please be aware that all these are just cheap hacks, attempting to simplify the extremely intricate topics of mental health and identity. Be kind to yourself.

And most importantly, know that _The Queue_ can not replace human contact nor a mental health professional.

#### Check-Ins

_Check-Ins_ are a little bit strange, but very neat. They are like habits, but formulated as a question to yourself and usually looking at the past or the general state of things. Here a few examples:

- _Did you go to bed at a reasonable time yesterday?_
- _Are you spending enough time with your family?_
- _Do you have a glass of water within reach?_

##### Useful for...

1. establishing habit systems that can't be supported by prompting specific actions in the moment, for example relating to sleep, exercise or lifestyle.
2. checking in with yourself on a broader scale, e.g. spiritually, regarding mental health, career trajectory, etc.
3. validating that you are actually applying learned concepts, processes or ideas

##### Example

```
---
q-interval: 3
q-priority: 10
q-type: check
---
[[office health]]
```

This check here will show up every three days, with fairly high [priority](app://obsidian.md/index.html#priority).

Whether you answer **No**, **Kind of** or **Yes** actually makes no difference (except for [leech counting](app://obsidian.md/index.html#leech-improvement)). There is no score, it's just you checking in with yourself.

##### Be gentle & take care of yourself

We ask you to be careful with this type of note. While there is likely nothing wrong with checking whether you have a glass of water on your desk, analyzing your own mental health is a serious endeavour.

While "_Are you happy with yourself?_" may be the ideal prompt for one person to adjust their priorities, it may spiral into self doubt for another.

If you choose to use `check` for these things, be gentle and kind. Set yourself up for easy wins, especially in the beginning or when attempting big changes in your life.

And please remember, _The Queue_ can not replace human contact nor a mental health professional.

#### Iterative Readings: Books and Articles

[Iterative Reading](https://en.wikipedia.org/wiki/Incremental_reading) is a method of getting through long reading lists. Instead of reading one article (or whatever) after another, you read everything "at the same time". _The Queue_ makes this possible by randomly showing you articles you saved, prompting you to read a bit — it is up to you whether you stop after a sentence or a chapter. Bit by bit, you make progress, until you finished a given document.

To have a note show up in your queue in this manner, you have to set `article` or `book` as the `q-type`.

As you can see in the examples, the two types are treated almost the same. The main difference is that _The Queue_ limits the number of books you read at a time, while the number of current `article`s is unlimited.

##### Useful for...

1. `article`:

- blog posts
- news articles
- videos
- (long-ish) emails
- any kind of content that takes 1 - 45 minutes to consume and understand

2. `book`:

- ...well, books
- long-form video, including movies
- large essays
- any kind of content that feels like a project to get through

##### Examples

###### Article

`Monthly self-expansion project.md`

```
---
q-type: article
---

- *formalia*:
	- [[Derek Sivers]]
	- https://sive.rs/exex

> idea: [[~Every month, pick something you hate or know nothing about, and get to know it well]]

- another recommendation for [[The First 20 Hours]]
- very theoretical wishy-washy though, no actual report of how it went

```

As you can see, you can add notes about the article on the note. In fact, we heavily recommend this.

Also, _note the difference between the buttons `Done` and `Finished`_!

1. `Done` means that the note will show up tomorrow again, prompting you to read a bit
2. `Finished` means that you finished the whole book or article, and it will now be treated as a [standard note](app://obsidian.md/index.html#standard-notes--miscellaneous--default)

###### Book

`Dune.md`

```
---
q-type: book
---

```

When you have less than five active books, _The Queue_ will randomly pick one of your `book`s and prompt you to start reading (which you can also decline by selecting **Not today**).

If you want to add a book to your queue that you have already started to read, set `q-type: book-started`.

#### Leech Improvement

_[Leech](https://docs.ankiweb.net/leeches.html)_ is a term from Anki, where it means a learning flashcard that you are repeatedly getting wrong. We use the term more expansively to mean:

1. `learn` notes that you just can't memorize
2. `habit`, `todo`, `book` and `article` notes where you repeatedly select **Not today**
3. `check` notes where you often answer **No**.

None of these is helpful; all of these are frustrating.

For this reason, _The Queue_ automatically detects leeches and will occasionally prompt you to redesign a leech note in certain ways.

This feature is fully automatic and you don't have to do any setup.

#### Orphan Adoption

[Linking in Obsidian](https://help.obsidian.md/Linking+notes+and+files/Internal+links) is extremely useful.

To support you in this regard, _The Queue_ detects notes (of type [misc](app://obsidian.md/index.html#standard-notes--miscellaneous--default)) with no outgoing links and will occasionally prompt you to add connections such a note.

Similar to [Leech Improvement](app://obsidian.md/index.html#leech-improvement), this feature is automatic and requires no setup from your side.

##### Example

Above is an example of _The Queue_ prompting you to find connections for an orphaned note. As you can see, the note in question is not bad, but it's missing obvious links (like `[[CSS]]`) so it's unlikely that it will come up in relevant contexts.

#### Note Improvement Prompt

Additionally to orphan detection, _The Queue_ also looks for the string `needs-improvement` anywhere on your notes.

Generally, the idea is that you tag notes with `needs-improvement` whenever a problem catches your eye, without having to rectify the problem immediately. Problems could be anything like:

1. missing meta-data
2. missing quotations
3. ugly layout
4. note too long
5. thoughts unclear
6. information outdated
7. ...

We recommend using a tag like `#needs-improvement` or a link to a note with aliases, like `[[needs-improvement|no citations]]`, so that you keep a good overview of your problematic notes.

Whatever your specific setup is, just include the text `needs-improvement` somewhere on a note and _The Queue_ knows what's up.

Your queue will then occasionally prompt you to improve such a note.

#### Additional, (secret) types

_The [type list at the beginning of the chapter](app://obsidian.md/index.html#types-of-notes) is actually not exhaustive. They are some additional types that the software uses internally. Unless you are transferring from a different system or hacking your queue on an advanced level, you will never need to set them. Anyways, for completion's sake, here they are:_

|`q-type` value|Usage|
|---|---|
|`learn-started`|A `learn` note after it's been shown for the first time. This distinction lets the software know whether to reveal the full note immediately (because it's shown for the first time) or not|
|`todo-done`|A `todo` that the user has completed. Treated the same as `exclude`. We opted for this option because we did not want to trigger destructive actions (like deleting a note) from _The Queue_.|
|`book-started`|A `book` that you are actively reading. Used to keep track of the number of books read at the same time.|
|`book-finished`|A `book` that is completely read. Treated the same as `misc`; the distinction only exists so that the note is still clearly recognizable as a book.|

After this tangent, here is some more stuff you can do within _The Queue_:

### Features

#### Edit notes

✏️

When you are in your queue, you can always jump to edit the note you are looking at — just select the little pen icon.

We recommend doing this — a lot! This way your notes become better and better, even the ones that may be forgotten otherwise.

Once you are done editing, you can jump back to the same note by just selecting the queue icon (📝) again.

If during editing you decide that you really don't need this note anymore, you can also delete it. _The Queue_ will just pick a new note once you start it again.

#### Filter notes in your queue

🌪️

If you have set `q-keywords` on at least some notes, you can use the filter icon to filter which notes show up in your queue.

This can be useful when cramming for an exam or for habits that can be done while riding the bus.

We recommend using this feature sparingly, as having all your notes wildly mixed is a lot of the fun.

You can also exclude folders from showing up in your queue in the `Settings`. This may be useful when you have things like a template folder or other collections of notes that make no sense to include in your queue.

#### Priority

On any note, you can set `q-priority`. The higher the priority is set for a note, the more will it be picked in comparison to notes with a lower priority value.

There are no fixed values for what "high" or "low" priority is; a given `q-priority` is always compared to the other priority values in your vault. So, there is nothing stopping you from giving priorities like `-10000` and `20000`, or `1.2` and `1.25`.

##### Technical Details

The actual `q-interval` value you set only matters for sorting your notes from "most important" to "least important" within the selection of notes of the same type (for example, _habit notes that are due right now_).

You can check out the actual selection algorithm in `src/utils/randomSelection.ts`, it's fairly readable and short.

#### Logging

Data about the number of due notes in your queue, as well as the notes displayed in your queue, is saved locally on your machine. These data never leave your device and nobody without access to the phone or computer you use Obsidian on can see them. You can export and reset these data in the Settings of the plugin. As of now, it is only available as a single `JSON` object download.

A comprehensive documentation as well as more accessibly statistics are in the works.

## Credit

This ongoing project is the culmination of quite a few years of researching and tinkering. As such, it incorporates uncountable ideas, approaches, tools and concepts that others have built. I could not possibly name (or even remember) all of them, so here is a non-exhaustive list of the most integral sources that enabled me to create this:

1. [Obsidian.md](https://obsidian.md/), which is not only the software this is built upon but also how I organize my thinking around it.
2. [Piotr Wozniak's writing](https://supermemo.guru/), which gave me many pointers on Spaced Repetition, iterative reading and more.
3. [ebisu](https://github.com/fasiha/ebisu.js), the algorithm that flashcards used to be based on.
4. [FSRS](https://github.com/open-spaced-repetition/ts-fsrs), the new flashcard algo.
5. The writings of Cal Newport, Niklas Luhmann, James Clear, Jeff Olson, Maxwell Maltz, Mihaly Csikszentmihalyi and many others, who all influenced my thinking about note-taking, productivity, learning and habits.
6. The folder settings' code is inspired by [Templater](https://github.com/SilentVoid13/Templater/blob/0596dc2c756e8c581d55ca3fd897abcb01f6c271/src/settings/suggesters/FolderSuggester.ts), which in turn credits [Liam's Periodic Notes Plugin](https://github.com/liamcain/obsidian-periodic-notes)

## Running Locally & Contributing

Pull requests are always welcome — for ideas, complaints, feature requests or software patches.

There are no specific guidelines for contributing as of now; be pleasant and kind.

Detailed instructions for running the project locally are still pending, however this is just a basic `ts` project. Cloning it locally, installing dependencies with `npm i` and then running it with `npm run dev` should work fine. To use it in Obsidian, you have to put the project folder in your plugin folder.

To start hacking away at the plugin, check `DOC.md` for a brief introduction on where to find what functionality.

If you have any trouble, please open an issue. Cheerz!