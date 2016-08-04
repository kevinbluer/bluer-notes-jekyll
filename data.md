---
layout: page
title: Data Science
permalink: /data-ml-ai/
---

# Data Science, Machine Learning, Artificial Intelligence, Deep Learning

### R Examples

Loading data into a data frame and calculating the mean of a column called 'Ozone'.

{% highlight r %}
head(flags) # show the first 6 rows of the data frame
dim(flags) # to check the dimensions of the data set (e.g. "[1] 194  30" would tell us "that there are 194 rows, or observations, and 30 columns, or variables")
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

Printing to the console

{% highlight r %}
cat("hello world")
{% endhighlight %}

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