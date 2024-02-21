# Data-analyst-portfolios
thanhnguyen.github.io/portfolio

#### Technical Skills: SQL, Power BI, Power Automtae, Excel VBA, Power Query, DAX

#### Profile
Outcome-driven and successful at managing multiple priorities with a high attention to detail. Strong capability in problem-solving by leveraging data analysis to drive business value. Technical skills in SQL, Power BI, DAX, Power Query and Excel VBA to improve workflows, productivity and reliability.

## Projects
### Call Centre Dashboard

[Call centre PBI DASHBOARD (/Call centre BI.PDF)
Data-analyst-portfolios/Call centre BI.pdf](https://github.com/Thnguyen1001/Data-analyst-portfolios/blob/main/Call%20centre%20BI.pdf)
#### Steps by step
- There was 1 data table for call centre
- Wrote DAX to create a date table for date, date No, day.
  * Date Table = CALENDAR(Min('Call Center_Call Center'[Call Timestamp]),MAX('Call Center_Call Center'[Call Timestamp]))
  * Date No = WEEKDAY('Date Table'[Date],1)
  * Day = FORMAT('Date Table'[Date], "ddd")
 -  Created new Measure for Avg call duration, % response time, Total call Duration by hours and Min, Total calls
  * Avg Call Duration = AVERAGE('Call Center_Call Center'[Call Duration In Minutes])
  * Respone Time % = CALCULATE([Total calls],'Call Center_Call Center'[Response Time]= "Within SLA" || 'Call Center_Call Center'[Response Time]= "Above SLA")/ [Total calls]
  * Total Call Duration (HRS) = [Total Call Durations(Min)]/60
  * Total Call Durations(Min) = SUM('Call Center_Call Center'[Call Duration In Minutes])
  * Total calls = COUNT('Call Center_Call Center'[Id])
- Built visualization charts to present the meaning of the data based on map, call by reason, calls by channel, sentiment by location of call centre. 
    
### Ecomerce Sale Dashboard
(https://github.com/Thnguyen1001/Data-analyst-portfolios/blob/ef2417aa1e4d2731b16d5eaf2ebab6905cbe56bd/Ecome%20sale%20dashboard.pdf)
#### Steps by step. 
- There was 2 available data tables which are "Ecom data and US state codes.
- Wrote DAX to create a Calendar table for Year, Month, Date, and Month Number.
  * Table Calendar = CALENDAR(MIN(ecommerce_data[order_date]),MAX(ecommerce_data[order_date]))
  * Month = FORMAT('Table Calendar'[Date],"mmm")
  * Month Number = MONTH('Table Calendar'[Date])
  * Year = YEAR('Table Calendar'[Date])
- Created new measures for YTD Sales, PTYD sales, YOY sales, sales icon colour, sale icon.
  * YTD sales = TOTALYTD(SUM(ecommerce_data[sales_per_order]),'Table Calendar'[Date])
  * PYTD = CALCULATE(SUM(ecommerce_data[sales_per_order]),DATESYTD(SAMEPERIODLASTYEAR('Table Calendar'[Date])))
  * YOY Sales = ([YTD sales]-[PYTD])/[PYTD]
  * Sale Icon Color = IF([YOY Sales]>0, "Green","Red")
  * Sales Icon = var postive_icon=UNICHAR(9650)  VAR negative_icone=UNICHAR(9660) VAR result =IF([YOY Sales]>0,postive_icon,negative_icone) return result
 - Apply the shape background with rules by condition based on the Sale Icon colour to change colours based on the formula.
 - Formated the 
 - Built up the shape, added cards and charts for visualization and updated month number and decs from Jan- Dec.
 - Similar steps applied for Profits, Qty, Profit Margin.
 - Selected different charts to present different meanings of the report and applied slicer and filters. 

    






