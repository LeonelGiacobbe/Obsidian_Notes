- `Big O`: upper bound
	- `Little O`: strict upper bound
- `Big Omega`: lower bound
	- `Little Omega`: strict lower bound
- `Big Theta`: used when upper and lower bounds are the same $\Omega$


### Proof 1 (Big O)
$f(n) = O(g(n) if 0 ≤ f(n) ≤ c·g(n)$
1) We want to show that $7(n^{2})= O(n^3)$
2) Plug in => $f(n) = O(g(n) if 0 ≤ 7(n^2) ≤ c·(n^3)$
3) Can choose any value of c. Let's use 7 => $f(n) = O(g(n) if 0 ≤ 7(n^2) ≤ 7·(n^3)$
4) Omitting constants: => $(n^2) ≤(n^3)$ for $n >= 1$
5) So setting $c = 7$ and $n0 = 1$ satisfies the definition

### Proof 2 (Big Omega)
$2n2 + 2 = Ω(n^2)$
$f(n) = O(g(n) if 0 ≤ c·(n^{2}) ≤ (n^{2})+2$
1) Want to show that $c·(n^{2}) ≤ (n^{2})+2$
2) Choosing $c = 1/4$ => ${1}/{4}·2(n^{2}) + 2 ≤ (n^2)$ => $1/2(n^{2}) ≤ (n^{2})+2$
3) Omitting constants:  $(n^2) ≤ (n^2)$
4) So setting $c = 1/4$ and $n0  = 1$ satisfies the definition

### Proof 3 (Big $\theta$)
$3n^2 + 5 = Θ(n^2)$
_Big O_
$f(n) = O(g(n) if 0 ≤ f(n) ≤ c·g(n)$
1) Want to show that $3n^2 + 5 = O(n^2)$
2) Plug in => $f(n) = O(g(n) if 0 ≤ 3(n^{2})+ 5 ≤ c·(n^2)$
3) Choosing $c = 4$ =>$f(n) = O(g(n) if 0 ≤ 3(n^{2})+ 5 ≤ 4·(n^2)$
4) $3(n^{2})+ 5 <= 4(n^2)$ for all $n >= 3$
5) So setting $c = 4$ satisfies the definition
_Big Omega_
$0 ≤  c·g(n) ≤f·(n)$
1) plug in => $0 ≤  c·(n^2) ≤3(n^2)+5$
2) Let $c = 3$ =>  $0 ≤  3·(n^2) ≤3(n^2)+5$ 
3) Above is true for all $n >= 1$
Having proven _Big O_ and _Big Omega_, _Big Theta_ is proven