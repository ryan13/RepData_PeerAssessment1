# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
## Loading and preprocessing the data

```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```



## What is mean total number of steps taken per day?

```r
steps.date <- aggregate(steps ~ date, data = activity, FUN = sum)
hist(steps.date$steps, xlab = "total amounts", ylab = "frequencies")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
