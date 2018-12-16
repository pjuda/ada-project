# **Amazon: 20 years of reviews**


# Abstract

The project focuses on the Amazon's dataset and aims to infer whether reviews that make Amazon's success are reliable or not. 
To do so,  several machine learning methods were implemented as well as text mining techniques to determine underlying features that make a review bad or good. 
The final model trained using *K-means* and *DBSCAN* on methodically chosen features performed well at discriminating reviews qualitatively different from the average opinion.


# Dataset

## Data collection
The dataset is provided by Amazon [here](https://s3.amazonaws.com/amazon-reviews-pds/readme.htm). It contains about 130 millions reviews collected from 1994 to 2014. 

The original set contains a collection of US reviews and also a smaller collection of multilingual reviews.

In our project we dealt only with the set of the US reviews,
which is composed of reviews grouped by 43 categories, such as: Books, Wireless, PC, Toys, Shoes, Luggage, etc.

Each category contains a collection of reviews records and each record is composed of metadata (the id of review author, the product id, number of positive and total votes about the review from other customers) and the review itself (including the headline and star rating of the product on a scale from 1 to 5).

## Data description
The raw data were originally in *tsv* format: tab separated value, a text format.

Given the size of the dataset (over 30 GB), we performed the initial filtering of the data
using *spark* and extracted the features of interest, such as  *review id*, *product category* and *helpful votes*.

We left out the review texts, not required for 
extracting the statistics about the temporal evolution of the reviews by category. 
It enabled us to use *pandas* to do this basic analysis, 
as we reduced the dataset to around 2 GB.

Finally *parquet* format was used to store the reduced dataset.

Link to parquet files:
```
Features of interest
https://drive.google.com/open?id=1CkC4OMzkUiwjt7un_K6jhMlBVD1L4t5o

Language analysis
https://drive.google.com/open?id=1yzH01tOqDSTRQm_s1Ex0ATbeybDkzbUK

```

# Contributions
```
Przemyslaw: Data filtering. Parquet file creation. Temporal evolution and statistical analysis.
Lucas: Model building and final classifier. Algorithm implementations.
Gianni: Temporal analysis. Reviews' sentiment analysis. Plotting graphs. Report writing.

All of us will work on the poster conception.

```






