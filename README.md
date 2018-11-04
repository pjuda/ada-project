# Title

# Abstract
A 150 word description of the project idea, goals, dataset used. What story you would like to tell and why? What's the motivation behind your project?

Amazon was founded in 1994 and started to sell books. It then diversified to sell all kind of items as we know it today.
Since its foundation, Amazon has collected millions of reviews for each article available on their website.
The aim of this project will be first to study the kind of products sold per Amazon and see the evolution on a time window of 20 years.
Then, as items are rated by consummers, it will be great to analyze reviews and determine if they are raliable or if they are fake.



# Research questions
A list of research questions you would like to address during the project. 

How has Amazon expanded during the past two decades from books online retailer to the most powerful web seller?

What role played the reviews in the evolution of Amazon?

Is there any relationship between the number of reviews, the ratings and the growth of Amazon?

Can we find a way to distinguish between fake and reliable reviews?

# Dataset
List the dataset(s) you want to use, and some ideas on how do you expect to get, manage, process and enrich it/them. Show us you've read the docs and some examples, and you've a clear idea on what to expect. Discuss data size and format if relevant.


The dataset contains reviews from 1994 to 2014 [here](http://jmcauley.ucsd.edu/data/amazon/).

The full set of reviews is a loose json file.
There are also sets with filtered duplicates
(e.g. for the same products but on different media like DVD/VHS)
and csv file with ratings only.

For the preliminary analysis and methodology testing we will use subsets of the full dataset,
which are available on the website and have a more reasonable size.

The review time is easily extracted from the data.

There are overall ratings and also helpfullness score of the data.



# A list of internal milestones up until project milestone 2

* Check time evolution of reviews on a subset dataset: identify product groups that emerged
* Scale-up to get more insight in the data and formulate more specific questions
* Develop a methodology using a subset of the data
* Apply the methodology to the full dataset




# Questions for TAa
Add here some questions you have for us, in general or project-specific.


