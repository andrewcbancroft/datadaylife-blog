---
title: "Load an Excel File With Python and Pandas"
author: "Andrew Bancroft"
date:   2019-05-22
description: "Several examples of how to load an excel file into a Pandas dataframe with Python"
type: technical_note
draft: false
comments: true
---
## Prerequisites

* Install the [Pandas](https://pandas.pydata.org/) library for your Python environment
* Cells in this notebook expect the <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.xlsx">Car Sales.xlsx</a> file to be in certain locations; specifics are in the cell itself
* [Resources](#resources) to help you practice are available at the end

## First Things First


```python
import pandas as pd
```

## Load Data From Excel

### File is in the same directory as your Jupyter Notebook


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



### File is in a different directory than your Jupyter Notebook
The example will use your "home directory" to make this example applicable across operating systems, but you can use any path as long as the file exists there...

##### Find the home directory using Python 


```python
from os.path import expanduser as ospath

user_home_directory = ospath("~")
```


```python
# Make sure to use "/" slashes and not "\" slashes
# There actually needs to be folders named "Path" and "To" and "Excel" and "File"
# in your home directory (the "~" means "home directory") for this cell to work
excel_file_path = user_home_directory + "/Path/To/Excel/File/Car Sales.xlsx"

other_path_car_sales_data = pd.read_excel(excel_file_path)

# Show the first 5 rows
other_path_car_sales_data.head(5)
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



### From a URL


```python
# Note the URL Encoding with "%20" for spaces
url_to_excel_file = "https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.xlsx"

# Read the Excel file
url_car_sales_data = pd.read_excel(url_to_excel_file)

# Show the first 5 rows
url_car_sales_data.head(5)
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



<a name="resources" class="jump-target"></a>
<div class="resources">
  <div class="resources-header">
    Resources
  </div>
  <ul class="resources-content">
    <li>
        <i class="fas fa-file-excel"></i> <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.xlsx">Car Sales.xlsx</a>
    </li>
    <li>
        <i class="fas fa-book"></i> <a href="https://raw.githubusercontent.com/andrewcbancroft/datadaylife-blog/master/content/notes/load-excel-file-with-python-pandas.ipynb">load-excel-file-with-python-pandas.ipynb</a>
    </li>
  </ul>
</div>
