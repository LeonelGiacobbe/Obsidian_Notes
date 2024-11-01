<mark style="background: #BBFABBA6;">IN A FEW WORDS: algorithms that call themselves</mark>

# ==Basic outline==

- Recursive algorithms have two main parts:
	- <mark style="background: #FF5582A6;">Base case</mark>: a conditional that, when triggered, stops the function calling cycle and effectively ends the recursion.
	- <mark style="background: #FF5582A6;">Recursive cases</mark>: when the base case is not triggered, the function will execute whatever commands it has been programmed to do, and then it will call itself, continuing a cycle only broken by the base case.

# Example code
```cpp
int factorial(int n) {
    if (n == 0 || n == 1) {
        return 1; // Base case: factorial of 0 or 1 is 1
    } else {
        return n * factorial(n - 1); // Recursive case
    }
}
```
