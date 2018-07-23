----
**Question 1:** Here is a matrix representing the signatures of seven columns, C1 through C7.

<p align="center">
  <img src= "https://raw.githubusercontent.com/owlfonso/Mining-Massive-Datasets/master/media/2-1.png"/>
</p>

Suppose we use locality-sensitive hashing with three bands of two rows each. Assume there are enough buckets available that the hash function for each band can be the identity function (i.e., columns hash to the same bucket if and only if they are identical in the band). Find all the candidate pairs, and then identify one of them in the list below.
* C2 and C4
* C4 and C7 
* C2 and C6
* C3 and C6

**Answer:**  C4 and C7
```
C1 and C3 both have (2.3)
C1 and C4 both have (1.2)
C1 and C6 both have (2.3), (3.4), (4.5)
C2 and C5 both have (2.3)
C4 and C7 both have (1.4)
```

----
**Question 2:** Suppose we have computed signatures for a number of columns, and each signature consists of 24 integers, arranged as a column of 24 rows. There are N pairs of signatures that are 50% similar (i.e., they agree in half of the rows). There are M pairs that are 20% similar, and all other pairs (an unknown number) are 0% similar.


We can try to find 50%-similar pairs by using Locality-Sensitive Hashing (LSH), and we can do so by choosing bands of 1, 2, 3, 4, 6, 8, 12, or 24 rows. Calculate approximately, in terms of N and M, the number of false positive and the number of false negatives, for each choice for the number of rows. Then, suppose that we assign equal cost to false positives and false negatives (an atypical assumption). Which number of rows would you choose if M:N were in each of the following ratios: 1:1, 10:1, 100:1, and 1000:1? Identify the correct choice from the list below.


* For M = 10N, pick r = 3.
* For M = 1000N, pick r = 12.
* For M = N, pick r = 1.
* For M = 100N, pick r = 6.

**Answer:**  For M = 100N, pick r = 6

```
Here is the table of false positives and false negatives for various values of r and b:
```
<p align="center">
  <img src= "https://raw.githubusercontent.com/owlfonso/Mining-Massive-Datasets/master/media/2-2.png"/>
</p>


```
If M=N, we need to find the value of r that minimizes the sum of the last two columns; this value is r = 3, 
where it is .40585. If M=10N, then we need to minimize the sum of the last column (false negatives) and 10 times
the third column (false positives). This minimum occurs at r = 4, where it is .77455. Similarly, 
the minimum of the last column plus 100 times the third column occurs at r = 5, where it is .96455.
The minimum of the last column plus 1000 times the third column is at r = 6, where it is .99601.
```

----
**Question 3:** Find the set of 2-shingles for the "document":
>**ABRACADABRA**


and also for the "document":
>**BRICABRAC**




Answer the following questions:
>1. How many 2-shingles does ABRACADABRA have?
>2. How many 2-shingles does BRICABRAC have?
>3. How many 2-shingles do they have in common?
>4. What is the Jaccard similarity between the two documents"?


Then, find the true statement in the list below.
* There are 4 shingles in common.
* BRICABRAC has 7 2-shingles.
* There are 6 shingles in common.
* ABRACADABRA has 10 2-shingles.

```
The 2-shingles for ABRACADABRA: AB, BR, RA, AC, CA, AD, DA.
The 2-shingles for BRICABRAC: BR, RI, IC, CA, AB, RA, AC.
There are 5 shingles in common:AB, BR, RA, AC, CA.
As there are 9 different shingles in all, the Jaccard similarity is 5/9.
```
**Answer:**  BRICABRAC has 7 2-shingles.

----
**Question 4:** Consider the following matrix:

<p align="center">
  <img src= "https://raw.githubusercontent.com/owlfonso/Mining-Massive-Datasets/master/media/2-4.png"/>
</p>

Compute the Jaccard similarity between each pair of columns. Which of the following is the true similarity of the two stated columns?
* C1 and C2 have similarity 1/5
* C1 and C4 have similarity 1/4
* C2 and C4 have similarity 1/4
* C1 and C4 have similarity 1/6

**Answer:**  C2 and C4 have similarity 1/4

```
sim(C1,C2) = 0/5 = 0 
sim(C1,C3) = 2/4 = 1/2
sim(C1,C4) = 1/3
sim(C2,C3) = 1/4
sim(C2,C4) = 1/4
sim(C3,C4) = 1/5
```
----
**Question 5:** Consider the following matrix:
<p align="center">
  <img src= "https://raw.githubusercontent.com/owlfonso/Mining-Massive-Datasets/master/media/2-5.png"/>
</p>

Perform a minhashing of the data, with the order of rows: R4, R6, R1, R3, R5, R2. Which of the following is the correct minhash value of the stated column? Note: we give the minhash value in terms of the original name of the row, rather than the order of the row in the permutation. These two schemes are equivalent, since we only care whether hash values for two columns are equal, not what their actual values are. 
* The minhash value for C4 is R4
* The minhash value for C1 is R5
* The minhash value for C3 is R5
* The minhash value for C2 is R4

**Answer:**  The minhash value for C1 is R5
```
Order of rows is R4, R6, R1, R3, R5, R2. So we need to find the first '1' in every column with that order.
h(C1) = R5
h(C2) = R6
h(C3) = R4
h(C4) = R3

```


