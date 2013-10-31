# Semantics and Discourse

### Place where philosophy, math, and computer science intersect


## History of semantics

The great breakthroughs in logic come from the development of semantics in the 1890s.

In the 1890s, the major player is Frege.  And Frege was really the firs tperson to think of taking a natural language and really translate them into a formal system.  His main goal was to translate these into formal systems that resolve ambiguities.  His work was called concept writing where he invented quantifier (first-order) logic.

The notation was so awful that it was almost incomprehensible to read.

Language consisted of if-then, negation, and universal quantifier.


Right away, there was a typographical error on the third page of it and it got a horrible review.  Then Russell rediscovered it later.

The idea was that you could take statements in science and mathematics and then manipulate them with formal rules.  The great problem that Frege solved is how to disambiguate quantifiers.


The formal system comprised the entire logic.  There is nothing else about it or in it at all.  It becomes a serious problem to use notions like truth or meaningfulness when all you have is symbols that you are manipulating.  Ex: Chess isn't true or false.

It wasn't until 1927-9 that Alfred Tarski came up with 'Semantics' or 'Model Theory' which was then really clarified by his students afterward.  His idea was this:  Just like sentences in english are true or false because they bear the relationship to the world.  Truth comes from a relationship between two different domains, a language and the world.  What Tarski did is he tried to relate the formal language here (the syntax).

Formal language includes things like:
- formulas
- rules of inference
- proofs
- etc

The semantics on the other hand is where truth and meaning reside.  Semantics are not a language, it is a mathematical structure of some kind.

EX:  Syntax is propositional logic and truth tables are semantics.

So any concept relating to truth or meaning is a semantic concept, not a syntactic concept.  Syntax is just symbols being manipulated, it has literally no meaning whatsoever.  Although the notation is designed to suggest it, it doesn't have that meaning.

So when you think about concepts like validity, it is a semantic notion.
Provability is a syntactic notion.


So what did it mean for a proof for a statement in the object language (syntax) and semantics (meta language)


What does it mean for a statement like p implies q to be true?


Soundness means if something is provable, it is valid.
Completeness means if something is valid it is provable.


Godel
1929 - showed first-order logic was complete
1931 - Showed arithmetic was incomplete

In the 1930s, Bertrand Russell showed up on the scene.  Russell was the first person to outline a research program where you would take natural language and put it into formal logic and process it.

He wrote a paper "On Denoting".  He outlined a method for encoding all of the information that was contained in a name and putting it into rigorous formal logic.  And inferred how names have to relate to each other.

NL problem (names) -> Logic -> Analysis

Then this kind of approach took off.  This is where the work that goes into NLP gets motivated.  It is out of this sort of program that NLP comes from today.

Take sentences in English and encode them to an artificial language and then manipulate them.

Other people then followed suit:
- Carnap
- Heppel

Hempel took scientific explanations and encoded them into 1st order logic.  Then he analyzed the logic to determine if a scientific explanation was true or a prediction or something else.

All of these attempts failed.  In a very clear way.
It always turns out that the artificial language is never powerful enough to represent the natural language.  The failures immediately suggest modification to the artificial language though.


Hempel thought a scientific explanation had to be a valid logical argument.

So his program was encoding explanations into first order logic.
Ex:
Mary takes birth control.
Women on B.C. don't get pregnant
Therefore: Mary not pregnant

encoded to
Bm
for each x Bx implies not Px
therefore not Pm

So that was a valid explanation for him.

But what about why Zac isn't pregnant?  He is a man.  So the explanation breaks down.  The causal link to the world is lost.  Because semantics of Zac are different from the semantics of Mary.

So one approach is you diagnose the logic as the problem with Hempel's theory.


Semantics are lost when just the logical form is given.  It is just syntax.


## Semantics and NLP

So NLP is about figuring out how to do this.  You can't just encode your entire vocabulary.  It has to be a simple, parsimonius way of doing it.


You want a framework that has enough flexibility that you can adapt it from one task to another when translating into formal logic.


One reason why it is easy to run semantic and syntactic concepts together is because they _have_ to mirror each other.  What you find for understanding syntactic concepts and semantic concepts is that there is a mirrored concept for each concept.


So when you start thinking of a proof system like propositional logic.  You have functions, constants, variables, connectives, quantifiers, predicates, etc.

Syntax For Frege:
Constants were like proper names.
Functions were operations that expressed relations.  They map objects to objects.  Ex: mother_of(x) yields mother of whoever x is.
Variables were pronouns. They are placeholders than can be made to refer to objects.  Ex: Bob is playing basketball. He is tall.
Predicates were things that were true or false (ex: is tall).  For every function there is a predicate.  `mother_of(x, y)` is true iff `mother_of(y) == mother_of(x)`


### Semantics (model)

Semantics is like a toy world that has a domain of objects.  Somethings called the "Universe of discourse".  And then it has, for every function in the syntax, a similar function.

The really basic example of this is just your standard truth table in classic propositional logic.  Your truth table is a universe with two objects, a true and a false.  A model of implication for example:

p | q | p -> q
T | T | T
T | F | F // counterexample
F | T | T // vacuously true: All even primes greater than 2 are 5.
F | F | T


Simple english example:
Bill has a dog.  He bit Sally.
Bill has a temper.  He bit Sally.

He refers to Bill, then he refers to Bill.

So the meaning of the entire statement hinges upon dog vs temper.  Compositionality fails.  Dog and temper are both nouns.


So you may have two classes of words - nouns with teeth, nouns without teeth.

Class1: Teethy
Class2: Nonteethy things

So if you had that information then the meanings of these two sentences would not necessarily fall prey to the same problem.

Now maybe you could build up a nice compositional way of describing these two sentences and attaching the meaning to them.  Your rule for combining may be that he refers to the last teethy thing that was mentioned.  In which case, you would carry the information about teethy and temper with you as you turned the sentence into logic.

There is a dispute both in computer science and in philosophy that on the one hand there are people that take natural language and think the right way to understand it is by turning it into logic then analyzing.  Then there are other people who think a full and complete way to do it has to be noncompositional.

Other people think that natural language is intrinsically richer than formal languages can be.
OED is QED. Oxford english dictionary is the end of the argument.


Montague - "It is my belief that there is no difference between formal language and natural language, but sufficient semantics have never been supplied."

Montague wants to have his cake and eat it too.

Natural example of a noncompositional formal language.


So if you're really into NLP, you don't want to go to noncompositional stuff.  We specify rules for evaluating things in the semantics.  That's why they're compositional because they're using functions to compose them.

Ex:  (p & q) -> (r & s)
So if you evaluating compositionally, from the inside out.  Evaluate p&q and then r&s.  Then you lose that information as you continue to evaluate.


You're always losing info because as soon as you do the evaluation.

We're building more and more info into the constituents so that it gives us more possible combinations and more unique ways to evaluate subexpressions.


They are flying planes.
Those things in the air are flying planes.  Bob and Sally are flying planes.


Two steps possible here: Tagging which requires context, and then evaluating the sentence with or without the sentence.

The dog example is meant to suggest that the problem with compositionally evaluating the sentence may just be that the compositional analysis didn't have enough information.








