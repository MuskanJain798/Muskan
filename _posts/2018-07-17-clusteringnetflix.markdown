---
layout: post
title:  Data Mining of OTT Platform Content
date:   2021-12-01 15:01:35 +0300
image:  dataMiningOTTimage.jpg
tags:   DataAnalytics
---
Technology boom today has changed the way each of us live our lives today. OTT platforms like Netflix, Amazon prime, Hulu etc. have become a prime source of entertainment in our day to day lives. With so many options available, a critical fact to note here is that the attention span of consumers have shrinked to as short as 90 seconds. Hence to stay at the top of their game, these platforms need to find a way to keep its consumers engaged. And the way, they can do this is by constantly leveraging and enhancing their Recommendation Engines.

The aim of the project here is to take some shows or movies that a user has seen and provide a list of recommended movies that the user would enjoy based on their viewership behavior. This repository contains code written in R containing clusters created based on movies and shows to understand how they relate to each other in terms of their ratings and their popularity. 


### DATASET

In this project, a Netflix dataset is imported from Kaggle. 

https://www.kaggle.com/datasets/ashishgup/netflix-rotten-tomatoes-metacritic-imdb


### DATA PREPROCESSING 

The first step here, was to understand the dataset and the correlations between the features. This was done using R libraries for visualizations. Further the dataset had to be cleaned to get rid of NULL values or any outliers to avoid any ambiguity in the results of the recommendation engine. During this ETL process, it was observed that many features like Metacritic Score, Awards Nominated for & Awards Received were not required and would just add on to the model as noise, hence they were gotten rid of. Additionally, the ratings provided by multiple websites were not on the same scale, hence they needed to be normalized. Finally, One Hot Encoding was used in order to convert categorical data to continuous values.

### EXPLORATORY DATA ANALYSIS

Multiple plots were plotted to observe trends and patterns in the clean dataset to help understand and portray our understanding of the dataset with plots and figures. These helped us figure out the most popular genres across movies and shows on Netflix. Other notable derivations from the plots were popular languages, popular directors, highly rated writers across movies and shows.


### DIMENSIONALITY REDUCTION

Two techniques of dimentionality reduction were experimented with to realize which attributes will be impactful for analysis:

1. Principal Component Analysis (For Linear relationships): 
PCA is the process of identifying components which are crucial in the dataset provided. In the PCA, the idea is to go with the principal components that account for the most variation in the data. After plotting the scaled PCA graph using scaledPCA and PRCOMP() functions, it was noted that the first two principal components accounted for more than 85% of the data. Additionally Scree plot was visualized which resulted in the observation that Score and Hidden.gem.score were only needed for the analysis.

2. T-Distributed Stochastic Neighbourhood Embedding (For Non-linear relationships): 
T-SNE is a statistical method for visualizing high-dimensional data by giving each datapoint a location in a 2D or 3D map. We used categorical variables inclusive of language, genres and found the distance between them using Gower distance using the daisy library in R. 
First, t-SNE constructs a probability distribution over pairs of high-dimensional objects in such a way that similar objects are assigned a lower probability. Second, it defines a similar probability distribution over the points in lower dimensional map, and minimizes the KL-Divergence between the two distributions with respect to the locations of the points in the map. Due to higher overlapping using perplexity=10, it was tuned to perplexity=50 to have better well defined clusters.


### CLUSTERING 

Two clustering techniques were experimented with:

1. Hierarchical Clustering: 
Complete and average linkage hierarchical clusters were modeled and plotted. The result of these clusterings can be visualized as dendogram, which shows the sequence of cluster fusion and the distance at which each fusion took place.

2. K-Means Clustering: 
K-Means has identified centroids with data points all around the centroid. It doesn't allow nearby data points to share the same cluster no matter how obvious the distance between them might be.


### RESULTS

The modelling results from heirarchical and k-means clustering showcases a clear logical seperation among the different clusters specifically noted in k-means. The recommendation engine was built such that for a particular movie or show, all other movies and shows belonging to the same cluster as the input were ranked in descending order of their scores and the top 5 were recommended.

This project would benefit OTT platforms such as Netflix, Hulu and Amazon Prime to understand their consumers better and accordingly improve their overall recommendation engines. These clusters can be used to understand how different consumer viewing behavior and taste can be used to recommend similar movies and shows to the associated consumers.


| Code is available to be viewed on Github |
