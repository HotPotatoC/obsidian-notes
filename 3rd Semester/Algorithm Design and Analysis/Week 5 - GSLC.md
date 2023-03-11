# Week 5 - GSLC
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 9 & 10
Topics: 
- Greedy Methods
- Huffman Code
Date: 2022-10-27
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Greedy Methods

Greedy means rapacious. Algorithms often perform some calculation phase before finding a final solution. Sometimes these stages produced a number of elements that will be used to formulate the final solution.

Greedy methods will *"ignore"* a complete calculation in the search for solutions, replacing it with using those elements to calculate the solution more quickly. It can be very useful if the search for solutions 100% take too long rather than waste time trying to calculate the *"best"* solution, it is better saved by finding a **"good enough"** solution.

## Knapsack Problem

The [Knapsack Problem](https://en.wikipedia.org/wiki/Knapsack_problem) is a really interesting problem in combinatorics

> *“given a set of items, each with a weight and a value, determine the number of each item to include in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible.”*

### Variations

- **Fractional Knapsack Problem:** Items should be brought in part (in fractional units).
- **0/1 Knapsack Problem:** Each item is only available in 1 unit, take it or leave it.
- **Bounded Knapsack Problem:** Each item is available in N units (limited number).
- **Unbounded Knapsack Problem:** Each item is available in more than one unit, the number is unlimited

### Assignment: Time Complexity Analysis Bounded Knapsack & Bounded Fractional Knapsack

#### 1. Bounded Fractional Knapsack

Pada *fractional bounded knapsack*, kita diperbolehkan untuk memecahkan item untuk memaksimalkan nilai total knapsack.

- Untuk setiap item, hitung rasio dari $\frac{V_i}{W_i} \rightarrow O(n)$
- Urutkan seluruh item secara menurun berdasarkan rasio $\frac{V_i}{W_i}$ bisa dengan menggunakan *mergesort* atau *quicksort* $O(n logn)$
- Terakhir, masukkan item ke dalam knapsack mulai dari rasio tertinggi $O(n)$

Maka kompleksitas dari fractional bounded knapsack adalah $O(n logn)$.

#### 2. Unbounded Fractional Knapsack

Prosesnya sama dengan bounded fractional knapsack tetapi pada variasi unbounded kita dapat mengambil item yang sama sebanyak mungkin. Pada variasi ini, algoritma hanya perlu menghitung rasio dari seluruh data sambil menampung nilai rasio tertinggi ($M$) dan akhirnya kalikan $M$ dengan target/kapasitas maksimal untuk mendapatkan nilai tertinggi $MaxProfit = W\cdot M$

Maka kompleksitas dari unbounded fractional knapsack adalah $O(n)$ karena tidak perlu melakukan *sorting*.

#### 3. Bounded Knapsack

Mirip dengan *0/1 Knapsack Problem*, yang membedakan aturan variasi bounded knapsack adalah setiap barang (dinotasikan sebagai $V$) hanya tersedia $N$ unit atau barangnya terbatas yang bisa kita notasikan sebagai $S_i$ ($1 \le i \le N$).

##### Suboptimal Solution

Salah satu solusinya adalah menggunakan *recursion*

- Pilih item saat ini dan ulangi untuk item yang tersisa dengan kapasitas knapsack yang dikurangi hingga kapasitas menjadi negatif.
- Tinggalkan item saat ini dari knapsack dan ulangi untuk item yang tersisa.
- Akhirnya kembalikan nilai maksimum yang didapatkan dengan memilih atau meninggalkan item saat ini.

```
%% INPUT: v (values), w (weights), t (target)
%% OUTPUT: maximum profit

BEGIN
FUNCTION knapsack(v, w, n, t) DO
	// Base: Jika tidak bisa mengambil item lagi
	IF target < 0 DO
		RETURN
	ENDIF

	// Base: Jika tidak ada item lagi
	IF n < 0 || target = 0 DO
		RETURN 0
	ENDIF

	include = v[n] + knapsack(v, w, n - 1, t - w[n])
	exclude = knapsack(v, w, n - 1, t)

	RETURN max(include, exclude)
ENDFUNCTION
END
```

Tetapi solusi ini akan menghasilkan kompleksitas $O(2^n)$ karena setiap operasi akan membuat $2$ subproblem sampai target tercapai atau kapasitas sudah habis. Juga, ada kemungkinan dimana sebuah item memiliki jumlah yang sangat banyak.

##### Feasible Solution

Dari hasil pencarian saya yang saya temui dari beberapa artikel/research/lectures di internet, salah satu solusi yang optimal adalah menggunakan dynamic programming.

```
%% INPUT: v (values), w (weights), t (target)
%% OUTPUT: maximum profit

BEGIN
FUNCTION knapsack(v, w, n, t) DO
	LET dp[t + 1]

	FOR i = 1 TO n + 1 DO
		FOR j = t TO 0 STEP j - 1 DO
			IF w[i - 1] <= j DO
				dp[j] = max(dp[j], dp[j - w[i - 1]] + w[i - 1])
			ENDIF
		ENDFOR
	ENDFOR

	RETURN dp[t]
ENDFUNCTION
END
```

Dengan metode ini, akan menghasilkan kompleksitas $O(NW)$, dimana $N$ jumlah item dan $W$ target / kapasitas maksimal.

***

## Minimum Spanning Tree

### Prim's Algorithm
### Kruskal Algorithm

## Shortest Path

### Dijkstra Algorithm
### A* Algorithm

***

### Assignment: Time Complexity Analysis MST with Prim-Dijkstra

#### 1. Prim's Algorithm

Merupakan greedy algorithm untuk mencari MST. Implementasi prim's algorithm tergantung kepada struktur data yang digunakan pada graph yaitu:

- Adjacency Matrix
- Binary Heap dengan Adjacency List

##### Adjacency Matrix

1. Inisialisasi array dengak ukuran $V$. $O(V)$
2. Pilih vertex awal $O(1)$
3. Kunjungi setiap vertex $O(V)$
4. Setiap edge yang terhubung dengan vertex sekarang ditandai sebagai aktif $O(1)$
5. Cari setiap edge yang aktif, untuk mencari nilai terkecil $O(E)$
6. Tambahkan vertex sekarang dengan nilai edge terkecil ke dalam array
7. Lakukan step 3 - 6 sampai jumlah vertex di array lebih kecil dari total vertex yang ada di graph $O(V^2)$

Dengan ini, kompleksitas waktu Prim's Algorithm dengan stuktur data adjacency matriks adalah $O(V^2)$

##### Binary Heap dengan Adjacency List

1. Sama dengan adjacency matrix step 1 - 2 $O(V)$
2. Masukkan setiap edge yang terhubung dengan vertex awal ke dalam Priority Queue $O(E)$
3. Lakukan BFS (Breadth First Search) pada vertex awal tersebut untuk melintasi semua vertex dari graph dan PQ untuk menyimpan vertex yang belum dimasukkan dalam MST dan seluruh vertex dapat dicari dengan kompleksitas $O(V + E)$
4. Ambil cost terkecil yang berada di PQ sekarang dan masukkan ke dalam array mst dan operasi decrease key $O(logV)$

Maka, komplesitas waktu Prim's Algorithm dengan struktur data Binary Heap dengan Adjacency List adalah

$$
O(V + E) \cdot O(logV) = O((V + E)logV)
= O(E \cdot logV)
$$

#### 2. Dijkstra's Algorithm

Dijkstra's Algorithm adalah algoritma graph untuk mencari jalur terpendek dari sebuah node sumber ke semua node lainnya dalam sebuah graph.

1. Pilih vertex awal dinotasikan sebagai $S=\emptyset$. $O(1)$
2. Cek semua vertices yang terhubung dengan vertex awal dan pilih edge dengan jarak terpendek $O(V)$
3. Setelah pilih vertex, lakukan *relaxation* untuk semua tetangga dari vertex sekarang. Dimaksud dengan *relaxation* adalah perbarui setiap jalur tetangga dengan nilai yang lebih kecil antara jalur saat ini atau ke yang baru ditemukan $O(V)$

Maka, kompleksitas waktu Dijkstra's Algorithm menggunakan Adjacency Matrix adalah $O(V^2)$ karena

1. Kunjungi seluruh vertices: $O(V)$
2. Perbarui seluruh vertex: $O(V)$
3. $O(V) \cdot O(V) = O(V^2)$

Algoritma ini dapat dibuat menjadi lebih efisien jika struktur data penyimpanan data graph menggunakan binary min-heap dan adjacency list. Akhirnya, kompleksitas waktu dapat menurun menjadi $O(V+E \cdot logV)$

***

# Huffman Code

Huffman Coding is a technique of **compressing data** to reduce its size without losing any of the details. It was first developed by [David Huffman](https://en.wikipedia.org/wiki/David_Huffman). It is generally useful to compress the data in which there are frequently occurring characters.

## How it works


### Assignment: Time Complexity Generating Huffman Tree

Proses pembuatan Huffman Tree mirip dengan pembuatan binary tree. Membuatnya kita dapat menggunakan sebuah priority queue.

1. Buat sebuah priority queue lalu masukkan semua symbol sebagai *leaf node* $O(n)$
2. Extract 2 node dengan frekuensi terkecil, lalu buat parent node ($z$) dengan value $z = x_{f} + y_{f}$ dimana $x_f$ adalah frekuensi left child dan $y_f$ frekuensi dari right child $O(logn)$
3. insert $z$ ke dalam priority queue $O(logn)$
4. Lakukan step 2-3 sampai node dalam priority queue habis $O(n)$

Lalu dapat kita analisa

- Proses insertion menggunakan priority queue membutuhkan $O(log n)$
- Juga setiap insertion, kedua node yang akan di-*extract* akan membuat 1 node parent, dan juga untuk sebuah tree dengan $n$ leaf akan menghasilkan $2n-1$ node pada tree $O(n)$

Maka pembuatan Huffman Tree memiliki time complexity  $O(n) \cdot O(log n) = O(n \cdot logn)$

Pseudocode:
```
%% INPUT: SF (Symbols & Freq struct array)
%% OUTPUT: Huffman Tree

BEGIN
FUNCTION createHuffmanTree(SF) DO
	Q = { SF }
	
	WHILE !Q.isEmpty() DO
		x, y = Q.extractMin(), Q.extractMin()
		
		z = newNode()
		z.frequency = x.frequency + y.frequency
		
		z.left = x
		z.right = y
		
		Q.push(z)
	ENDWHILE

	RETURN Q.extractMin()
ENDFUNCTION
END
```

### Assignment: Time Complexity Compound Function

```
%% INPUT: X
%% OUTPUT: Y
BEGIN
	Y = 0
	FOR J = 1 TO X STEPS J * 2 DO
		Y = Y + A(J)
	ENDFOR
	RETURN Y
END
```

Ada dua operasi yang bersifat konstan yaitu saat inisialisasi nilai `Y` dan return nilai `Y`

$$
T=2O(1)
$$

Diketahui function `A(J)` memiliki kompleksitas $O(n)$ karena akan berjalan sebanyak `J` kali.

$$
T = 2O(1)+O(n)
$$

Lalu, terdapat sebuah looping mulai dari $J = 1$ sampai $X$ dimana $J$ akan bertambah sebanyak $J = J \cdot 2$.

**Simulasi**
```c
X = 32

START
J = 1 => A(1) 1x
J = 2 => A(2) 2x
J = 4 => A(4) 4x
J = 8 => A(8) 8x
J = 16 => A(16) 16x
J = 32 => A(32) 32x
STOP
```

Dapat dilihat dari simulasi, bahwa for loop akan berjalan sebanyak $log(32) = 5$ kali maka $O(log n)$.

Maka kompleksitas fungsi `C` adalah,

$$
T=2O(1) + O(n) \cdot O(logn)
$$
$$
T=O(n) \cdot O(logn)
$$
$$
T=O(n \cdot logn)
$$