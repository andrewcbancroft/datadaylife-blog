---
title: "What is the Difference Between axis=0 and axis=1 When Working with Pandas Dataframes?"
author: "Andrew Bancroft"
date:   2019-05-22
description: "Provides an example scenario to help decipher the difference between axis=0 and axis=1 when working with Pandas dataframes"
type: technical_note
draft: false
comments: true
wip: false
---
Sometimes, functions ask you to specify an `axis`.  The documentation can often feel vague and/or technical.

For instance, here's a quote from the `apply` function's documentation:
    
> axis : {0 or ‘index’, 1 or ‘columns’}, default 0
Axis along which the function is applied:
0 or ‘index’: apply function to each column.
1 or ‘columns’: apply function to each row.

Uuuum... right.

So what's the difference?  Here's an example...

<a name="resources" class="jump-target"></a>
<div class="resources">
  <div class="resources-header">
    Resources
  </div>
    <div class="resources-download-instructions">
    Right-click -> Save as...
  </div>
  <ul class="resources-content">
    <li>
        <i class="fas fa-file-csv"></i> <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.csv" download>Car Sales.csv</a>
    </li>
    <li>
        <i class="fas fa-book"></i> <a href="https://raw.githubusercontent.com/andrewcbancroft/datadaylife-blog/master/content/notes/data-engineering-python/difference-between-axis-0-axis-1-python-pandas.ipynb" download>difference-between-axis-0-axis-1-python-pandas.ipynb</a>
    </li>
  </ul>
</div>

## Load a CSV file to play with 

### Prerequisites (if you want to practice)

* Install the [Pandas](https://pandas.pydata.org/) library for your Python environment
* Cells in this notebook expect the <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.csv">Car Sales.csv</a> file to be in the same directory as your notebook
* [Resources](#resources) to help you practice

### First Things First


```python
import pandas as pd
```


```python
# Read the CSV file
# This assumes "Car Sales.csv" is in the same directory as your notebook
car_sales_data = pd.read_csv("Car Sales.csv")

# Show the first 5 rows
first_five = car_sales_data.head(5)
display(first_five)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DealershipName</th>
      <th>RedCars</th>
      <th>SilverCars</th>
      <th>BlackCars</th>
      <th>BlueCars</th>
      <th>MonthSold</th>
      <th>YearSold</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Clyde's Clunkers</td>
      <td>902.0</td>
      <td>650.0</td>
      <td>754.0</td>
      <td>792.0</td>
      <td>1.0</td>
      <td>2018.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Clyde's Clunkers</td>
      <td>710.0</td>
      <td>476.0</td>
      <td>518.0</td>
      <td>492.0</td>
      <td>2.0</td>
      <td>2018.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Clyde's Clunkers</td>
      <td>248.0</td>
      <td>912.0</td>
      <td>606.0</td>
      <td>350.0</td>
      <td>3.0</td>
      <td>2018.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Clyde's Clunkers</td>
      <td>782.0</td>
      <td>912.0</td>
      <td>858.0</td>
      <td>446.0</td>
      <td>4.0</td>
      <td>2018.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clyde's Clunkers</td>
      <td>278.0</td>
      <td>354.0</td>
      <td>482.0</td>
      <td>752.0</td>
      <td>5.0</td>
      <td>2018.0</td>
    </tr>
  </tbody>
</table>
</div>


The car sales data looks like it contains one row that summarizes the **total sales of each color** of car for a **given dealership**, for **each month** of the **year**. 

To state the "grain" of the data frame another way, the data frame contains **one row per dealership, month, year** combo and reports the total number of cars sold by color.

### Choose Your Scenario

Suppose that two people come to you and ask separate questions about **average car sales**.

* Lucy asks, "Can you calculate the average number of cars sold for each color?"

* Zack asks, "Can you calculate the average number of cars sold (regardless of color) for each dealership in each month & year?" (so basically the average of red, silver, black, and blue cars for each row)

#### Start with Lucy. 
Think about what you'd do to answer Lucy's question by hand, manually, if you didn't have Pandas to do the work for you. Here's what I'd do:

1. Start with the RedCars column.  
2. Add up 902, 710, 248, 782, 278, and so on.
3. Divide that sum by the total number of values.  Boom.  RedCars average.
4. Rinse and reapeat steps 1-3 for SilverCars, BlackCars, and BlueCars.

**This is an axis=0 scenario** in Pandas.


```python
first_five[['RedCars', 'SilverCars', 'BlackCars', 'BlueCars']].mean(axis=0)
```




    RedCars       584.0
    SilverCars    660.8
    BlackCars     643.6
    BlueCars      566.4
    dtype: float64



#### What about Zack?  
What would you do to answer his question by hand, without Pandas? How's this...

1. Start with the first row of data (Row 0), since his question matches the "grain" of the data frame... one row per dealership per month & year.
2. Add up the RedCars, SilverCars, BlackCars, and BlueCars values for Row 0 and divide by 4.  So (902 + 650 + 754 + 792)/4
3. Rinse and repeat steps 1 & 2 for every row in the data frame.  Boom.  Average cars sold by dealer/month/year.

**This is an axis=1 scenario**.


```python
first_five[['RedCars', 'SilverCars', 'BlackCars', 'BlueCars']].mean(axis=1)
```




    0    774.5
    1    549.0
    2    529.0
    3    749.5
    4    466.5
    dtype: float64



### Summarizing the Findings
Specifying an `axis` to a function in Pandas is helping answer one of the following questions:

* Should I (Pandas) **start with a column** and make this function do its job *downward* on all the "cells" for that column, and then continue doing the same thing **for all the rest of the columns** in the data frame? (`axis=0`)

*or*

* Should I (Pandas) **start with the first row** of data in the data frame and make this function do its job *horizontally* on all of the "cells" for that row, and then continue doing the same thing **for all the rest of the rows** in the data frame? (`axis=1`)

