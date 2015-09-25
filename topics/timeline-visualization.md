#Visualization of timelines

The data on a given storage device can be broken down into many smaller pieces of information. A piece can have zero, one, or multiple timestamps associated with it. For example, in file systems that keep track of a file's modified, accessed, created timestamps, there are already 3 timestamps per file. 

This group will focus on the visualization of such timebound information. The general idea of such a visualization is to provide an interactive interface to the data, making it easier for forensics investigators to see links between items, spot patterns, and get a grasp on the course of events. Such tools will likely also be useful in some of our own work (for example, in our Newsreader project). 

Regarding the technological side of things, we will likely use JavaScript based technologies such as D3.js (visualization), CrossFilter (a JavaScript library for efficient filtering of data), dc.js (combination of D3 and CrossFilter). 

Examples of interesting data sets include (see [here](https://github.com/NLeSC/Sherlock/blob/master/Datasets.md) for a more complete overview):
- the Enron data set;
- Twitter
- disk images of mobile devices, harddisks (note: we've deciced not to use harddisk off of Marktplaats/eBay as that will quickly land us in a quagmire of ethical dillemas)
- in principle, any data set that has time annotations is interesting

Possible things you can work on:
- Graphical querying, using the interface to (implicitly) make selections 
- Timestamps may also be derived from the content of files; e.g a photo may have a person in it before that person had a terrible accident and lost a leg, placing the photo either before or after the time of the accident. Another example may be somebody referring to an event that happened last summer in an email. Note that this poses challenges with regard to visualization of uncertainty. 
- analyze twitterfeeds that are close (in space and time) to a known event such as pop festivals, SAIL, Zwarte Cross, a soccer game, the riots in The Hague after (supposed?) police violence, etc. Could be interesting to combine this with someone who's working the NLP end of things.
- I'm sure there are many other things we can come up with...let's have a brainstorm as one of the first things we do.
