# Day 8
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 8
Topics: Dynamic Programming - Travelling Salesman Problem
Date: 2022-12-07
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Travelling Salesman Problem

Given a set of cities and distances between every pair of cities, the problem is to find the shortest possible route that visits every city exactly once and returns to the starting point.

Formula of Dynamic Programming in TSP

```
p[i, L] = min(c[j, i] + p[j, L-{j}])
```

- `p[i, L]` is distance of path from initial *node* to *node* i after path L.
- `c[j, i]` is distance from *node* j to *node* i (cost)
- `c[j, i]` does note equal to `c[i, j]` because the *graph* contains 2 *directed edges* different *weight*.
- `L - {j}` is distance of path L substracted by *node* j
- Then, the shortest path for the *graph* is `p[A, {B, C, D}]` that means distance of path from initial *node* A after going through *node* B, C, D by any sequences (found shortest path)

## Case

![[Pasted image 20221207121342.png]]
