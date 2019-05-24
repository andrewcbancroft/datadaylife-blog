---
title: ""
author: "Andrew Bancroft"
date:   2019-05-22
description: ""
type: technical_note
draft: true
comments: true
wip: true
---

```python
import pandas as pd
```


```python
# Read the Excel file
car_sales_data = pd.read_excel("Car Sales.xlsx")

# Show the first 5 rows
car_sales_data.head(5)
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
      <td>902</td>
      <td>650</td>
      <td>754</td>
      <td>792</td>
      <td>1</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Clyde's Clunkers</td>
      <td>710</td>
      <td>476</td>
      <td>518</td>
      <td>492</td>
      <td>2</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Clyde's Clunkers</td>
      <td>248</td>
      <td>912</td>
      <td>606</td>
      <td>350</td>
      <td>3</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Clyde's Clunkers</td>
      <td>782</td>
      <td>912</td>
      <td>858</td>
      <td>446</td>
      <td>4</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clyde's Clunkers</td>
      <td>278</td>
      <td>354</td>
      <td>482</td>
      <td>752</td>
      <td>5</td>
      <td>2018</td>
    </tr>
  </tbody>
</table>
</div>




```python
car_sales_data["DateSold"] = car_sales_data.apply(lambda row: datetime.date(row["YearSold"], row["MonthSold"], 1), axis=1)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-aea3d58f27d1> in <module>()
    ----> 1 car_sales_data["DateSold"] = car_sales_data.apply(lambda row: datetime.date(row["YearSold"], row["MonthSold"], 1), axis=1)
    

    ~/anaconda3/lib/python3.7/site-packages/pandas/core/frame.py in apply(self, func, axis, broadcast, raw, reduce, result_type, args, **kwds)
       6012                          args=args,
       6013                          kwds=kwds)
    -> 6014         return op.get_result()
       6015 
       6016     def applymap(self, func):


    ~/anaconda3/lib/python3.7/site-packages/pandas/core/apply.py in get_result(self)
        140             return self.apply_raw()
        141 
    --> 142         return self.apply_standard()
        143 
        144     def apply_empty_result(self):


    ~/anaconda3/lib/python3.7/site-packages/pandas/core/apply.py in apply_standard(self)
        246 
        247         # compute the result using the series generator
    --> 248         self.apply_series_generator()
        249 
        250         # wrap results


    ~/anaconda3/lib/python3.7/site-packages/pandas/core/apply.py in apply_series_generator(self)
        275             try:
        276                 for i, v in enumerate(series_gen):
    --> 277                     results[i] = self.f(v)
        278                     keys.append(v.name)
        279             except Exception as e:


    <ipython-input-6-aea3d58f27d1> in <lambda>(row)
    ----> 1 car_sales_data["DateSold"] = car_sales_data.apply(lambda row: datetime.date(row["YearSold"], row["MonthSold"], 1), axis=1)
    

    NameError: ("name 'datetime' is not defined", 'occurred at index 0')



```python
car_sales_data.head(5)
```


```python

```
