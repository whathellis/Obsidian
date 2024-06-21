---
share: true
---
query: '/(Regex: \d)/'
query: 'path: Atlas tag: # '
query: 'path: abc/deb OR path: atlas/notes'
query: path:abc/deb OR path: atlas/notes 
> notice the spacing differences without quotes
path can be used to select an individual folder or recursively collect it.
Has options for sorting, limiting # of results and recursively scanning folders.

note-gallery
sort: desc
limit: 9


> [!example] Syntax
**note-gallery**
**query:** 'tag:#mytag'
 optional: anything you'd put into an obsidian search query
 make sure to wrap into single quotes for any regex e.g.: '/\d/'
**debugQuery:** false | true - display native search results to debug
**path:** atlas
 optional: current note folder | path/to/folder - you don't need to use path if you are using query, path will source additional notes
**recursive:** true | false
**limit:** 0 | any number
**sort:** desc | asc
**sortBy:** mtime | ctime | name
**fontSize:** 6pt | NUMBERpt | NUMBERpx
**showTitle:** true | false
**breakpoints:** default: 4 | 100000: 10 | 3500: 10| 3100: 9 | 2700: 8 | 2300: 7 | 1900: 6 | 1500: 5 | 1000: 4 | 700: 3 | 400: 2 | 200: 1

##### Responsive Breakpoints
> Different columns can be specified by passing an object containing key's of the window widths and their value as the number of columns. To have a fallback value, use the default key.

breakpoints:
default: 4
1100: 3
700: 2
500: 1
Calentar file.mtime -> mod time
Where weight > 1
Where !completed
Sort date desc