---
layout: page
title: Data Science
permalink: /data/
menu: main
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