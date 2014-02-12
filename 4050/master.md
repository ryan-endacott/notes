# Master Theorem for Recurrence Relations

Note: `Th(n) = Big Theta(n)`

Examples:
1. `T(n) = T(n/2) + n` => `T(n) = Th(n)`

2. `T(n) = 2T(n/2) + n` => `T(n) = Th(nlgn)`

3. `T(n) = 4T(n/2) + n` => `T(n) = Th(n^2)`


## The master theorem:

1. If `f(n) = O(n^(logb(a)-e))` for some `e > 0` then `T(n) = Th(n^(logb(a)))`
Note: this means that `f(n)` is smaller than `n^(logb(a))`

2. If `f(n) = Th(n^(logb(a)))` then `T(n) = Th(n^(logb(a)) * lgn)`.  This is also the same as `T(n) = Th(f(n) * lgn)`
Note: both asymptotically equal.

3. If `f(n) = Omega(n^(logb(a) + e))` and if `af(n/b) < cf(n)` for some positive `c` and sufficiently large `n`, then `T(n) = Th(f(n))`


