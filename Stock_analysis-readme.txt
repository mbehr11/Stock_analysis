## Overview of Project:
I was working with Steve to show a stock analysis for his parents on the “DQ” stock, as they were looking to make some investments. One he saw that the overall return for 2018 was -63%, he wanted to look at all other stocks for with better return. We were able to add in the timer code to ask the user to choose the year and for Excel to track the time using this code at the beginning: **yearValue = InputBox ("What year would you like to run the analysis on?")**. Once this was run, we were able to breakdown our analysis of the ticker, total daily volume and return by year. We ever added buttons to make it so Steve could showcase his analysis with ease.
Now Steve wanted to be able use our analysis for a larger dataset. Let’s refactor our All-Stocks Analysis for the entire stock market over the last couple years. 
Sub AllStocksAnalysisRefactored()

    Dim startTime As Single
    Dim endTime As Single

    yearValue = InputBox("What year would you like to run the analysis on?")

    startTime = Timer

 ‘1a) Format the output sheet on All Stocks Analysis worksheet

Worksheets ("All Stocks Analysis"). Activate

Range("A1"). Value = "All Stocks (" + yearValue + ")"

'1b) Create a header row.
    Cells (3, 1). Value = "Ticker"
    Cells (3, 2). Value = "Total Daily Volume"
    Cells (3, 3). Value = "Return"

'1c) Initialize an array of all tickers
    Dim tickers(12) As String
    tickers(0) = "AY"
    tickers(1) = "CSIQ"
    tickers(2) = "DQ"
    tickers(3) = "ENPH"
    tickers(4) = "FSLR"
    tickers(5) = "HASI"
    tickers(6) = "JKS"
    tickers(7) = "RUN"
    tickers(8) = "SEDG"
    tickers(9) = "SPWR"
    tickers(10) = "TERP"
    tickers(11) = "VSLR"
    '2) Activate the data worksheet for all years.
    
    Worksheets(yearValue). Activate

    '3) Get number of rows to loop over.
    RowCount = Cells (Rows.Count, "A"). End (xlUp). Row

    '4a) Create a ticker Index.
       Dim tickerIndex
       
    '4b) Create three output arrays.
       Dim tickerVolumes(12) As Long
       Range("H1") = tickerVolume
       
       Dim tickerStartingPrice As Single
       Range("C1") = tickerStartingPrice
       
       Dim tickerEndingPrice As Single
       Range("F1") = tickerEndingPrice

    ''5a) Create a for loop to initialize the tickerVolumes to zero.
        rowStart = 2
        RowEnd = RowCount = Cells (Rows.Count, "A"). End (xlUp). Row
        
        '5b) Loop over all the rows in the spreadsheet
    Worksheets ("All Stocks Analysis"). Activate
            tickerIndex = ticker
            tickerVolume = 0
    '3a) Increase volume for current ticker
 tickerVolumes(tickerIndex) = tickerVolumes(tickerIndex) + Cells (i, 8). Value
 
    '3b) Check if the current row is the first row with the selected tickerIndex.    
            If Cells (i - 1, 1). Value <> ticker And Cells(i, 1).Value = ticker Then
 
        tickerStartingPrice = Cells (i, 6). Value

        End If
    
    '3c) check if the current row is the last row with the selected ticker.
    
            If Cells (i + 1, 1). Value <> tickerIndex And Cells (i, 1). Value = tickerIndex Then
 
                tickerEndingPrice = Cells (i, 6). Value
               
    '4) Loop through your arrays to output the Ticker, Total Daily Volume, and Return.
    For i = 0 To 11
    
Worksheets ("All Stocks Analysis"). Activate
Cells (4 + j, 1). Value = ticker
Cells (4 + j, 2). Value = totalVolume
Cells (4 + j, 3). Value = endingPrice / startingPrice - 1
    Next i
    'Formatting
Worksheets ("All Stocks Analysis"). Activate 
Range ("A3:C3").Font.Bold = True
Range ("A3:C3"). Borders(xlEdgeBottom).LineStyle = xlContinuous
Range ("B4:B15").NumberFormat = "#,##0"
Range ("C4:C15").NumberFormat = "0.0%"
Columns("B"). AutoFit
dataRowStart = 4
dataRowEnd = 15

For i = dataRowStart To dataRowEnd

If Cells (i, 3) > 0 Then
        'Change cell color to green.
        Cells (i, 3).Interior.Color = vbGreen
    
    ElseIf Cells (i, 3) < 0 Then
    'Change cell color to red
    Cells (i, 3).Interior.Color = vbRed

End If

Next i

'endTime = Timer
    MsgBox "This code ran in " & (endTime - startTime) & " seconds for the year " & (yearValue)

End If

End Sub

##Results
 The Results were inconclusive as my code broke here. 
'3a) Increase volume for current ticker
         tickerVolumes(tickerIndex) = tickerVolumes(tickerIndex) + Cells (i, 8).Value
        
