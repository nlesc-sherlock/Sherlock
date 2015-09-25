Tools and Data Integration (TDI)
================

One of the challenges we face at the NLeSC is the large and heterogeneous collection of libraries, tools, and data available to us. Integrating many existing components into a single system is a important topic in many of our projects. Sherlock offers us the perfect setting to improve our skills in this area. How do we combine the solutions developed by the different Sherlock groups ? How do we efficiently access data stored in different formats (possibly in a distributed setting) ? How do we combine this data into a single result ? How do we integrate everything into the existing NFI workflow ? How do we execute this workflow efficiently ?

The goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system. 

First Step
----------

The major goal of this group is to integrate the tools used and created by the other teams into the Hadoop based system used by the NFI. Hence, we will need a Hadoop cluster. The one selected for this project is the [Hadoop cluster](https://userinfo.surfsara.nl/systems/hadoop/description) from SurfSara which provides the following (components)[https://userinfo.surfsara.nl/systems/hadoop/software]. For that we need to (setup an account at DAS)[https://userinfo.surfsara.nl/systems/hadoop/obtaining-account].


Second Step
-----------

Once you have an account, it is time to get your Linux/Mac machine ready to (access the cluster and submit jobs)[https://userinfo.surfsara.nl/systems/hadoop/usage]. Note, if you only have an windows machine we advise you to install a virtual machine with linux (Ubuntu is recommended).


Third Step
----------

The goal of this team is to develop knowledge and techniques on assembling heterogeneous components into a large and effective system. For that we will explore a solution which allows us to to run third party tools as User Defined Functions we will use/explore SCAPE Tool-to-MapReduce Wrapper (ToMaR). It is developed at the university of Vienna and we met one of the authors at IEEE eScience Conference poster session. For more info you should read the [project description](https://github.com/openpreserve/ToMaR#about), but also the [installation and use](https://github.com/openpreserve/ToMaR#installation-and-use) section to know the pre-requisites before using it.
