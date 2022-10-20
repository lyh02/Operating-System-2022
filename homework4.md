---
layout: page
title: "homework4"
permalink: /homework/4/
---

# P249: Problem 4.5 (8th Edition)   P428: Problems 9.1, 9.2, 9.3 (8th Edition)

**4.5.** If a process exits and there are still threads of that process running, will they continue to run?

**9.1** Consider the following workload:

![image-20221002102141748](https://cdn.jsdelivr.net/gh/lyh02/images/img/image-20221002102141748.png)

**a.** Show the schedule using shortest remaining time, nonpreemptive priority (a smaller priority number implies higher priority) and round robin with quantum 30 ms. Use time scale diagram as shown below for the FCFS example to show the schedule for each requested scheduling policy.

Example for FCFS (1 unit = 10 ms):

![image-20221002102222244](https://cdn.jsdelivr.net/gh/lyh02/images/img/image-20221002102222244.png)

**b.** What is the average waiting time of the above scheduling policies?

**9.2.** Consider the following set of processes:

![image-20221002102256230](https://cdn.jsdelivr.net/gh/lyh02/images/img/image-20221002102256230.png)

Perform the same analysis as depicted in Table 9.5 and Figure 9.5 for this set.

**9.3.** Prove that, among nonpreemptive scheduling algorithms, SPN provides the minimum average waiting time for a batch of jobs that arrive at the same time. Assume that the scheduler must always execute a task if one is available.