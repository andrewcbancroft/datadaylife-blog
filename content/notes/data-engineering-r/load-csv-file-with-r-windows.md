---
title: "Load a CSV File With R"
author: "Andrew Bancroft"
date:   2019-05-29
description: "Several examples of how to load a csv file into an R dataframe"
type: technical_note
draft: false
comments: true
---
## Prerequisites

* No additional R packages are necessary for this notebook to run
* Cells in this notebook expect the <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.csv">Car Sales.csv</a> file to be in certain locations; specifics are in the cell itself
* [Resources](#resources) to help you practice are available at the end

## Load Data From a CSV File

### File is in the same directory as your Jupyter Notebook


```R
# Read the CSV file
car.sales <- read.csv("Car Sales.csv")

# Show the first 5 rows
head(car.sales, 5)
```


<table>
<thead><tr><th scope=col>DealershipName</th><th scope=col>RedCars</th><th scope=col>SilverCars</th><th scope=col>BlackCars</th><th scope=col>BlueCars</th><th scope=col>MonthSold</th><th scope=col>YearSold</th></tr></thead>
<tbody>
	<tr><td>Clyde's Clunkers</td><td>902             </td><td>650             </td><td>754             </td><td>792             </td><td>1               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>710             </td><td>476             </td><td>518             </td><td>492             </td><td>2               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>248             </td><td>912             </td><td>606             </td><td>350             </td><td>3               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>782             </td><td>912             </td><td>858             </td><td>446             </td><td>4               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>278             </td><td>354             </td><td>482             </td><td>752             </td><td>5               </td><td>2018            </td></tr>
</tbody>
</table>



### File is in a different directory than your Jupyter Notebook
The example will use your "home directory" to make this example applicable across operating systems, but you can use any path as long as the file exists there...


```R
# Make sure to use "\" slashes and not "/" slashes (it's a Windows thing)
# There actually needs to be folders named "Path" and "To" and "CSV" and "File"
# in your home directory (the "~" means "home directory") for this cell to work
csv.file.path = normalizePath("~\\Path\\To\\CSV\\File\\Car Sales.csv", winslash = "\\")

other.path.car.sales <- read.csv(csv.file.path)

# Show the first 5 rows
head(other.path.car.sales, 5)
```


<table>
<thead><tr><th scope=col>DealershipName</th><th scope=col>RedCars</th><th scope=col>SilverCars</th><th scope=col>BlackCars</th><th scope=col>BlueCars</th><th scope=col>MonthSold</th><th scope=col>YearSold</th></tr></thead>
<tbody>
	<tr><td>Clyde's Clunkers</td><td>902             </td><td>650             </td><td>754             </td><td>792             </td><td>1               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>710             </td><td>476             </td><td>518             </td><td>492             </td><td>2               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>248             </td><td>912             </td><td>606             </td><td>350             </td><td>3               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>782             </td><td>912             </td><td>858             </td><td>446             </td><td>4               </td><td>2018            </td></tr>
	<tr><td>Clyde's Clunkers</td><td>278             </td><td>354             </td><td>482             </td><td>752             </td><td>5               </td><td>2018            </td></tr>
</tbody>
</table>



### From a URL


```R
# Note the URL Encoding with "%20" for spaces
url.to.csv.file <- "https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.csv"

# Read the CSV file
url.car.sales = read.(url_to_csv_file)

# Show the first 5 rows
head(url.car.sales, 5)
```


    Error in read.table(file = file, header = header, sep = sep, quote = quote, : object 'url_to_csv_file' not found
    Traceback:


    1. read.csv2(url_to_csv_file)

    2. read.table(file = file, header = header, sep = sep, quote = quote, 
     .     dec = dec, fill = fill, comment.char = comment.char, ...)


<a name="resources" class="jump-target"></a>
<div class="resources">
  <div class="resources-header">
    Resources
  </div>
  <ul class="resources-content">
    <li>
        <i class="fas fa-file-csv"></i> <a href="https://github.com/andrewcbancroft/datadaylife-blog/raw/master/datasets/Car%20Sales.csv">Car Sales.csv</a>
    </li>
    <li>
        <i class="fas fa-book"></i> <a href="https://raw.githubusercontent.com/andrewcbancroft/datadaylife-blog/master/content/notes/load-csv-file-with-python-pandas.ipynb">load-csv-file-with-python-pandas.ipynb</a>
    </li>
  </ul>
</div>
