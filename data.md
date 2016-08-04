---
layout: page
title: Data Science
permalink: /data/
menu: main
---

# Data Science, Machine Learning, Artificial Intelligence, Deep Learning

# R

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

### Basics

{% highlight r %}
sum(flags$orange)
{% endhighlight %}

Printing to the console

{% highlight r %}
cat("hello world")
{% endhighlight %}

### Looping and Apply (with notes from Swirl)

#### Apply

Different typess of apply

- lapply ("list" apply)

| The lapply() function takes a list as input, applies a function to each element of the list, then returns a list
| of the same length as the original one. Since a data frame is really just a list of vectors (you can see this
| with as.list(flags)), we can use lapply() to apply the class() function to each column of the flags dataset.

{% highlight r %}
lapply(flag_colors, sum)
{% endhighlight %}

- sapply ("simplify" apply )

| In general, if the result is a list where every element is of length one, then sapply() returns a vector. If the
| result is a list where every element is a vector of the same length (> 1), sapply() returns a matrix. If sapply()
| can't figure things out, then it just returns a list, no different from what lapply() would give you.




{% highlight r %}
cls_list <- lapply(flags, class)
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