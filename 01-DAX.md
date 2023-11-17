# Key measure Table
- easy to manage all measure calculates.
- HOME => Enter Data => create a table.
- select measure => in measure tool , in home table select table you want to move measure in.

# Aggregation functions. (MAX, AVARAGE...)
- Average sales quantity = AVERAGE( sales[quantity] )
- Maximum of sales quantity = MAX( sales[quantity] )
- Depends on where measure is usued.

# Version of COUNT.
- Sample Measure COUNT = COUNT(SampleTable[Sample Column 1]) : counts the numbers in a column , without real blank values. can not work with type boolean.
- Sample Measure COUNT = COUNTROWS(SampleTable) : COUNTROWS : counts the number of rows in a table. number of rows in a table is the same. so argument will be table name.
- Sample Measure COUNT = COUNTA(SampleTable[Sample Column 2]) : COUNTA : count the number of values in a column. like COUNT include boolean and not real blank.
- Sample Measure COUNT = DISTINCTCOUNT(SampleTable[Sample Column 1]) : DISTINCTCOUNT : Counts the number of distinct values in a column.
- Sample Measure COUNT = COUNTBLANK(SampleTable[Sample Column 1]) : COUNTBLANK : Counts the number of blanks in a column.


- Revenue Measure sumx = SUMX(sales, sales[quantity] * sales[price]) : SUMX :  calculate row by row. (table, expression)


# The CALCULATE Function
- Revenue LastYear = CALCULATE( [Revenue Measure], SAMEPERIODLASTYEAR( DateTable[Date]))
- SAMEPERIODLASTYEAR : calculate from the last year , same date same day.

- Revenue Measure = SUMX( sales, sales[price] * sales[quantity])
- Revenue filtered by state = CALCULATE([Revenue Measure], FILTER(location, location[state] = "Utah"))
- FILTER return a table has been filtered.
- SampleFilterTable = FILTER(products, products[price] > 5) => return a table with less rows and have been filtered.

## ALL Function.
