# A View of the Stock Market the Past Year
## Overview of Project
### Purpose

To expand the dataset to include the entire stock market over the last few years. We will check to see if the information is the same as previously shown. Then we will refactor so the VBA script runs in a timely fashion by adjusting the code to loop through all the data one time in order to collect the same information in the Data Analysis Section. Some possible techniques to accomplish this are by taking fewer steps, using less memory, or improving the logic of the code.

### Background

Steve, this project is due to your parent’s desire to invest in alternative energy sources which lead to their investment in DAQO New Energy Corp. You promised them an assessment of the company’s performance as well as you have concerns about diversity. Your new program request will help provide you with data to assist you in making some better possible choices of diversification for their portfolio.

### Analysis

#### Refactoring VBA Code Process Explained with Examples.

TickerIndex was created as a variable and set to zero before iterating over all the rows. It will be used to access the appropriate index across the four different arrays.
For i = 0 To 11 tickerIndex = tickers(i)

#### Output Arrays were designated as Long data type (ticker Volumes) and Single data type (ticker starting Prices and ticker ending prices).

Dim tickerVolumes As Long Dim tickerStartingPrices As Single Dim tickerEndingPrices As Single

#### A loop initiates the tickerVolume to Zero and accessed by the tickerIndex. Providing a filter if the next row's ticker doesn't match, the tickerIndex is increased.

tickerVolumes = 0 For j = 2 To RowCount If Cells(j, 1).Value = tickerIndex Then

#### The code loops through the stock data, reading and storing the data from all the rows. Modifying withing the loop, allows for the increase of the tickerVolume variable thereby increasing the tickerVolume for the stock ticker. We utilized if-then statements as a filter if to assign the closing price to the ticker starting prices and ticker ending prices variable.

If Cells(j, 1).Value = tickerIndex Then tickerVolumes = tickerVolumes + Cells(j, 8).Value If Cells(j - 1, 1).Value <> tickerIndex And Cells(j, 1).Value = tickerIndex Then tickerStartingPrices = Cells(j, 6).Value End If If Cells(j + 1, 1).Value <> tickerIndex And Cells(j, 1).Value = tickerIndex Then tickerEndingPrices = Cells(j, 6).Value

#### Formatting the cells with codes added visual appeal plus more visually logical understanding of the results.

If Cells(i, 3) > 0 Then Cells(i, 3).Interior.Color = vbGreen Else Cells(i, 3).Interior.Color = vbRed

## Results:

The All Stock Analysis datasets were consistent with that of the Refactored Analysis datasets. However the runtimes varied in outcomes.The initial 2017 code ran in .08125 seconds.

## Before Refactoring 2017 Stock Data Set:

![Before Refactoring](https://github.com/hansonj34/stocks-analysis/blob/main/Resources/Before%20refactoring%202017.png?raw=true)

## After Refactoring 2017 Stock Data Set:

![After Refactoring](https://github.com/hansonj34/stocks-analysis/blob/main/Resources/After%20refactoring%202017.png?raw=true)


The results were positive. The trial allowed for a decrease of .09 seconds. 

## Before Refactoring 2018 Stock Data Set:

![Before Refactoring](https://github.com/hansonj34/stocks-analysis/blob/main/Resources/Before%20Refactoring%202018.png?raw=true)

## After Refactoring 2018 Stock Data Set:

![After Refactoring](https://github.com/hansonj34/stocks-analysis/blob/main/Resources/After%20refactoring%202018.png?raw=true)

The results were negative. This trial time decreased about -.02 in the refactored coding. More analysis needs to be done to account for this discrepancy.

## Summary
### Advantages of refactoring code:

Refactoring is a way to optimize the existing code by making it easier, faster, and more efficient without changing its behavior. It will improve readability and maintenance. It also helps identifies any bugs in the code.

### Disadvantages of refactoring code:

It is time consuming and there is the possibility of introducing mistakes. It can be really expensive and risky.  One can accidentally change the content of the code.

## How these Pros and cons apply to refactoring the original VBA script:
The pros are that the run time decreased and thus making the code more efficient for the 2017 data set. However, cons are that this only works on some data sets but not for others. The 2018 data run time increased. Some other cons are that its very time consuming and can allow for error and an alteration of content. For example, if a particular line is changed in the order the data is read, a new meaning of the code could result or can cause the code to run properly.
