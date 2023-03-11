# ADT

Abstract data type is  an abstract concept created by humans to simplify the calculation of a process through abstraction

Example ADT:
- Stack
- Queue
- Tree
- Graph

## Stack
---
- Stack uses LIFO (Last-In First-Out)
- Can be implemented with array or linked list
- Operations
	- `PUSH(x)` adding x into the top of the stack $O(1)$
	- `POP()` take the top element of the stack $O(1)$
	- `EMPTY()` emptying the stack $O(n)$

## Queue
---
- Queue uses FIFO (First-In First-Out)
- Can be implemented with array or linked list
- Operations
	- `ENQUEUE(x)` queues x $O(1)$
	- `DEQUEUE` take the top element in the queue $O(1)$
	- `EMPTY` emptying the queue $O(n)$

## Tree
---
- A hierarchical tree structure with a set of linked nodes
- Parent and child
- A child node must have a parent
- A parent node can have multiple child nodes

### Binary Tree
---
- A tree data structure in which each node has at most two child nodes (left & right)
- Maximum number of nodes in level $k = 2k - 1$
- Maximum number of nodes in a Binary Tree depth $k = 2k - 1$
- Can be implemented in array or linked list
- Operations
	- Inserting data $O(log\ n)$
	- Searching data $O(log\ n)$
	- Deleting data $O(log\ n)$
	- Sorting data
		Averages on: $O(n\ log\ n)$
		Worst case:
		$T(Insertion) + T(Traversal) = O(n^2) + O(n) = O(n^2)$

### Tree Traversal
---
- Process of visiting each node in a tree data structure exactly once
- Such traversals are classified by the order in which the nodes are visited
	- Pre-order Traversal: $parent \rightarrow left \rightarrow right$
	- In-order Traversal: $left \rightarrow parent \rightarrow right$
	- Pre-order Traversal: $left \rightarrow right \rightarrow parent$
	- Level-order Traversal: $parent \rightarrow left \rightarrow right$ (each level)

![[Pasted image 20221120165605.png|400]]

## Graph
---
- Consists of a set of nodes (vertices) and edges
- An edge connects 1 or 2 nodes.
- Edge, which only connects to its own node is called a loop edge.
- Graph types:
	- Directed Graph
	- Undirected Graph

### Adjacency Matrix
- Represents a graph as a matrix of booleans (0's and 1's).
- Vertices are represented as the rows and columns of the matrix ($V \times V$ size matrix)
- The boolean value of a matrix indicates if there is a direct path between two vertices

![[Pasted image 20221120165958.png|400]]

![[Pasted image 20221120170508.png|400]]

#### Pros of Adjacency Matrix
- The basic operations like adding an edge, removing an edge, and checking whether there is an edge $V_i$ to $V_j$ takes constant time
- If the graph is dense and the number of edges is large, an adjacency matrix should be the first choice.

#### Cons of Adjacency Matrix
- The $V\times V$ space requirement of the adjacency matrix makes it a memory hog.
- While basic operations are easy, operations like `inEdges` and `outEdges` are expensive when using the adjacency matrix representation.

### Adjacency List

- Represents a graph as an array of linked lists.
- The index of an array represents a vertex.
- Each element in the linked list represents the other vertices that form an edge with the vertex.

![[Pasted image 20221120165958.png|400]]
![[Pasted image 20221120170048.png|600]]

#### Pros of Adjacency List
- It is efficient in terms of storage.
- Helps find all the vertices adjacent to a vertex easily.

#### Cons of Adjacency List
- It is slow compared to adjacency matrix because all the connected nodes must be first explored to find them.


# Math

## Notations

- Best Case $\rightarrow \ohm(\dots)$
- Average Case $\rightarrow \theta(\dots)$
- Worst Case $\rightarrow O(\dots)$

