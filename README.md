# Assignment8
## Sriya Reddy 

For this assignment, I was required to read and analyze the given data. 
I first installed the required libraries and packages using

```
> install.packages("pryr")
> require(pryr)
> install.packages("ISLR")
> require(ISLR)
> require(boot)
> install.packages("plyr")
> library(data.table)
> library(plyr)
```

I then read the provided data into a table in R, using

```
> student_assignment_6 <- read.table(file.choose(), header=TRUE, sep=",")
```

Viewing the data, 
```
> View(student_assignment_6)
```
![](https://github.com/venatisriya/assignment8/blob/main/Table.png)

