# Analyzing document corpora
#### ( or What are you talking about?)

### Overview

While searching a device for incriminating evidence, text documents are commonly encountered.  Analyzing the content of such documents is a challenging task which would require investigators to read through large volumes of text, without any information to guide them through the search. What is this document about? How does it relate to other documents? Are there any trends amongst them? Do I need to read through this pile of documents? Or could I spot a particular document which is more interesting than the rest?

We will tackle these problems using natural language processing tools. The aim of this group is to use NLP tools to group documents with similar content and provide investigators with the tools to quickly gain insight into large collections of text.

### A bit of technical detail

In the field of NLP, topic modeling has become a popular technique for analyzing large sets of documents. Topic models attempt to infer a set of topics (basically, bags of words) and then identify the probability of a topic being contained in a document (e.g. Document1 is made up of 0.5 * Football topic + 0.2 * General sports topic + 0.3 * Drugs and crime topic).

However there are still many open questions when using topic modeling: document pre-processing, optimum number of topics to use, visualization and interpretation of the results, etc.

One focus are is investigating techniques for visualizing results from topic models in the most useful and meaningful way. The ultimate aim is to be able to take a list set of documents (e.g. emails from an inbox) and cluster them into different groups of similar emails (e.g. emails work, family, leisure). To achieve this we will need to use existing natural language processing technique, investigate suitable similarity metrics between documents, and develop (interactive?) visualization techniques.

### Data

We will be using the infamous Enron email data set as our document collection.

https://www.cs.cmu.edu/~./enron/

### Reading resources:

 - This blog post gives an introduction to what is topic modeling and how it is applied used: http://journalofdigitalhumanities.org/2-1/topic-modeling-a-basic-introduction-by-megan-r-brett/

 - This blog post explains topic modeling in some more detail: http://tedunderwood.com/2012/04/07/topic-modeling-made-just-simple-enough/

 - This blog post talks about Latent Dirichlet Allocation (LDA, the maths behind topic modeling) applied to data from xkcd: http://cpsievert.github.io/xkcd/

 - This R tutorial shows one alternative for visualizing topic models: https://ropensci.org/blog/2014/04/16/topic-modeling-in-R/

 - This paper gives a good introduction to the basics of topic modeling: http://www.cs.princeton.edu/~blei/papers/Blei2012.pdf

 - This paper discusses the problem of Evaluating topic quality: http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=7008665&tag=1

 - This paper compares different types of topic models: http://maroo.cs.umass.edu/pdf/IR-689.pdf
