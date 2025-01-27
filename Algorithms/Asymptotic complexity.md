- `Big O`: upper bound
	- `Little O`: strict upper bound
- `Big Omega`: lower bound
- `Little Omega`: strict lower bound
- `Big Theta`: used when upper and lower bounds are the same $\Omega$


### Proof
$f(n) = O(g(n) if 0 ≤ f(n) ≤ c·g(n)$
1) We want to show that $7(n^{2})= O(n^3)$
2) Plug in => $f(n) = O(g(n) if 0 ≤ 7(n^2) ≤ c·(n^3)$
3) Can choose any value of c. Let's use 3 => $f(n) = O(g(n) if 0 ≤ 7(n^2) ≤ 7·(n^3)$
4) Omitting constants: => $(n^2) ≤(n^3)$ for $n >= 1$
5) So setting $c = 7$ and $n0 = 1$ satisfies the definition

