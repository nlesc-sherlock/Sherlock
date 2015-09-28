Collection of ideas of topic we can work on:
============================================

Analyzing document corpora
--------------------------

Topic modeling has become a popular technique for analyzing large sets of documents. However there are still many open questions when using topic modelling: document pre-processing, optimum number of topics to use, visualization 
and interpretation of the results, etc.

One potential work package for Sherlock could focus on investigating techniques for visualizing results from topic models in the most useful and meaningful way. The ultimate aim is to be able to take a list set of documents (e.g. 
emails from an inbox) and cluster them into different groups of similar emails (e.g. emails work, family, leisure). To achieve this we will need to use existing natural language processing technique, investigate suitable 
similarity metrics between documents, and develop (interactive?) visualization techniques.

Reading resources:

* This blog post gives an introduction to what is topic modeling and how it is applied used: http://journalofdigitalhumanities.org/2-1/topic-modeling-a-basic-introduction-by-megan-r-brett/
* This blog post explains topic modeling in some more detail: http://tedunderwood.com/2012/04/07/topic-modeling-made-just-simple-enough/
* This blog post talks about Latent Dirichlet Allocation (LDA, the maths behind topic modeling) applied to data from xkcd: http://cpsievert.github.io/xkcd/ 
* This R tutorial shows one alternative for visualizing topic models: https://ropensci.org/blog/2014/04/16/topic-modeling-in-R/
* This paper gives a good introduction to the basics of topic modeling: http://www.cs.princeton.edu/~blei/papers/Blei2012.pdf
* This paper discusses the problem of Evaluating topic quality: http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=7008665&tag=1 
* This paper compares different types of topic models: http://maroo.cs.umass.edu/pdf/IR-689.pdf


Finding all faces in an image dataset
-------------------------------------

There are several tools around that can find faces in unconstrained images and perform some analysis on them. A fun example by microsoft:

* http://how-old.net/?q=tom+cruise

Some papers on this topic can be found here:

* http://www.openu.ac.il/home/hassner/Adience/publications.html

This would allow us to answer questions like ranging from "find all images with people in them" to "find all -unique- people in all images" to "find me all images with adult males". There is also an algorithm in there that does 
face frontilization:

* http://www.openu.ac.il/home/hassner/projects/frontalize/

which would give us a series of 'passphoto-like' iimages of all faces found in a dataset. 


Optimizing processing pipeline
-------------------------------

The current Hansken processing pipeling is based on map-reduce and requires several iterations (typically 3 or 4) to fully analyze a disk image. Initial tests by J. indicate that this is not optimal. Startup time per iteration is 
high ( the first two iterations have only a single task, the last two iterations seem to have a skewed distribution of tasks (most last only a few seconds, a few last a couple of minutes) which leads to a 'long tail' problem, all 
steps after the first lose data locality, all data is read at least twice. Sending finished traces to ES may cause high overhead. Optimizations in mapreduce or switching to other models may help here.


Hansken integration
-------------------

The analysis tool created during the Sherlock sprints need to be integrated into Hansken by wrapping them into the right tool API. This may be require a specialized team in one or more sprints ?

## Concept search/query expansion/pseudo relevance

Goal: suggest relevant related terms to search queries, e.g. when searching for 'weapon', suggest 'knife', 'gun', etc.

[Wikipedia definition of concept search](https://en.wikipedia.org/wiki/Concept_search) (concept search doesn't seem to be a scientific term, though).

### Papers

* [A Survey of Automatic Query Expansion in Information Retrieval](http://www-labs.iro.umontreal.ca/~nie/IFT6255/carpineto-Survey-QE.pdf) (2012)

## Sentiment Analysis for Dutch

Goal: (semi-)automatic sentiment analysis for Dutch text.

Start with lexicon based approaches and try to move beyond positive/negative/neutral and work with more complex emotion models. 

Problems:

* We need a good (sufficiently large) Dutch corpus (Corpus Hedendaags Nederlands is unavailable for research)
* We might need annotated data, but it is probably better to try and keep it unsupervised, for example by looking at topic modeling for emotion related terms(?)

### Papers/lexicons

* ["Vreselijk mooi!" (terribly beautiful): A Subjectivity Lexicon for Dutch Adjectives](http://www.clips.ua.ac.be/sites/default/files/desmedt-subjectivity.pdf)
    * Part of Pattern (Python library)
* [NRC emotion lexicon](https://github.com/felipebravom/StaticTwitterSent/tree/master/extra/NRC-Emotion-Lexicon-v0.92) (Piek Vossen made a Dutch translation)
* LIWC (licensed, and Janneke has a license :))
