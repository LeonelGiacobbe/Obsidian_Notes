
Each element to the right of `|` is true.

```
1 | B & P
2 | B     --> & E 1, E for elimination
3 | B     --> R 2, R for reiteration
----------
1 | B
2 | P
3 | B & P --> & I 1, 2  I for introduction
---------
1 | B
2 | B v W --> v I 1, I for introduction, W is any sentence at all 
------
1 | B v P
2 | not B 
3 | P       --> v E 1, E for elimination
-------
1 | B & not S
2 | S v Q
3 | not S  --> & E 1
4 | B      --> & E 1
5 | Q      --> v E 2, 3
---------
1 | P -> B
2 | P
3 | B     --> `->` E 1,2
---------
1 || B
2 || B   --> R 1 
	3 | B -> B   -> I 1-2
```

`||` - > True on the assumption that...
- Reiteration: re-stating [[Sentences]] that are proven to be true
	- Defined as `R1`, where `1` is the line where the statement was defined.
- Introduction: each connector can be introduced in a statement 
	- Ex: if `A` is true and `B` is true, then `A & B` is true.
- Elimination: each connection can be eliminated
	- Ex: if `A & B` is true, then `A` is true and `B` is true.

### Universality of disjunction
given a sentence `A` is true, then `A v W` will be true, `W` being whatever sentence.

### Rules of Replacement
- Commutativity (comm):
	- `(A & B) == (B & A)`
	- `(A v B) == (B v A)`
	- `(A <-> B) == (B <-> A)`
- DeMorgan's (DeM):
	- `not(A v B) == not A & not B`
	- `not(A & B) ==  not A v not B`
- Double Negation (DN):
	- `not not A == A`
- Material Conditional (MC):
	- `A -> B == not A v B`
	- `A v B == not A -> B` 
- Biconditional Exchange (`<->ex`):
- `A <-> B == (A -> B) & (B -> A)`