----
**Question 1:** Suppose our input data to a map-reduce operation consists of integer values (the keys are not important). The map function takes an integer i and produces the list of pairs *(p,i)* such that p is a prime divisor of i. For example, map(12) = [(2,12),(3,12)].
The reduce function is addition. That is, reduce(*p,[i1,i2,...,ik]*) is (*p,i1+i2+...+ik*).
Compute the output, if the input is the set of integers 15, 21, 24, 30, 49. Then, identify, in the list below, one of the pairs in the output.

* (7,86)
* (2,102)
* (7,70)
* (3,75)

```
map(15) = [(3,15), (5,15)]
map(21) = [(3,21), (7,21)]
map(24) = [(2,24), (3,24)]
map(30) = [(2,30), (3,30), (5,30)]
map(49) = [(7,49)]

reduce(2, [24,30] = (2, 54)
reduce(3, [15,21,24,30] = (3, 90)
reduce(5, [15,30] = (5, 45)
reduce(7, [21,49] = (7, 70) 
```

**Answer:**  (7, 70) 

----
**Question 2:** Consider three Web pages with the following links:

![](https://d396qusza40orc.cloudfront.net/mmds/images/otc_pagerank2.gif)

Suppose we compute PageRank with a β of 0.7, and we introduce the additional constraint that the sum of the PageRanks of the three pages must be 3, to handle the problem that otherwise any multiple of a solution will also be a solution. Compute the `PageRanks a, b, and c` of the three pages A, B, and C, respectively. Then, identify from the list below, the true statement.

* b + c = 2.7
* a + c = 2.745
* b + c = 3.25
* b + c = 2.735

```
a = 0.3
b = 0.7 * (a/2) + 0.3
c = 0.7 * (a/2 + b + c) + 0.3

b = 0.405
c = 2.295
```
**Answer:**  b + c = 2.7

----
The next two problems refer to the following diagram.

![](https://lagunita.stanford.edu/assets/courseware/v1/6c5d817caf80f616e75cc185d6918267/asset-v1:ComputerScience+MMDS+SelfPaced+type@asset+block/pagerank3.gif)

**Question 3:** Suppose we compute PageRank with β=0.85. Write the equations for the PageRanks a, b, and c of the three pages A, B, and C, respectively. Then, identify in the list below, one of the equations.

* .85a = c + .15b
* b = .575a + .15c
* b = .475a + .05c
* .95a = .9c + .05b


```
a = 0.85 * c + 0.15
b = 0.85 * a/2 + 0.15
c = 0.85 * (a/2 + b) + 0.15
```
**Answer:**  .95a = .9c + .05b

**Question 4:** Assuming no "taxation," compute the PageRanks a, b, and c of the three pages A, B, and C, using iteration, starting with the "0th" iteration where all three pages have rank a = b = c = 1. Compute as far as the 5th iteration, and also determine what the PageRanks are in the limit. Then, identify the true statement from the list below.

* After iteration 4, b = 3/5
* In the limit, c = 9/7
* After iteration 5, c = 9/8
* After iteration 4, c = 11/8

```
       a     b     c
 a   0.050 0.05 0.90
 b   0.475 0.05 0.05
 c   0.475 0.90 0.05

 	a         b         c
 i = 1, 1	 0.5 	1.5
 i = 2, 1.5	 0.5 	1
 i = 3, 1	 0.75 	1.25
 i = 4, 1.25	 0.5 	1.25
 i = 5, 1.25	 0.625 	1.125
```
**Answer:**  After iteration 5, c = 9/8
