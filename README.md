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

I now used the command below to find the mean according to the category 'Sex' and obtained the following.

```
> student_average = ddply(student_assignment_6, "Sex", transform, Grade.Average=mean(Grade))
> student_average
        Name Age    Sex Grade Grade.Average
1      Lauri  21 Female    90       86.9375
2     Leonie  21 Female    91       86.9375
3    Sherlyn  22 Female    85       86.9375
4    Mikaela  20 Female    69       86.9375
5       Aiko  24 Female    97       86.9375
6   Tiffaney  21 Female    78       86.9375
7     Corina  23 Female    81       86.9375
8  Petronila  23 Female    98       86.9375
9     Alecia  20 Female    87       86.9375
10   Shemika  23 Female    97       86.9375
11    Fallon  22 Female    90       86.9375
12   Deloris  21 Female    67       86.9375
13    Randee  23 Female    91       86.9375
14     Eboni  20 Female    84       86.9375
15   Delfina  19 Female    93       86.9375
16 Ernestina  19 Female    93       86.9375
17      Raul  25   Male    80       80.2500
18    Booker  18   Male    83       80.2500
19   Raphael  23   Male    91       80.2500
20      Milo  19   Male    67       80.2500
```

I wrote the data to a .csv file using the command

```
> write.table(student_average, "Sorted_Average", sep=",")
```

Now for the second and third steps, I need to filter out the students whose names contain the letter 'i' and save the data in a separate .csv file. 
For this, I used the following command.

```
students_i = subset(student_assignment_6, grepl("[iI]", student_assignment_6$Name))
```

I also found that the following command also does the same job. 

```
> students_i = subset(student_assignment_6, grepl("i", student_assignment_6$Name, ignore.case = T))
```

Printing out `students_i`, we get

```
> students_i
        Name Age    Sex Grade
3      Lauri  21 Female    90
4     Leonie  21 Female    91
6    Mikaela  20 Female    69
8       Aiko  24 Female    97
9   Tiffaney  21 Female    78
10    Corina  23 Female    81
11 Petronila  23 Female    98
12    Alecia  20 Female    87
13   Shemika  23 Female    97
15   Deloris  21 Female    67
17     Eboni  20 Female    84
18   Delfina  19 Female    93
19 Ernestina  19 Female    93
20      Milo  19   Male    67
```

I wrote to a .csv file using

```
> write.table(students_i, "Subset", sep=",")
```

From this assignment, I learnt interesting ways to process data and I found the file.choose() attribute very useful as it allows us to select what file we want to analyze without having to specify the file location. 






