# Contemporary Applications of NLP

- Sentiment analysis
- Trend prediction
- Social network analysis stuff



Searching for disease outbreak by analyzing news articles.

Speed vs. sophistication.

Throw 200k documents in as bags of words.

Get maybe 1 million words.

1.  Eliminate stopwords or other too common words. (fish in this case)
2.  Eliminate words that are too rare.  (Proper names or typos or encoding errors), appears <100 or <1000 times.
3.


### Information Theory from Shannon/Weaver
Awesome for really fast parsing:  Also beautiful applied math:

I(x) is information contained in event x.

Events that were certain carry no information.

The more possible events, the more information is carried.
Flipping a coin carries less info that tossing a die.

The more events the more info.
If x and y are independent, then I(x & y) = I(x) + I(y)


Suppose you have a coin toss (2 possibilities) and a die throw (6 possibilities)

I(2) + I(6) = I(12)

I(1) = 0
I is an increasing function.

Only function that satisfies those conditions is the logarithm function.

ln(a * b) = lna + lnb

Therefore, the amount of information contained in an event is the log of the number of possible outcomes.


Mutual Information Criterion


You want a word like Barack that tells you a lot of info about the other words.  It tells you possibly Obama, possibly white house, president, etc.

So look at pairs of words and determine if they are probabilistically dependent on one another.


Look at every pair of words.

If one has information about the other then
p(w1 & w2) > p(w1) + p(w2)

So the probability of having both is higher than probability of having the two separately.


log2( p(w1 & w2) / (p(w1) * p(w2)) )


This has to do with feature selection.

This feature selection for words can be run just once.


