# Day 2
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 3 & 4
Topics: 
	- Algorithms and complexity functions
	- Complexity of algorithms analysis
Date: 2022-10-5
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

![[Pasted image 20221005113218.png]]

- $O(1)$
- $O(n)$

```
FOR i = 1 TO n STEP 1 DO
	PRINT i
ENDFOR

PRINT "SELESAI"
```

- Still $O(n)$

```
FOR i = 1 TO n STEP 2 DO
	PRINT i
ENDFOR

PRINT "SELESAI"
```

Execution takes $O(n/2)$ but in notation rules we take the highest degree that is $O(n)$

- $O(lg(n))$
$lg(n) = log_{2}(n)$

```
FOR i = 1 TO n STEP i*2 DO
	PRINT i
ENDFOR

PRINT "SELESAI"
```

Take $n = k$ Execution pattern $2^k$ then $lg(n) + 1$ therefore $O(lg(n))$

- $O(n^2)$

```
FOR i = 1 TO n DO
	FOR j = 1 TO n DO
		PRINT j
	ENDFOR
ENDFOR
```

- $O(n * m)$

```
FOR i = 1 TO n DO
	FOR j = 1 TO m DO
		PRINT j
	ENDFOR
ENDFOR
```

- Also $O(n^2)$

```
FOR i = 1 TO n DO
	FOR j = 1 TO i DO
		PRINT j
	ENDFOR
ENDFOR
```

Execution goes like $1 + 2 + 3 + 4 + ... + n$. This expression can be simplified as $\frac{n(n+1)}{2}$
Therefore

$$
1 + 2 + 3 + 4 + ... + n = \frac{n(n+1)}{2}
						  = \frac{n^2 + 1}{2}
$$

Take the highest degree and we get $O(n^2)$

## Degree Order

$$
1 < lg(n) < \sqrt{n} < n < nlg(n) < n^2 < n^3 < ... < n^n
$$

- Worst Case: $n^2 < n^3 < ... < n^n$ IS the upper-bound or $O(...)$
- Average Case: Lower bound otherwise $\ohm(...)$
- Best Case: $\theta(...)$
$$
f(n) = n^2 + n <= 2n^2 + n
$$

**Proof Checking**

Proof that $O(n^2)$ for $f(n) = n^2 + n$ if $g(n) = n$

$$
f(n) = n^2 + n <= c g(n)
$$
$$
		n^2 + n <= 2n^3
$$

## Example

Calculating selection sort