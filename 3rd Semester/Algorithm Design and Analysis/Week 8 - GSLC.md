# Week 8 - GSLC
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 16 & 17
Topics: Dynamic Programming - Multistage Graph
Date: 2022-12-15
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Multistage Graph

A graph with special characteristics
1. Directed graph
2. Each edge has weight
3. Has only 1 source (called as $s$) and 1 sink (called as $t$)
4. Path from source to sink consists some stages $V_1$ to $V_k$
5. All stages connect node in $V_i$ to node $V_{i+1}$ where $1 \le i \le k$
6. There are $k$ stages, where $k \ge 2$
7. Each path from $s$ to $t$ is consequence of chouse $k-2$

## Graph Problem

Short path finding problem from source to sink in Multistage Graph. The problem is one of good implementation of Dynamic Programming.

## DP in Multistage Graph Problem

- Solving of Multistage Graph problem using Dynamic Programming in shortest path of previous stage added by distance of one of an edge connects to a stage

## Forward Method

Calculate distance to front (from sink)

- Analysis by calculating *path* from a *node* to *sink*
- Formula: $cost(i, j) = min[c(j, k) + cost(i+1, k)]$
- Calculation starts from nodes in stage $k-2$
- $c(j, i)$ is distance of path from *node* $j$ to *node* $i$ to $sink(t)$
- $c(j, l)$ is distance of path from *node* $j$ to *node* $l$

## Backward Method

Calculate distance to back (from source)

- Analysis by calculating *path* from source to a *node*
- Formula: $bcost(i, j) = min[bcost(i - 1, l) + c(l, j)]$
- $bcost(i,j)$ is distance of path *backward* from source to node $j$ in stage $i$
- $c(j, l)$ is distance of path from *node* $j$ to *node* $l$

# Assignment

1. Apakah semua directed graph dapat dihitung shortest path-nya dengan menggunakan teknik DP: Multi Stage Graph?

Tidak, karena syarat-syarat untuk menggunakan teknik DP: Multi Stage Graph yaitu:

- Directed graph
- Setiap edge punya weight
- Hanya memiliki 1 source (dinotasikan $s$) dan 1 sink (dinotasikan $t$)
- Jalur dari source ke sink terdiri dari beberapa tahapan $V_1$ to $V_k$
- Setiap tahapan menghubungkan node pada $V_i$ ke node $V_{i+1}$ dimana $1 \le i \le k$
- Terdapat $k$ tahap, dimana $k \ge 2$
- Setiap jalur dari $s$ ke $t$ merupakan konsekuensi dari pilihan $k-2$

2. Apakah ada perlakuan khusus terhadap graph tersebut? Berikan contoh graph dan perhitungan shortest pathnya dengan DP: Multi Stage Graph ini.