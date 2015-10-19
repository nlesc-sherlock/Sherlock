#Visualization of timelines

- [technology](#technology)
- [data](#data)
- [some random ideas for things you can work on](#some-random-ideas-for-things-you-can-work-on)
- [work plan](#work-plan-subject-to-change)
- [further reading](#further-reading)

The data on a given storage device can be broken down into many smaller pieces of information. A piece can have zero, one, or multiple timestamps associated with it. For example, in file systems that keep track of a file's modified, accessed, created timestamps, there are already 3 timestamps per file. 

This group will focus on the visualization of such timebound information. The general idea of such a visualization is to provide an interactive interface to the data, making it easier for forensics investigators to see links between items, spot patterns, and get a grasp on the course of events. Such tools are also useful in some of our own work (e.g. [DiLiPaD](https://www.esciencecenter.nl/project/dilipad), [Mining shifting concepts through time](https://www.esciencecenter.nl/project/mining-shifting-concepts-through-time-shico), [BiographyNet](https://www.esciencecenter.nl/project/biographynet), [TwiNL](https://www.esciencecenter.nl/project/twinl), [HADRIANVS](https://www.esciencecenter.nl/project/handrianvs-a-digital-gateway-to-the-dutch-presence-in-rome-through-the-ages)).

The visualization problem breaks down into 3 problems:
   1. the technological side of making the code work
   1. the data collection and preparation side
   1. the visual analytics side: what visualization is best suited to simply represent a given aspect of the data

## technology

The visualization will likely be a timeline with events, with additional synchronized view(s) providing details (and maybe context, relations to other events, etc). It should be easy to interact with the data using zooming and filtering. Perhaps it's also useful (and feasible) to have some history (of the interface), such that a user can retrace (Undo/Redo) his/her steps. We will likely use JavaScript based technologies such as D3.js (visualization), CrossFilter (a JavaScript library for efficient filtering of data), dc.js (combination of D3 and CrossFilter). Perhaps we need a database as well. Preparation of the data will most likely be done with Python.

## data

Examples of interesting data sets include (see [here](https://github.com/NLeSC/Sherlock/blob/master/organization/Datasets.md) for a more complete overview):
- the [Enron data set](http://www.cs.cmu.edu/%7Eenron/enron_mail_20150507.tgz);
- Twitter; I already made a Python script that collects tweets using Python's [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) library ([here](https://github.com/jspaaks/twitgrab/));
- disk images of mobile devices, harddisks (note: we've deciced not to use harddisk off of Marktplaats/eBay as that will quickly land us in a quagmire of ethical dillemas)
- [GovDocs1](http://digitalcorpora.org/corp/files/govdocs1/); it may be easiest to download this to a new partition, make an image out of it, and then let Hansken process it;
- data from the NewsReader project (talk to Maarten or Janneke);
- in principle, any data set that has time annotations is interesting.

## some random ideas for things you can work on

- Graphical querying, using the interface to (implicitly) make selections 
- Timestamps may also be derived from the content of files; e.g a photo may have a person in it before that person had a terrible accident and lost a leg, placing the photo either before or after the time of the accident. Another example may be somebody referring to an event that happened last summer in an email. Note that this poses challenges with regard to visualization of uncertainty. 
- analyze twitterfeeds that are close (in space and time) to a known event such as pop festivals, SAIL, Zwarte Cross, a soccer game, the riots in The Hague after (supposed?) police violence, etc. Could be interesting to combine this with someone who's working the NLP end of things.
- periodic visualization e.g. [here](http://dougmccune.com/blog/2011/04/21/visualizing-cyclical-time-hour-of-day-charts/) and [here](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/timeline%20visualization/2001-weber-et-al-visualizing-time-series-on-spirals.pdf)
- pattern analysis of the enron data set;
   - at what time of day/ day of week do people read email?
   - what are the response times?
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


## further reading

Additional literature (and data) can be found on our [Sherlock OneDrive](https://nlesc.sharepoint.com/sites/sherlock/_layouts/15/GroupsDocuments.aspx#InplviewHashaeee6a96-ce93-4f21-a2d0-3055e41f961d=).

Of particular interest are:
- The paper by [Worring et al. (2012)](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/timeline%20visualization/WorringICM2012.pdf) touches on most of the problems that we will encounter, so please read through that before the sprint.
- I also found a couple of books online about visual analytics (peruse at your leisure):
   - [_Illuminating the path -- the research and development agenda for visual analytics_](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/timeline%20visualization/2005-thomas-visual-analytics-illuminating-the-path.pdf) by Thomas and Cook (2005)
   - [_Solving problems with visual analytics_](https://nlesc.sharepoint.com/sites/sherlock/Shared%20Documents/papers/timeline%20visualization/2010-keim-et-al-visual-analytics-book-lowres.pdf) by Keim et al (2010)
    
And here's a collection of semi-related links (for inspiration)
 - Time Maps: Visualizing Discrete Events Across Many Timescales https://districtdatalabs.silvrback.com/time-maps-visualizing-discrete-events-across-many-timescales
 - visualization of a timeline about genetics research http://wellcomelibrary.org/collections/digital-collections/makers-of-modern-genetics/genetics-timeline
 - simple timeline visualization using timelinesetter (seems to be popular with online newspapers), e.g.
  - http://www.minnpost.com/data/2011/09/timeline-michele-bachmanns-rise
  - http://www.jsonline.com/news/129159038.html
  - http://www.chicagotribune.com/sports/hockey/blackhawks/ct-patrick-kane-timeline-20150923-htmlstory.html
  - http://www.huffingtonpost.com/2011/09/09/ground-zero-world-trade-center-freedom-tower_n_955845.html
  - http://www.nytimes.com/interactive/2011/03/23/movies/20110323-ELIZABETH-TAYLOR-TIMELINE.html?_r=0
 - Simile Widgets list of examples http://www.simile-widgets.org/timeline/examples/index.html, e.g.
  - http://www.simile-widgets.org/timeline/examples/religions/jewish-history.html
 - TimeGlider e.g. http://timeglider.com/widget/
  - http://timeglider.com/timeline/line_cialeak
       http://timeglider.com/timeline/line_idaho
       http://timeglider.com/timeline/line_7fa40ebcc6f03f8fd1e73a61b0b53edf
       http://timeglider.com/timeline/line_5c6601911676ed09bbfb48a89396ff98



Almende Timeline
   list of examples http://almende.github.io/chap-links-library/timeline.html
   e.g. http://almende.github.io/chap-links-library/js/timeline/examples/example24_individual_editable_events.html
        http://almende.github.io/chap-links-library/js/timeline/examples/example28_custom_controls.html
        http://almende.github.io/chap-links-library/js/timeline/examples/example15_mobile.html

CFTL timeline visualization program:
   https://github.com/jensolsson/CFTL



