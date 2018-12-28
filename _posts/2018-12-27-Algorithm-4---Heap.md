---
layout:     post
title:      Algorithm 4 - Priority Queues & Symbol Tables
subtitle:   Introduce the priority queue data type and binary search tree.
date:       2018-12-28
author:     Heli
header-img: img/404-bg.jpg
catalog: true
tags:
    - Priority Queue
    - Symbol Tables
---

# Overview

**Priority Queues** We introduce the priority queue data type and an efficient implementation using the *binary heap* data structure. This implementation also leads to an efficient sorting algorithm known as *heapsort*. We conclude with an applications of priority queues where we simulate the motion of N particles subject to the laws of elastic collision.

**Elementary Symbol Tables** We define an API for *symbol tables* (also known as *associative arrays*) and describe two elementary implementations using a sorted array (binary search) and an unordered list (sequential search). When the keys are Comparable, we define an extended API that includes the additional methods min, max floor, ceiling, rank, and select. To develop an efficient implementation of this API, we study the *binary search tree* data structure and analyze its performance.

# Priority Queues

‣API and elementary implementations

Order of growth of running time for priority queue with N items

| implementation  | insert | del max | max   |
| --------------- | ------ | ------- | ----- |
| unordered array | 1      | N       | N     |
| ordered array   | N      | 1       | 1     |
| binary heaps    | log N  | log N   | log N |

‣binary heaps (We study max heap here)

Binary tree: Empty or node with links to left and right binary trees.

Complete tree: Perfectly balanced, **except for bottom level**.

Binary heap.  Array representation of a heap-ordered complete binary tree.
Heap-ordered binary tree: 
・Parent's key no smaller than children's keys.
・Indices start at 1.

Proposition.  Largest key is a[1], which is root of binary tree.
Proposition.  Can use array indices to move through tree.
・Parent of node at k is at k/2. 
・Children of node at k are at 2k and 2k+1.

![](https://ws2.sinaimg.cn/large/006tNbRwly1fyn72j99r0j30nc0ek74u.jpg)

‣heapsort

‣event-driven simulation

# Assignment: 8-Puzzle

Programming Assignment: 8-Puzzle.** Your programming assignment is to implement the famous A* search algorithm to solve a combinatorial problem, and to substantially speed it up with an efficient priority queue implementation.