**ChartKitX** : Charts that are not available in Swift's Charts framework.


[![Swift Version](https://img.shields.io/badge/Xcode-16.0+-blue.svg)](https://swift.org)
[![Swift Version](https://img.shields.io/badge/iOS-18.0+-blue.svg)](https://swift.org)
[![Swift Version](https://img.shields.io/badge/Swift-5.0+-orange.svg)](https://swift.org)

## Radial Range Chart

### Parameter

- `data` : The data source for the chart, an array of `DataType` elements.
- `frameSize`: The size of the chart's frame, defining the overall width and height. Default is 400.
- `minValue` : The minimum value for the data range, used for normalizing data values.
- maxValue: The maximum value for the data range, used for normalizing data values.
- iscolorgra: A Boolean flag to indicate whether to apply a color gradient to the bars.
- minColor: The color for the lowest values on the gradient (or single color if `iscolorgra` is false).
- maxColor: The color for the highest values on the gradient (used only if `iscolorgra` is true).
- labelKeyPath: A key path for accessing the label associated with each data element, used to display labels along the x-axis.
- minValueKeyPath: A key path for accessing the minimum value of each data element, used to determine the start point of each radial bar.
- maxValueKeyPath: A key path for accessing the maximum value of each data element, used to determine the end point of each radial bar.
- barWidth: The width of each bar in the radial chart. Default is 30.
- cornerRadius: The corner radius for each bar, to apply rounded corners. Default is 5.
- xaxis: The number of labels to display along the x-axis, spaced evenly. If set to 0, all labels are displayed.

### Example

<img width="500" alt="Radial Range Chart" src="https://github.com/user-attachments/assets/69b3bc4e-33fc-464a-a87b-adeceba94117">

```swift
ZStack {
    RadialBarChartView(
        data: data3,
        frameSize: isMac ? 1000 : 300,
        minValue: 0,
        maxValue: 100,
        iscolorgra: true,
        minColor: Color.blue.opacity(0.5),
        maxColor: Color.orange.opacity(0.5),
        labelKeyPath: \.sequence,
        minValueKeyPath: \.start,
        maxValueKeyPath: \.end,
        barWidth: 2,
        xaxis: 5
    )
    RadialBarChartView(
        data: data3,
        frameSize: isMac ? 1000 : 300,
        minValue: 0,
        maxValue: 100,
        iscolorgra: false,
        minColor: Color(red: 0.55, green: 0.55, blue: 0.55).opacity(0.25),
        maxColor: Color(red: 0.55, green: 0.55, blue: 0.55).opacity(0.25),
        labelKeyPath: \.sequence,
        minValueKeyPath: \.startBaseline,
        maxValueKeyPath: \.endBaseline,
        barWidth: 2,
        xaxis: 5
    )
}
```