- $O(1)$: Constant Time
- $O(n)$: Linear
- $O(n^2)$: Quadratic
- $O(n^3)$: Cubic
- $O(n^m)$: Exponential
- $O(n\cdot log\ n)$: Linearithmic
- $O(log\ n)$: Logarithmic

- Summation
$$
a_1 + a_2 + \dots + a_n = \sum^{n}_{k=1} a_k
$$

- Linearity

$$
\sum^{n}_{k=1} \theta [f(k)] = \theta \sum^{n}_{k=1} [f(k)]
$$

- Arithmetic Series

$$
\sum^{n}_{k=1} k = 1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}=O(n^2)
$$

- Harmonic Series

$$
H_n = 1 + \frac{1}{2} + \frac{1}{3} + \dots + \frac{1}{n} = \sum^{n}_{k=1} \frac{1}{k} = O(ln\ n)
$$

## Induction Steps

A method to prove an equation is true for all unsigned integers

1. Prove $P(1)$ is true
2. Prove if $P(n)$ is true and $P(n + 1)$ is also true
3. Conclusion $\forall{n}\ P(n)$ is true

# Greedy Algorithms

A greedy algorithm is an approach for solving a problem by **selecting the best option available at the moment**. It doesn't worry whether the current best result will bring the overall optimal result.

![[Pasted image 20221120173709.png|500]]

## Fractional Knapsack

### Problem

Given a list of weight and prices of certain items and a bag/knapsack of a certain capacity $W$. Fill this bag in such a manner that the total price of all the items that you take in this bag is maximum for all the configurations. And you can either collect any object as a whole or a fraction of it.

### Process

- Sort the items in decreasing order of value/weight ratio $V_i:W_i$.
- Start selecting items by running a loop $i=0 \dots n$
	- If $W_i \leq W$ add it to the knapsack
	- Otherwise add the fractional part of it to the total profit $P = P + V_i (\frac{T}{W_i})$

### Simulation

Let $V$ be a list of profits and Let $W$ be a list of weights and Let $T$ be the maximum capacity of the knapsack

$$
\begin{align}
i &= 1, 2, 3 \\
V &= \{20, 18, 14\} \\
W &= \{4, 3, 2\} \\
T &= 7
\end{align}
$$

Let $R$ be the sorted ratio of $V_i : W_i$ in decreasing order

$$
\begin{align}
R &= \{20/4, 18/3, 14/2\} \\
&= \{5, 6, 7\} \\ \\

R &= \{7, 6, 5\}\\
V &= \{14, 18, 20\} \\
W &= \{2, 3, 4\}
\end{align}
$$

- $i = 1$

$V_1 = 14$
$W_1 = 2$

$W_1 \leq T$
	$T = 7 - 2 = 5$
	$P = 14$

- $i = 2$

$V_2 = 18$
$W_2 = 3$

$W_2 \leq T$
	$T = 5 - 3 = 2$
	$P = 14 + 18 = 32$

- $i = 3$

$V_3 = 20$
$W_3 = 4$

$W_3 \geq T$
	$P = 32 + 20 \times \frac{2}{4} = 42$

Therefore the maximum profit is $P = 42$

## Minimum Spanning Tree (MST)

- A **Spanning Tree** is a sub-graph of an undirected connected graph, which includes all the vertices of the graph with a minimum possible number of edges.
- A **Minimum Spanning Tree** is a spanning tree in which the sum of weight of the edges is as minimum as possible.

### Prim's Algorithm

# Divide & Conquer

## Quicksort
## Mergesort
## Binary Search

# Dynamic Programming

## Huffman Coding



## Knapsack

### 0/1 Knapsack



### Bounded Knapsack


### Unbounded Knapsack


## Coin Change


![[Pasted image 20221121015356.png]]

```
low = 0, high = 9
WHILE low <= high DO
	mid = (low + high) / 2
	IF array[mid] - array[mid - 1] == 12 DO
		low = mid + 1
	
ENDWHILE
```