Cluster Analysis
================

Cluster analysis or clustering is the task of grouping a set of objects in such a way that objects in the same group are more similar (in some sense or another) to each other than to those in other 
groups. It is a main task of exploratory data mining, and a common technique for statistical data analysis and used in many fields.

In digital forensics, clustering may play an important role by 'condensing' the data into several clusters with a similar content, for example, documents on the same topic, images containing the 
same objects or people, or files with the same creation times. It is not always clear a priori how the data should be clustered, as this may depends on the search queries provided by the 
investigators. In these cases it is important that the clustering is efficient enough for interactive use, even with large data sets.

The goal of this team will be to create an overview of the different clustering techniques and software used at the NLeSC, and to determine if there are one (or more) 'general' solutions that 
should be part of eStep. To test these solutions, we will apply them on the various types of data available in Sherlock.

Goals
-----

As part of project Sherlock, we have several applications for cluster analysis in mind. However, the goal is to arrive at generic solutions from which multiple projects within the NLeSC may benefit.

One of the first goals is to create an overview of the myriad of clustering problems, algorithms, applications, libraries, and tools:
* What clustering problems are we faced with in NLeSC projects?
* Can we come up with a subset of tools that cover most of our needs?
* Are there any high-level and easy to use clustering frameworks? 
* What tools are available for visualizing clusters?
* How is information on clusters within data sets typically stored?

Once we have this overview, we can apply that knowledge in any way we want. This is basically the starting point from where we as a team decide on what direction to take.

Possible directions are: 
* If we were able to find suitable tools for analyzing and/or visualizing clusters, we can figure out what is required to use them in NLeSC projects
* Building a high-level and easy to use tool for cluster analysis on top of existing libraries, in case no such tools exists
* Apply our new-found understanding of the field of cluster analysis to any of the applications listed below.


Applications in Digital Forensics
---------------------------------

1. Common Image Source Identification is one of the example applications that have for project Sherlock. It uses PRNU (Photo-Response Non-Uniformity) patterns in images to identify images
created by the same image sensor or camera. After the extraction of the PRNU patterns they can be compared and clustered based on how similar they are.

2. Clustering information derived by Hansken. The Hansken tool generates a huge amount of traces, which are inserted into Elastic Search to be queried by forensic investigators. However, making 
sense of and finding relevant information in the huge amount of data that is produced by Hansken is very difficult. If we can find ways to cluster the data, based on whatever metrics, it can
be extremely helpful for making sense of all the data and improving search results.

