# Corpora

Three main problems:
- Getting Corpora
- Validating Corpora
- Using Corpora

## Getting Corpora

We can...
### Scoop up 
Ex:
- twitter
- listserv
- web pages

Implications:
- Little or no curation
- very heterogeneous


### Donated from someone
Ex:
- WSJ
- Bibles
- Open Source Journal articles

Implications
- some curation
- High level of duplication
- Purpose-driven

## enter it ourselves
Ex: Brown Corpus,
- humans typed in 2k word long chunks of text.
- Text was selected to have even distribution in 15 genre considered
- Starting point for chunk was randomly chosen in text

Implications:
- Highly curated
- Minimal duplication
- Purpose-driven
  

## Validating Corpora

How do you know how good the corpus is?  What mistakes can you have?

### Manual

Very difficult.

Brown Corpus:
Imagine that you are sitting in 1967 and your job is to validate the typed text.  You have 500 chunks of 2000 words each.  

It had words that gradually became delimited.  It has parts-of-speech tags (check concordance among the experts, 100 types of tags).  It had locations of the chunk in the original text.  

In the Penn Tree Bank - ~ POS 250 tags

Differences:
  - Penn could be more finely grained than Brown Corpus
  - Could have different input texts
  - Time (Penn - 1980s onward, Brown - 1960s onward)


### Iteratively build a context-free grammar

CFG:  Grammars of relatively simple natural sentences.

What can you do?

- Count/Identify/(conditional) frequency distributions
  - Ex: Which words occur as a function of position in the sentence?
- Find Unique words:
  - Lemmae - head words, root
  - Groups of words
- (Morpho)Syntactic rules:
  - Grammar
- index (determine position of each word in text)
- tokenize
  - Identifying the functional units of the text (can be challenging)
  - the_blue_car (_=space)
  - ADP Ribosyldiphosphate (must be taken as one token)
- Classes of words (ways to classify)
  - Parts-of-speech
    - Word sense disambiguation, ex:
      - saw - noun, tool w/ serrated edge
      - saw - verb, past participle of see
      - I saw the board.  (cannot know tense from the sentence.  Can only know saw is a verb).
  - Stop words
  - Proper nouns
  - Long words
  - Semantic groups of words
  - Try and resolve pronouns
  - Generate output:  Goal: machines that can talk with humans.

Note that level of difficulty is increasing.



# Lexica

A word-book or dictionary.
A list of meaningful units in a language like as in a dictionary, but without the definitions (usually).

Big medical lexicon.  
has tons of info

Wordnet is an example of a semantic network.  
Concept hierarchy tree.  (Meronymy)
Wordnet is a network of concepts to which eventually terms are mapped.  Example in the book (p91).  artefact is manufactured object, motor vehicle is a class of manufactured object, motorcar, go-kart, truck are motor vehicles, etc.  

Nyms:
Meronymy
Holonymy - higher in hierarchy
Homonyms - spelled same
Metanyms
Hyponyms 
Antonymy - opposites

British English - He is credited as inventor of motorcar.
American English - He is credited as inventor of automobile.
Difference between the two is pragmatics.
Sidenote:  Harry Potter was translated from British English to American English.

Car can be...:
  - Auto
  - Rails
  - Gondola (skiing)
  - Elevator

When thinking about relations, we have to think about the type and nature of the relations we have.

Brief remarks about semantics:
## Semantics

Where is the unit of meaning in text? Can be in..
- Semantic lexicon
- Sentence
- Dialogue
  - Paragraph
  - Whole text

Non sequiter, meaning it does not follow.
How to distinguish non sequiter from logical followings that _are_ connected.


Ex:
When will you be finished studying?
I will be finished studying by 5pm.

When can I borrow your biology book?
I will be finished studying by 5pm.

Initial assumption for semantics was that it was compositional.  E.g. if I know semantics of the words, I can get semantics of sentences, I can get semantics of entire text, etc.  

#### How to figure out relationships like the biology example above?

Ontologies: encoding relationships directly.
Ontologies are available for..:
- common sense
- weather
- medicine

Or we have tools:
Ontosem, simple lex
ontology is wordnet


Languages spoken:  Greek, Italian, Latin, German, Biology, Opera, 
