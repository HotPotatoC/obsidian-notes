# Week 6 - GSLC
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 11 & 12
Topics: 
- Welsh Powell Algorithm
- Dynamic Programming: Fibonacci Sequence
Date: 2022-11-02
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Graph Coloring

Graph coloring algorithm is the process of coloring a graph with different colors for each node that is "adjacent".

- There is an edge connects between two nodes
- Adjacency value is greater than 0

The objective is to find the minimum number of required colors

Minimum number of colors should be used for coloring a graph is called the **chromatic number**.

- **Edge coloring**
	- Color only the edges not the nodes. Number of edges that meet at a particular node **should not be given the same color**.
- **Region coloring**
	- Coloring piece of region, divided into small sub-region. Each sub-region which has a border **should not be given the same color**. This problem is known as graph coloring.
	- Map coloring can be solved by turning it into graph, color the graph, and then mapped back.

## Welsh & Powell Algorithm

This algorithm is also an example of greedy method

1. Sort nodes in a graph based on the number of edges connected to it (degree denoted as $deg(v)$), in descending order or large -> small.
2. Based on the above sequence, coloring all nodes in a graph with 1 color if a node is not adjacent to a node that has been colored.
3. Repeat step 1 -> 2 until all nodes have been given a color.

## Four Color Theorem

The theorem states that every map **can be colored by 4 colors or less**. This theorem provides a benchmark that like any form of maps that we have we can have up to 4 chromatic numbers. **This theory can not be proven true in mathematics**.

## Assignment: Welsh Powell Algorithm Graph Coloring Analysis

### Pseudocode

```
%% INPUT: G (Graph Adjacency List)
%% OUTPUT: A map, Node -> Color code

BEGIN
FUNCTION welshPowell(G) DO
	%% A map with key of type Node and value of Number Degree of the Node
	m = Map<Node, int>()

	FOR i = 0 TO G.size() STEP 1 DO
		%% Populate map with node and degree
		m[G[i]] = G[i].size()
	ENDFOR

	PQ = PriorityQueue()
	FOREACH node, degree IN m DO
		%% Push node with the degree as the priority
		PQ.enqueue(node, degree)
	ENDFOREACH

	nodeColors = Map<Node, int>()
	availableColors = Boolean[G.size()]
	
	FOR i = 0 TO G.size() STEP 1 DO
		%% Set that all colors are available by default
		availableColors[i] = true
	ENDFOR
	
	start = PQ.dequeue()
	nodeColors[start] = 0
	
	FOR _ TO G.size() DO
		node = PQ.dequeue()
		
		FOREACH neighbor IN node.edges() DO
			IF nodeColors[neighbor] != -1 DO
				availableColors[nodeColors[neighbor]] = false
			ENDIF
		ENDFOREACH
		
		color = 0
		FOR color = 0 TO G.size() STEP 1 DO
			IF availableColors[color] DO
				BREAK
			ENDIF
		ENDFOR
		
		nodeColors[node] = color
		
		FOR i = 0 TO G.size() STEP 1 DO
			availableColors[i] = true
		ENDFOR
	ENDFOR
	
	RETURN nodeColors
ENDFUNCTION
END
```

### Time Complexity Analysis

Berikut merupakan implementasi yang saya coba perbuat

1. Pertama, buat sebuah map untuk menyimpan node serta dengan degree nodenya (Key: $v$, Value: $deg(v)$)
2. Lalu, Masukkan setiap node dalam graf serta dengan $deg(v)$nya $\rightarrow O(V)$
3. Buat sebuah priority queue lalu masukkan setiap node dan jadikan $deg(v)$ sebagai prioritynya $\rightarrow O(V \cdot logV)$
4. Buat sebuah map baru untuk menyimpan result akhir dan array berisi boolean `availableColors` untuk menyimpan warna-warna yang tersedia dan set default value `availableColors` menjadi `true` $\rightarrow O(V)$
5. Ambil node awal dengan lakukan pop pada priority queue $\rightarrow O(log V)$
6. kunjungi setiap node yang bertetangga dengan node $v$ sekarang dan tandakan tetangga-tetangganya sebagai not available $\rightarrow O(logV) + O(E)$
7. Cari warna yang tersedia sekarang $\rightarrow O(V)$
8. Tetapkan node sekarang dengan warna yang tersedia
9. Reset list warna yang tersedia (ubah semua nilai jadi `true`) $\rightarrow O(V)$
10. Lakukan step 5 - 9 sampai tidak ada node lagi dalam priority queue $\rightarrow O(V)$

Perhitungan time complexity:

$$
\begin{align}
T &= O(V) + O(V) + O(V) +O(V \cdot logV) + O(logV) + O(V) \cdot [O(logV) + O(E) + O(V)] \\
&= O(V \cdot logV) + O(logV) + O(V) \cdot [O(logV) + O(E) + O(V)] \\
&= O(VlogV) + O(V+E) + O(V^2) \\
&= O(V^2 + E)
\end{align}
$$

Maka time complexity dari implementasi saya menghasilkan $O(V^2 + E)$

# Dynamic Programming

## Assignment: Dynamic Programming Fibonnaci Sequence

Pseudocode:

1. Tabulation
```
%% INPUT: n-th number in the fibonacci sequence  
%% OUTPUT: n fibonacci number  
  
BEGIN 
FUNCTION fibonacci(n) DO  
  IF n <= 2 DO  
    RETURN n
  ENDIF
  
  LET f[n]  
  f[0] = 0  
  f[1] = 1  
  
  FOR i = 2 TO n DO  
    f[i] = f[i - 1] + f[i - 2]  
  ENDFOR  
  
  RETURN f[n - 1]  
ENDFUNCTION  
END
```

To optimize the algorithm we can use memoization

2. Memoization
```
%% INPUT: n-th number in the fibonacci sequence  
%% OUTPUT: n fibonacci number  
  
BEGIN  
  
LET memo[] = {0, 1}  
  
FUNCTION fibonacci(n) DO  
  IF n <= 2 DO  
    RETURN n
  ENDIF  
  
  IF NOT memo[n-1].empty() DO  
    RETURN memo[n-1]
  ENDIF  
  
  LET f[n]  
  f[0] = 0  
  f[1] = 1  
  
  FOR i = 2 TO n DO  
    memo[i] = f[i - 1] + f[i - 2]  
  ENDFOR  
  
  RETURN memo[n - 1]  
ENDFUNCTION  
END
```
