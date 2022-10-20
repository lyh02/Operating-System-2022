---
layout: page
title: "homework6"
permalink: /homework/6/
---

# P249: Problems 5.5, 5.6, 5.12, 5.13, 5.14, 5.15, 5.16 (8th Edition)

**5.5.** Is busy waiting always less efficient (in terms of using processor time) than a blocking wait? Explain.

**5.6.** Consider the following program:

``` c
boolean blocked [2]; 
int turn;
void P (int id)
{
	while (true) { 
		blocked[id] = true; 
		while (turn != id) {
			while (blocked[1-id]) 
				/* do nothing */;
			turn = id; 
		}
		/* critical section */
		blocked[id] = false;
		/* remainder */
	} 
}

void main() {
	blocked[0] = false; 
	blocked[1] = false; turn = 0;
	parbegin (P(0), P(1));
}
```

This software solution to the mutual exclusion problem for two processes is proposed in [HYMA66]. Find a counterexample that demonstrates that this solution is incorrect. It is interesting to note that even the *Communications of the ACM* was fooled on this one.

**5.12.** Consider the following definition of semaphores:

``` c
void semWait(s)
{
	if (s.count > 0) { 
		s.count--;
	}
	else {
		place this process in s.queue;
		block; 
	}
}

void semSignal (s) {
	if (there is at least one process blocked on semaphore s) {
		remove a process P from s.queue;
		place process P on ready list;
	}
	else
		s.count++;
}

```
Compare this set of definitions with that of Figure 5.3. Note one difference: With the preceding definition, a semaphore can never take on a negative value. Is there any difference in the effect of the two sets of definitions when used in programs? That is, could you substitute one set for the other without altering the meaning of the program?

The codes in Figure 5.3:

```
struct semaphore { 
	int count;
	queueType queue; 
};
void semWait(semaphore s) {
	s.count--;
	if (s.count < 0) {
		/* place this process in s.queue */;
		/* block this process */; 
	}
}

void semSignal(semaphore s)
{
	s.count++;
	if (s.count <= 0) {
		/* remove a process P from s.queue */;
		/* place process P on ready list */;
	}
}
```

**5.13.** Consider a sharable resource with the following characteristics: (1) As long as there are fewer than three processes using the resource, new processes can start using it right away. (2) Once there are three process using the resource, all three must leave before any new processes can begin using it. We realize that counters are needed to keep track of how many processes are waiting and active, and that these counters are themselves shared resources that must be protected with mutual exclusion. So we might create the following solution:

<img src="https://s2.loli.net/2022/10/20/VPAocqe2jCkwH97.png" width="600">

The solution appears to do everything right: All accesses to the shared variables are protected by mutual exclusion, processes do not block themselves while in the mutual exclusion, new processes are prevented from using the resource if there are (or were) three active users, and the last process to depart unblocks up to three waiting processes.
- a. The program is nevertheless incorrect. Explain why.
- b. Suppose we change the if in line 6 to a while. Does this solve any problem in the program? Do any difficulties remain?


**5.14.** Now consider this correct solution to the preceding problem:

<img src="https://s2.loli.net/2022/10/20/MmoZiKpeIRukChj.png" width="600">

- a. Explain how this program works and why it is correct. 
- b. This solution does not completely prevent newly arriving processes from cutting in line but it does make it less likely. Give an example of cutting in line.
- c. This program is an example of a general design pattern that is a uniform way to implement solutions to many concurrency problems using semaphores. It has been referred to as the **I’ll Do It For You** pattern. Describe the pattern.

**5.15.** Now consider another correct solution to the preceding problem:

<img src="https://s2.loli.net/2022/10/20/uMYfIhqEDaJnomL.png" width="600">

- a. Explain how this program works and why it is correct.
- b. Does this solution differ from the preceding one in terms of the number of processes that can be unblocked at a time? Explain.
- c. This program is an example of a general design pattern that is a uniform way to implement solutions to many concurrency problems using semaphores. It has been referred to as the Pass The Baton pattern. Describe the pattern.

**5.16.** It should be possible to implement general semaphores using binary semaphores. We can use the operations `semWaitB` and `semSignalB` and two binary semaphores, `delay` and `mutex`. Consider the following:

```
void semWait(semaphore s) 
{
	semWaitB(mutex); 
	s--;
	if (s < 0) {
		semSignalB(mutex);
		semWaitB(delay);
	}
	else SemsignalB(mutex);
}

void semSignal(semaphore s); 
{
	semWaitB(mutex);
	s++;
	if (s <= 0)
		semSignalB(delay);
	semSignalB(mutex);
}
```

Initially, `s` is set to the desired semaphore value. Each `semWait` operation decrements `s`, and each `semSignal` operation increments `s`. The binary semaphore mutex, which is initialized to 1, assures that there is mutual exclusion for the updating of `s`. The binary semaphore delay, which is initialized to 0, is used to block processes.

There is a flaw in the preceding program. Demonstrate the flaw and propose a change that will fix it. *Hint*: Suppose two processes each call `semWait(s)` when `s` is initially 0, and after the first has just performed `semSignalB(mutex)` but not performed `semWaitB(delay)`, the second call to `semWait(s)` proceeds to the same point. All that you need to do is move a single line of the program.
