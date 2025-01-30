---
{}
---
Mood Tracker for Obsidian.md, inspired by [Amazing Marvin's](https://amazingmarvin.com/) Mood Tracker.

## Why this plugin?

While you definitely can build a mood tracking system in Obsidian with markdown files, metadata and Dataview, it can be tedious to maintain and use.

This plugin provides a clean, user-friendly alternative with a lot of "batteries included".

The data is stored in your vault, in plain JSON.

## Track your moods & emotions

Monitor mood with "mood rating"; personalize mood labels.

Incorporate detailed emotions (fully customizable).

Include notes in entries.

[See demo](app://obsidian.md/index.html#mood-tracking)

## Add mood tracking data to your journals

Mood Tracker allows adding entries to notes, like a daily journal, with dynamic note paths based on the entry date.

[See demo](app://obsidian.md/index.html#add-entry-to-daily-note)

## Mood tracking stats & history

View mood history in a graph.  
Track average and frequent moods and emotions.  
Click a graph point to explore daily details.

[See demo](app://obsidian.md/index.html#history-and-stats)

You can also edit past entries and add new entries for past days.

[See demo](app://obsidian.md/index.html#edit-past-entries)

#### Embeddable graph

You can embed the graph into a note with `mood-tracker-stats` codeblock:

```mood-tracker-stats
end: current-week
daysBeforeEnd: 90
showAverage: true
showMostCommonMood: true
showCommonEmotionsList: true
height: 500px
```

Options:

- end: date in "YYYY-MM-DD" format, or dynamic date ("today", "current-week" (end of), "previous-week" (end of), "current-month" (end of), "previous-month" (end of))
- daysBeforeEnd: number of days to show
- showAverage: show average mood rating (defaults to false)
- showMostCommonMood: show the most common emotion (defaults to false)
- showCommonEmotionsList: show a list of the most common emotions (defaults to false)
- height: height of the graph (pixels, %, anything that `style` attribute of HTML element would support) (defaults to 350px)
- width: the same as height (defaults to 100%)

For example, this codeblock will render records for the current month, with no additional info:

```mood-tracker-stats
end: current-month
daysBeforeEnd: 39
```

## Roadmap

- [x] Customize mood emojis
- [x] Edit past entries
- [x] Emotion sections / blocks
- [x] Add data to journals / daily notes
- [ ] Customize graph colors
- [ ] More chart types
- [ ] Export data
- [ ] Import data

## Demos

`````col
````col-md
flexGrow=1
===
#### Mood tracking

![[Pasted image 20240704190318.jpg]]

#### Add entry to daily note

![[Pasted image 20240704190344.jpg]]
````
````col-md
flexGrow=1
===
#### History and stats

![[Pasted image 20240704190404.jpg]]

#### Edit past entries

![[Pasted image 20240704190417.jpg]]
```
````
`````