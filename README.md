# VBA_Challenge
Sub VBA_Challenge()
'define variables
Dim Ticker As String
Dim Year_Open As Double
Dim Year_Close As Double
Dim Yearly_Change As Double
Dim Percent_Change As Double
Dim Total_Vloume As Long
Dim lastrow As Long
Dim Sheet As Worksheet

Summary = 2
Tick_Count = 0
Year_Open = 0
Year_Close = 0
Yearly_Change = 0
Total_Vloume = 0

'create column headers
Cells(1, 9).Value = "Ticker"
Cells(1, 10).Value = "Yearly_Change"
Cells(1, 11).Value = "Percent_Change"
Cells(1, 12).Value = "Total_Volume"

'find last row
lastrow = Cells(Rows.Count, 1).End(xlUp).Row


'create loop
For i = 2 To lastrow


'create summary table
'if subsequent cell value is different than current cell value
If Cells(i + 1, 1).Value <> Cells(i, 1) Then
'then input unique value pulled from column A
Ticker = Cells(i, 1).Value
Tick_Count = Tick_Count + Cells(i, 7).Value
Year_Close = Cells(i, 6).Value
Year_Open = Cells(i, 3).Value
Range("I" & Summary).Value = Ticker
Range("L" & Summary).Value = Ticker_Total
Yearly_Change = Year_Close - Year_Open
Range("K" & Summary).Value = Yearly_Change
Summary = Summary + 1
Ticker_Count = 0

Else
Total_Volume = Total_Volume + Cells(i, 1).Value

End If



Next i

End Sub
