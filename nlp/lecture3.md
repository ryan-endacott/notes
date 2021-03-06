

### Johann Wolfgang Von Goethe

What do we want to do with this text?
1. Identify characters
2. Translate
3. Summarize
4. Stylistic determination


## Tokenization
When we tokenize something, we want to identify:
- Chapters
- Paragraphs
- Lines
- Sentences
- Words
- Parts of words


- Sentence
  - Spaces
    - \s
    - \t
  - punctuation
    - Full stops
    - continuation
    - Capitalization
      - start
      - (proper) nouns
      - acronyms

- Word
  - single words
  - phrases
    - ex: rock n' roll
  - single and phrases both have
    - affixes
      - verb -> nouns
        - ex: to close -> closure
      - double consonants
        - ex: traveler vs traveller
      - verb inflection
      - cliticization
        - ex: I'm a' goin' in.
      - Insertions and substitutions
        - roofs vs rooves
        - fox vs foxes
      - agreement

- Paragraph
  - indented
  - skip one or more lines
  - indent and skip lines

The moral of the story is that if we are to tokenize, we have to be able to summarize phenomena like this in a set of rules.  Tokenization is the application of rules like this such that you produce whatever you want (sentences, words, etc.).


The order in which we put the transformation rules will have a large effect on the output.


Two words, how many lemmas?

lie
- noun
  - untruth
  - contour of landscape
- verb
  - to tell an untruth
  - to recline
  - to place something

five lemmas.  

How to transform lying -> lie

A stemmer is  a program to normalize words so you can find its original lemma.

## Steps to do:
1. Text
  - Clean Up
  - Format
  - Transform (ex html -> ascii)
2. Tokenize
3. Stem or Lemmatize or both
4. Something interesting!
  - Count words, ngrams, etc.
  - Zac's experiment with NYT.
  - Translate, etc.


Tokenization depends on the context.  
Ex:  Nursing journals, tweets, etc.

## Chomsky Hierarchy
You can have grammars for anything, but Chomsky's is a grammar for strings.

Outer to inner:
- Type Not (0) (Outer level)
  - Natural language, phrase-structure
  - L0 (L sub 0)
- Context-Sensitive Language
  - L1
- Mildly Context-Sensitive Language
  - L1.5
- Context-Free Language
  - L2
- Regular Language
  - L3

In general, we can say that a grammar G is a tuple:
G = (N, T, S, P)
- N = set of nonterminals in a language
  - Nouns
  - Phrases
  - Sentences
  - Ex: Speech, stage direction
- T = set of terminals in a language
  - terminals are instantiated whoozywhatsits of the language.  For string languages this is words.
- S = sentence or construct
  - Thing we want to generate, recognize, or parse.
- P = Production rules
  - When you think of a grammar, this is what you think of.  They are the rules.
  - They are called this because in the beginning there were three models of computation:
    - Alan Turing's model
    - Kleene's recursive model
    - Post's set of production rules

N intersect T = empty set.  If something is a terminal, it can't be a nonterminal, visa versa.

Sigma = alphabet
  - Set of symbols out of which we produce the terminals.
  - In string grammar: 
    - letters
    - punctuation marks
    - numbers
    - white space

Any good grammar will let you recognize, generate, and parse.


If we have two strings (w, v)
1. some derivation of rules w => v, according to G is true iff 
u1, u2 together must lie in the union of N and T for some u1, u2 in the process.
2. w has at least one letter that exists in N.
3. w has to be equal to some composition of u1 and u2
4. v has to be equal to some composition of u1 and u2
5. alpha => beta in P
6. A language L, generated by G words created from the grammar.


For a regular language example, L3:

Sigma: empty set and the set: {epsilon (e, the empty word) }
For every a in Sigma, {a}
For any symbol a in Sigma, {a}
P:
- A -> w B (terminal nonterminal)
- A -> w (terminal)
N:
- {A, B}
T:
- {w}
- [w in T*]

    

Sheep language example:
Sigma: empty set, {e}, {a,b}
ex:
- baa
- baabaa
- Cannot do 'baaa baa black sheep' because no symbols to generate it. No spaces or other letters.


For convenience, we can define operators for regular languages.
Ex:  Kleene star (*):
- V0 = {e}
- V1 = V
- V(i+1) = {wv | w in Vi, v in V}, i > 0  # Recursive definition
- Zero or more of immediately preceding symbol
Ex:  Kleene Plus (+):
- super mathy definition here
- One or more of immediately preceding

On page 123 of the book, regex operations.


