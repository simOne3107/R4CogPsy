# Welcome to **R** 4 CogPsy

Here you will find everything I have been learning about R and statistics. I hope my notes will be useful to other research students struggling with R and statistics.


## Downloading R ##

Go to [CRAN](https://cloud.r-project.org), the Comprehensive R Archive Network, to download **R** for free.

## Downloading R Studio

Go to [rstudio.com](https://rstudio.com/products/rstudio/) to download **RStudio** for free.


## Using R as a calculator

One of the simplest and easiest things you can do in R is to use it as a calculator. Type the operation in the console pane, and then press **enter** to run it.

- Addition
```r
1 + 1
```
```r
[1] 2
```

- Subtraction
```r
3 - 1
```
```r
[1] 2
```

- Multiplication
```r
4 * 5
```
```
[1] 20
```

- Division
```r
40 / 5
```
```r
[1] 8
```

- Square root
```r
sqrt (9)
```
```
[1] 3
```

- Exponentiation
```r
4^4
```
```r
[1] 256
```

## Creating variables

In R, you can easily create `variables` and assign different values to them. You can see in the examples below that pretty much anything can be used as a variable's name.

```r
NewVariable <- 2 + 2
Price <- 9.99
Bananas <- 0.50
Apples <- 0.89
ReactionTime <- 567
wordcount <- 16785
```

The new `variable` will be stored in R. Type the variable's name in the R console to see the value which is associated with it. Note that R is case sensitive so make sure you type any variables' names appropriately.

```r
NewVariable
```
```r
[1] 4
```

You can also perform simple mathematical operations with one or more previously stored `variables`:

```r
Bananas * 4
```
```r
[1] 2
```

```r
Bananas + Apples
```
```
[1] 1.39
```

## Installing packages ##

In order to install a package in **R**, enter the following line of code in the console pane with the package name you wish to install, and press enter to run it. Do not forget to use quotation marks.

```r
install.packages ("rmarkdown")
```

Each package must be installed only once. However, each time you wish to use a previously installed package in a new session, you must reload that package with the `library()` function:

```r
library (rmarkdown)
```

### Useful R packages ###

Below is a list of packages which I have been using for data analysis, data wrangling, and data visualization in R:

```r
library (tidyverse)
library (ggplot2)
library (powersim)
```


#### Importing data files ####

sss

## Tidying your data ##

When your data is tidy, each row in your dataset is an observation (e.g., trial), whereas each column is a variable (e.g. accuracy, reaction time)

## Creating plots

The first function which must be used when we want to create a plot with ggplot2 is `ggplot()`. With that function, a coordinate system is created to which we can subsequently add layers. 

```r
ggplot (data = MyDataFrame)
```
At least one layer should be added to the function above, otherwise we will have an empty graph.

If you want to create a scatterplot, you can use the function `geom_point()` which will add points to the aforementioned coordinate system. 

```r
ggplot(data = MyDataFrame) + 
  geom_point(mapping = aes(x = variable1, y = variable2))
```
![](https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot.PNG)

By changing or adding further levels to `aes`, the aesthetic properties of a scatterplot, we can change the size, the shape or even the colour of the points. 

```r
ggplot(data = MyDataFrame) + 
  geom_point(mapping = aes(x = variable1, y = variable2, color = variable3))
```


<img src="https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot2.PNG" >


Some of the `variables` which can be added to `aes` are:
1. `class`
2. `size`
3. `alpha` (this refers to the level of transparency of the points)
4. `shape`
5. `colour`
6. `stroke`
7. `group`
8. `fill`

Below is a list with the possible shapes which can be used in a scatterplot generated with `ggplot2`:

<img src="http://ggplot2.tidyverse.org/reference/scale_shape-6.png" width ="500">


Image extracted from **tidyverse.org**.




```r
ggplot(data = MyDataFrame) + 
  geom_point(mapping = aes(x = variable1, y = variable2, color = variable3), shape = 2)
```


<img src="https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot3.PNG" >





[editor on GitHub](https://github.com/simOne3107/R4CogPsy/edit/master/README.md) 
