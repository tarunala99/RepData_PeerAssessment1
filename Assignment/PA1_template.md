---
output: html_document
---
Reproducible Research
========================
Loading and preprocessing the data

```r
setwd("~/Desktop/workinprogress")
mydata<-read.csv("activity.csv",header=TRUE,sep=",")
truedata<-split(mydata$steps,mydata$date)
histdata<-lapply(truedata,sum,na.rm=TRUE)
mean1<-lapply(truedata,mean,na.rm=TRUE)
histdata1<-lapply(truedata,median,na.rm=TRUE)
con<-as.matrix(histdata)
con1<-as.numeric(con,na.rm=TRUE)
```
Histogram of the total number of steps taken each day 

```r
hist(con1,xlab="Number of steps per day",main="Fitness tracker activity")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)


```r
## "The mean and median"
print(mean1)
```

```
## $`2012-10-01`
## [1] NaN
## 
## $`2012-10-02`
## [1] 0.4375
## 
## $`2012-10-03`
## [1] 39.41667
## 
## $`2012-10-04`
## [1] 42.06944
## 
## $`2012-10-05`
## [1] 46.15972
## 
## $`2012-10-06`
## [1] 53.54167
## 
## $`2012-10-07`
## [1] 38.24653
## 
## $`2012-10-08`
## [1] NaN
## 
## $`2012-10-09`
## [1] 44.48264
## 
## $`2012-10-10`
## [1] 34.375
## 
## $`2012-10-11`
## [1] 35.77778
## 
## $`2012-10-12`
## [1] 60.35417
## 
## $`2012-10-13`
## [1] 43.14583
## 
## $`2012-10-14`
## [1] 52.42361
## 
## $`2012-10-15`
## [1] 35.20486
## 
## $`2012-10-16`
## [1] 52.375
## 
## $`2012-10-17`
## [1] 46.70833
## 
## $`2012-10-18`
## [1] 34.91667
## 
## $`2012-10-19`
## [1] 41.07292
## 
## $`2012-10-20`
## [1] 36.09375
## 
## $`2012-10-21`
## [1] 30.62847
## 
## $`2012-10-22`
## [1] 46.73611
## 
## $`2012-10-23`
## [1] 30.96528
## 
## $`2012-10-24`
## [1] 29.01042
## 
## $`2012-10-25`
## [1] 8.652778
## 
## $`2012-10-26`
## [1] 23.53472
## 
## $`2012-10-27`
## [1] 35.13542
## 
## $`2012-10-28`
## [1] 39.78472
## 
## $`2012-10-29`
## [1] 17.42361
## 
## $`2012-10-30`
## [1] 34.09375
## 
## $`2012-10-31`
## [1] 53.52083
## 
## $`2012-11-01`
## [1] NaN
## 
## $`2012-11-02`
## [1] 36.80556
## 
## $`2012-11-03`
## [1] 36.70486
## 
## $`2012-11-04`
## [1] NaN
## 
## $`2012-11-05`
## [1] 36.24653
## 
## $`2012-11-06`
## [1] 28.9375
## 
## $`2012-11-07`
## [1] 44.73264
## 
## $`2012-11-08`
## [1] 11.17708
## 
## $`2012-11-09`
## [1] NaN
## 
## $`2012-11-10`
## [1] NaN
## 
## $`2012-11-11`
## [1] 43.77778
## 
## $`2012-11-12`
## [1] 37.37847
## 
## $`2012-11-13`
## [1] 25.47222
## 
## $`2012-11-14`
## [1] NaN
## 
## $`2012-11-15`
## [1] 0.1423611
## 
## $`2012-11-16`
## [1] 18.89236
## 
## $`2012-11-17`
## [1] 49.78819
## 
## $`2012-11-18`
## [1] 52.46528
## 
## $`2012-11-19`
## [1] 30.69792
## 
## $`2012-11-20`
## [1] 15.52778
## 
## $`2012-11-21`
## [1] 44.39931
## 
## $`2012-11-22`
## [1] 70.92708
## 
## $`2012-11-23`
## [1] 73.59028
## 
## $`2012-11-24`
## [1] 50.27083
## 
## $`2012-11-25`
## [1] 41.09028
## 
## $`2012-11-26`
## [1] 38.75694
## 
## $`2012-11-27`
## [1] 47.38194
## 
## $`2012-11-28`
## [1] 35.35764
## 
## $`2012-11-29`
## [1] 24.46875
## 
## $`2012-11-30`
## [1] NaN
```

```r
print(histdata1)
```

```
## $`2012-10-01`
## [1] NA
## 
## $`2012-10-02`
## [1] 0
## 
## $`2012-10-03`
## [1] 0
## 
## $`2012-10-04`
## [1] 0
## 
## $`2012-10-05`
## [1] 0
## 
## $`2012-10-06`
## [1] 0
## 
## $`2012-10-07`
## [1] 0
## 
## $`2012-10-08`
## [1] NA
## 
## $`2012-10-09`
## [1] 0
## 
## $`2012-10-10`
## [1] 0
## 
## $`2012-10-11`
## [1] 0
## 
## $`2012-10-12`
## [1] 0
## 
## $`2012-10-13`
## [1] 0
## 
## $`2012-10-14`
## [1] 0
## 
## $`2012-10-15`
## [1] 0
## 
## $`2012-10-16`
## [1] 0
## 
## $`2012-10-17`
## [1] 0
## 
## $`2012-10-18`
## [1] 0
## 
## $`2012-10-19`
## [1] 0
## 
## $`2012-10-20`
## [1] 0
## 
## $`2012-10-21`
## [1] 0
## 
## $`2012-10-22`
## [1] 0
## 
## $`2012-10-23`
## [1] 0
## 
## $`2012-10-24`
## [1] 0
## 
## $`2012-10-25`
## [1] 0
## 
## $`2012-10-26`
## [1] 0
## 
## $`2012-10-27`
## [1] 0
## 
## $`2012-10-28`
## [1] 0
## 
## $`2012-10-29`
## [1] 0
## 
## $`2012-10-30`
## [1] 0
## 
## $`2012-10-31`
## [1] 0
## 
## $`2012-11-01`
## [1] NA
## 
## $`2012-11-02`
## [1] 0
## 
## $`2012-11-03`
## [1] 0
## 
## $`2012-11-04`
## [1] NA
## 
## $`2012-11-05`
## [1] 0
## 
## $`2012-11-06`
## [1] 0
## 
## $`2012-11-07`
## [1] 0
## 
## $`2012-11-08`
## [1] 0
## 
## $`2012-11-09`
## [1] NA
## 
## $`2012-11-10`
## [1] NA
## 
## $`2012-11-11`
## [1] 0
## 
## $`2012-11-12`
## [1] 0
## 
## $`2012-11-13`
## [1] 0
## 
## $`2012-11-14`
## [1] NA
## 
## $`2012-11-15`
## [1] 0
## 
## $`2012-11-16`
## [1] 0
## 
## $`2012-11-17`
## [1] 0
## 
## $`2012-11-18`
## [1] 0
## 
## $`2012-11-19`
## [1] 0
## 
## $`2012-11-20`
## [1] 0
## 
## $`2012-11-21`
## [1] 0
## 
## $`2012-11-22`
## [1] 0
## 
## $`2012-11-23`
## [1] 0
## 
## $`2012-11-24`
## [1] 0
## 
## $`2012-11-25`
## [1] 0
## 
## $`2012-11-26`
## [1] 0
## 
## $`2012-11-27`
## [1] 0
## 
## $`2012-11-28`
## [1] 0
## 
## $`2012-11-29`
## [1] 0
## 
## $`2012-11-30`
## [1] NA
```
Time series plot of the average number of steps

```r
a<-split(mydata$steps,mydata$interval)
b<-lapply(a,mean,na.rm=TRUE)
c<-as.matrix(b,na.rm=TRUE)
d<-as.numeric(c,na.rm=TRUE)
```
The plot

```r
plot(names(a),c[,1],type="l",xlab="The intervals",ylab="Mean steps",main="Fitness tracker activity")
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png)


