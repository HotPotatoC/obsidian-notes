# Day 4
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 7 & 8
Topics: Divide and Conquer
Date: 2022-10-19
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Divide and Conquer

Breaks down a problem into smaller sub-problems until it becomes simple enough to be solved directly.

## Merge Sort

A divide and conquer sorting algorithm with the time complexity of $O(nlog(n))$.  
- Given a sequence of $n$ elements $(a[1], ..., a[n])$.
- General idea, split the elements into two sets $a[1], ..., a[n/2]$ and $a[n/2+1], ..., a[n]$.
- Each set is individually sorted, and then the resulting sorted sequences are merged to produce a single sorted sequence of $n$ elements.

**Merge Sort Algorithm**

```
FUNCTION MergeSort(array, low, high) DO
	IF low < high
		RETURN
	ENDIF
	
	mid = (low + high) / 2

	MergeSort(array, low, mid)
	MergeSort(array, mid + 1, high)
	merge(Array, low, mid, high)
ENDFUNCTION
```

**Merge Sort Illustration**

![[Pasted image 20221019121857.png]]

## Quicksort

Another divde and conquer algorithm with the time complexity of $O(n log(n))$
- **Divide**: Rearrange the elements and split the array into two subarrays and an element in between such that so that each element in the left subarray is less than or equal the middle element and each element in the right subarray is greater than the middle element (pivot).
- **Conquer**: Recursively sort the two subarrays
- **Combine**: None
	
**Quicksort Illustration**

![[Pasted image 20221019131412.png]]