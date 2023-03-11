# Day 10
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 21 & 22
Topics:
- Backtracking
- Branch and Bound
Date: 2022-12-21
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Branch and Bound

Used to solve problems using Search Tree
- Travelling Salesman Problem
- N-Queen Problem
- 0/1 Knapsack Problem
- Shortest Path

## Techniques

- FIFO Branch and Bound
- LIFO Branch and Bound
- Least Cost Branch and Bound
	- Calculates cost for each node. Node that has the smallest cost supposed as having the biggest probability to be the solution

## Travelling Salesman Problem Case

Travelling Salesman Problem can be solved using the LC Branch and Bound

**Steps**

- Describe the problem with weighted graph $G = \{V, E\}$
- $C(i, j) = value$ on the edge $<i, j>$ where $C(i, j) = \infty$, If there is no edge between $i$ and $j$
- By the definition of value (cost) above, up Cost Matrix of the TSP
- Perform the reduction of the Cost Matrix, obtained **RCM** (Reduced Cost Matrix)
- Use the barrier function (bound), to build the Search Tree from the RCM
- And so on to obtain a desired set of solutions

**RCM Calculation**
- For each row and column, find the minimal cost $R_{i,j}$ from the cost matrix and subtract the edges with $R_{i,j}$.
- Calculate the sum for each $R_{i,j}$ to get $R$

**LC construction**
- Set the root node as the first node in the TSP Graph
- From the root RCM node, get the total cost from that node to each edge $b$.
- Create the children nodes from the RCM
- Calculate the RCM for each children node
- Calculate the cost for the nodes $RCM_i = b + min(RCM) + C(i, j)$
- Find the minimal RCM cost node and continue to solve the problem from that node
- Rinse and repeat to obtain the desired set of solutions.