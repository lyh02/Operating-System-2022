---
layout: page
title: "homework7"
permalink: /homework/7/
---

# P302: Problems 6.5, 6.11, 6.15, 6.16, 6.18 (8th Edition)

**6.5.** Given the following state for the Banker’s Algorithm. 
- 6 processes P0 through P5
- 4 resource types: A (15 instances); B (6 instances)
- C (9 instances); D (10 instances)
- Snapshot at time T0:

<img src="https://s2.loli.net/2022/10/29/EUWBwl7jbZiPykY.png" width="600">

<img src="https://s2.loli.net/2022/10/29/zp2nZYjNBCgG3qU.png" width="600">

- a. Verify that the Available array has been calculated correctly.
- b. Calculate the Need matrix.
- c. Show that the current state is safe, that is, show a safe sequence of processes. In addition, to the sequence show how the Available (working array) changes as each process terminates.
- d. Given the request (3,2,3,3) from Process P5. Should this request be granted? Why or why not?

**6.11** Consider a system with a total of 150 units of memory, allocated to three processes as shown:

| Process | Max| Hold|
| - | - |  - |
| 1 | 70 | 45 |
| 2 | 60 | 40 |
| 3 | 60 | 15| 

Apply the banker’s algorithm to determine whether it would be safe to grant each of the following requests. If yes, indicate a sequence of terminations that could be guaranteed possible. If no, show the reduction of the resulting allocation table.
- a. A fourth process arrives, with a maximum memory need of 60 and an initial need of 25 units.
- b. A fourth process arrives, with a maximum memory need of 60 and an initial need of 35 units.

**6.15** Consider a system consisting of four processes and a single resource. The current state of the claim and allocation matrices are:

<!-- $$
% \mathbf{C}=\left(\begin{array}{l}3 \\ 2 \\ 9 \\ 7\end{array}\right) \quad \mathbf{A}=\left(\begin{array}{l}1 \\ 1 \\ 3 \\ 2\end{array}\right)
$$ -->

<img src="https://s2.loli.net/2022/10/29/LmrAs9P3gFUyOKo.png" width="300">

What is the minimum number of units of the resource needed to be available for this state to be safe?

**6.16** Consider the following ways of handling deadlock: (1) banker’s algorithm, (2) detect deadlock and kill thread, releasing all resources, (3) reserve all resources in advance, (4) restart thread and release all resources if thread needs to wait, (5) resource ordering, and (6) detect deadlock and roll back thread’s actions.
- a. One criterion to use in evaluating different approaches to deadlock is which approach permits the greatest concurrency. In other words, which approach allows the most threads to make progress without waiting when there is no deadlock? Give a rank order from 1 to 6 for each of the ways of handling deadlock just listed, where 1 allows the greatest degree of concurrency. Comment on your ordering.
- b. Another criterion is efficiency; in other words, which requires the least processor overhead. Rank order the approaches from 1 to 6, with 1 being the most efficient, assuming that deadlock is a very rare event. Comment on your ordering. Does your ordering change if deadlocks occur frequently?

**6.18** Suppose that there are two types of philosophers. One type always picks up his left fork first (a “lefty”), and the other type always picks up his right fork first (a “righty”). The behavior of a lefty is defined in Figure 6.12. The behavior of a righty is as follows:

```
begin 
    repeat
        think;
        wait ( fork[ (i+1) mod 5] ); wait ( fork[i] );
        eat;
        signal ( fork[i] );
        signal ( fork[ (i+1) mod 5] );
    forever
end;
```
Prove the following:
- a. Any seating arrangement of lefties and righties with at least one of each avoids deadlock.
- b. Any seating arrangement of lefties and righties with at least one of each prevents starvation.