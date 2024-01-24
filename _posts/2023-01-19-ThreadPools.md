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
A thread can be described as the basic unit of **compute** utilization, the most basic set of elements that can make a computation (a stack pointer, a program counter and some registers usually are enough to do anything). As I mentioned previously, a thread is (*not always) a part of a process, along with memory pages,I/O handles, other threads and so on. Each thread executes independently of the other threads (unless stated differently) and most importantly, they can execute **silmutaneously**. Simply speaking, we can have multiple computation procedures on our machine **silmutaneously**, which is a pretty big thing, since we can split a task in half and assign it to 2 threads (if our machine supports it) and get the result in (theoretically) half the time.

### Multi-threading
Before we are carried away by all the computations we can do faster, I think it's proper to talk briefly about multi-threading. So, ok, we can **spawn** threads in processes and do stuff faster, but how many of them can we actually spawn?. To answer this one shall inspect its CPU. Modern CPUs consists of multiple __cores__, which are independent processing units and actually is the number of threads we can spawn on that machine, unless our CPU supports [simultaneous multithreading](https://en.wikipedia.org/wiki/Simultaneous_multithreading) which supports multiple threads per core. 

Ok done, to sum up, processes execute computations (or programs) using one or more threads. We can use more than one thread, in proper ways and actually make our computation faster.

Let's look into some code now. For start, we'll just execute some computations on a thread, just to see how the code looks like.


(not always, there are cases threads exist in kernel level)