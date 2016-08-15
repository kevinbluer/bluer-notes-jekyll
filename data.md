---
layout: page
title: Data Science
permalink: /data/
---

# Data Science, Machine Learning, Artificial Intelligence, Deep Learning

# R

### Looking at Data

Using the [United States Department of Agriculture's PLANTS Database](http://plants.usda.gov/adv_search.html) loaded into *plants*.

{% highlight r %}
ls()
class(plants)
dim(plants) # to see exactly how many rows and columns we're dealing with (assuming it's a data frame)
nrow(plants) # number of rows
ncol(plants) # number of columns
object.size(plants) # to see how much space the dataset is occupying in memory
names(plants) # return a character vector of the column names (e.g. variables)
head(plants) # to look at the top of the dataset
head(plants, 10)
tail(plants, 15)
summary(plants)
table(plants$Active_Growth_Period)
str(plants)
{% endhighlight %}

### Simulating

"One of the great advantages of using a statistical programming language like R is its vast collection of tools for simulating random numbers."

{% highlight r %}
sample(1:6, 4, replace = TRUE) # simulating rolling four six-sided dice
sample(1:20, 10) # given there was no replacement this time, no number appears more than once in the output
LETTERS # a predefined variable in R containing a vector of all 26 letters of the English alphabet
sample(LETTERS)
flips <- sample(c(0,1), 100, replace = TRUE, prob = c(0.3, 0.7)) # 100 coin flips, with a bias towards 0
sum(flips) # yep the bias is correct
{% endhighlight %}

Each probability distribution in R has the following:

- r*** function (for "random")
- d*** function (for "density")
- p*** for "probability"
- q*** (for "quantile")

##### rbinom

"A binomial random variable represents the number of 'successes' (heads) in a given number of independent 'trials' (coin flips)." Examples below:

{% highlight r %}
rbinom(1, size = 100, prob = 0.7)
flips2 <- rbinom(n = 100, size=1, prob=0.7)
{% endhighlight %}

###### rnorm

"The standard normal distribution has mean 0 and standard deviation 1. As you can see under the 'Usage' section in the documentation, the default values for the 'mean' and 'sd' arguments to rnorm() are 0 and 1, respectively. Thus, rnorm(10) will generate 10 random numbers from a standard normal distribution. Give it a try."

{% highlight r %}
rnorm(10)
rnorm(10, mean = 100, sd = 25)
{% endhighlight %}

##### rpois

"Finally, what if we want to simulate 100 *groups* of random numbers, each containing 5 values generated from a Poisson distribution with mean 10?"

{% highlight r %}
rpois(5, lambda = 10)
my_pois <- replicate(100, rpois(5, 10))
cm <- colMeans(my_pois) # the mean of each column in my_pois using the colMeans() function
{% endhighlight %}

Note that "replicate() created a matrix, each column of which contains 5 random numbers generated from a Poisson distribution with mean 10."

### Data Types

##### Matrices

{% highlight r %}
m <- matrix(
	c(3, 1, 5, 7), # the data elements 
	nrow=2,        # number of rows 
	ncol=2,        # number of columns 
	byrow = TRUE)
{% endhighlight %}

The above produces the following:

![Matrix Example](/images/r-matrix.png)

More examples [here](http://www.r-tutor.com/r-introduction/matrix).

### Basics

{% highlight r %}
x <- iris[iris$Species == "virginica",]
mean(x$Sepal.Length)

sum(flags$orange)
{% endhighlight %}

Printing to the console

{% highlight r %}
cat("hello world")
{% endhighlight %}

### Code Samples

Loading data into a data frame and calculating the mean of a column called 'Ozone'.

{% highlight r %}
head(flags) # show the first 6 rows of the data frame
dim(flags) # to check the dimensions of the data set (e.g. "[1] 194  30" would tell us "that there are 194 rows, or observations, and 30 columns, or variables")
viewinfo()
class(flags)
{% endhighlight %}

{% highlight r %}
data <- data.frame(read.csv('hw1_data.csv'))
mean(data$Ozone, na.rm=TRUE)
{% endhighlight %}

{% highlight r %}
q <- subset(data, Month == 6)
mean(q$Solar.R, na.rm=TRUE)
{% endhighlight %}

{% highlight r %}
m <- subset(data, Month == 5)
max(m$Ozone, na.rm=TRUE)
{% endhighlight %}

### Looping and Apply (with notes from Swirl)

#### Apply

Different typess of apply. Note that applying adheres to the "Split-Apply-Combine" methodology.

- lapply ("list" apply)

| The lapply() function takes a list as input, applies a function to each element of the list, then returns a list
| of the same length as the original one. Since a data frame is really just a list of vectors (you can see this
| with as.list(flags)), we can use lapply() to apply the class() function to each column of the flags dataset.

{% highlight r %}
lapply(flag_colors, sum)
{% endhighlight %}

{% highlight r %}
cls_list <- lapply(flags, class)
{% endhighlight %}

{% highlight r %}
lapply(flag_shapes, range)
{% endhighlight %}

- sapply ("simplify" apply )

| In general, if the result is a list where every element is of length one, then sapply() returns a vector. If the
| result is a list where every element is a vector of the same length (> 1), sapply() returns a matrix. If sapply()
| can't figure things out, then it just returns a list, no different from what lapply() would give you.

{% highlight r %}
sapply(flag_colors, mean)
{% endhighlight %}

{% highlight r %}
shape_mat <- sapply(flag_shapes, range)
shape_mat
{% endhighlight %}

- vapply

| Whereas sapply() tries to 'guess' the correct format of the result, vapply() allows you to specify it explicitly.
| If the result doesn't match the format you specify, vapply() will throw an error, causing the operation to stop.
| This can prevent significant problems in your code that might be caused by getting unexpected return values from
| sapply().

{% highlight r %}
vapply(flags, unique, numeric(1))
{% endhighlight %}

- tapply ("Apply a Function Over a Ragged Array")

| As a data analyst, you'll often wish to split your data up into groups based on the value of some variable, then
| apply a function to the members of each group. The next function we'll look at, tapply(), does exactly that.

## Base Graphics

"One of the greatest strengths of R, relative to other programming languages, is the ease with which we can create publication-quality graphics. In this lesson, you'll learn about base graphics in R."

Some of the more advanced libraries include: lattice, ggplot2 and ggvis (not included below).

##### plot

{% highlight r %}
data(cars)
plot(cars) # note that R tries very hard to give you something sensible given the information that you have provided to it. also note that 'plot' is short for 'scatterplot'.
?plot # there's quite a few arguments, e.g.
plot(x = cars$speed, y = cars$dist, xlab = "Speed", ylab = "Stopping Distance", main="My Plot")
plot(cars, main="My Plot", sub="My Plot Subtitle") # moar
?par # for a full list of the parameters that can be passed into 'plot'
plot(cars, col=2) # changing the plots to red
plot(cars, xlim = c(10,15)) # limited the values shown on the x-axis
?points # note that you can change the shape of the symbols in the plot
plot(cars, pch=2) # tada
ggplot2 # ... is far more intitive than some of the above arcaneness
{% endhighlight %}

##### boxplot

"boxplot(), like many R functions, also takes a "formula" argument, generally an expression with a tilde ("~") which indicates the relationship between the input variables. This allows you to enter something like mpg ~ cyl to plot the relationship between cyl (number of cylinders) on the x-axis and mpg (miles per gallon) on the y-axis."

{% highlight r %}
boxplot(formula = mpg ~ cyl, data = mtcars)
{% endhighlight %}

##### histogram

{% highlight r %}
hist(mtcars$mpg)
{% endhighlight %}

## General

# Tools and Services

- OpenAI Gym (https://gym.openai.com)
- Tensorflow Playground (http://playground.tensorflow.org)

### Concepts

- Decision Trees
- Support Vector Machines

### R Resources

- [The Comprehensive R Archive Network](https://cran.r-project.org)
- [Microsoft R Application Network](https://mran.microsoft.com)

### AI Resources

- [Berkley AI Materials](http://ai.berkeley.edu/lecture_videos.html)

### TensorFlow

- [Fizz Buzz in TensorFlow](http://joelgrus.com/2016/05/23/fizz-buzz-in-tensorflow/)

### Courses

- [Data Camp](https://www.datacamp.com)
- [Coursera Data Science](https://www.coursera.org/specializations/jhu-data-science)

### Data Sets

- [Flags dataset from the UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Flags)
- [Iris](#)
- [mtcars](#)
- [United States Department of Agriculture's PLANTS Database](http://plants.usda.gov/adv_search.html)

### Thoughts & Notes

- [Is Data Scientist a Useless Job Title?](https://yanirseroussi.com/2016/08/04/is-data-scientist-a-useless-job-title/)