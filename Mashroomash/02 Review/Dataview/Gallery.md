---
cssclasses:
  - wide
---
```page-gallery
# Any options given at the root level of the configuration
# will be used as defaults for all views (but can be overridden
# in any individual view).
fields: [file.name]
columns: 3
orientation: landscape

# If you don't include an explicit `views` option (which needs
# to be an array), then page-gallery will just use all the root
# level options as a single unnamed view.
views:
  - name: Read
    from: '"07/Read/Stuff"'
    columns: 4
  - name: Playlist
    from: '"07/YouTube/Playlist"'
    columns: 4
  - name: Animation
    from: '"07/YouTube/Animation"'
    columns: 4
  - name: Study
    from: '"07/YouTube/Study"'
    columns: 4
  - name: Watched
    from: '"07/YouTube/Watched"'
    columns: 4
```