---
layout: page
title: Data Science
permalink: /data-ml-ai/
---

# Data Science, Machine Learning, Artificial Intelligence

- Decision Tree
- Support Vector Machine

### R Examples

```
data <- data.frame(read.csv('hw1_data.csv'))
mean(data$Ozone, na.rm=TRUE)
```

```
q <- subset(data, Month == 6)
mean(q$Solar.R, na.rm=TRUE)
```

```
m <- subset(data, Month == 5)
max(m$Ozone, na.rm=TRUE)
```