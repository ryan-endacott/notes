
# Algorithmic Patterns

The book discusses several patterns, but there are multiple, and depending on the needs of your problem, some paradigms are better than others.  

Imagine we need to find a ringing telephone.  The phone rings indefinitely.  Our task is to find the telephone.  The search space that we have is going to be in a landscape and have one or more buildings.  The searcher has no memory, but has extremely acute hearing.

In the first case, where we want to find the phone, we can imagine that we have an old fashioned motel.  Rooms are in linear array, each with a door.

Search linearly -> 
[_|_|_|_|_|_|_|_]

Searcher checks volume, direction, echo or ring.

Linear search vs branched search.

Search space can be inherently branched (Palladium villa) or can be made branched (motel floor).

Algorithmic paradigm means the structure of the problem and how you go about solving it.


## Methods:
1. Brute Force
2. Branch and Bound

Must compute cost function and prune search tree wisely.

3. Greedy Heuristic

It requires that you be able to evaluate the cost function and requires that you be able to construct a model of the graph.

Pick the best and recur, pick next best, etc.

4. Divide and Conquer
Divide arbitrarily and ask for value of cost function.

5. Dynamic Programming

Resembles divide and conquer with important differences.

In DP, we have to know about the structure of the problem to know if we can divide it recursively.  
The trick is we're going to divide the problem recursively.  We're going to use the structural relationships among the pieces of the recursion to solve the problem by solving each subproblems in the same way.  

DP is good for string comparison.  

6. Random search

Randomly hopping, but can be structured. E.g. Tesselate the search space.

7. Machine Learning

Development set, training set, testing set.

Then use favorite machine learning technique and hand it the dev data.  Ask it to sort through the dev data based on some objective function it is given.  Data should be sorted into stuff that I know works and that I know doesn't work.  

Then hand it the training set divided in the same way.  Ask how well it performs.  

Then hand it data it has never seen and see how well it performs.


Usually, you don't have enough data to train the machine learning algorithm.or data is too heterogeneous.

Problem: Sentences are unique.

What you can do when not enough data.  You can divide data into groups and train for example on 1..9 then test on 10.  This is a cross-validation procedure. Data must be evenly distributed into the groups though.

## How to choose an algorithm

It's up to you.  Check the literature.  Compare their corpora to your corpus.  See if those methods will carry over.  

# Computational Paradigms

### Expression paradigms
Three main ways
#### Functional programming
Lambda calculus, John McCarthy
You write a series of mathematical functions.  The program has no state.

With this, if I want to parse, I can't keep track of state.

Functions have no side effects.

E.g. Lisp, Haskell

#### Imperative programming
- State-dependent
- Side effects (referential transparency)
- Subroutines

Can be C, Perl, Python in some cases

#### Declarative programming
- Logical statements and conditions
- Relations
- Proof tree
- No side effects

Relations are called predicates. 

Ex: Prolog, SQL



Given any statement, you can read it in a procedural way or in a declarative way. This can often be helpful in understanding what the code is doing.  


We need a way to encode the semantics of text.  We can encode it in a procedural way.  We could encode it in a declarative way.  We need to abstract something in order to encode it.  

### Organizational paradigms
  - Stream of Consciousness programming
    - -> natural groupings
    - -> refactor code to be more structured.
  - Very structed programming


# Logic


## Universe of discourse

- Words
- Topics
- Concepts

Universe of discourse can be open or closed.
If it is closed, then we assume everything we need for problem (closed world assumption) is included in our corpus.
Open (open world assumption) means there are cases that are not in universe of discourse.



Differences in open vs closed:
If we get a failure in closed, we lose it.  
In open, we trap the failures to analyze later.

Example: 
- Cyc is an open world system.  Started by Douglas Lenat.
- Was designed to learn common sense reasoning.  
- Started with axioms and simple reasoning.
- Handed Cyc data and asked what could learn from data.

Figure 10-2 in book.


## Flavors of Logic

Two main ones:
- Propositional Calculus
  - Relations are
    - AND (p & q)
    - OR (p V q)
    - IF THEN (p -> q)
    - NOT (_p)
    - IFF (p <-> q)
- Predicate Calculus (First-Order Logic)
  - Relations are above and more
    - Ex:  sitting(we, room) & are(we, enclosure) & have(I, chromosomes(2, X))

Two important practical differences:
- Granularity of the statements
  - Propositional Logic: Sentences are whole clauses, Coarsely grained
    - If we are sitting in a room
    - We are in an enclosure.
    - I have two X chromosomes.
  - First-Order Logic: Relations, finely-grained
    - sitting(we, room)
- Allowable relations

Aristotle lived 2500 years ago, therefore Aristotle is dead.  
I am a woman, therefore I have 2 X chromosomes.  
We are sitting in a room, therefore we are in an enclosure.





