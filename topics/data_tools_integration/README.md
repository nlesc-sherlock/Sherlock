Tools and Data Integration (TDI)
================

One of the challenges we face at the NLeSC is the large and heterogeneous collection of libraries, tools, and data available to us. Integrating many existing components into a single system is a important topic in many of our projects. Sherlock offers us the perfect setting to improve our skills in this area. How do we combine the solutions developed by the different Sherlock groups? How do we efficiently access data stored in different formats (possibly in a distributed setting)? How do we combine this data into a single result? How do we integrate everything into the existing NFI workflow? How do we execute this workflow efficiently?

The goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system. At the same time, we will do performance profiling and decide if replacing current MapReduce jobs by Spark jobs improves performance. 

First Step
----------

The major goal of this group is to integrate the tools used and created by the other teams into the Hadoop based system used by the NFI. Hence, we will need a Hadoop cluster. The one selected for this project is the [Hadoop cluster](https://userinfo.surfsara.nl/systems/hadoop/description) from SurfSara which provides the following [components](https://userinfo.surfsara.nl/systems/hadoop/software). For that we need to [setup an account at DAS](https://userinfo.surfsara.nl/systems/hadoop/obtaining-account).


Second Step
-----------

Once you have an account, it is time to get your Linux/Mac machine ready to [access the cluster and submit jobs](https://userinfo.surfsara.nl/systems/hadoop/usage). Note, if you only have an windows machine we advise you to install a virtual machine with linux (Ubuntu is recommended).


Third Step
----------

One of the goals is to integrate the tools used and created by the other teams into the Hadoop based system used by the NFI. For that we will explore a solution which allows us to to run third party tools as User Defined Functions we will use/explore SCAPE Tool-to-MapReduce Wrapper (ToMaR). It is developed at the university of Vienna and we met one of the authors at IEEE eScience Conference poster session. For more info you should read the [project description](https://github.com/openpreserve/ToMaR#about), but also the [installation and use](https://github.com/openpreserve/ToMaR#installation-and-use) section to know the pre-requisites before using it.


Fourth Step
-----------

Another goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system. For this task we will look at portable service frameworks (such as [Apache Thrift](http://thrift.apache.org/)), interchange formats (such as [Protocol Buffers](https://developers.google.com/protocol-buffers/?hl=en)), messaging systems (such as [ZeroMQ](http://zeromq.org/)) applications containers (such as [Docker](https://www.docker.com/whatisdocker), few [NLeSC examples](https://hub.docker.com/u/nlesc/)), etc. 


Fifth Step
----------

The Hadoop based system used by the NFI, Hansken processing pipeline, is based on map-reduce and requires several iterations (typically 3 or 4) to fully analyze a set of files, such as a disk image. An initial performance profile done by Jason indicates there are few aspects for be improved: 
* startup time per iteration is high
* load balancing issue related with skewness on tasks execution
* lost of data locality between tasks
* several reads of the same files

Hence, we have decided to explore a different model, [Spark](http://spark.apache.org/) and investigate how Yarn capacity scheduler works. 

* Spark: the [Spark documentation](http://spark.apache.org/documentation.html) contains nice screen cast tutorial videos for your [first steps with Spark](http://spark.apache.org/screencasts/1-first-steps-with-spark.html) or how to setup a [stand alone job in Scala](http://spark.apache.org/screencasts/4-a-standalone-job-in-spark.html), but also [examples](http://spark.apache.org/examples.html). There are third party globs which my also help you in [creating a simple spark job](https://hadoopi.wordpress.com/2014/09/05/spark-create-a-simple-spark-job/) or determine [correlation on two vectors](http://blog.sequenceiq.com/blog/2014/09/29/spark-correlation-and-testing/) or [K-Means](http://blog.sequenceiq.com/blog/2014/07/31/spark-mllib/). Note that Spark is one of [SurfSara components](https://userinfo.surfsara.nl/systems/hadoop/software/spark).

* Yarn capacity scheduler: The [Capacity Scheduler](https://hadoop.apache.org/docs/r2.4.1/hadoop-yarn/hadoop-yarn-site/CapacityScheduler.html) is designed to run Hadoop applications as a shared, multi-tenant cluster in an operator-friendly manner while maximizing the throughput and the utilization of the cluster. Through different queue setups we should be able to understand how [Yarn capacity scheduler](http://blog.sequenceiq.com/blog/2014/03/14/yarn-capacity-scheduler/) works.
 
