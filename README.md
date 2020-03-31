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
```r
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
```r
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

In **R**, you can easily create `variables` and assign different values to them. By using the symbol `<-`, we assign the value on its right to the `variable` on its left. You can see in the examples below that pretty much anything can be used as a variable's name:

```r
NewVariable <- 2 + 2
Price <- 9.99
Bananas <- 0.50
Apples <- 0.89
reaction_time <- 567
word.count <- 16785
```
**Alt** + **-** can be used as a shortcut for `<-`


The new `variable` will be stored in **R**. Type the variable's name in the R console to inspect the value which is associated with it. Note that **R** is case sensitive so make sure you type any variables' names appropriately.

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

## Installing packages in **R** ##

In order to install a package in **R**, enter the following line of code in the console pane with the package name you wish to install, and press enter to run it. Do not forget to use quotation marks.

```r
install.packages ("rmarkdown")
```

Each package must be installed only once. However, each time you wish to use a previously installed package in a new session, you must reload that package with the `library( )` function:

```r
library (rmarkdown)
```

### Useful **R** packages ###

Below is a list of packages which I have been using for data analysis, data wrangling, and data visualization in R:

```r
library (broom)
library (ggplot2)
library (lme4)
library (powersim)
library (tidyverse)
```

## Useful built-in **R** functions ##

1. To make regular **sequences** of numbers:
```r
seq (10,30)
```
```r
[1] 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
```

2. To view an entire dataset:
```r
View(MyDataFrame) # note the capitalized V in this function
```

3. To check whether a value is missing:
```r
is.na(variable)
```



## Useful functions by package ##

### Tidyverse ###


1. To **subset** observations by their values:
**Example 1:**
```r
filter(MyDataFrame, column == value)
```

```r
> filter (diamonds, color == "E")
# A tibble: 9,797 x 10
   carat cut       color clarity depth table price     x     y     z
   <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
 1  0.23 Ideal     E     SI2      61.5    55   326  3.95  3.98  2.43
 2  0.21 Premium   E     SI1      59.8    61   326  3.89  3.84  2.31
 3  0.23 Good      E     VS1      56.9    65   327  4.05  4.07  2.31
 4  0.22 Fair      E     VS2      65.1    61   337  3.87  3.78  2.49
 5  0.2  Premium   E     SI2      60.2    62   345  3.79  3.75  2.27
 6  0.32 Premium   E     I1       60.9    58   345  4.38  4.42  2.68
 7  0.23 Very Good E     VS2      63.8    55   352  3.85  3.92  2.48
 8  0.23 Very Good E     VS1      60.7    59   402  3.97  4.01  2.42
 9  0.23 Very Good E     VS1      59.5    58   402  4.01  4.06  2.4 
10  0.23 Good      E     VS1      64.1    59   402  3.83  3.85  2.46
# ... with 9,787 more rows
```

**Example 2:**
```r
filter(MyDataFrame, column > value)
```

```r
> filter (diamonds, price > 400)
# A tibble: 53,689 x 10
   carat cut       color clarity depth table price     x     y     z
   <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
 1  0.23 Very Good F     VS1      60      57   402  4     4.03  2.41
 2  0.23 Very Good F     VS1      59.8    57   402  4.04  4.06  2.42
 3  0.23 Very Good E     VS1      60.7    59   402  3.97  4.01  2.42
 4  0.23 Very Good E     VS1      59.5    58   402  4.01  4.06  2.4 
 5  0.23 Very Good D     VS1      61.9    58   402  3.92  3.96  2.44
 6  0.23 Good      F     VS1      58.2    59   402  4.06  4.08  2.37
 7  0.23 Good      E     VS1      64.1    59   402  3.83  3.85  2.46
 8  0.31 Good      H     SI1      64      54   402  4.29  4.31  2.75
 9  0.26 Very Good D     VS2      60.8    59   403  4.13  4.16  2.52
10  0.33 Ideal     I     SI2      61.8    55   403  4.49  4.51  2.78
# ... with 53,679 more rows
```
**Example 3:**

```r
filter(MyDataFrame, columnA == value1, columnB == value2)
```
```r
> filter (diamonds, color == "E", price == 402)
# A tibble: 6 x 10
  carat cut       color clarity depth table price     x     y     z
  <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
1  0.23 Very Good E     VS1      60.7    59   402  3.97  4.01  2.42
2  0.23 Very Good E     VS1      59.5    58   402  4.01  4.06  2.4 
3  0.23 Good      E     VS1      64.1    59   402  3.83  3.85  2.46
4  0.23 Very Good E     VS2      60.8    58   402  3.98  4.02  2.43
5  0.23 Very Good E     VS2      60.5    58   402  3.92  3.95  2.38
6  0.23 Very Good E     VS2      60.8    58   402  3.97  4.05  2.44
```

