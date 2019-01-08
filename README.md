# Cuckoo-Hashing
# Abstract
In this project you will design, implement, and analyze one algorithm for the hashing problem. The algorithm is called Cuckoo Hashing, presented in class. For this problem, you will design and implement one algorithm in C++, test it on various inputs and complete a hash table with a given input. No algorithm analysis is needed for this project.
The Cuckoo Hashing Algorithm
There are several versions of cuckoo hashing. The version we learned in class is the simplest, where there are two hash functions, and thus only two places where any given item could be stored in the table. Let us consider the set of keys to be printable ASCII strings of length no more than 80. Let us consider the hash table size to be 17 .

If key is the string representing the key, then let keysize be the size of the string and key[i] be the ASCII code of the (i+1)th character in the string key read from left to right: key=key0 key1...keykeysize-1
Java uses the following hash function on strings:
 val=31keysize-1key0 +31keysize-2key1+...+311keykeysize-2 +keykeysize-1

Let us consider two hash functions, f1 and f2. Function f2 will compute the hash value using Java’s hash function formula, while the function f1 computes a different hash value using a different hash function. Function f1 computes a large number and then brings the result into the proper range using the formulas below:
val=i=0keysize-1key[i]31 i
f1=val % tablesize
if f1<0then f1=f1+ tablesize
 
Function f2 also computes a large number and then brings the result into the proper range using the formulas below:

val=i=0keysize-1key[keysize-i-1]31 i
f2=val % tablesize
if f2<0then f2=f2+ tablesize
Both functions  f1 and f2 compute first a large number then it brings the result into the proper range 0..tablesize-1. But we bring the intermediate results into the proper range after each calculation, we do not need to wait until we compute the final result. Also, we can ring the power term 31indexinto the proper range before multiplying it with keyindex

You need to insert the strings  below (also given in the input file in6.txt) into the hash table provided next. Please put an empty line at the end of the file.

Algorithm Engineering
California State University
Fullerton
College of Engineering
and Computer Science
Department of Computer
Science
Dynamic Programming
Monge Properties
String Matching
Matrix Searching
Optimal Tree Construction
Online algorithms
emphasis on
Server Problem
Some related problem
Self-Stabilization
One of the greatest
mysteries in science
Quantum Nature of Universe
In physics and
are known
Cuckoo hashing is fun

into the hash table (next page) using f1 for the first table and f2 for the second table. Show the result of the insertion in the table shown on next page.

Hint: consider a two-dimensional table of strings t, where t[0] is T1 and t[1] is T2. Consider a variable index that oscillates between 0 and 1as it would have oscillated between T1 and T2. In C++, the value of index could be changed using the tertiary operator: index = index? 0:1. Depending on the value of index, either apply hash function f1 (index == 0) or f2 (index == 1).


# Input the file name (no spaces)!
      in4.txt

      String <Algorithm Engineering> will be placed at t[11][0]
      String <California> will be placed at t[16][0]
      String <State University> will be placed at t[5][0]
      String <Fullerton> will be placed at t[15][0]
      String <College of Engineering and Computer Science> will be placed at t[10][0]
      String <Department of Computer Science> will be placed at t[5][0] replacing <State University>
      String <State University> will be placed at t[7][1]
      String <Dynamic Programming> will be placed at t[3][0]
      String <Monge Properties> will be placed at t[9][0]
      String <String Matching> will be placed at t[16][0] replacing <California>
      String <California> will be placed at t[2][1]
      String <Matrix Searching> will be placed at t[5][0] replacing <Department of Computer Science>
      String <Department of Computer Science> will be placed at t[12][1]
      String <Optimal Tree Construction> will be placed at t[5][0] replacing <Matrix Searching>
      String <Matrix Searching> will be placed at t[11][1]
      String <Online algorithms> will be placed at t[0][0]
      String <emphasis on> will be placed at t[15][0] replacing <Fullerton>
      String <Fullerton> will be placed at t[3][1]
      String <Server Problem> will be placed at t[9][0] replacing <Monge Properties>
      String <Monge Properties> will be placed at t[2][1] replacing <California>
      String <California> will be placed at t[16][0] replacing <String Matching>
      String <String Matching> will be placed at t[16][1]
