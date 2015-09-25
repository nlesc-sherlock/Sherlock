# Concept search

One of the core components of Hansken, the data processing pipeline used by the NFI, is Elasticsearch, a 
full text search engine. To find clues for investigations, detectives query the data stored in 
Elasticsearch. As a traditional, keyword-based search engine, Elasticsearch suffers from 'the vocabulary 
problem', i.e., a mismatch between terms used in queries and terms used in documents. For example, words can 
have different meanings, e.g., 'java' (synonymy), and different words can have the same or similar meanings, 
e.g., 'tv' and 'television' (polsemy). The goal of this sub-project is to explore solutions to this problem by 
building a tool that suggests relevant related term to search queries. For example, when someone searches for 
'weapon', the tool might suggest terms such as 'knife' or 'gun'. The idea is to implement and compare different 
strategies based on word co-occurences (so, data-driven). We will start with relative simple techniques for 
query expansion, such as pseudo-relevance feedback, and subsequently work our way to more advanced approaches, 
for example using topic modeling, or deep learning. 

See also
https://en.wikipedia.org/wiki/Concept_search
http://www-labs.iro.umontreal.ca/~nie/IFT6255/carpineto-Survey-QE.pdf
https://www.elastic.co/products/elasticsearch
https://www.elastic.co/products/hadoop
