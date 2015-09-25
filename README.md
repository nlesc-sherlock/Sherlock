# Sherlock

Sherlock is an NLeSC-wide project with the following goals:

  - Team building: get to know your (new) colleagues, their interests, skills, knowledge, etc.
  - Knowledge sharing & development: learn from each other and collectively learn new skills.
  - Boost the parent project: give a project access to the skills and knowledge 30 engineers instead of 2.
  - eStep: producing generic tools, knowledge and research for eStep.

## Sprint dates

All sprints will consists of three consecutive days (Tuesday to Thurday). The dates are:

- 20-22 October        
- 1-3 December         
- 12-14 Januari          
- 16-18 Februari       

## Team Topics

The Sherlock teams will work on the following topics:

*Analyzing large document collections*

While searching a device for incriminating evidence, text documents are commonly encountered.  Analyzing the content of such documents is a challenging task which would require investigators to read through large volumes of text, without any information to guide them through the search. What is this document about? How does it relate to other documents? Are there any trends amongst them? Do I need to read through this pile of documents? Or could I spot a particular document which is more interesting than the rest?

[Read more here](https://github.com/NLeSC/Sherlock/topics/analysing_documents.md)

*Concept search*

One of the core components of Hansken, the data processing pipeline used by the NFI, is Elasticsearch, a full text search engine. To find clues for investigations, detectives query the data stored in Elasticsearch. As a traditional, keyword-based search engine, Elasticsearch suffers from 'the vocabulary problem', i.e., a mismatch between terms used in queries and terms used in documents. Words can have different meanings (synonymy), for example, 'java' (island, coffee or programming language), and different words can have the same or similar meanings (polsemy), for example, 'tv' and 'television'. The goal of this team is to explore solutions to this problem by building a tool that suggests relevant related term to search queries. For example, when someone searches for 'weapon', the tool might suggest terms such as 'knife' or 'gun'. The idea is to implement and compare different strategies based on word co-occurences (so, data-driven). We will start with relative simple techniques for query expansion, such as pseudo-relevance feedback, and subsequently work our way to more advanced approaches, for example using topic modeling, or deep learning.

[Read more here](https://github.com/NLeSC/Sherlock/topics/concept_search.md)

*Deep learning for computer vision*

Convolutional Neural Networks (CNN) are a type of deep learning networks particularly designed for use on two-dimensional data, such as images. In image analysis CNNs have been succesfully used for facial recognition and object classification. It is important that in NLeSc we have knowledge and experience with the latest research in data analytics, where deep learning is currently the trend. In the context of project Sherlock we look at some of the questions asked by the digital forensic investigators, for example: “Can we automatically and quickly find a (red) Ferrari in the images on a suspect’s disk?”, “Can we automatically and quickly find the persons identity, age or gender in the image data?”, etc. Tacking such questions, which are image classification tasks, with deep learning seems very promising.

[Read more here](https://github.com/NLeSC/Sherlock/blob/master/topics/deeplearning/deeplearning4computervision.md)

*Visualization of timelines*

The data on a given storage device can be broken down into many smaller pieces of information. Many of these pieces have timestamps associated with them. For example, files in a file systems usually have creation, modification, and access timestamps. Emails have timestamps, as do log entries, cached HTML pages, exif information in JPG images, etc. Events may have a clear causal relation, such as a thread of emails going back and forth, or a less clear one, such as a link in an email causing a file to be downloaded separately. Timestamps may also be derived from the content of files. For example, document or email texts may explicitly contain dates or contain relative time indicators, such as "yesterday" or "next week". This poses interesting challenges with regard to visualization of uncertainty. This team will focus on the visualization of such timebound information.

[Read more here](https://github.com/NLeSC/Sherlock/topics/timeline_visualization.md)

*Cluster analysis*

Cluster analysis or clustering is the task of grouping a set of objects in such a way that objects in the same group are more similar (in some sense or another) to each other than to those in other groups. It is a main task of exploratory data mining, and a common technique for statistical data analysis and used in many fields.

In digital forensics, clustering may play an important role by 'condensing' the data into several clusters with a similar content, for example, documents on the same topic, images containing the same objects or people, or files with the same creation times. It is not always clear a priori how the data should be clustered, as this may depends on the search queries provided by the investigators. In these cases it is important that the clustering is efficient enough for interactive use, even with large datasets.

The goal of this team will be to create an overview of the different clustering techniques and software used at the NLeSC, and to determine if there are one (or more) 'general' solutions that should be part of eStep. To test these solutions, we will apply them on the various types of data available in Sherlock.

[Read more here](https://github.com/NLeSC/Sherlock/topics/cluster_analysis.md)

*Tool and data integration*

One of the challenges we face at the NLeSC is the large and heterogeneous collection of libraries, tools, and data available to us. Integrating many existing components into a single system is a important topic in many of our projects. Sherlock offers us the perfect setting to improve our skills in this area. How do we combine the solutions developed by the different Sherlock groups ? How do we efficiently access data stored in different formats (possibly in a distributed setting) ? How do we combine this data into a single result ? How do we integrate everything into the existing NFI workflow ? How do we execute this workflow efficiently ? The goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system. 

[Read more here](https://github.com/NLeSC/Sherlock/topics/data_tools_integration.md)




