# Day 9
Class: [[COMP6049001 - Algorithm Design and Analysis]]
Session: 
Topics: 
- The Knuth-Morris-Pratt Algorithm 
- Naïve String Matching Algorithm
Date: 2022-12-14
Lecturer: [[D3442 - HERRU DARMADI, S.Kom., M.TI]]

# Naïve String Matching Algorithm

The naïve approach is similiar to a brute force approach. The algorithm accepts a text of length $n$ and a pattern of length $m$ characters from the position of the text. If there is a mismatch, the pattern is shifted by one position. On the other hand, if there is a match, then the next character is checked.

## Simulation

**Text:** Learning
**Pattern:** ar

- **Loop 1**
```
Learning
ar
```

No match

- **Loop 2**
```
Learning
 ar
```

No match

- **Loop 3**
```
Learning
  ar
```

Found Match

- **Loop 4**
```
Learning
   ar
```

No Match

- **Loop 5**
```
Learning
    ar
```

No Match

- **Loop 6**
```
Learning
     ar
```

No Match

- **Loop 7**
```
Learning
      ar
```

No Match

- **Conclusion**

Pattern *ar* exists in *Le**ar**ning*

- **Time Complexity:** $O(nm)$

# KMP Algorithm

Used to find a *Pattern* in a *Text*. This algorithm compares character by character from left to right. But whenever a mismatch occurs, it uses a preprocessed table called *Prefix Table* to skip characters comparison while matching.

## Simulation


- **Time Complexity:** $O(n + m)$