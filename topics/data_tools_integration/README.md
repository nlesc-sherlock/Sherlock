Tools and Data Integration (TDI)
================

One of the challenges we face at the NLeSC is the large and heterogeneous collection of libraries, tools, and data available to us. Integrating many existing components into a single system is a important topic in many of our projects. Sherlock offers us the perfect setting to improve our skills in this area. How do we combine the solutions developed by the different Sherlock groups? How do we efficiently access data stored in different formats (possibly in a distributed setting)? How do we combine this data into a single result? How do we integrate everything into the existing NFI workflow? How do we execute this workflow efficiently?

The major goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system ([Target 1](#target-1) and [Target 2](#target-2)). If things go as planned, we will also do performance profiling and decide if replacing current MapReduce jobs by Spark jobs improves Hansken's performance ([Target 3](#target-3)). 

Any documentation which cannot be made public available on github it will be placed at the [Sherlock one drive's tool and data integration directory](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/tool%20and%20data%20integration).

Setup
-----

The major goal of this group is to integrate the tools used and created by the other teams into the Hadoop based system used by the NFI. Hence, we will need a Hadoop cluster. The one selected for this project is the [DAS-4 Hadoop Cluster](http://www.cs.vu.nl/das4/hadoop.shtml). If needed, [DAS-4 user accounts](http://www.cs.vu.nl/das4/accounts.shtml) for the team members will requested before the sprint. The cluster is small, but it offers the perfect environment for our project since it is easy to request access and it is not an overloaded cluster. For large scale experiments and to run our final outcome we will use the [Hadoop cluster](https://userinfo.surfsara.nl/systems/hadoop/description) from SurfSara which provides the following [components](https://userinfo.surfsara.nl/systems/hadoop/software). For that we need to [setup an account with SURFsara](https://userinfo.surfsara.nl/systems/hadoop/obtaining-account).

Here are the steps to get you up and running:
* DAS-4 Hadoop cluster: before you submit a job read the [DAS-4 Usage Policy](http://www.cs.vu.nl/das4/usage.shtml) and [Job Execution](http://www.cs.vu.nl/das4/jobs.shtml) to learn how to submit a job. More info is under [setup directory](https://github.com/NLeSC/Sherlock/blob/master/topics/data_tools_integration/setup). 
* SURFsara Hadoop cluster: once you have an account, get your Linux/Mac machine ready to [access the cluster and submit jobs](https://userinfo.surfsara.nl/systems/hadoop/usage). Note, if you only have an windows machine we advise you to install a virtual machine with linux (Ubuntu is recommended).


Target 1
--------

One of the goals is to integrate the tools used and created by the other teams into the Hadoop based system used by the NFI. For that we will explore solutions which allow us to to run third party tools as User Defined Functions. 

One example is the SCAPE Tool-to-MapReduce Wrapper (ToMaR), developed at the university of Vienna. For more info you should read the [project description](https://github.com/openpreserve/ToMaR#about), but also the [installation and use](https://github.com/openpreserve/ToMaR#installation-and-use) section to know the pre-requisites before using it. There are few examples where ToMaR is used, for example: [How to let your preservation tools scale](http://openpreservation.org/blog/2014/03/14/tomar-how-let-your-preservation-tools-scale/) and [Web Archive FITS Characterization using ToMaR](http://openpreservation.org/blog/2013/12/16/web-archive-fits-characterisation-using-tomar/). There is also a paper from 2015 [Constructing Scalable Data-Flows on Hadoop with Legacy Components](https://www.researchgate.net/publication/280044065_Constructing_Scalable_Data-Flows_on_Hadoop_with_Legacy_Components).

Another example to consider is [Arvados](https://dev.arvados.org/projects/arvados/wiki/Introduction_to_Arvados). *"Arvados is a platform for storing, organizing, processing, and sharing genomic and other big data. The platform is designed to make it easier for data scientists to develop analyses, developers to create genomic web applications and IT administers to manage large-scale compute and storage genomic resources. The platform is designed to run in the cloud or on your own hardware"*. Its [user documentation](http://doc.arvados.org/user/) is pretty well organized.

Suggestions for other integration tools are welcome!

Target 2
--------

Another goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a single effective system. For this task we will look at portable service frameworks (such as [Apache Thrift](http://thrift.apache.org/)), interchange formats (such as [Protocol Buffers](https://developers.google.com/protocol-buffers/?hl=en)), messaging systems (such as [ZeroMQ](http://zeromq.org/)) applications containers (such as [Docker](https://www.docker.com/whatisdocker), few [NLeSC examples](https://hub.docker.com/u/nlesc/) and [docker tooling](https://github.com/NLeSC/Sherlock/blob/master/topics/data_tools_integration/target_2/docker-tooling.md)), etc. For each of them you can find more information in [target 2/README.md](https://github.com/NLeSC/Sherlock/blob/master/topics/data_tools_integration/target_2/README.md). 


Target 3
--------

The Hadoop based system used by the NFI, in Hansken processing pipeline (see [Figure 2](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/digital%20forensics/DigitalInvestigation-Hansken.pdf#page=11)), is based on map-reduce and requires several iterations (typically 3 or 4) to fully analyze a set of files, such as a disk image. An initial performance profile done by Jason indicates there are few aspects for be improved: 
* startup time per iteration is high
* load balancing issue related with skewness on tasks execution
* lost of data locality between tasks
* several reads of the same files

Hence, we have decided to explore a different model, [Spark](http://spark.apache.org/) and investigate how Yarn capacity scheduler works. 

* Spark: the [Spark documentation](http://spark.apache.org/documentation.html) contains nice screen cast tutorial videos for your [first steps with Spark](http://spark.apache.org/screencasts/1-first-steps-with-spark.html) or how to setup a [stand alone job in Scala](http://spark.apache.org/screencasts/4-a-standalone-job-in-spark.html), but also [examples](http://spark.apache.org/examples.html). There are third party globs which my also help you in [creating a simple spark job](https://hadoopi.wordpress.com/2014/09/05/spark-create-a-simple-spark-job/) or determine [correlation on two vectors](http://blog.sequenceiq.com/blog/2014/09/29/spark-correlation-and-testing/) or [K-Means](http://blog.sequenceiq.com/blog/2014/07/31/spark-mllib/). Note that Spark is one of [SurfSara components](https://userinfo.surfsara.nl/systems/hadoop/software/spark).

* Yarn capacity scheduler: The [Capacity Scheduler](https://hadoop.apache.org/docs/r2.4.1/hadoop-yarn/hadoop-yarn-site/CapacityScheduler.html) is designed to run Hadoop applications as a shared, multi-tenant cluster in an operator-friendly manner while maximizing the throughput and the utilization of the cluster. Through different queue setups we should be able to understand how [Yarn capacity scheduler](http://blog.sequenceiq.com/blog/2014/03/14/yarn-capacity-scheduler/) works.
 
