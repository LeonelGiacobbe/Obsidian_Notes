## Computational Complexity

- amount of resources used by an algorithm
    - time to run → _time complexity_
    - memory used to run → _space complexity_

## Asymptotic Complexity

- The rate of growth of an algorithm’s time complexity function `f(n)`
- `bigO`: rough upper bound
- `bigOmega`:rough lower bound
- `bigTheta`: average bound used for functions with identical growth rates.

  

## Growth rates

We put Theta when both complexity functions have the same rate of growth. We put big O in the function with the greater growth rate (`bigO n^3 = n^2`). The opposite happens with `omega`. `7^n = omega 5^n`).