<img width="400" alt="Radial Range Chart" src="https://github.com/user-attachments/assets/3b061069-c785-4d1c-b2cf-8797bd784c2c">



**ChartKitX** : Charts that are not available in Swift's Charts framework.


[![Swift Version](https://img.shields.io/badge/Xcode-16.0+-blue.svg)](https://swift.org)
[![Swift Version](https://img.shields.io/badge/iOS-18.0+-blue.svg)](https://swift.org)
[![Swift Version](https://img.shields.io/badge/Swift-5.0+-orange.svg)](https://swift.org)

## Radial Range Chart

### Parameter

- `data` : Chart data source, an array of DataType elements.
- `frameSize` : (`CGFloat`) Chart's frame size (width and height). Default is 400.
- `minValue` : (`Double`) Minimum data range value for normalization.
- `maxValue` : (`Double`) Maximum data range value for normalization.
- `iscolorgra` : (`Bool`) Applies color gradient to bars if true.
- `minColor` : (`CGFloat`) Color for the gradient's lowest value.
- `maxColor` : (`CGFloat`) Color for the gradient's highest value.
- `labelKeyPath` : (`KeyPath`) Key path for x-axis labels from data elements.
- `minValueKeyPath` : (`KeyPath(Double)`) Key path for each bar's start point.
- `maxValueKeyPath` : (`KeyPath(Double)`) Key path for each bar's end point.
- `barWidth` : (`CGFloat`) Radial bar width. Default is 30.
- `cornerRadius` : (`CGFloat`) Bar corner radius. Default is 5.
- `xaxis` : (`Int`) Number of x-axis labels to display (0 shows all). Default is 0.

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
