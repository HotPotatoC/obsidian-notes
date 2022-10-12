# Day 1
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 1 & 2
Topics: 
	- Introduction of design and analysis of algorithms
	- Mathematical induction and recursive function
Date: 2022-09-28
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Evaluation

Assignment (Individual & Indonesia National Contest): 40%
Mid Exam: 30%
Final Exam: 30%

# Materials
- Definition of algorithms
- Definition of pseudocode
- Introduction to analysis of algorithms

# What is an algorithm
A sequence of computational steps that transform the input into the output.

## Criteria of algorithms
- Input
- Output
- Correctness
- Simplicity
- Definiteness
- Finiteness
- Effectiveness
- Traceable

## Paradigms of programming
- Sequence
- Condition
- Repetition

## What is a program

An expression of an algorithm

## Areas study of algorithms
1. How to devise algorithms
2. How to validate algorithms
3. How ot analyze algorithms
4. How to test a program

# Standard of writing pseudocode

### Blocks
Always start with `BEGIN` and ends with `END` and always use indentation

### Assignment Operation
Do `x = 20`. Data types do not need to be explicit

Variable naming should be **reflective**.
`sum = 90`

### Input
Inputs should be explicit
`INPUT x`

### Output
`PRINT x`

### Conditional
If Else:
```
IF TODAY = "MONDAY" THEN
	...
ELSE
	...
ENDIF
```

Switch case:
```
CASE TODAY
BEGIN
	"MONDAY": ...
	"TUESDAY": ...
	.
	.
	OTHERWISE: ...
END
ENDCASE
```

### Repetition

```
FOR i = 1 TO 100 STEP 2 DO
	...
ENDFOR
```

```
WHILE condition DO
	...
ENDWHILE
```

```
REPEAT
	...
UNTIL condition
```

## Example pseudocode

Selection sort

```
// INPUT: arr (unsorted), n (array length)
// OUPUT: sorted array
BEGIN
	FOR i = 1 TO n - 1 STEP 1 DO
		min = i
		FOR j = i + 1 TO n STEP 1 DO
			IF arr[j] < arr[min] THEN
				min = j
			ENDIF
		ENDFOR
		
		SWAP(arr[min], arr[i])
	ENDFOR
	
	PRINT arr // sorted array
END
```

$$
a_1 + a_2 + ... + a_n = \sum^{n}_{k=1}a_k
$$
```
BEGIN
	sum = 0
	FOR k = 1 TO n STEP 1 DO
		sum += a[k]
	ENDFOR

	PRINT sum
END
```