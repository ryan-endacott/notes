### Syntax
- Proof
- WFF

### Semantics and Model Theory
- Truth Table
- Truth
- Meaning
- Validity



The language of first-order logic was explicitly designed to mirror what was going on in natural language.  Names, predicates, quantifiers, connectives, etc.  Is what Frege thought were central components of natural language.

For blank we have blank:
Names : Constants (a, b, c, ..)
Variables : Pronouns (x, y, z, ..)
Quantifiers : For all, there exists
Predicates : Properties or "gappy" sentences
Connectives : If then, or, and, etc.
Parenthesis : ()
Functions :


## Model
Domain: all the objects
U = {a, b, c, ...} (Universe of Discourse)
P = { a, c, ... }set of objects that when inserted into gappy sentence (predicate) yield true.
Q = {<a, c>, <a, b> }
Note: <> = order matters

f = {<a, b>, f(a) = b}
Function: the mother of ____  Note: Not true or false no matter what you put there, just references an object.
Functions cannot be ambiguous.  Must be inrjective.


Pa, check if a is in P in model.  Because we just check membership.
Pa = T if a exists in P.

Pf(a) = Pb = False



If first order logic is turing complete, why do we need more?
It sucks for natural language.

An assumption that seems harmless is false.  The assumption is that any sentence can be evaluated in the model.

Suppose you had a universe of discourse that was {Alice, Bob, Carol}.
Pxy "x is taller than y"
So for any pair, I can get a meaningful assignment of true and false

"Colorless green ideas sleep furiously."  Meaningless sentence that is grammatically correct.

So in FOL, we need to have a way of evaluating all of these terms in our language.  But a lot of those combinations of terms are not meaningful.  It is wrong to be able to evaluate this.  It is not T or F.  So we should not be able to construct an interpretation of this.  We need restrictions and a way to rule out the sentence.  So FOL we can't do this.


Just adding a 'meaningless' term is hard to deal with.
T -> F is F
but what is O -> O ?


"Every farmer who owns a donkey beats it."

For all x (if x is a farmer, (there is exists a y such that x owns that y and y is a donkey) then x beats y.)

Thus the quantifier scopes are all wrong.

For all x (if x is a farmer, (there is exists a y (such that x owns that y and y is a donkey then x beats y.)))

Arrow in existential is bad. Because here this statement is vacuously true.


Fixed:
For every x and for every y (if f is a farmer and y is a donkey and x owns y then x beats y).

But this syntax looks completely different from the original sentence.


Alternative model?  Assign classes to objects and don't allow sentences that aren't meaningful to be even built.

2 + 3 < 7
2 + (3 < 7)
(2 + 3) < 7

<+, <N, N>, N>
<<, <N, N>, Truthy>


(2 + 3) < 7 is the correct interpretation granted by ambigutation






