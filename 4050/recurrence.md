# Solving Recurrence Relations

## Iteration
Already covered.

## Recursion Tree
Already covered.

## Substitution
We're learning this today! This is induction in disguise.

Prove `S(n) = 1 + 2 + 3 + ... + n = (n(n+1))/2`

Base case:
`S(1) = 1 = (1(1+1))/2 = 2/2 = 1`

Induction step:
`S(n) = S(n-1) + n = (n-1)*((n-1)+1)/2 + n = (n(n+1))/2`

For substitution, the base case is always constant.
In order to use induction, you must know the answer already. It is a chicken and the egg problem.

The difficulty of substitution is you need to have a good guess of the solution.  You have a good hunch for the solution.  If your hunch is wrong, you will know it by substitution.

Example substitution:
`T(n) = T(n-1) + Theta(1)`

Note: Let `Th(1) = Theta(1)`
Guess: `T(n) <= Cn`
`T(n) <= C(n-1) + Th(1) = Cn - C + Th(1) <= ? Cn`  (We can figure out that `-C + Th(1) <= 0` because `-C < Th(1)` for some value of `C`)

Now if we tried substitution with: `T(n) = T(n-1) + Th(n)` it wouldn't work if our guess was `T(n) <= Cn`.



Then he did a big O(nlgn) example that Brendan took really good notes on.  I assume it's in the book too.
