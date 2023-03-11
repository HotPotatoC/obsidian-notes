
# Multistage Graph

![[Pasted image 20230128135734.png]]

## Backward Method & Forward method

kertas yh

# String Matching KMP

P = abababa
T = abacbababababaacbacaababababaababababababacac

$i = \set{0, 1, 2, 3, 4, 5, 6}$
$P_i = \set{a, b, a, b, a, b, a}$
$F_i = \set{0, 0, 1, 2, 3, 4, 5}$

abacbababababaacbacaababababaababababababacac
aba**b**aba

$3-F(2)=3-1=2$

abacbababababaacbacaababababaababababababacac
   a**b**ababa
$1-F(0)=1$

abacbababababaacbacaababababaababababababacac
      **a**bababa

abacbababababaacbacaababababaababababababacac
        **a**bababa

abacbababababaacbacaababababaababababababacac
          abababa

# SCC

```
FOR EACH v in GRAPH g TANDAI INDEX, LOWEST_ANCESTOR PUSH IN STACK FOR ALL EDGES CONNECTED TO VERTEX v IF NEXT NODE IS UNVISITED SCC to NEXT VERTEX COMPARE LOWEST_ANCESTOR END IF IF IN STACK COMPARE LOWEST_ANCESTOR END IF END FOR IF INDEX == LOWEST_ANCESTOR POP STACK UNTIL CURRENT_INDEX IS POPPED COUNT POPPED ELEMENTS AS ONE SCC END IF END FOR
```