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

Link to parquet files (approx. 2 GB) [Parquets](https://drive.google.com/open?id=1CkC4OMzkUiwjt7un_K6jhMlBVD1L4t5o)

Data filtering and storage into parquet files is done in the notebook `reviews-cleaning.ipynb`.
__TODO__ *this part will be merged to the main notebook.*

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

## More detailed planning

29-30 November
- Continue the **temporal analysis** by category. (Przemek)
- Prepare the review datasets with pyspark (create parquets). (Przemek)
- Find bad reviews (very low usefulness) and do **statistical analysis**. (Przemek)
- Define the concept of reviews and how it works (for the report)
- Distinguish between helpful reviews and less helpful ones.

1-10 December (Gianni and Lucas)
- Finalize the project: 
- Analyse of bad reviews? Machine learning to predict a bad review?
- ...

13-14 December
- write up the report or data story (we'll probably go for the report) (Przemek, Gianni)

16 December
- final deadline

# Notes

To read the parquet files with read_parquet function of pandas librairy you need to install "fastparquet". The parquet files can also be read by pyspark.

Don't forget about importing pyspark before using it:

```
from pyspark.sql import SparkSession, SQLContext
from pyspark.sql.types import StructType, StructField, IntegerType, StringType, DateType

spark = SparkSession.builder.getOrCreate()
sc = spark.sparkContext
sql_context = SQLContext(sc)
```

If kernel dies repetadly, using del(df) might help, for instance in this way (not tested):

```
def count_reviews_with_del(parquet_file):
    """
    Counts reviews from specified file
    """
    df = pd.read_parquet(PARQUET_DIR + parquet_file)
    length = df.shape[0]
    del(df)
    return length
```