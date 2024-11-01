- Collection of objects, also referred as elements
- Defined by what elements belong to them
- Elements of a subset can be subset themselves. This does not change the cardinality. No matter how big the subset element is, it still counts as only 1 element.
- A null set $\empty$﻿ is considered False
- a Universal set `U` is considered True

## ==Set Notation==

- Roster notation of a set: ==_A ={2,4,6,8,10}._== Order is not important
- `∈`is used to denote an element belongs in a set. `2 ∈ A`
- `∉` is used for the contrary. `5 ∉ A`
- The amount of unique elements inside a set is called its cardinality. Denoted by `|A|`
- `U` denotes a universal set that contains all elements in a context. Essentially equals `True`. This could also be referred to as an infinite set.
- `∅` denotes an empty set. Essentially equals `False`
- `B x A` denotes the set of all possible ordered pairs `(a,b)` where `b ∊ B and a ∊ A`

  

## ==Subsets==

`⊆` denotes a subset. `A⊆B` states that A is a subset of B. `⊄` denotes the opposite.

A is considered a proper subset of B is all the elements in A are in B, but not all elements in B are in A. This is determined by `A ⊂ B`

`∅` is technically a proper subset of any Set.

  

## ==Power sets==

A power set of A, denoted as `P(A)` is the set of all possible subset of `A`

To find how many possible subsets of `A`, do `2^(|A|)`.

  

### ==Intersections==

- The intersection of A and B is denoted as $A \cap B$﻿
- $\empty \cap B$﻿ is true for all sets B

  

### ==Differences==

- The difference between A and B is denoted as $A - B$﻿, and is the set of elements that are in A but not in B
- Two sets are disjointed if $A \cap B = \empty$﻿

  

### ==Symmetric Differences==

- The union of the differences between A and B is denoted as $A \oplus B = (A - B) \cup (B-A)$﻿. It is the set of the elements that are in only ONE of the sets.

  

  

### ==Ordered pairs==

- using `()` instead of `{}` in sets means that the order of the elements is important, so

$(1,2) \neq (2,1)$﻿ .

  

### ==Ordered lists==

- Ordered triple: ordered list of three items `(x,y,z)`
- for $n \geqslant 4$﻿, an ordered list of n items is called an `ordered n-tuple`
- Strings are an example of an ordered string

  

### ==Binary strings==

- strings whose alphabet is `{0,1}`
- A string of length n is called an n-bit string
- empty string denoted by $\lambda$﻿

  

### ==Partitions==

- A subset of a non-empty set A so that each element of A is exactly in one partition.