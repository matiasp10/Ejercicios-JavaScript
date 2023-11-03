## Exercism y Leetcode

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Radar

#-----------------#
#- chart data    -#
#-----------------#
data:
  - item: "Learning"
    user: "Matias"
    score: 23
  - item: "Easy"
    user: "Matias"
    score: 19
  - item: "Medium"
    user: "Matias"
    score: 0
  - item: "Hard"
    user: "Matias"
    score: 0

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "item"
  yField: "score"
  seriesField: "user"
  meta:
    score:
      alias: "Score"
      min: 0
      nice: true
  xAxis:
    line: null
    tickLine: null
  yAxis:
    label: false
    grid:
      alternateColor: "rgba(0, 0, 0, 0.04)"
  point: {}
  area: {}
```
## Codewars

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Radar

#-----------------#
#- chart data    -#
#-----------------#
data:
  - item: "8kyu"
    user: "Matias"
    score: 32
  - item: "7kyu"
    user: "Matias"
    score: 23
  - item: "6kyu"
    user: "Matias"
    score: 11
  - item: "5kyu"
    user: "Matias"
    score: 3
  - item: "4kyu"
    user: "Matias"
    score: 0
  - item: "3kyu"
    user: "Matias"
    score: 0
  - item: "2kyu"
    user: "Matias"
    score: 0
  - item: "1kyu"
    user: "Matias"
    score: 0
  - item: "0kyu"
    user: "Matias"
    score: 0

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: "item"
  yField: "score"
  seriesField: "user"
  meta:
    score:
      alias: "Score"
      min: 0
      nice: true
  xAxis:
    line: null
    tickLine: null
  yAxis:
    label: false
    grid:
      alternateColor: "rgba(0, 0, 0, 0.04)"
  point: {}
  area: {}
```
```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Pie

#-----------------#
#- chart data    -#
#-----------------#
data:
  - type: "8kyu"
    value: 32
  - type: "7kyu"
    value: 23
  - type: "6kyu"
    value: 11
  - type: "5kyu"
    value: 3
  - type: "4kyu"
    value: 0
  - type: "3kyu"
    value: 0
  - type: "2kyu"
    value: 0
  - type: "1kyu"
    value: 0
  - type: "0kyu"
    value: 0
    
#-----------------#
#- chart options -#
#-----------------#
options:
  angleField: "value"
  colorField: "type"
  radius: 0.5
  label:
    type: "spider"
    content: "{percentage}\n{name}"
  legend:
    layout: "horizontal"
    position: "bottom"
```

```chartsview
#-----------------#
#- chart type    -#
#-----------------#
type: Funnel

#-----------------#
#- chart data    -#
#-----------------#
data:
  - label: 8kyu
    values: 32
  - label: " 7kyu"
    values: 23
  - label: " 6kyu"
    values: 11
  - label: " 5kyu"
    values: 3
  - label: " 4kyu"
    values: "0"
  - label: " 3kyu"
    values: "0"
  - label: " 2kyu"
    values: "0"
  - label: " 1kyu"
    values: "0"
  - label: " 0kyu"
    values: "0"

#-----------------#
#- chart options -#
#-----------------#
options:
  xField: label
  yField: values
```
