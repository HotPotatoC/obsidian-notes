# Day 7
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 13 & 14
Topics: Dynamic Programming
Date: 2022-11-09
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Generalization

- **Tabulation**
A dynamic programming approach where you solve a problem by first filling up a table, and then compute the solution to the original problem based on the results in this table

![[Pasted image 20221109114650.png]]

- **Memoization**
An optimization process by storing the intermediate results of the solutions of sub-problems.

![[Pasted image 20221109114640.png]]

# DP: Coin change problem

The change-making problem addresses the question of finding the minimum number of coins that add up to a given amount of money. It is a special case of the integer knapsack problem, and has applications wider than just currency. 
[Read more](https://en.wikipedia.org/wiki/Change-making_problem)

Time Complexity: $O(n\cdot m)$
Space Complexity: $O(n)$

# DP: Knapsack Problem

