---
layout: page
title: "homework8"
permalink: /homework/8/
---

# P331: Problems 7.5, 7.6, 7.8, 7.9 (8th Edition)

**7.5** Another placement algorithm for dynamic partitioning is referred to as worst-fit. In this case, the largest free block of memory is used for bringing in a process.
- a. Discuss the pros and cons of this method compared to first-, next-, and best-fit.
- b. What is the average length of the search for worst-fit?


**7.6** This diagram shows an example of memory configuration under dynamic partitioning, after a number of placement and swapping-out operations have been carried out. Addresses go from left to right; gray areas indicate blocks occupied by processes; white areas indicate free memory blocks. The last process placed is 2-Mbyte and is marked with an X. Only one process was swapped out after that.
<img src="https://s2.loli.net/2022/11/07/4XEVSGOdHm9qznA.png" width=600>
- a. What was the maximum size of the swapped-out process?
- b. What was the size of the free block just before it was partitioned by X?
- c. A new 3-Mbyte allocation request must be satisfied next. Indicate the intervals of memory where a partition will be created for the new process under the following four placement algorithms: best-fit, first-fit, next-fit, and worst-fit. For each algorithm, draw a horizontal segment under the memory strip and label it clearly.

**7.8** 
Consider a buddy system in which a particular block under the current allocation has an address of `011011110000`.
- a. If the block is of size 4, what is the binary address of its buddy?
- b. If the block is of size 16, what is the binary address of its buddy?

**7.9** Let $$\text{buddy}_k(x) = \text{address} $$ of the buddy of the block of size $2^k$ whose address is $x$. Write a general expression for $$\text{buddy}_k(x)$$.
