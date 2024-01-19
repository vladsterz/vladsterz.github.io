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
A computer process is an entity that provides all the resources needed
in order to execute a program. So, when we're talking about any program running on our machine, that program is a part of a process along with a virtual address space, the actual code at **least one thread of execution** (there are also some other stuff in there that ~~I hardly undestand~~ we don't care about them in this context ). So a thread (or more) is part of a process.