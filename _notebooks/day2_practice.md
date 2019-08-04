---
layout: post
title:  Practice
date:   2019-08-04
day: 2
next:
prev:
---


# Coding practice

Let's practice the tools and functions we have looked at the past couple of days. We'll have 2 main probems to solve today: staircase and sentiment analysis.

### Staircase

For a given $n$, print the corresponding staircase made out of hash symbols. For example, if $n=6$, we should get:

```
#
##
###
####
#####
######
```


```python
n = 6
for i in range(n + 1):
    print("#" * i)
```

### Sentiment analysis

[Sentiment analysis](https://en.wikipedia.org/wiki/Sentiment_analysis), or *emotion AI*, is an area of Natural Language Processing (NLP) that allows us to extract and quantify opinions and emotions from the text.

We will continue looking at this task more later, but for now let us create a super simple sentiment analysis system. Namely, we will let the computer read a sentence and decide whether it is nice or rude. 

Let us start by learning one more function defined for strings -- `str.split()`.


```python
s = "This is a string"
my_list = s.split()
print(my_list)
```

As you can see, this method splits a string into separate words.

Now we can start the sentiment analysis task!


***What is good and what is bad?***

Below, define two lists: `good_words` and `bad_words` that contain good and bad words, correspondingly. After, define a string `tweet` that will contain some phrase. (For now, avoid using punctuation)


```python
good_words = ["good", "well", "nice", "love", "fun"]
bad_words = ["bad", "nasty", "eww", "negative", "itchy"]
tweet = "This book is good and nice :)"
```

Now, split the `tweet` into separate words. Try these tweets:

1. "Sentiment analysis is fun and easy!" 
2. "I don't like reading all of the negative tweets. :("
3. "I love ice cream. :D"
4. "My back is itchy."`


```python
tweet = tweet.split()
print(tweet)
```

Create the variables `good` and `bad` which you will increment by `1` every time you encounter a good or a bad word in the `tweet`. Using a loop, look at every word in your `tweet`, and see whether you can find it in the list of good or bad words. Every time you see a good or a bad word, update the corresponding counter.


```python
# create two counters
good = 0
bad = 0

# using while, loop over every word in your tweet
for word in tweet:
    # if the word in the good or bad list, update the corresponding counter
    if word in good_words:
        good += 1
    elif word in bad_words:
        bad += 1
```

Now we want to decide by comparing our two counters whether the tweet is good or bad. Let's write conditions which:
1. will print `not enough data` if both counters are zero;
2. will print that the text is mostly positive if `good` is bigger than `bad`;
3. think about two additional outcomes!


```python
if good == 0 and bad == 0:
    print("Not enough data!")
elif good > bad:
    print("The tweet is good!")
elif bad > good:
    print("The tweet is bad!")
else:
    print("The tweet is neutral.")
```


```python

```