**Group:** 6

**Members:**
- 2501991864 – NOEL NATHANAEL TUAN JUNIOR
- 2501994771 – Juan Christian
- 2501989462 – Owen Farida

## Problem

From a list of participants’ ids, find which id is missing from the list. The participant ids sorted in ascending order with a certain difference. 

**Input:**

```
120001 
120014
120027
120040
120053
120066
120092
120105
120118
120131 
```

**Output:**

```
120079
```

**Design** your algorithm in a pseudocode with the complexity of **$O (lg\ n)$**! (PS: use **divide and conquer algorithm**)

Do **analysis** for your algorithm resulting in an **asymptotic notation**!

Give a new example using your own data based on your algorithm (use 5 input data)!

## Pseudocode

```
%% INPUT: arr
%% OUTPUT: missing_num

BEGIN
%% Get difference using min(b - a, c - b)
%% Because there's a possibility that the missing number 
%% is either in the second position or the third
%% so we pick the smallest diff
diff = min(arr[1] - arr[0], arr[2] - arr[1])

low = 0, high = arr.size()

# Modified binary search
WHILE (high - low) > 1 DO
	mid = (low + high) / 2
	IF (arr[mid] - arr[low]) == (mid - low) * diff DO
		low = mid
	ELSE
		high = mid
	ENDIF
ENDWHILE

RETURN arr[low] + diff
END
```

## Analysis

This algorithm is a modified binary search. Since the time complexity of binary search is $O(lg\ n)$ we can conclude that this is also $O(lg\ n)$

Let $c_0$ and $c_1$ define the declaration of `diff`, `low`, and `high`

$$
\begin{align}
c_{0} &= O(1) \\
c_{1} &= O(1)
\end{align}
$$

On this block of code

```
WHILE (high - low) > 1 DO
	IF (arr[mid] - arr[low]) == (mid - low) * diff DO
		low = mid
	ELSE
		high = mid
	ENDIF
ENDWHILE
```

This runs on $O(lg\ n)$ since on every operation it always divides the observed region of the array (low, mid, and high). So

$$
\begin{align}
T &= c_0 + c_1 + O(lg\ n) \\
&= O(lg\ n)
\end{align}
$$

## Simulation

#### 1. Using the same dataset

```
120001 : 0
120014 : 1
120027 : 2
120040 : 3
120053 : 4
120066 : 5
120092 : 6
120105 : 7
120118 : 8
120131 : 9
```

- $diff = min(120014 - 120001, 120027 - 120014) = 13$
- $low = 0;\ mid = \frac{9+0}{2} = 4;\ high = 9$

```
WHILE (9 - 0) > 1
=> true

	arr[low] = 120001
	arr[mid] = 120053
	
	IF (120053 - 120001) == (4 - 0) * 13
 	=> 52 = 52 true
		low = mid
		low = 4
```

- $low = 4;\ mid = \frac{9+4}{2} = 6;\ high = 9$

```
WHILE (9 - 4) > 1
=> true

	arr[low] = 120053
	arr[mid] = 120092
	
	IF (120092 - 120053) == (6 - 4) * 13
 	=> 39 = 26 false
		high = mid
		high = 6
```

- $low = 4;\ mid = \frac{6+4}{2} = 5;\ high = 6$

```
WHILE (6 - 4) > 1
=> true

	arr[low] = 120053
	arr[mid] = 120066
	
	IF (120066 - 120053) == (5 - 4) * 13
 	=> 13 = 13 true
		low = mid
		low = 5
```

- $low = 5;\ mid = \frac{6+5}{2} = 5;\ high = 6$

```
WHILE (6 - 5) > 1
=> false

RETURN arr[low] + diff
RETURN 120066 + 13

120079 => Correct Expected output
```

#### 2. Using different dataset

```
5   : 0
15  : 1
20  : 2
25  : 3
30  : 4
35  : 5
40  : 6
```

- $diff = min(15 - 5, 20 - 15) = min(10, 5) = 5$
- $low = 0;\ mid = \frac{6+0}{2} = 3;\ high = 6$

```
WHILE (6 - 0) > 1
=> true

	arr[low] = 5
	arr[mid] = 25
	
	IF (25 - 5) == (3 - 0) * 5
 	=> 20 = 15 false
		high = mid
		high = 3
```

- $low = 0;\ mid = \frac{3+0}{2} = 1;\ high = 3$

```
WHILE (3 - 0) > 1
=> true

	arr[low] = 5
	arr[mid] = 15
	
	IF (15 - 5) == (1 - 0) * 5
 	=> 10 = 5 false
		high = mid
		high = 1
```

- $low = 0;\ mid = \frac{1+0}{2} = 0;\ high = 1$

```
WHILE (3 - 0) > 1
=> true

	arr[low] = 5
	arr[mid] = 5
	
	IF (5 - 5) == (0 - 0) * 5
 	=> 0 = 0 true
		low = mid
		low = 0
```

- $low = 0;\ mid = \frac{1+0}{2} = 0;\ high = 0$

```
WHILE (0 - 0) > 1
=> false


RETURN arr[low] + diff
RETURN 5 + 5

10 => Correct Expected output
```
