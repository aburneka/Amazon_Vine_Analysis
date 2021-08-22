# Amazon_Vine_Analysis

# Overview 

A large dataset of Amazon reiews was used to determine if the paid Vine Review program generates more favorable product reviews than non-Vine memebers.

* DataSet used: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz 
* Sotware: Pyspark 3.0.0, AWS RDS, PGAdmin

## Process:
* Extract data from Amazon Dataset into GoogleCollab using Pyspark
* Transform Data create a new dataframe vine_df to pull out all vine information and applying filters to create new dataframes
* Load data into PGAdmin for easy extraction as csv file



![sql_query](https://user-images.githubusercontent.com/79999761/130370432-2060592d-a108-4448-9c08-9ea5f5986c01.png)

# Results 

<img width="367" alt="Screen Shot 2021-08-22 at 2 12 27 PM" src="https://user-images.githubusercontent.com/79999761/130370462-1ec87f3e-b077-45bb-bac3-d7a9ce35c4f3.png">

<img width="413" alt="Screen Shot 2021-08-22 at 2 12 34 PM" src="https://user-images.githubusercontent.com/79999761/130370468-eb0f2815-f298-4c37-87c1-d31c769b0466.png">


As seen in the image above, there is a 15% difference in 5-star reviews betwen Vine (38%) and non-Vine program(54%) participants. The Vine participants 5-star reviews are lower than non-Vine memebers. However, there is a far larger amount of non-Vine rewiews than Vine member reviews supporting the idea of no bias based on Vine reveiws in favor of pet products.

Further bias can be accumulated through verified purchasers, so an additional analysis removing non-verified purchasers to only show filter.df(["verified_purchase"] == "Y") and running the full summaries for total_reviews, 5-star_reviews, and percentage of 5 star reviews could provide a more accurate idea of product reviews.

