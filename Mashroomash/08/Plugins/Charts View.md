---
{}
---
This is a data visualization plugin for [Obsidian](https://obsidian.md/), based on [Ant Design Charts](https://charts.ant.design/). Support plots and graphs.

- [Obsidian Charts View Plugin](app://obsidian.md/index.html#obsidian-charts-view-plugin)
    - [Chart Templates](app://obsidian.md/index.html#chart-templates)
        - [Word Count](app://obsidian.md/index.html#word-count)
            - [Multi files](app://obsidian.md/index.html#multi-files)
            - [ALL files](app://obsidian.md/index.html#all-files)
            - [Folder](app://obsidian.md/index.html#folder)
        - [Pie](app://obsidian.md/index.html#pie)
        - [WordCloud](app://obsidian.md/index.html#wordcloud)
        - [Treemap](app://obsidian.md/index.html#treemap)
        - [DualAxes](app://obsidian.md/index.html#dualaxes)
        - [Mix](app://obsidian.md/index.html#mix)
        - [Bar](app://obsidian.md/index.html#bar)
        - [OrganizationTreeGraph](app://obsidian.md/index.html#organizationtreegraph)
        - [Radar](app://obsidian.md/index.html#radar)
        - [TinyLine](app://obsidian.md/index.html#tinyline)
        - [Dataviewjs Example (Column)](app://obsidian.md/index.html#dataviewjs-example-column)
    - [Chart Wizard](app://obsidian.md/index.html#chart-wizard)
    - [Data from CSV file](app://obsidian.md/index.html#data-from-csv-file)
        - [Import data from external CSV file (Desktop)](app://obsidian.md/index.html#import-data-from-external-csv-file-desktop)
        - [Load data from internal CSV file](app://obsidian.md/index.html#load-data-from-internal-csv-file)
            - [Multi CSV files](app://obsidian.md/index.html#multi-csv-files)
    - [Dataview Plugin Integration](app://obsidian.md/index.html#dataview-plugin-integration)
        - [Allowed methods](app://obsidian.md/index.html#allowed-methods)
    - [Interaction](app://obsidian.md/index.html#interaction)
        - [Enable search interaction](app://obsidian.md/index.html#enable-search-interaction)
    - [Examples](app://obsidian.md/index.html#examples)
    - [Manually installing the plugin](app://obsidian.md/index.html#manually-installing-the-plugin)
    - [Ant Design Charts Demos](app://obsidian.md/index.html#ant-design-charts-demos)

## Chart Templates

### Word Count

Use command `Insert Template` -> `Word Count` to insert code block.

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: WordCloud

#-----------------#
#- chart data    -#
#-----------------#
data: "wordcount:Words"

#-----------------#
#- chart options -#
#-----------------#
options:
  wordField: "word"
  weightField: "count"
  colorField: "count"
  wordStyle:
    rotation: 30
```

![image](https://user-images.githubusercontent.com/150803/136478725-be28a56b-0075-4f0a-a719-f61b30e83b6a.jpg)

#### Multi files

```
data: "wordcount:Words,PARA,@Inbox/"
```

#### ALL files

```
data: "wordcount:/"
```

#### Folder

```
data: "wordcount:@Inbox/"
```

`````col
````col-md
flexGrow=1
===
### Pie
Use command `Charts View: Insert Template` -> `Pie` to insert code block.
![[Pasted image 20240704180510.jpg]]
### WordCloud
Use command `Charts View: Insert Template` -> `WordCloud` to insert code block.
![[Pasted image 20240704180539.jpg]]
### Treemap
Use command `Charts View: Insert Template` -> `Treemap` to insert code block.
![[Pasted image 20240704180557.jpg]]
### DualAxes
Use command `Charts View: Insert Template` -> `DualAxes` to insert code block.
![[Pasted image 20240704180614.jpg]]
### Mix
Use \- and `options.<any name>` to set data and options. Keep data and options `<any name>` same.
Use command `Charts View: Insert Template` -> `Mix` to insert code block.
![[Pasted image 20240704180628.jpg]]
### Bar
Use command `Charts View: Insert Template` -> `Bar` to insert code block.
![[Pasted image 20240704180642.jpg]]

````
````col-md
flexGrow=1
===
### Radar
Use command `Charts View: Insert Template` -> `Radar` to insert code block.
![[Pasted image 20240704180717.jpg]]
### TinyLine
Use command `Charts View: Insert Template` -> `TinyLine` to insert code block.
![[Pasted image 20240704180735.jpg]]
### Dataviewjs Example (Column)
Chart data by dataviewjs.  
Use command `Charts View: Insert Template` -> `Dataviewjs Example (Column)` to insert code block.
![[Pasted image 20240704180748.jpg]]
## Chart Wizard
Use command `Charts View: Wizard` to insert code block.
![[Pasted image 20240704180816.jpg]]
![[Pasted image 20240704180843.jpg]] 
![[Pasted image 20240704180908.jpg]]
![[Pasted image 20240704180927.jpg]]
### OrganizationTreeGraph
Use command `Charts View: Insert Template` -> `OrganizationTreeGraph` to insert code block.
![[Pasted image 20240704180657.jpg]]
```
````
`````

## Data from CSV file

### Import data from external CSV file (Desktop)

Use command `Charts View: Import data from external CSV file` to insert data from CSV file.

### Load data from internal CSV file

Load CSV file from data path.  
Data path should be specified in settings.

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Mix

#-----------------#
#- chart data    -#
#-----------------#
data.area:
  - time: 1246406400000
    temperature: [14.3, 27.7]
  - time: 1246492800000
    temperature: [14.5, 27.8]
  - time: 1246579200000
    temperature: [15.5, 29.6]
  - time: 1246665600000
    temperature: [16.7, 30.7]
  - time: 1246752000000
    temperature: [16.5, 25.0]
  - time: 1246838400000
    temperature: [17.8, 25.7]

data.line: LineData.csv

#-----------------#
#- chart options -#
#-----------------#
options:
  appendPadding: 8
  syncViewPadding: true
  tooltip:
    shared: true
    showMarkers: false
    showCrosshairs: true
    offsetY: -50

options.area:
  axes: {}
  meta:
    time:
      type: 'time'
      mask: 'MM-DD'
      nice: true
      tickInterval: 172800000
      range: [0, 1]
    temperature:
      nice: true
      sync: true
      alias: '温度范围'
  geometries:
    - type: 'area'
      xField: 'time'
      yField: 'temperature'
      mapping: {}

options.line:
  axes: false
  meta:
    time:
      type: 'time'
      mask: 'MM-DD'
      nice: true
      tickInterval: 172800000
      range: [0, 1]
    temperature:
      sync: 'temperature'
      alias: '温度'
  geometries:
    - type: 'line'
      xField: 'time'
      yField: 'temperature'
      mapping: {}
    - type: 'point'
      xField: 'time'
      yField: 'temperature'
      mapping:
        shape: 'circle'
        style:
          fillOpacity: 1
```

#### Multi CSV files

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: DualAxes

#-----------------#
#- chart data    -#
#-----------------#
data: DualAxesData.csv, DualAxesData.csv

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: 'time'
  yField: ['value', 'count']
  yAxis:
    value:
      min: 0
      label:
        formatter:
          function formatter(val) {
            return ''.concat(val, '个');
          }
  geometryOptions:
    - geometry: 'column'
    - geometry: 'line'
      lineStyle:
	    lineWidth: 2
```

## Dataview Plugin Integration

### Allowed methods

- dv.current()
- dv.pages(source?)
- dv.pagePaths(source?)
- dv.page(path)
- dv.array(value)
- dv.isArray(value)
- dv.date(text)
- dv.fileLink(path, embed?, display-name?)
- dv.date(pathlike)
- dv.query(source, settings?)
- dv.io

See [Dataview Codeblock Reference](https://blacksmithgu.github.io/obsidian-dataview/api/code-reference/)

## Interaction

### Enable search interaction

Enable the Search in Obsidian interaction when click a chart element by add an option `enableSearchInteraction`.  
Use default:

```
#-----------------#
#- chart options -#
#-----------------#
options:
  ...
  enableSearchInteraction: true
```

or custom:

```
#-----------------#
#- chart options -#
#-----------------#
options:
  ...
  enableSearchInteraction:
    field: 'word'
    operator: 'path'
```

- `field` indicate where to get keyword for search.
- `operator` enums from [Obsidian search opertaors](https://help.obsidian.md/Plugins/Search#Search+operators):

|operator|Obsidian search opertaor|
|---|---|
|||
|`tag`|`tag:`|
|`path`|`path:`|
|`file`|`file:`|
|`task`|`task:`|
|`taskTodo`|`task-todo:`|
|`taskDone`|`task-done:`|
|`matchCase`|`match-case:`|
|`ignoreCase`|`ignore-case:`|
|`line`|`line:`|
|`block`|`block:`|
|`content`|`content:`|
|`section`|`section:`|
|`fileopen`|Open a file inside Vault|

## Examples

See [https://github.com/caronchen/obsidian-chartsview-plugin/wiki/Chart-examples](https://github.com/caronchen/obsidian-chartsview-plugin/wiki/Chart-examples)

## Manually installing the plugin

- Copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/obsidian-chartsview-plugin/`.

## Ant Design Charts Demos

See [https://charts.ant.design/en/examples/gallery](https://charts.ant.design/en/examples/gallery)