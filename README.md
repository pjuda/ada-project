# **Amazon: 20 years of reviews**


# Abstract

Amazon was founded in 1994 and started to sell books. It then diversified to sell all kind of items as we know it today.
Since its foundation, Amazon has collected millions of reviews for each article available on their website.

These reviews are collected daily from people using Amazon's services. They played an important role in the development of Amazon. Why so? Because they are the keys in the purchasing process. Indeed, one often feel more comfortable and safe when acting as the others, aren't you.

The aim of this project will be first to study the kind of products sold per Amazon and see the evolution on a time window of 20 years.
Then, as items are rated by consummers, it will be great to analyze reviews and determine if they are reliable or if they are fake and how they can influence someone's decision to buy an article.



# Research questions

- How has Amazon expanded during the past two decades from books online retailer to the most powerful web seller?

- Secondly, can we find a way to distinguish between fake and reliable reviews? How reviews influence people decision to buy an article or not?


# Dataset

## Data handling
The dataset contains reviews from 1994 to 2014. A description is provided [here](http://jmcauley.ucsd.edu/data/amazon/), but the raw data we obtained were in tsv format: tab-delimited csv file. As the original dataset is significant (33Gb), *Spark* was used to handle and filter the data as a first process step.

The different files were then gather to collect relevant information. The features of interest were stored in *parquet format*. The latter can be handled by *Spark* but also with *Pandas* which could be more convenient to work with at some point.

Link to parquet files (approx. 3.5 GB) [Parquets](https://drive.google.com/open?id=1BkH7vfupcBaLs2gTYphff6z9Qvg-TcAq)

Data filtering and storage into parquet files is done in the notebook `reviews-cleaning.ipynb`.

## Data description
It appears that the Amazon review dataset consists of set of tsv files (tab-delimited csv files) containing information about the product itself but also all reviews link to that product.
A non-exhaustiv list of data's caracteristics:

- Product's ID
- Product's category
- Review's date
- Customer's ID

Preliminary test were performed to determine data's statistic repartition (e.g. item's repartition per category, reviews' number across time) and data's content to ensure that the provided dataset can answer our research questions.
We will then used more specifically a subset of the original dataset and focus on particular categories to determine review's reliability.

Data exploration and feasability tests were performed in the notebook `amazon-reviews.ipynb`.

# A list of internal milestones up until project milestone 3

- Characterize Amazon's expansion from 1994 to 2014.
- Estimate reviews' reliabilities based on the ratings' pertinence and on the reviewers who wrote them.
