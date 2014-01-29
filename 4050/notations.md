# Asymptotic notations

Big Oh | O | <=
Big Omega | Hill looking thing | >=
Theta | Theta | ~=
Little Oh | o | <
Little Omega | u | >


O(g(n)) = { f(n):
There exists 2 positive constants c and n0 such that
0 <= f(n) <= c * g(n)
for all n >= n0 }
O(g(n)) is a *set* of all functions that satisfy that property.o

We say
f(n) = O(g(n))

Big Omega(g(n)) is the same set as above, but switch f(n) and c * g(n)


f(n) = O(g(n)) <=> g(n) = bigomega(f(n))


f(n) = theta(n) means that f(n) = O(g(n)) and f(n) = bigomega(g(n))


o(g(n)) = { f(n):
For any positive constant c there exists a positive constant n0
such that n0 <= f(n) < cg(n) for all n >= n0
}

little ones imply big ones.  little oh implies big oh.  little omega implies big omega.

lim n->inf of f(n)/g(n), if it is a constant, they are theta each other.
