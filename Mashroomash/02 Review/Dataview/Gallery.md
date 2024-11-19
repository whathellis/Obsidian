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
  - name: Obsidin
    from: '"08/Plugins"'
    columns: 5
  - name: Playlist
    from: '"07/YouTube/3D/Playlist"'
    columns: 4
  - name: Read
    from: '"07/Read"'
    columns: 4
  - name: Tutorial
    from: '"07/YouTube/Watched/Tutorial"'
    columns: 4
  - name: Animation
    from: '"07/YouTube/Animation"'
    columns: 4
  - name: Art
    from: '"07/YouTube/Art"'
    columns: 4
```