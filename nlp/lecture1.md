# Natural Language Processing Lecture 1


NLP == computational lingistics
(mostly equal to)

NLP is asking the machine to reason with text.

Things we want it to do:
1.  Translate oral notes to text -> grab structured data from notes -> produce analytical and narrative summary of the data.
2.  Summarize evidence and precedents in court cases.
3.  Better identification of interesting scientific papers.
  - May be interested in cell death in plants, but also want to know about molecules that appear during cell death.  Want to know if those molecules can autofluoresce yellow.
4.  Better automated translation of text.  
5.  Better human computer interaction with robots taking care of us.  

High level issues:
-  Involves text interpretation with explicit and implicit semantics.
-  And they involve reasoning with that knowledge (background and in text).
Machinery/low level issues:
-  Understand the meaning of texts of different sizes.
-  Recognize and define what it means to be similar.
-  Resolve ambiguities.
-  Divide text in useful ways.


How do these problems get solved?

For the NLP World, we need data and we need thinking.

## Data

In NLP, data comes in several different varieties:

### Corpora
- Corpora (plural of corpus, a body) - The body of text we want to work on.
Is it suitable?  Is it sufficient?  Find what breaks it and what works with it.  You need enough data and it needs to vary enough.
Ex:
  - Wall Street Journal Articles
  - Brown != WSJ
  - Chinese bible translations
  - Bilingual texts, Ex: (French/English texts from Canada)
  - Twitter feeds
  - Shakespeare
  - Gutenburg project, novels of Jane Austen
Results may vary a lot depending on the corpus.

### Lexica
Lexica (lexicons):
- words
- phrases
- markers of linguistic structure
Ex:
  - German declension (sp?)
  - English plurals:
    - s: books
    - es: foxes
    - [f->v]es: hooves


### Rules
Rules/grammars of....
  - Morphology
  - Syntax
  - Semantics
  - Pragmatics
These rules help us understand how the text organizes meaning.

## Thinking

### Statistical

#### Counts
Counts of things.
Must know the structure of population.
Correlations (numbers games):
  - Predict next word or sentence
  - N-grams (number of consecutive words (and their lengths) in each sentence)
  - Distributions of co-occurrence can be diagnostic, both for individual writers but also pieces of text and layers of meaning.
  - Mappings between chunks can display meaning.

### Linguistic/Analytical

A says:  "Where's the store?"
B says:  "Downstairs."

The specific act of trying to represent text in some computationally useful way, including the phenomena that occur in natural language.  

There are rules for morphology, syntax, semantics, and pragmatics.

How do we solve these NLP problems?  Your mileage will vary depending on your corpus, lexicon, and rules.


## How do we do all of this computationally?
#### Morphology
Morphemes: [Prefix|Stem|Suffix]
  - re turn
    - re describes physical circuit, coming back to same place
  - re scrubbed (orthographic rule: how do you spell correctly?)
    - re implies occuring twice
    Ex: 'your' will become 'ur' in the future
  - 're' difference is semantics

Morphotactic rules
Ex: 
- How many prefixes can I have in English?
  - Antidisestablishmentarianism
  - Anti|dis|establish(table)|ment|ar|ian|ism
  - 2+ prefixes
  - 4+ suffixes
- How can I join words?
  - book-mark -> bookmark

How do we analyze these morphological rules?
Finite State Automata/Transition Machines

#### Syntax

Zeilig Harris was a linguist interested in rules that governed the syntax of language.
Harris had a student named Noam Chomsky.
Chomsky got his start by looking at the formal properties of grammars.

Chomsky was able to show that string grammars fall into one of four classes.  Languages also fall into those classes.
Classes (in to out):
  - Regular
  - Context-Free
  - Context-Sensitive
  - Type not - natural language

### How do we express these rules?


### Pragmatics

Pragmatics is the hardest part.
Ex: Sarcasm, irony, etc.


