![GitHub release](https://img.shields.io/github/v/release/pyrochlore/obsidian-tracker)



This is an [Obsidian](https://obsidian.md/) plugin that helps you collect data from notes and represent it comprehensively.

[Here](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md) is a table containing simplified examples showing what you can track.

# Examples

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md#examples)

We provide a simplified table of use cases and full examples including data.

## Table of Use Cases

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md#table-of-use-cases)

Check where (Location) and what (Target to Track) is your target and find the settings (Tracker) you need.

|Location|Target to Track|Tracker|Get (O)ccurrences/(V)alues|
|:--|:--|:--|:-:|
|content|`#meditation`|searchType: tag  <br>searchTarget: meditation|O|
|frontmatter|---  <br>tags: meditation  <br>---|searchType: tag  <br>searchTarget: meditation|O|
|content|`#weight:60.5kg`|searchType: tag  <br>searchTarget: weight|V|
|content|`#finance/bank1/transfer:100USD`|searchType: tag  <br>searchTarget: finance/bank1/transfer|V|
|content|`#finance/bank1/transfer:100USD`  <br>`#finance/bank1/income:80USD`  <br>`#finance/bank1/outcome:-120USD`|searchType: tag  <br>searchTarget: finance/bank1|V|
|content|`#blood-pressure:180/120`|searchType: tag  <br>searchTarget: blood-pressure[0], blood-pressure[1]|V|
|content|dvTarget:: 20.5|searchType: dvField  <br>searchTarget: dvTarget|V|
|content|dvTarget:: 20.5/30.5|searchType: dvField  <br>searchTarget: dvTarget[0], dvTarget[1]|V|
|content|dvTarget:: 20.5, 30.5|searchType: dvField  <br>searchTarget: dvTarget[0], dvTarget[1]  <br>separator: 'comma'|V|
|frontmatter|---  <br>mood: 10  <br>---|searchType: frontmatter  <br>searchTarget: mood|V|
|frontmatter|---  <br>bp: 184.4/118.8  <br>---|searchType: frontmatter  <br>searchTarget: bp[0], bp[1]|V|
|frontmatter|---  <br>bp: 184.4, 118.8  <br>---|searchType: frontmatter  <br>searchTarget: bp[0], bp[1]  <br>separator: 'comma'|V|
|frontmatter|---  <br>bp: [184.4, 118.8]  <br>---|searchType: frontmatter  <br>searchTarget: bp[0], bp[1]|V|
|frontmatter|---  <br>clock-in: 10:45  <br>clock-out: 20:51  <br>---|searchType: frontmatter  <br>searchTarget: clock-in, clock-out|V|
|content|[[journal|journal]]|searchType: wiki  <br>searchTarget: journal|O|
|content|⭐|searchType: text  <br>searchTarget: ⭐|O|
|content|love|searchType: text  <br>searchTarget: love|O|
|content|[test@gmail.com](mailto:test@gmail.com)  <br>[test@hotmail.com](mailto:test@hotmail.com)|searchType: text  <br>serchTarget: '.+\@.+\..+'|O|
|content|`#weightlifting: 50`|searchType: text  <br>searchTarget: 'weightlifting: (?<value>[\-]?[0-9]+[\.][0-9]+\|[\-]?[0-9]+)'|V|
|content|I walked 10000 steps today.|searchType: text  <br>searchTarget: 'walked\s+(?<value>[0-9]+)\s+steps'|V|
|content|myvalues 1/2/3|searchType: text  <br>searchTarget: 'myvalues\s+(?<value>[0-9]+)/([0-9]+)/([0-9]+), myvalues\s+([0-9]+)/(?<value>[0-9]+)/([0-9]+), myvalues\s+([0-9]+)/([0-9]+)/(?<value>[0-9]+)'|V|
|table content|{ a table filled with dates and values }  <br>[example table](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/data/Tables.md)|searchType: table  <br>searchTarget: filePath[0][0], filePath[0][1]|V|
|table content|{ a table filled with dates and values }  <br>[example table](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/data/Tables.md)|searchType: table  <br>searchTarget: filePath[1][0], filePath[1][1][0], filePath[1][1][1]|V|
|file meta|meta data from files  <br>(size, cDate, mDate, numWords, numChars, numSentences)|searchType: fileMeta  <br>searchTarget: size|V|
|content|- [x] Say love  <br>- [ ] Say love|searchType:task  <br>searchTarget: Say love|O|
|content|- [x] Say love|searchType:task.done  <br>searchTarget: Say love|O|
|content|- [ ] Say love|searchType: task.notdone  <br>searchTarget: Say love|O|

## Full examples

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md#full-examples)

Full tracker code blocks can be found in folder [examples](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples) and the corresponding notes (data) can be found under folder '[diary](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples/diary)' and '[data](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples/data)'.

List of all examples

- [Bloodpressure Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/BloodPressureTracker.md)
- [Error Messages](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/ErrorMessages.md)
- [Finance Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/FinanceTracker.md)
- [Habit Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/HabitTracker.md)
- [Star Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/StarTracker.md)
- [Bar Chart](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestBarChart.md)
- [Axis Interval and Format](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestAxisIntervalAndFormat.md)
- [Bullet Chart](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestBullet.md)
- [Calendar](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestCalendar.md)
- [Date Formats](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDateFormats.md)
- [Dataview Inline Field](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDvField.md)
- [Expression](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md)
- [File Meta](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFileMeta.md)
- [Legends](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestLegends.md)
- [Multiple Targets / Multiple Values](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestMultipleTargetsMultipleValues.md)
- [Pie Chart](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestPieChart.md)
- [Scaling and Positioning](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestScalingAndPositioning.md)
- [Specified Files](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestSpecifiedFiles.md)
- [Summary](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestSummary.md)
- [Table](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTable.md)
- [Task](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTask.md)
- [Text-value Map/Mood Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTextValueMap.md)
- [Time Values](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTimeValues.md)
- [Word Counting](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestWordCounting.md)
- [X Dataset](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestXDataset.md)
- [Regular Expression](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestRegex.md)
- [Weight Tracker](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/WeightTracker.md)
- [Wiki](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/WikiTracker.md)

# Expressions

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#expressions)

Expressions could help us create new and meaningful data from the original collected data by using operators and functions.

## !!! Breaking Changes !!!

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#-breaking-changes-)

From version 1.9.0, template variables, e.g. '{{sum}}', are deprecated. Instead, Tracker provide operators (+, -, *, /, %) and functions (dataset(), sum(), maxStreak(), ......etc) to help us do data processing. For users having code blocks from previous version, please replace '{{sum}}' by '{{sum()}}' or '{{sum(1)}}' by '{{sum(dataset(1))}}'.

## Where to Use

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#where-to-use)

Currently, we can only use expressions in some parameters. These includes `template` in `summary` output, `value` in `bullet` output, and  `label` `extLabel` in `pie` output. In future release, there will be more parameters using expressiones as input.

## How to Use

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#how-to-use)

Expressions should be be wrapped in curly brackets. By using the combination of operators and funtions, Tracker can resolve the whole expression in brackets and then generate a number or a string according to what was requested.

If the resolved output of an expression is a string, we can assign a format string to it. The format string should be placed after the expression in curly brackets following by two colons. For example, The expression '{{sum()::i}}' will force the output number represented as an integer (i for integer).

For the number output, use '[Printf Format String](https://en.wikipedia.org/wiki/Printf_format_string)' for the format string. For the date output, use the date format string defined in [Moment.js](https://momentjscom.readthedocs.io/en/latest/moment/04-displaying/01-format/).

The following tables show all the operators and functions available for now. Please make sure the input type and output type when you are combining them together. Examples could be found [here](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md). Requests for operators or functions are welcome.

## List of Operators

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#list-of-operators)

### Uniry Operators

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#uniry-operators)

|Function|Description|Operant|Output|
|:--|:--|:--|:--|
|+|positive|number or dataset|number or dataset|
|-|negative|number or dataset|number or dataset|

### Binary Operators

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#binary-operators)

|Function|Description|Left Operant|Right Operant|Output|
|:--|:--|:--|:--|:--|
|+|plus|number or dataset|number or dataset|number or dataset|
|-|minus|number or dataset|number or dataset|number or dataset|
|*|multiply|number or dataset|number or dataset|number or dataset|
|/|divide|number or dataset|number or dataset|number or dataset|
|%|modulo|number or dataset|number or dataset|number or dataset|

e.g.

- number + number --> number
- dataset + number --> dataset
- number + dataset -> dataset
- dataset + dataset --> dataset

## List of Functions

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#list-of-functions)

### Get Dataset by Index

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#get-dataset-by-index)

|Function(InputType): OutputType|Description|
|:--|:--|
|dataset(number): Dataset|Get dataset from dataset id (the order in `searchTarget`)|

### Functions Accept Dataset and return a value

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#functions-accept-dataset-and-return-a-value)

**If the input dataset is missing, it will use the first available Y dataset found.**

|Function(InputType): OutputType|Description|
|:--|:--|
|min(Dataset): number|Minimum value of the dataset|
|minDate(Dataset): Date|Latest date of minimum value|
|max(Dataset): number|Maximum value of the dataset|
|maxDate(Dataset): Date|Latest date of maximum value|
|startDate(Dataset): Date|Start date of the dataset|
|endDate(Dataset): Date|End date of the dataset|
|sum(Dataset): number|Summation of values of the dataset|
|numTargets(Dataset): number|Total counts of targets|
|numDays(Dataset): number|Days from startDate to endDate|
|numDaysHavingData(Dataset): number|Number of days having data|
|maxStreak(Dataset): number|Maximum continuous days without breaks|
|maxStreakStart(Dataset): Date|Start date of the max streak|
|maxStreakEnd(Dataset): Date|End date of the max streak|
|maxBreaks(Dataset): number|Maximum break days|
|maxBreaksStart(Dataset): Date|Start date of the maximum break days|
|maxBreaksEnd(Dataset): Date|End date of the maximum break days|
|currentStreak(Dataset): number|Current continuous days|
|currentStreakStart(Dataset): Date|Start date of current streak|
|currentStreakEnd(Dataset): Date|End date of current streak|
|currentBreaks(Dataset): number|Current break days|
|currentBreaksStart(Dataset): Date|Start date of current breaks|
|currentBreaksEnd(Dataset): Date|End date of current breaks|
|average(Dataset): number|Average value of the dataset|
|median(Dataset): number|Median value of the dataset|
|variance(Dataset): number|Variance value of the dataset|

### Functions Accept Dataset and Return Dataset

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#functions-accept-dataset-and-return-dataset)

|Function(InputType): OutputType|Description|
|:--|:--|
|normalize(Dataset): Dataset|rescale the Y values to [0, 1]|
|setMissingValues(Dataset, number): Dataset|set the missing values|

## Missing Values

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md#missing-values)

Notice that the missing values (null values) are ignored in function like sum or average. Moreover, a value plus a missing value will leads to null value (missing value). To avoid these, you can set those missing values to a value by using parameter `penalty` or use expression function `setMissingValues`.

# Input Parameters

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#input-parameters)

Obsidian-tracker parses key-value pairs in YAML format in your code block and uses them as input parameters. The minimum requirements for parameters are `searchType`, `searchTarget` and at least one output parameter (`line`, `bar`, `summary`, `bullet`, `month`, or `pie`).

## Array Input for a Parameter

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#array-input-for-a-parameter)

Some of the parameters can accept more than one value for each target. For those parameters accept different value for each given search target, the maximum number of values should equal to the number of search target (NT). If the number of values are less than the number of targets, Tracker will use the previously provided one in sequence or use the default value if nothing is provided.

For Y axis related parameters, like `yMin`, `yMax`, or `yAxisLabel`, they accept one value for each Y axis (`left` and `right`). If you only use one axis, or the values for the two axes are the same, only one value is required. If you need the two axes to have different values, provide two values to do the work. The first one will be used for the left Y axis and the second one for the right Y axis.

To enter array of values, we can use YAML array (e.g. ['value1', 'value2', 'value3']) or simply values separated by comma (e.g. value1, value2, value3). The second method is a syntax surgar of Tracker to simplify input process. If YAML special characters are required in the inputs, be sure to wrap the whole values by single quotes (e.g. 'value1, value2, value3'). Please also check [this](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/YAML.md) for more information about YAML in Tracker.

## List of Parameters

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#list-of-parameters)

### Root Parameters

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#root-parameters)

These key-value pairs are placed under the root of the code block.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`searchType`|Type of `searchTarget` (tag\|frontmatter\|wiki\|text\|dvField\|table\|fileMeta\|task)|1~NT|Must be provided|
|`searchTarget`|Target to search  <br>[[detail](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md)]|NT (Number of Targets)|Must be provided|
|`folder`|Root path containing notes to search|1|Root of this vault|
|`file`|Files to include for searching|N|null|
|`specifiedFilesOnly`|Ignore files found in `folder`|1|false|
|`fileContainsLinkedFiles`|Include the linked files in the specified files here|N|null|
|`fileMultiplierAfterLink`|Regex string include named group 'value'  <br>to search the multiplier after link|1|''|
||Date format  <br>Use [Moment.js](https://momentjscom.readthedocs.io/en/latest/moment/04-displaying/01-format/) format or use [iso-8601](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDateFormats.md#iso-8601-date-format)|1|'YYYY-MM-DD'|
||Prefix before your dateFormat (accept regex)|1|''|
||Suffix after your dateFormat (accept regex)|1|''|
|`startDate`|Start date to collect data from  <br>accept [relative date](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDateFormats.md#relative-date-input-for-startdate-and-enddate)|1|Min date found|
|`endDate`|End date of to collect data  <br>accept [relative date](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDateFormats.md#relative-date-input-for-startdate-and-enddate)|1|Max date found|
||Name of the dataset for a search target`|1~NT|untitled|
|`separator`|Character used to separate multiple values appearing in the search target|1~NT|'/'  <br>',' in front matter tags|
|`xDataset`|Index of `searchTarget` used as xDataset|1~NT|-1 (use filename as xDataset)|
|`constValue`|Constant value of a target if no value attached|1~NT|1.0|
|`ignoreAttachedValue`|Use `constValue` even if the target has a value attached on (true\|false)|1~NT|false|
|`ignoreZeroValue`|Treat zero value as missing (true\|false)|1~NT|false|
|`accum`|Accumulatively sum the values over time (true\|false)|1~NT|false|
|`stack`|Support stacked charts (true\|false)|1|false|
|`penalty`|Value to use if the search target is missing on the day|1~NT||
|`valueShift`|Amount to shift for each collected value|1~NT|0|
|`shiftOnlyValueLargerThan`|Do `valueShift` only if the value is larger then the specifed one|1~NT|null|
|`valueType`|Not implemented yet|1~NT||
|`textValueMap`|A container key for multiple text-value mapping|||
|`fixedScale`|Uniform scaling factor to the graph dimensions|1|1.0|
|`fitPanelWidth`|Auto-fit the width of the chart to the container|1|false|
|`aspectRatio`|Change the 1:1 aspect ratio of the graph|number:number|1:1|
|`margin`|Four margins (top\|right\|bottom\|left) of the graph|1~4|10|
|`line`|A container key for parameters related to the line chart|||
|`bar`|A container key for parameters related to the bar chart|||
|`summary`|A container key for parameters related to the summary output|||
|`bullet`|A container key for parameters related to the bullet chart|||
|`month`|A container key for parameters related to the month view|||
|`pie`|A container key for parameters related to the pie chart|||

### Parameters for Common Charts

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-common-charts)

These key-value pairs should be placed under the key `line` or `bar`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`title`|Title of this chart|1|''|
|`xAxisLabel`|Label of X axis|1|'Date'|
|`xAxisColor`|Color of X axis|1|'white'('black'*)|
|`xAxisLabelColor`|Color of X axis label|1|'white'('black'*)|
|`yAxisLabel`|Label of Y axis|1~2|'Value'|
|`yAxisColor`|Color of Y axis|1~2|'white'('black'*)|
|`yAxisLabelColor`|Color of Y axis label|1~2|'white'('black'*)|
|`yAxisUnit`|Unit displayed aside Y axis label|1~2|''|
|`xAxisTickInterval`|X axis interval between ticks|1~2|null|
|`xAxisTickLabelFormat`|Format of tick label on X axis|1~2|null|
|`yAxisTickInterval`|Y axis interval between ticks|1~2|null|
|`yAxisTickLabelFormat`|Format of tick label on Y axis|1~2|null|
|`yMin`|Minimum value on Y axis|1~2|Minimum Y value found|
|`yMax`|Maximum value on Y axis|1~2|Maximum Y value found|
|`reverseYAxis`|Flip (upside down) the Y Axis or not (true\|false)|1~2|false|
|`allowInspectData`|Show data value when mouse hovered (true\|false)|1|true|
|`showLegend`|Show/Hide legend (true\|false)|1|false|
|`legendPosition`|Legend position (top\|bottom\|left\|right)|1|bottom|
|`legendOrientation`|Legend orientation (vertical\|horizontal)|1|horizontal for bottom and top  <br>vertical for left and right|
|`legendBgColor`|Legend background color|1|none|
|`legendBorderColor`|Legend border color|1|white|

### Parameters for a Line Chart

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-a-line-chart)

These key-value pairs should be placed under the key `line`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`lineColor`|Color of the lines in the chart|1~NT|'white'('black'*)|
|`lineWidth`|Width of the lines in the chart|1~NT|1.5|
|`showLine`|Show/hide lines (true\|false)|1~NT|true|
|`showPoint`|Show/hide data points (true\|false)|1~NT|true|
|`pointColor`|Color of data points|1~NT|`#69b3a2`|
|`pointBorderColor`|Border color of data points|1~NT|`#69b3a2`|
|`pointBorderWidth`|Border width of data points|1~NT|0|
|`pointSize`|Radius of data points|1~NT|3|
|`fillGap`|Connect points over missing data (true\|false)|1~NT|false|
|`yAxisLocation`|Corresponding Y axis for the dataset (left\|right)|1~NT|left|

### Parameters for a Bar Chart

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-a-bar-chart)

These key-value pairs should be placed under the key `bar`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`barColor`|Color of bars in the chart|1~NT|`#69b3a2`|
|`yAxisLocation`|Corresponding y-axis for the dataset (left\|right)|1~NT|left|

### Parameters for a Summary

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-a-summary)

These key-value pairs should be placed under the key `summary`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`template`|Text template (you may embed [expressions](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md)|1|''|
|`style`|CSS style applied to the rendered text block|1|''|

### Parameters for a Bullet Chart

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-a-bullet-chart)

These key-value pairs should be placed under the key `bullet`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`title`|Title of this chart|1|''|
||Index of the dataset of your interest|1|0|
|`orientation`|Bar orientation (horizontal\|vertical)|1|'horizontal'|
|`value`|Actual value of interest  <br>(you may embed [expressions](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md)|1|''|
|`valueUnit`|Unit of the Y value displayed aside|1|''|
|`valueColor`|Color of the value bar|1|'#69b3a2'|
|`range`|Data anges of defined by series of numbers|N|[]|
|`rangeColor`|Color of the range bands|N|[]|
|`showMarker`|Show/hide the marker line (true\|false)|1|true|
|`markerValue`|Value of the markder|1|0|
|`markerColor`|Color of the marker|1|'black'|

### Parameters for a Month View

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-a-month-view)

These key-value pairs should be placed under the key `month`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`mode`|Pick one mode of the two(circle\|annotation)|1||
||Index of the dataset of your interest|1~NT|all indices of non-x searchTarget|
|`startWeekOn`|First day of a week ('Sun'\|'Mon')|1|'Sun'|
|`threshold`|Threshold to determine showing a circle on a day or not|1~NT|0|
|`yMin`|Minimum value|1~NT|Minimum value of the dataset|
|`yMax`|Maximum value|1~NT|Maximum value of the dataset|
|`showCircle`|Circle the day label if the collected value reach the threshold (value > `threshold`)|1|true|
|`color`|Main color (can be override by other color parameters)|1|null|
||Dim the color for days not in current month|1|true|
|`showStreak`|Show/hide streaks between circles|1|true|
|`showTodayRing`|Show/hide the ring on the label today|1|true|
|`showSelectedValue`|Show/hide the value on the selected day|1|true|
|`showSelectedRing`|Show/hide a ring on the label of the selected day|1|true|
|`circleColor`|Color of circles|1|'#69b3a2'|
|`circleColorByValue`|Display circle colors based on the value|1|false|
|`headerYearColor`|Color of the year text in header|1|'white'|
|`headerMonthColor`|Color of the month text in header|1|'white'|
||Color of the dividing line|1|'#69b3a2'|
|`todayRingColor`|Color of the ring on today|1|'white'|
|`selectedRingColor`|Color of the ring on the selected day|1|'firebrick'|
|`initMonth`|Initial month to show (YYYY-MM)|1|last month found|
|`showAnnotation`|Show/hide annotation|1|false|
|`annotation`|Annotation for each piece of data|NT|''|
|`showAnnotationOfAllTargets`|Show annotation of all targets at the same time|1|false|

### Parameters for Pie Chart

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md#parameters-for-pie-chart)

These key-value pairs should be placed under the key `pie`.

|Key|Description|Number of Values|Default|
|:--|:--|:-:|:--|
|`title`|Title of this chart|1|''|
||Array of values, each represents the number or fraction of a circular sector|N|''|
||Color of each circular sector|N|''|
||Name of each data shown on legend|N||
|`label`|Labels for each data shown on circular sector|N||
|`hideLabelLessThan`|Hide the label with its fraction number lower than|1|0.03|
|`showExtLabelOnlyIfNoLabel`|Show/hide the external label only if the correstponding label is missing or empty (true\|false)|1|false|
|`extLabel`|Labels for each data shown aside out of circular sector|N||
|`ratioInnerRadius`|Ratio of donut inner radius to pie radius|1|0|
|`showLegend`|Show/hide legend (true\|false)|1|false|
|`legendPosition`|Legend position (top\|bottom\|left\|right)|1|right|
|`legendOrientation`|Legend orientation (vertical\|horizontal)|1|horizontal for bottom and top  <br>vertical for left and right|
|`legendBgColor`|Legend background color|1|none|
|`legendBorderColor`|Legend border color|1|white|