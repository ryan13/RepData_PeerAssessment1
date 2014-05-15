# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
## Loading and preprocessing the data

```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```



## What is mean total number of steps taken per day?
1. Make a histogram of the total number of steps taken each day

```r
steps.date <- aggregate(steps ~ date, data = activity, FUN = sum)
hist(steps.date$steps, xlab = "total amounts", ylab = "frequencies")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

2. Calculate and report the **mean** and **median** total number of
   steps taken per day


```r
mean(steps.date$steps)
```

```
## [1] 10766
```

```r
median(steps.date$steps)
```

```
## [1] 10765
```

## What is the average daily activity pattern?
1. Make a time series plot (i.e. `type = "l"`) of the 5-minute
   interval (x-axis) and the average number of steps taken, averaged
   across all days (y-axis)


```r
steps.interval <- aggregate(steps ~ interval, data = activity, FUN = mean)
plot(steps.interval, type = "l")
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 


2. Which 5-minute interval, on average across all the days in the
   dataset, contains the maximum number of steps?


```r
steps.interval$interval[which.max(steps.interval$steps)]
```

```
## [1] 835
```




## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
