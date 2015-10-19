# Concept Search for Exploratory Data Analysis

One of the core components of Hansken, the data processing pipeline used by the
NFI, is Elasticsearch, a full text search engine. To find clues for
investigations, detectives query the data stored in Elasticsearch. As a
traditional, keyword-based search engine, Elasticsearch suffers from 'the
vocabulary problem', i.e., a mismatch between terms used in queries and terms
used in documents. For example, words can have different meanings, e.g., 'java'
(synonymy), and different words can have the same or similar meanings, e.g.,
'tv' and 'television' (polsemy). The goal of this sub-project is to build and
evaluate a tool that suggests relevant related terms to search queries. For
example, when someone searches for 'weapon', the tool might suggest terms such
as 'knife' or 'gun'. Because data processed by the NFI typically is very
different from standard web data, and, there is no gold standard
available to evalute such a system, this is a challenging task.

The overall goal of the tool is to make the task of searching for evidence
easier and faster. However, this is not something that can be measured directly.
We will therefore use a different approach, in particular, one that is based on
common agreement between algorithms. So, the idea is to implement different
algorithms for query expansion, and to somehow merge the results
to come to the final suggestions. In this context, terms suggested by all or a
majority of algorithms can be considered a gold standard for new algorithms.
However, because we are using search to explore data (instead of looking for a
single best document or a set of relevant documents), outliers (terms suggested
by a small subset of algorithms) might also be of interest. Presenting the
results to the user in a meaningful way is another challenge that is part of
this subproject. A possibility would be to visualize suggestions in a word
co-occurence network.

![example visualization of word co-occurnce network](https://github.com/NLeSC/Sherlock/blob/master/topics/concept_search/images/word_co-occurrence_network.jpg)

(Picture taken from https://www.pnas.org/content/112/35/10837.full)

More information on the techniques we will use can be found on the Wikipedia
page on [Concept search](https://en.wikipedia.org/wiki/Concept_search).

## Algorithms for Automatic Query Expansion

The commonality between the algorithms we will implement is that they are
based on word co-occurences (so, data-driven), for example:

* Pseudo-relevance feedback
* Topic modeling
* Deep learning
* Probabilistic approaches
* Association rules
* Local context analysis
* Query language modeling (mixture model and relevance model)
* [Elasticsearch significant terms aggregation](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-significantterms-aggregation.html)
* [Parsimonious Language Modeling](https://github.com/larsmans/weighwords)
* ...

## Software

* [Elasticsearch](https://www.elastic.co/products/elasticsearch)
* [Elasticsearch for Hadoop](https://www.elastic.co/products/hadoop)
* [scikit-learn](http://scikit-learn.org/stable/)
* [word2vec](https://code.google.com/p/word2vec/)
* ...

## Papers/literature

* Carpineto, C. and Romano, G. (2012). [A Survey of Automatic Query Expansion
in Information Retrieval](http://www-labs.iro.umontreal.ca/~nie/IFT6255/carpineto-Survey-QE.pdf). _ACM Comput. Surv._ 44, 1
* Manning, C., Raghavan, P., and Schutze, H. (2008).
[Chapter 9: Relevance feedback and query expansion](http://nlp.stanford.edu/IR-book/pdf/09expand.pdf).
In _Introduction to Information Retrieval_. Cambridge: Cambridge University Press.
* Query Expansion Using Topic Modeling
* Deep learning
* Mehta, V.; Caceres, R.S.; Carter, K.M., Evaluating topic quality using model clustering, in _2014 IEEE Symposium on Computational Intelligence and Data Mining (CIDM)_, pp.178-185, 2014
* Hiemstra, D., Robertson, S., and Zaragoza, H. [Parsimonious language models for
information retrieval](http://eprints.eemcs.utwente.nl/7256/01/p178-hiemstra.pdf).
In _Proceedings of the 27th annual international ACM SIGIR conference on Research
and development in information retrieval_. ACM, 2004.

## Data

* [Enron email dataset](https://en.wikipedia.org/wiki/Enron_Corpus)
* [Govdocs 1](http://digitalcorpora.org/corpora/govdocs)

## Subtasks

* Make list of test queries (single term vs multiple terms/phrase queries)
* Implement query expansion algorithms
* Merge/cluster results from query expansion algorithms
* Visualize merged query expansion results
* Build simple user interface/demo
