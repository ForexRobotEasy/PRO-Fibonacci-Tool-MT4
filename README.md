# PRO Fibonacci Tool MT4 - ReadMe

This is a code for the PRO Fibonacci Tool MT4, developed by the Forex Robot Easy Team. For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/pro-fibonacci-tool-mt4-review-advanced-forex-software-for-serious-traders/).

## Description

The PRO Fibonacci Tool MT4 is an advanced forex software designed for serious traders. It allows users to draw Fibonacci levels on the chart and automatically adjust them based on market conditions. The tool also includes trading operations for seamless execution of trades.

## Installation

To use the PRO Fibonacci Tool MT4, follow these steps:

1. Include the necessary libraries by adding the following lines at the beginning of your code:

```c++
#include <Trade\Trade.mqh>
#include <ChartObjects\ChartObjectsFibonacci.mqh>
```

2. Declare the global variables:

```c++
CTrade trade; // Trading object
CChartObjectFibonacci fibonacci; // Fibonacci object
bool isDrawingEnabled = false; // Flag to indicate if drawing mode is enabled
```

3. Initialize the expert advisor by adding the following code to the `OnInit()` function:

```c++
isDrawingEnabled = true; // Enable the drawing mode by default
fibonacci.SetAnchorPoints(0, 1); // Set the initial Fibonacci levels
```

4. Handle key events for quick drawing of Fibonacci levels by adding the following code to the `OnChartEvent()` function:

```c++
if (id == CHARTEVENT_KEYDOWN)
{
    if (sparam == 'D' || sparam == 'd')
    {
        isDrawingEnabled = !isDrawingEnabled; // Toggle the drawing mode
    }
}
```

5. Calculate and adjust Fibonacci levels on new market highs or lows by adding the following code to the `OnTick()` function:

```c++
if (isDrawingEnabled)
{
    double marketHigh = High[0]; // Get the current market high
    double marketLow = Low[0]; // Get the current market low
    fibonacci.SetAnchorPoints(marketLow, marketHigh); // Adjust the Fibonacci levels
}
```

6. Handle chart updates and drawing of Fibonacci levels by adding the following code to the overloaded `OnChartEvent()` function:

```c++
if (isDrawingEnabled)
{
    fibonacci.Clear(); // Clear existing Fibonacci levels
    fibonacci.Draw(); // Draw the Fibonacci levels on the chart
}
```

7. Handle the deinitialization of the expert advisor by adding the following code to the `OnDeinit()` function:

```c++
fibonacci.Clear(); // Clear existing Fibonacci levels
```

8. Finally, start trading operations by adding the following code to the `OnStart()` function:

```c++
trade.Trade(); // Start trading operations
```

## Disclaimer

Please note that Forex Robot Easy is not the official developer of this product. This code is provided as a sample that can work as described in the product. To find the official developer of this product, please use MQL5.

For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/pro-fibonacci-tool-mt4-review-advanced-forex-software-for-serious-traders/).
