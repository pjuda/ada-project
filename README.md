# **How Amazon reviews reflect its expansion?**


# Abstract

Amazon was founded in 1994 and started to sell books. It then diversified to sell all kind of items as we know it today.
Since its foundation, Amazon has collected millions of reviews for each article available on their website. These reviews are collected daily from the user's themselves.

Reviews are collected daily from people using Amazon's services. They played an important role in the development of Amazon. Why so? Because they are the keys in the purchasing process. Indeed, one ofen feel more comfortable and safe when acting as the others, aren't you.

The aim of this project will be first to study the kind of products sold per Amazon and see the evolution on a time window of 20 years.
Then, as items are rated by consummers, it will be great to analyze reviews and determine if they are raliable or if they are fake and how they can influence someone's decision to buy an article.



# Research questions

How has Amazon expanded during the past two decades from books online retailer to the most powerful web seller?

Secondly, can we find a way to distinguish between fake and reliable reviews? How reviews influence people decision to buy an article or not?


# Dataset

## Data handling
The dataset contains reviews from 1994 to 2014 [here](http://jmcauley.ucsd.edu/data/amazon/). As the original dataset is significant (33Gb), *Spark* was used to handle and filter the data as a first process step.

The different files were then gather to collect relevant information. The features of interest were stored in *parquet format*. The latter can be handled by *Spark* but also with *Pandas* which could be more convenient to work with at some point.

```
Link to parquet files: [GoogleDrive](https://drive.google.com/open?id=1BkH7vfupcBaLs2gTYphff6z9Qvg-TcAq). Download them all.
```


## Data description
It appears that the Amazon review dataset consists of set of CSV files containing information about the product itself but also all reviews link to that product.
A non-exhastiv list of data's caracteristics:

- Product's ID
- Product's category
- Review's date
- Customer's ID

Note that There are also sets with filtered duplicates (e.g. for the same products but on different media like DVD/VHS) and csv file with ratings only.

Preliminary test were performed to determine data's statistic repartition (e.g. item's repartition per category).
We will then used a subset of the original dataset and focus on a particular category to determine review's reliability and answer our second question: try to infere how a review can positively or negatively influence someone's perception.




# A list of internal milestones up until project milestone 3

* ...
* ...




# Questions for TAs
...


