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
