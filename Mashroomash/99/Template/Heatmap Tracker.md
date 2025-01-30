```contributionGraph
graphType: calendar
dateRangeValue: 180
dateRangeType: FIXED_DATE_RANGE
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: left
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"00 Daily"'
  dateField:
    type: PAGE_PROPERTY
    value: date
  countField:
    type: PAGE_PROPERTY
    value: calories
fillTheScreen: false
enableMainContainerShadow: false
fromDate: 2024-06-01
toDate: 2024-08-31
cellStyle:
  minWidth: 17px
  minHeight: 17px
cellStyleRules:
  - id: default_b
    color: "#9be9a8"
    min: 1
    max: "200"
  - id: default_c
    color: "#40c463"
    min: 2
    max: "500"
  - id: default_d
    color: "#30a14e"
    min: 5
    max: "1000"
  - id: default_e
    color: "#216e39"
    min: 10
    max: "9990"

```

```contributionGraph
graphType: month-track
dateRangeValue: 180
dateRangeType: FIXED_DATE_RANGE
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: left
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"00 Daily"'
  dateField:
    type: PAGE_PROPERTY
    value: date
  countField:
    type: PAGE_PROPERTY
    value: weight
fillTheScreen: false
enableMainContainerShadow: false
fromDate: 2024-06-01
toDate: 2024-07-31
cellStyle:
  borderRadius: 40%
  minWidth: 30px
  minHeight: 30px
cellStyleRules:
  - id: Lovely_a
    color: "#fedcdc"
    min: 36
    max: 37
  - id: Lovely_b
    color: "#fdb8bf"
    min: 37
    max: 38
  - id: Lovely_c
    color: "#f892a9"
    min: 38
    max: 39
  - id: Lovely_d
    color: "#ec6a97"
    min: 39
    max: 9999

```


```contributionGraph

graphType: default
dateRangeValue: 180
dateRangeType: LATEST_DAYS
startOfWeek: "1"
showCellRuleIndicators: true
titleStyle:
  textAlign: left
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: '"00 Daily"'
  dateField: {}
  filters: []
fillTheScreen: false
cellStyle:
  minWidth: 20px
  minHeight: 20px
enableMainContainerShadow: false
```
