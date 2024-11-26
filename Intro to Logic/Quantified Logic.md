- Use lowercase letters for constants
- `Px` the predicate `P` applies to `x`
	- Cannot exist by itself

### Well Formed Formulas
- An atomic formula is a well formed sentence
- if $\phi$ and $x$ is a wff, then $\forall_x$ $\phi_x$ and $\exists_x$ $\phi_x$
- 

# Symbols 
- $\forall$ x : for all x
- $\exists$x : there is at least one x
	- We can also negate this quantifier, meaning there does not exist an `x`
- `a = b`: identity claim. Read as `a` is `b`

# Application examples

### "At least"
$\exists$x, $\exists$y (Fx & Fy & x $\neq$ y)

### "At most"
One: $\forall$ x , $\forall$ y [(Fx & Fy) -> (x=y)]
"If Fx and Fy are true, then x is equal to y (they are the same object)"
- Can chain equality statements with disjunction. `x = y v y = z v x = z ...`

### Exactly how many
Only one: $\exists$x (Fx & $\neg$ Ey(Fy & x $\neq$ y))
Two: $\exists$x, $\exists$y, (Fx & Fy & x $\neq$ y) & $\neg$ Ez (Fz & z $\neq$ x & z $\neq$ y)





P : ___ is a professor
D : ___ is a Duck
s : Seth 
Ps : Seth is a Professor
$\forall$x (Px -> Dx) 
---------
a: Amos
b: Bouncer
c: Cleo 
-
Zx: ___ lives at the zoo
Rx: ___ is a reptile
Ax: ___ is an alligator
Lxy: ___ loves ___
Mx: ___ is a monkey
-
(Za & Zb) & Zc ---> Amos, Bouncer and Cleo all live at the zoo
(Rb & $\neg$ Ab) --> Bouncer is a reptile but not an alligator
Lcb -> Mb --> If Cleo loves Bouncer then Bouncer is a monkey
$\exists$m(Rm & Zm) --> There is a reptile that lives at the zoo
$\forall$x(Ax -> Rx)