# Sarcasm-Generation

This repository contains code for a rule-based JAPE Generator for computational humour generation.For further info on the JAPE Generator,please refer to :
The JAPE riddle generator: technical specification by Graeme Ritchie(2003)

# Data

The dataset used for constucting one-liners consists of an alphabetically ordered text file containing homophones.The contents of the file have been scraped from the web using a simple Selenium Web Scraper
Further,the data on the basis of which jokes have been generated consists of movie summaries of 50 movies from the Cornell Movie Summaries Corpus.

#Generator:

5 types of one-liners have been generated according to the following rules:

1. NA Joke:

"What do you call  a\an " + d1  " that is  a\an d2 ? " "A\An" + w1  + w2 + "."

w1 - adjective
w2 - noun

d1 - adjective definition
d2 - noun definition

2. N2A2 Joke:

"What do you call a\an" + d1  " that is  a\an" d2 ?"  "A\An" + w1  + w2 + "."

w1 - adjective
w2 - noun

d1 - synonym of w2
d2 - synonym of w1

3.N2AN Joke:

"When is a\an " + d1 + " like a\an " + d2 + "? "     "When it is a\an " w1 + w2 + "."

w1 - adjective
w2 - noun

d1 and d2 are synonyms

4.N2V2 Joke:

"Why did someone " + d2 + "a\an " + d1 + "? "      "So they could " + w1 + " a\an "  + w2 + "." 

w1 - verb
w2 - noun

d1 - verb synonym
d2 = noun synonym


5.N4 Joke:

"When is a/an" + d1 + " like a\an" + d2 + "? "     "When it is a\an " + w2 + "." 

d1 - noun
d2 - noun
w2 - Synonym of d1

Note here that d2 and w2 are homophones


# Further Work and Reading:

As of now, a rule based joke generator has been created successfully.I propose two further steps

Step1: Build a generative model based on RNN architecture and train it on the dataset of all jokes have been generated by the rule-based generator.
Step2: Build a seq2seq model with variational attention mechanism which is capable of generating jokes similar to the rule-based generator given a movie summary.Variational attention has been proposed here because it has been proved to generate a greater variety of questions.For further info,please refer to :
Variational Attention for Sequence-to-Sequence Models - Hareesh Bahuleyan(2018).
