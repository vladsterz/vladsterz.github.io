---
title: C++ Thread Pool
#date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [C++, Programming]
tags: [c++, multithreading, programming, performance]     # TAG names should always be lowercase
published: false
---

# C++ Thread Pool, the only pool that all the kids run away from
What a topic I chose for my first post. So, thread pools, let me explain myself and the evil we're about to unveil. To do so, I must 
briefly explain some prerequisite terms.

## Processes and Threads
We'll start with processes and threads and the relation between them so we can understand what a computer program requires to be able to be executed.
### Process
A computer process is an entity that provides all the resources required
in order to execute a program. So, when we're refering to any program running on our machine, that program is a part of a process along with a virtual address space, the executable code and **at least one thread of execution** (there are also some other stuff in there that ~~I hardly undestand~~ we don't care about in this context ).

### Thread
A thread can be described as the basic unit of **compute** utilization, the most basic set of elements that can make a computation. (a stack pointer, a program counter and some registers usually are enough to do anything). As I mentioned previously, a thread is (not always*) a part of a process, along with memory pages,I/O handles, other threads and so on.

### Physical vs Logical Cores

To sum up, processes execute computations (or programs) using one or more threads.



(not always, there are cases threads exist in kernel level)