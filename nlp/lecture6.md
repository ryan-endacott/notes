
# n-grams and POS stagging
(parts of speech)

## n-grams

The fundamental problem an n-gram tries to answer is: If I have a sequence of words, what is the next word going to be?

Ex:
The quick brown fox jumped over the lazy dog.
words 1-9
<w1, w2, ... w9>
Likelihood of `the` being followed by quick is 1/2.

Let us imagine a corpus that consists of many sequences of words.  And now, what we want to know is over the entire corpus, what is the likelihood that `jumped` will be followed by `over`.

How to do it with tons of varying data in a corpus?  The big issue is data sparsity.

For a given corpus that contains a given Q somethings (loosely, words) arranged in M strings, we can ask how many combinations are of length N:  C(Q, N) 
The answer depends on what the thingies are.  We can just count up the number of words.  OR.

In a corpus, Q = total # words (tokens)
The total # of unique words, let us call the wordforms.
The total number of inflection-related, same part-of-speech, used in the same sense sets are the lemmas.

Ex:  Book, field, cart are words that can be a noun or verb.  Depending on how they are used, they can form different lemmas.


Figure on site has chart for this:
How many different combinations can we get, if we sample (with replacement).  The longer the n-gram, the faster the combination we can get.
If I have a sequence of length 2, 3, 4, 5.

Even with a large corpora, when we pick a large n-gram size (like 5), we tend to get mostly unique sequences.  So when we pick a long sequence from a corpora, chances are it will be unique.


So we have to clean up the text.  The way we clean up the text will depend on what we want to do.  In the examples given, text was clean up to wordform.  The rationality is that we need important signals from morphology of the word.  We can clean out punctuation or lowercase. 


So we want to figure out the probability of a word, given the preceding n-1 words.
P(word | preceding n-1 words)
<w1, w2, ... wn-1, wn>

If we have a sequence, this probability is just the counts.  So
probability of current word (last word in the sequence) given the first word in the sequence up to the penultimate word (second to last).
P(wn|w1 to wn-1) = Count(w1 to wn) / Count(w1 to wn-1)
= P(w1) * P(w2|w1) * P(w3|w2w1)... P(wn| w1 to wn-1)

While it's easy to write this formula, due to data sparsity, we can't get these probabilities.

There's a trick we can use. But it turns out it works a lot better than you would think.


### Markov process
Trick for dodging data sparsity

In order to understand the trick, we must discuss processes.

Suppose I'm in my garden and I'm going from stone to stone in the garden, describing a path.  Have two choices where I can go from start point.  Now two more choices, keep going, then only one choice.

I can make different choices, but my next choice always depends on my current position.  Eventually, I can learn and remember my path back more preceding steps.

This is called a Markov process (named after Russian mathematician).
Can be 1-step or multiple.

So we're going to approximate like this:
P(wn|w1 to wn-1) ~= P(wn|wn-1)
~= is approximately equal
Notice that the right side of the equation is just a bigram.

The general case:
P(wn|w1 to wn-1) ~= P(wn|w[n-N+1] to w[n-1])

Note:
w[x] is the xth word
wx is also the xth word

P(w1 to wn) ~= the product from k = 1 to n of P(wk|wk-1)
Maximum likelihood estimate.

P(w[n]|w[n-1]) = Count(wn-1, wn) / Count(wn-1, wn)
But here, wn in numerator is a particular word, like "dog"
wn in denominator is all possible second words
wn-1 in denominator is all possible 1st words.
Numerator is particular sequences, denominator is all sequences.


At the beginning and end of strings, we put in a special token, ex: <s>xxxx</s>

The maximum likelihood estimate (MLE) is not necessarily the best estimate.  It is the upper bound of the best estimate.  Why?  Because the data is sparse!  Darn data!

Suppose we take all of the bigrams we observe in our corpus and ask, what is the relative frequency?  Then sort them in decreasing order of frequency.
We get a distribution that tails off pretty rapidly with some kind of exponential function.

Zipf's law.

You must figure out how to close the gaps in your data.  
Ways to do:
- Bigger corpus
- More diverse corpus
- Both

## Language Model

Language Model is what we do when we come up with the n-gram models.

#### Extrinsic

Inputs ->
Machine (with language model) ->
outputs

We evaluate the outputs given the inputs.


#### Intrinsic

Inputs ->
language model ->
outputs 

Unigram
Bigram
Trigram
etc.

We think of the language function as an evaluation of the stuff in our language model.  And we gain a quality of prediction.

If our language model is great, we get an ideal function depending on what we're predicting.  In reality, we get a gap between ideal function and our observed (real) function.  We then ask what is in the gap?  How do we improve?

If you were an economist, you would compute the area under the observed function.  Then you would compute the area under the ideal function (its integral).  Then subtract ideal area - observed area to see a summary measure of how you did. This is called a Gini test.
Our ideal function may not be correct if we didn't make a thoughtful prediction.  If we tweak the language model, can we get closer to the ideal function?  This is what economists do.  NLP people use something called perplexity.  

#### Perplexity

If we have a test set of sequences, W = <w1, w2, ..., wn>, <w21, w22, w...2n>
PP(W) = P(w1* w2 * ... wn) ^ (-1/N)
= (the product from i = 1 to N of (P(wi|wi-1) ^ (-1)) ) ^ (1/N)

Perplexity decreases as length of n-gram increases.




