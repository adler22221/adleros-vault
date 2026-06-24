#_GTD_0_inbox

Created on: [[20230408]]
Who's involved: 
About what: 

My note: 

Author: Nuno Campos
Source: 
https://medium.com/technology-hits/my-obsidian-setup-part-27-habits-tracker-84478aebb18e
Retrieved 

> In this part of My Obsidian Setup, I’ll show you how I track my habits, consisting basically in adding the fields to the daily notes and adding a tracker. I do this using a very helpful plugin called…

# My Obsidian Setup (Part 27) — Habits Tracker - Technology Hits - Medium
In this part of My Obsidian Setup, I’ll show you how I track my habits, consisting basically in adding the fields to the daily notes and adding a tracker. I do this using a very helpful plugin called Obsidian Tracker.

## Obsidian Tracker

[Obsidian Tracker](https://github.com/pyrochlore/obsidian-tracker) is an Obsidian plugin that collects data you configure in your notes and represents it in charts.

![](https://miro.medium.com/v2/resize:fit:980/1*hUkuVFIUY9YJpR4ammYkWQ.png)

[Image from Obsidian Tracker GitHub](https://github.com/pyrochlore/obsidian-tracker)

## Collecting Data

You can collect data from `tag`, `frontmatter`, `wiki`, `text`, `table`, `dvField`, `task`, and `fileMeta`.

-   **Tag**: tags in the format of ‘#tagName’ in the note content are evaluated as a constant value (default: 1.0). A value can be attached to the tag in the format of ‘#tagName:value’.
-   **Frontmatter**: evaluate key-value pairs in the front matter.

```
---run: 60---
```

-   **Wiki**: count wiki links in articles. For example, \[\[NoteA\]\].
-   **Text**: count the number of occurrences of the provided text. You can also use regular expressions.

_Occurrences of Email:_

```
searchType: textsearchTarget: '.+\@.+\..+'
```

-   **dvField**: evaluate key::value inline fields.

```
run:: 60
```

-   **Table**: Finds specified table in the specified file and collects data from the specified columns.

```
searchType: tablesearchTarget: data/Table[0][0], data/Table[0][1], data/Table[0][2]
```

Where `data/Table`is the path for the file, `data/Table**[0]**[0]`is the index of the table in the file `data/Table[0]**[0]**`and is the index of the column.

-   **fileMeta**: data from the files, like cDate, mDate, size, numWords, numChars or numSentences.
-   **Task**: collects data from tasks. `task` or `task.all` returns all tasks, done or not. To get tasks done, use `task.done`or `task.notdone`for not done.

So, depending on the `searchType`, you can track the occurrences of the target or its value.

## Output

You can render output in: `line`, `bar`, `summary`, `bullet`, `month` or`pie`.

## Line

This type of visualization is great for number values that change over time and you need to see the progress.

![](https://miro.medium.com/v2/resize:fit:753/1*1dYWoyuG6e1kt8YJw-2DIg.png)

Line visualization. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: dvFieldsearchTarget: RundatasetName: RunningconstValue: 0.0folder: Daily NotesstartDate: 2022-10-30line:    title: Running Log    yAxisLabel: Running Time    yAxisUnit: minutes    yMin: 0    lineColor: yellow```
```

**Bar**

The bar chart visualization is great for comparisons.

![](https://miro.medium.com/v2/resize:fit:819/1*ZvkANsu5rndrHq07bKPy-w.png)

Bar visualization. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: dvFieldsearchTarget: Reading, WritingdatasetName: Reading, WrittingconstValue: 0.0folder: Daily NotesstartDate: 2022-10-30bar:    title: Reading vs Writting    yAxisLabel: Time    yAxisUnit: minutes    yMin: 0    barColor: red, green```
```

## Summary

Just a text output with the collected data. Good for statistics.

![](https://miro.medium.com/v2/resize:fit:223/1*cklILwz2Q4KAjafDDjIxNQ.png)

Summary. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: dvFieldsearchTarget: RundatasetName: Runningfolder: Daily Notessummary:    template: "Minimum: {{min()}}min\nMaximum: {{max()}}min\nMedian: {{median()}}min\nAverage: {{average()}}min"```
```

## Bullet

Good to monitor the progress of a value until reaching the goal.

![](https://miro.medium.com/v2/resize:fit:379/1*xQaCCGa7O1HiBLmPHn-vWg.png)

Bullet visualization. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: dvFieldsearchTarget: RundatasetName: RunningconstValue: 0.0folder: Daily NotesstartDate: 2022-10-30bullet:    title: "Running Time"    dataset: 0    orientation: vertical    range: 150, 300, 450    rangeColor: darkgray, silver, lightgray    value: "{{sum()}}"    valueUnit: minutes    valueColor: steelblue    showMarker: true    markerValue: 80    markerColor: red```
```

## Month

Displays a calendar showing whether something has occurred or not. Good for keeping track of the recurrence of events.

![](https://miro.medium.com/v2/resize:fit:728/1*97Lp7xiCYP7jVMeFvy40Jg.png)

Month visualization. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: dvFieldsearchTarget: RundatasetName: Runningfolder: Daily Notesmonth:```
```

## Pie

Also good for comparisons, but based on a total value.

![](https://miro.medium.com/v2/resize:fit:489/1*WuElegsg-HKosK6Z7lx3pA.png)

Pie visualization. Image by [Nuno Campos](https://medium.com/@nuno.f.s.campos)

```
```trackersearchType: tagsearchTarget: ad, exchangefolder: TasksdateFormat: 'YYYY-  \W\k w \T\a\s\k\s'pie:    data: '{{sum(dataset(0))}}, {{sum(dataset(1))}}'    dataColor: '#4daf4a,#377eb8'    label: AD Occ., Exchange Occ.    ratioInnerRadius: 0.3```
```

## My Trackers

I’m using this plugin to track:

-   My running, with dvField `Run:: <minutes>`in my daily notes and a `line`view
-   Blood pressure, with dvFields `BloodpressureS:: <value> BloodPressureD:: <value>`in my daily notes and a `line`view
-   Weight, with dvField `Weight:: <value>`and a `line`view
-   Team meetings, with dvField `TeamMeeting:: 1|0`and a `month`view

_You can read the previous parts of My Obsidian Setup series here:_

![Nuno Campos](https://miro.medium.com/v2/resize:fill:40:40/1*3j603cCbPpsU2PBQ7nEg1A.png)

## My Obsidian Setup

_Click_ [_here_](https://medium.com/subscribe/@nuno.f.s.campos) _to be notified every time I publish a new story 😉._

_If you’re not a Medium member yet and wish to support me or get access to all my stories, click_ [_here_](https://medium.com/@nuno.f.s.campos/membership)_._
