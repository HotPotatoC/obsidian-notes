
Nama: Juan Christian
NIM: 2501994771

## Apakah semua directed graph bisa menggunakan teknik DP: Multistage Graph?

**Tidak** setiap directed graph bisa menggunakan teknik DP: Multistage Graph, dikarenakan untuk menggunakan teknik DP: Multistage Graph memiliki beberapa syarat tertentu yaitu:

1. Setiap edge harus memiliki weight
2. Hanya memiliki 1 source (dinotasikan $s$) dan 1 sink (dinotasikan $t$)
3. Jalur dari source ke sink terdiri dari beberapa tahapan $V_1$ to $V_k$
4. Setiap tahapan menghubungkan node pada $V_i$ ke node $V_{i+1}$ dimana $1 \le i \le k$

## Contoh perhitungan shortest path menggunakan DP: Multistage Graph

![[Pasted image 20221216164150.png]]

Mencari shortest path pada graph terlampir di atas $A \rightarrow G$ menggunakan metode DP: Multistage Graph ada dua metode yaitu

1. Backward Method (dari source ke sink)
2. Forward Method (dari sink ke source)

### Backward Method

$bcost(2, B) = c(A, B) = 5$
$bcost(2, C) = c(A, C) = 2$
$bcost(2, D) = c(A, D) = 1$

$$
\begin{align}
bcost(3, E) &= min \{ c(B, E) + bcost(2, B) | c(C, E) + bcost(2, C) | c(D, E) + bcost(2, D) \} \\
&= min \{\ 9 + 5\ |\ 6 + 2\ |\ 4 + 1\ \} \\
&= min \{\ 14\ |\ 8\ |\ 5\ \} \\
&= 5
\end{align}
$$

$$
\begin{align}
bcost(3, F) &= min \{ c(B, F) + bcost(2, B) | c(C, F) + bcost(2, C) | c(D, F) + bcost(2, D) \} \\
&= min \{\ 1 + 5\ |\ 2 + 2\ |\ 12 + 1\ \} \\
&= min \{\ 6\ |\ 4\ |\ 13\ \} \\
&= 4
\end{align}
$$

$$
\begin{align}
bcost(4, G) &= min \{\ c(E, G) + bcost(3, E)\ |\ c(F, G) + bcost(3, F)\ \} \\
&= min \{\ 5 + 5\ |\ 1 + 4 \ \} \\
&= min \{\ 10 \ |\ 5\ \} \\
&= 5
\end{align}
$$

Maka shortest pathnya adalah $A \rightarrow C \rightarrow F \rightarrow G$ dengan jarak $5$

### Forward Method

$cost(3, E) = c(E, G) = 5$
$cost(3, F) = c(F, G) = 1$

$$
\begin{align}
cost(2, B) &= min\{\ c(B, E) + cost(3, E)\ |\ c(B, F) + cost(3, F) \ \} \\
&= min\{\ 9 + 5 \ |\ 1 + 1 \ \} \\
&= min\{\ 14 \ |\ 2 \ \} \\
&= 2
\end{align}
$$

$$
\begin{align}
cost(2, C) &= min\{\ c(C, E) + cost(3, E)\ |\ c(C, F) + cost(3, F) \ \} \\
&= min\{\ 6 + 5 \ |\ 2 + 1 \ \} \\
&= min\{\ 11 \ |\ 3 \ \} \\
&= 3
\end{align}
$$

$$
\begin{align}
cost(2, D) &= min\{\ c(D, E) + cost(3, E)\ |\ c(D, F) + cost(3, F) \ \} \\
&= min\{\ 4 + 5 \ |\ 12 + 1 \ \} \\
&= min\{\ 9 \ |\ 13 \ \} \\
&= 9
\end{align}
$$

$$
\begin{align}
cost(1, A) &= min\{\ c(A, B) + cost(2, B)\ |\ c(A, C) + cost(A, C)\ |\ c(A, D) + cost(A, D) \ \} \\
&= min\{\ 5 + 2 \ |\ 2 + 3 \ |\ 1 + 9 \ \} \\
&= min\{\ 7 \ |\ 5 \ |\ 10 \ \} \\
&= 5
\end{align}
$$

Maka shortest pathnya juga $A \rightarrow C \rightarrow F \rightarrow G$ dengan jarak $5$