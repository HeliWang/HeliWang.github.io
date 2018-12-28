---
layout:     post
title:      Algorithm 4 - Priority Queues & Binary Search Tree
subtitle:   Introduce the priority queue data type and symbol tables.
date:       2018-12-28
author:     Heli
header-img: img/404-bg.jpg
catalog: true
tags:
    - Priority Queue
    - Symbol Tables
---

# Assignment - Collinear

![Points and lines](http://coursera.cs.princeton.edu/algs4/assignments/lines2.png)

Given a set of *n* distinct points in the plane, find every (maximal) line segment that connects a subset of 4 or more of the points.The method segments() should include each maximal line segment containing 4 (or more) points exactly once. For example, if 5 points appear on a line segment in the order p→q→r→s→t, then do not include the subsegments p→s or q→t. 

*Performance requirement.* The order of growth of <u>the running time of your program should be n^2 log n in the worst case and it should use space proportional to n plus the number of line segments returned</u>. 

**A sorting-based solution:** Think of p as the origin. For each other point q, determine the slope it makes with p.
<u>Sort the points according to the slopes they makes with p</u>. Check if any 3 (or more) adjacent points in the sorted order have equal slopes with respect to p. If so, these points, together with p, are collinear. Applying this method for each of the n points in turn yields an efficient algorithm to the problem. The algorithm solves the problem because points that have equal slopes with respect to p are collinear, and sorting brings such points together. The algorithm is fast because the bottleneck operation is sorting.

**Way of deduplication (check starting point is the lowest point among all points with the same slope):**

When you sort the points by the slope order, you get all collinear points grouped up. Let's consider one of these groups. Assume the points are sorted by the slope order relative to point P. Assume the collinear points in one of the groups are: A, B, C. As such a line can be drawn through all of P, A, B and C.

Let's sort P, A, B and C by the natural order (i.e. via Point#compareTo). Assume the result is: P -> A -> B -> C. That means the peaks of our line are P and C, and this is where we want to draw the line.

Now, as we continue iterating over all of our points, we eventually get to point A we previously considered in the group above. As such, we sort our points by the slope order relative to A. At this juncture we are guaranteed for one of the groups to consist of: P, B, C. Let's sort A, B, C, P by the natural order. The result is, again: P -> A -> B -> C.

Notice how the point A which we are considering on this particular iteration is not a peak (neither the smallest, nor the biggest point, based on the natural order). Point A is in the middle. Which means the line has either already been drawn or will be drawn at one point.