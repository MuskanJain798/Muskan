---
layout: post
title:  Comparative Candidate Profiling and Matching
date:   2020-12-23 00:00:35 +0300
image:  profileEvaluationImage.jpg
tags:   Supervised Machine Learning
---

This project aims to provide a tool for students to assess their likelihood of admission to the top 5 universities based on their GRE scores and other relevant factors. This tool will aid students in identifying suitable universities to apply to, considering that GRE scores are not the only factor in the admission decision.

### DATASET 

A dataset from kaggle was imported that was created for prediction of Graduate Admissions from an Indian perspective. This dataset has about 400 entries alongside the following features : 

1. GRE Scores ( out of 340 )
2. TOEFL Scores ( out of 120 )
3. University Rating ( out of 5 )
4. Statement of Purpose and Letter of Recommendation Strength ( out of 5 )
5. Undergraduate GPA ( out of 10 )
6. Research Experience ( either 0 or 1 )
7. Chance of Admit ( ranging from 0 to 1 )

https://www.kaggle.com/datasets/mohansacharya/graduate-admissions

### DATA PREPROCESSING (ETL)

Since the dataset is already cleaned, this did not require much preprocessing. The data was directly used for the next stage which is data Visualization.

### EXPLORATORY DATA ANALYSIS

Various graphs and figures were plotted to get a good understanding of the data. Python libraries were leveraged for this exercise. Initially, all the features were plotted against the target feature which is the Chance-of-admit to understand how each feature contributes towards the target variable. The prime reluts deduced in this stage are as follows:

1. CGPA is by far the most important factor in Graduate Admissions.
2. An additional point on the GRE increases chances of graduate admission by about 0.14%.
3. An additional point on the TOEFL increases chances of graduate admission by about 0.28%.
4. Performing research is only reasonably beneficial if the college rating is low.
5. A high TOEFL score can't counteract a medium/low GRE score; TOEFL only begins to contribute statistically significantly to admission chances once the GRE score is high enough.

### MODEL BUILDING

It is important to note that the target feature (chance-of-admit) being a continuous variable suggests that Supervised Machine learning techniques like Regression can be utilized to build predictive models. The following algorithms were used to build and experiment with:

1. Linear Regression
2. Decision tree 
3. Random Forest

### RESULT

The accuracies for all three models were noted and it was observed that Random Forest performed the best giving an accuracy of 93.125%. The accuracies of Linear Regression and Decision Tree are 81.974% and 86.647% respectively.

The models predicted the chance of admit of a student based on multiple scores and factors input by the user into one of the top 5 universities.


| Code is available to be viewed on Github |
