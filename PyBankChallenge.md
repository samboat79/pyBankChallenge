```python
#import dependencies
import numpy as np
import pandas as pd
```

```python
budgetOne = "raw_data/budget_data_1.csv"
```

```python
dataFrameOne = pd.read_csv(budgetOne)
```

```python
dataFrameOne.head()
```

<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Oct-12</td>
      <td>1154293</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nov-12</td>
      <td>885773</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Dec-12</td>
      <td>-448704</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jan-13</td>
      <td>563679</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Feb-13</td>
      <td>555394</td>
    </tr>
  </tbody>
</table>
</div>

```python
#printing the columns
dataFrameOne.columns
```

    Index(['Date', 'Revenue'], dtype='object')

```python
#Calculating the total months in dataset
totalMonths = dataFrameOne["Date"].count()
totalMonths
```

    41

```python
#Calculating the total Amount of Revenue gained over the entire period
totalRevenueGained = dataFrameOne["Revenue"].sum()
totalRevenueGained
```

    18971412

```python
#The average change in Revenue
averageChangeInRevenue = dataFrameOne["Revenue"].mean()
averageChangeInRevenue
```

    462717.3658536585

```python
#The greatest Increase in Revenue over the entire period
greatestRevenueIncrease = dataFrameOne["Revenue"].max()
greatestRevenueIncrease
```

    1195111

```python
#Locating the highest Revenue date/Month
greatestRevenueDate = dataFrameOne.loc[dataFrameOne["Revenue"]  == greatestRevenueIncrease, "Date"]
maximumDate = greatestRevenueDate.iloc[0]
maximumDate
```

    'Sep-15'

```python
#The greatest decrease in Revenue (date, Month) over the entire period
greatestRevenueDecrease = dataFrameOne["Revenue"].min()
greatestRevenueDecrease
```

    -1172384

```python
#calculating the Revenue Decrease Date
greatestRevDecDate = dataFrameOne.loc[dataFrameOne["Revenue"] == greatestRevenueDecrease, "Date"]
minimumDate = greatestRevDecDate.iloc[0]
minimumDate
```

    'Aug-14'

```python
print(f" Total Months: {totalMonths}\n Total Revenue: {totalRevenueGained}\n Average Revenue Change: {averageChangeInRevenue}\n Greatest Increase in Revenue: {maximumDate} {greatestRevenueIncrease}\n Greatest Decrease in Revenue: {minimumDate} {greatestRevenueDecrease}")
```

     Total Months: 41
     Total Revenue: 18971412
     Average Revenue Change: 462717.3658536585
     Greatest Increase in Revenue: Sep-15 1195111
     Greatest Decrease in Revenue: Aug-14 -1172384
