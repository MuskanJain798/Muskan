---
layout: post
title:  Book Recommendation System using Collaborative Filtering
date:   2022-03-05 15:01:35 +0300
image:  bookReccEngImage.png
tags:   DataAnalytics DataMining
---

This project aims at building yet another Recommendation engine. This is a Book Recommendation engine which can be used by applications and websites like Amazon Kindle, Goodreads, Apple Books etc. to recommend books by studying consumer interests. This model makes use of Collaborative Filtering as a recommendation technique.

### DATASET

The projects makes use of three different datastes that can be uniformly integrated with the help of common features like ISBN ID for books and UserID. 

Dataset : https://www.kaggle.com/code/hilalmleykeyuksel/book-recommender/data

### DATA PREPROCESSING and ETL

As mentioned earlier, some preprocessing is done initially to integrate all datasets in a single dataframe using Joins in Python. This dataframe collectively has 0.2M records along with 12 descriptive attributes. It is important to note that there is a difference between the Highly rated books and the the most Popular books (which depends on how many readers have rated these books). In order to account for this ambiguity, a new attribute called "weighted-rating" was introduced and calculated for each record. 

### EXPLORATORY DATA ANALYSIS

Multiple graphs and figures were plotted uisng python libraries. These helped to understand the highly rated and popular books. Further this stage also helped to provide a good insight to the demography of the readers. This observation was especially leveraged while building the recommendation engine.

### USER BASED RECOMMENDATION ENGINE

This project uses a slightly differemnt approach to user-based CF. Instead of using cosine similarity, it calculates and uses a Correlation Matrix. You can refer the Github repository to get a perfect understanding of this process. The way this model works is that you need to enter a UserID and it generates a list of 10 books this user would enjoy based on the calculated correlation matrix.

### ITEM BASED RECOMMENDATION ENGINE

In this engine, multiple clustering techniques are experimented with to test what works best for the dataset under consideration. The following clustering techniques were leveraged:
1. k-Means
2. DBSCAN
3. Hierarchical 

It is important to mention that due to the size of the dataset and computational limitation of the system, the entire dataset was divided into three subsets based on the age groups of the users. Each of these subsets were trained using all the clustering models. 

The evaluation metric for each of the subsets consisted of the following scores:
1. Silhouette score
2. Calinski-Harabasz score
3. Davies-Bouldin score

It was observed that for this dataset, the Hierarchical Clustering provided the best results and was hence used to model the Item Based recommendation engine.

| Code can be viewed on Github |