```r
## "The maximum number of steps in the interval"
min<-0
for (r in names(a))
{
        t=unlist(b[r])
        if(t>min)
        {
                min<-t;
                max<-r;
        }
}
```
The values and the interval

```r
print(min)
```

```
##      835 
## 206.1698
```

```r
print(max)
```

```
## [1] "835"
```
Imputing the missing data
This is done by subsituting the NA values with the mean value at the interval and 0's when the mean doesn't exist

```r
count=1
histdata<-lapply(truedata,mean,na.rm=TRUE)
con<-as.matrix(histdata)
while(count-1<dim(mydata)[1])
{
        if(is.na(mydata[count,"steps"]))
        {
                g<-b[mydata[count,"interval"]]
                g<-unlist(g)
                if(is.null(g))
                {
                        w=0;
                }
                if(!is.null(g))
                {
                        w=g;
                }
                mydata[count,"steps"]=0
        }
        count=count+1
}
truedata<-split(mydata$steps,mydata$date)
histdata<-lapply(truedata,sum,na.rm=TRUE)
mean1<-lapply(truedata,mean,na.rm=TRUE)
histdata1<-lapply(truedata,median,na.rm=TRUE)
con<-as.matrix(histdata)
con1<-as.numeric(con,na.rm=TRUE)
```
Missing Values

```r
def<-mydata$steps
print(length(def[is.na(def)]))
```

```
## [1] 0
```
The histogram after the imputing of the data

```r
hist(con1,xlab="Number of steps per day",main="Fitness tracker activity")
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10-1.png)


```r
## "Plotting data for weekdays and weekends"
t<-as.Date(mydata$date,"%Y-%m-%d")
s<-weekdays(t)
w=s=="Sunday" | s=="Saturday"
mydata["weekday"]=w
truedata<-split(mydata$steps,mydata$weekday)
truedata1<-split(mydata$interval,mydata$weekday)
a1<-split(mydata,mydata$weekday)
a100<-split(a1[["FALSE"]]$"steps",a1[["FALSE"]]$"interval")
b<-lapply(a100,mean,na.rm=TRUE)
c100<-as.matrix(b,na.rm=TRUE)
a1<-split(mydata,mydata$weekday)
a<-split(a1[["TRUE"]]$"steps",a1[["TRUE"]]$"interval")
b<-lapply(a,mean,na.rm=TRUE)
c<-as.matrix(b,na.rm=TRUE)
d<-as.numeric(c,na.rm=TRUE)
```
The plot

```r
par(mfcol=c(1,2))
plot(names(a),c[,1],type="l",xlab="time of day",ylab="number of steps",main="Weekday")
plot(names(a100),c100[,1],type="l",xlab="time of day",ylab="number of steps",main="Weekend")
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-12-1.png)