**Example 4:**
```r
filter (MyDataFrame, columnA >=value1, columnB != value2)
```
```r
> filter (diamonds, price >= 18790, color != "E")
# A tibble: 10 x 10
   carat cut       color clarity depth table price     x     y     z
   <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
 1  1.71 Premium   F     VS2      62.3    59 18791  7.57  7.53  4.7 
 2  2.15 Ideal     G     SI2      62.6    54 18791  8.29  8.35  5.21
 3  2.04 Premium   H     SI1      58.1    60 18795  8.37  8.28  4.84
 4  2    Premium   I     VS1      60.8    59 18795  8.13  8.02  4.91
 5  2.29 Premium   I     SI1      61.8    59 18797  8.52  8.45  5.24
 6  2    Very Good H     SI1      62.8    57 18803  7.95  8     5.01
 7  2.07 Ideal     G     SI2      62.5    55 18804  8.2   8.13  5.11
 8  1.51 Ideal     G     IF       61.7    55 18806  7.37  7.41  4.56
 9  2    Very Good G     SI1      63.5    56 18818  7.9   7.97  5.04
10  2.29 Premium   I     VS2      60.8    60 18823  8.5   8.47  5.16
```



2. To reorder the rows in the dataset:


#### Importing data files ####

sss


## Creating plots

#### Scatterplots ####

The first thing we do when generating a plot with `ggplot2` is to create a coordinate system to which we can subsequently add layers.


```r
ggplot (data = MyDataFrame)
```
At least one layer should be added to the function above, otherwise we will have an empty graph.

If you want to create a **scatterplot**, you can use the function `geom_point( )` which will add data points to the aforementioned coordinate system. 

```r
ggplot(data = MyDataFrame) + 
  geom_point(mapping = aes(x = variable1, y = variable2))
```
![](https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot.PNG)

By changing or adding further levels to `aes`, the aesthetic properties of a scatterplot, we can change the size, the shape or even the colour of the data points. 

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


Please note the plus sign `+` should always come at the end of the line when creating `ggplot2` graphics.



In some cases, if you wish, your dataset can also be subsetted, and you can use `ggplot2` to create subplots to display each of the subsets.

```r
ggplot(data = MyDataFrame) + 
  geom_point(mapping = aes(x = variable1, y = variable2)) + 
  facet_wrap(~ aDiscreteVariable, nrow = 3)
```

`nrow` refers to the number of rows in which you would like the subplots to be displayed.
`ncol` can also be used to change the number of columns in which you would like the subplots to be displayed.

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot4.PNG">


Instead of generating a plot with points, we can use the function `geom_smooth` to create a plot with a smooth line fitted to our data.

```r
ggplot(data = MyDataFrame) + 
  geom_smooth(mapping = aes(x = variable1, y = variable2))
```
<img src="https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot5.PNG">

To remove the confidence interval, add `se=FALSE` to the code above.


It is also possible to add points **and** a smooth line to any given scatterplot:

```r
ggplot(data = MyDataFrame) +
  geom_point(mapping = aes(x = variable1, y = variable2)) +
  geom_smooth(mapping = aes(x = variable1, y = variable2))
```
*or*

```r
ggplot(data = MyDataFrame, mapping = aes (x = variable1, y= variable2) +
  geom_point()+
  geom_smooth()
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/scatterplot6.PNG">


You can also add different aesthetic values to different layers if you wish:

```r
ggplot(data = MyDataFrame, mapping = aes (x = variable1, y= variable2) +
  geom_point(mapping = aes(color = variable3)+
  geom_smooth(color = "red")
```
<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/scatterplot7.PNG">

With the function `geom_jitter()` we can add some degree of noise to the datapoints:

```r
ggplot(data = MyDataFrame, mapping = aes (x = variable1, y= variable2) +
  geom_point(mapping = aes(color = variable3)+
  geom_smooth(color = "red")+
  geom_jitter()
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/scatterplot8.PNG" >


#### Bar charts ####

To generate a bar chart with `ggplot2`, we can use the function `geom_bar`.

```r
ggplot (data = MyDataFrame) +
  geom_bar (mapping =  aes (x = variable1))
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/barchart1.PNG">

In the example above, the y axis displays the number (count) of occurrences of the variable in question. We can also generate a barchart with the proportion of cases in the y axis:

```r
ggplot (data = MyDataFrame) +
  geom_bar (mapping =  aes (x = variable1, y = stat(prop), group = 1))
```

Conveniently, bar charts can also be color-coded with the `fill` argument:

```r
ggplot (data = MyDataFrame) +
geom_bar (mapping = aes (x = variable1, fill = variable1)
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/barchart3.PNG" >

It may sometimes be hard to read long labels when the bars are displayed vertically, as in the example below:

```r
ggplot (data = MyDataFrame) +
geom_bar (mapping = aes (x = variable1, fill = variable1)
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/barchart4.PNG" >

To solve that, you can flip your plot so that the bars are displayed horizontally rather than the vertical default.

```r
ggplot(data = MyDataFrame) +
  geom_bar (mapping = aes(x = variable1, fill = variable1) +
  coord_flip ()
```

<img src = "https://github.com/simOne3107/R4CogPsy/blob/master/images/barchart5.PNG" >

Instead of a stacked bar chart, we can also display our data as follows:

```r
ggplot (data = MyDataFrame) +
geom_bar (mapping = aes (x = variable1, fill = variable1) +
coord_polar ()
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/barchart6.PNG" >

#### Box plots ####

`ggplot2` also allows us to easily create boxplots with the `geom_boxplot()` function.

```r
ggplot(data = MyDataFrame) +
geom_boxplot (mapping = aes (x = variable1, y = variable2)
```

<img src="https://github.com/simOne3107/R4CogPsy/blob/master/images/boxplot1.PNG">




[editor on GitHub](https://github.com/simOne3107/R4CogPsy/edit/master/README.md) 
