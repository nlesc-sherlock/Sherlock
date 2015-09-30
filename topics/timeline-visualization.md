#Visualization of timelines

- [technology](#technology)

The data on a given storage device can be broken down into many smaller pieces of information. A piece can have zero, one, or multiple timestamps associated with it. For example, in file systems that keep track of a file's modified, accessed, created timestamps, there are already 3 timestamps per file. 

This group will focus on the visualization of such timebound information. The general idea of such a visualization is to provide an interactive interface to the data, making it easier for forensics investigators to see links between items, spot patterns, and get a grasp on the course of events. Such tools are also useful in some of our own work (e.g. [DiLiPaD](https://www.esciencecenter.nl/project/dilipad), [Mining shifting concepts through time](https://www.esciencecenter.nl/project/mining-shifting-concepts-through-time-shico), [BiographyNet](https://www.esciencecenter.nl/project/biographynet), [TwiNL](https://www.esciencecenter.nl/project/twinl), [HADRIANVS](https://www.esciencecenter.nl/project/handrianvs-a-digital-gateway-to-the-dutch-presence-in-rome-through-the-ages)).

The visualization problem breaks down into 3 problems:
   1. the technological side of making the code work
   1. the data collection and preparation side
   1. the visual analytics side: what visualization is best suited to simply represent a given aspect of the data

## technology

The visualization will likely be a timeline with events, with additional synchronized view(s) providing details (and maybe context, relations to other events, etc). It should be easy to interact with the data using zooming and filtering. Perhaps it's also useful (and feasible) to have some history (of the interface), such that a user can retrace (Undo/Redo) his/her steps. We will likely use JavaScript based technologies such as D3.js (visualization), CrossFilter (a JavaScript library for efficient filtering of data), dc.js (combination of D3 and CrossFilter). Perhaps we need a database as well.

## data

Examples of interesting data sets include (see [here](https://github.com/NLeSC/Sherlock/blob/master/Datasets.md) for a more complete overview):
- the Enron data set;
- Twitter; I already made a Python script that collects tweets [here](https://github.com/jspaaks/twitgrab/) using Python's [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) library.
- disk images of mobile devices, harddisks (note: we've deciced not to use harddisk off of Marktplaats/eBay as that will quickly land us in a quagmire of ethical dillemas)
- in principle, any data set that has time annotations is interesting

## some random ideas for things you can work on

- Graphical querying, using the interface to (implicitly) make selections 
- Timestamps may also be derived from the content of files; e.g a photo may have a person in it before that person had a terrible accident and lost a leg, placing the photo either before or after the time of the accident. Another example may be somebody referring to an event that happened last summer in an email. Note that this poses challenges with regard to visualization of uncertainty. 
- analyze twitterfeeds that are close (in space and time) to a known event such as pop festivals, SAIL, Zwarte Cross, a soccer game, the riots in The Hague after (supposed?) police violence, etc. Could be interesting to combine this with someone who's working the NLP end of things.
- etc.

## work plan (subject to change)

So here's how I envision us starting work on this. 

1. First, we should have a brainstorm to make an inventory of the data sets that we will be working with, and we should discuss what JavaScript libraries are likely best suited for visualizing them what problems we may have. 
1. Second, we should divide over two subteams.
   1. The first team focuses on collecting and preparing (other) data sets
   1. The second team focuses on the technological part. Their immediate goal is to set up the **simplest possible** timeline visualization they can (perhaps just showing events on a timeline; we can expand later on).
   1. Obviously, there needs to be interation between the 2 subteams to make sure that the datasets we chose can be visualized, the data are prepared in the right format, etc.
1. After we manage to get some data visualized, we should reconvene and discuss how to proceed
  - how will we expand the visualization
  - what other aspects of the data do we want to highlight
  - etc

I also want to take the time to disseminate our collective findings within our group. For example if you've been working on preparing data and you're interested in how to set up the visualization, there should be time for this (perhaps in the form of paired programming --we can discuss what's the best way for a given person/task).

I think this is probably enough to fill up the first sprint.



