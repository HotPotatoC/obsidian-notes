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

#### 1. Bounded Knapsack

Mirip dengan *0/1 Knapsack Problem*, yang membedakan aturan variasi bounded knapsack adalah setiap barang (dinotasikan sebagai $V$) hanya tersedia $N$ unit atau barangnya terbatas yang bisa kita notasikan sebagai $S_i$ ($1 \le i \le N$).

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

**Feasible Solution**

Dari hasil pencarian saya yang saya temui dari beberapa resource artikel/research/lectures di internet, salah satu solusi yang optimal adalah menggunakan *bottom-up dynamic programming*.

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

#### 2. Fractional Bounded Knapsack