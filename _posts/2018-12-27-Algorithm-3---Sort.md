---
layout:     post
title:      Algorithm 3 - Quick Sort & Merge Sort
subtitle:   Study the randomized sort algorithm and analyze its performance
date:       2018-12-27
author:     Heli
header-img: img/home-bg-geek.jpg
catalog: true
tags:
    - Quick Sort
    - Merge Sort
    - Algorithm
---

# Assignment - Collinear

![Points and lines](http://coursera.cs.princeton.edu/algs4/assignments/lines2.png)

Given a set of *n* distinct points in the plane, find every (maximal) line segment that connects a subset of 4 or more of the points.The method segments() should include each maximal line segment containing 4 (or more) points exactly once. For example, if 5 points appear on a line segment in the order p→q→r→s→t, then do not include the subsegments p→s or q→t. 

*Performance requirement.* The order of growth of <u>the running time of your program should be n^2 log *n* in the worst case and it should use space proportional to *n* plus the number of line segments returned</u>. 

**A sorting-based solution:** Think of p as the origin. For each other point q, determine the slope it makes with p.
<u>Sort the points according to the slopes they makes with p</u>. Check if any 3 (or more) adjacent points in the sorted order have equal slopes with respect to p. If so, these points, together with p, are collinear. Applying this method for each of the n points in turn yields an efficient algorithm to the problem. The algorithm solves the problem because points that have equal slopes with respect to p are collinear, and sorting brings such points together. The algorithm is fast because the bottleneck operation is sorting.