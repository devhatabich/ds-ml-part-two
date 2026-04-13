18.01
Chose the project, installed a dataset, imported all necessary libraries

20.01
Cleaned dataset from any NaN values

02.02 
https://www.kaggle.com/code/abrahamanderson/tutorial-use-of-kmeans-clustering-for-universities/notebook

Name:               Temur Rustamov 
Student Number:     C00280204
Module:             Data Science & Machine Learning 2

# Dairy:
##  Data loading and first check Date: 02/02/2026
Loaded the College_Data dataset using pandas. Reviewed the dataset structure and summary statistics using df.describe().

What I found:
The dataset contains college information such as applications, enrolment, tuition, and graduation rate. The values are on very different scales, so scaling would be needed before using K-Means.

## Missing value check Date: 14/02/2026
Checked the dataset for missing values and used dropna() to remove any rows with missing data.

What I found:
K-Means cannot work with missing values, so cleaning the data was necessary before clustering.

## Feature scalingDate: 14/02/2026

Used StandardScaler to scale the features Apps, Accept, and Enroll. Created new scaled columns: app_t, acc_t, and enr_t.

What I found:
Scaling was important because K-Means uses distance. Without scaling, large values such as applications would dominate the clustering.

## Choosing the number of clusters Date: 21/02/2026

Implemented Elbow Method into a function and plotted inertia values for different values of K.

What I found:
The biggest drop in inertia happened from K = 1 to K = 2. After that, the improvement became smaller.

Decision that I have made:
Chose K = 2 as the best number of clusters.

## Applying K-means Date: 21/02/2026
Ran K Means using the scaled features app_t and enr_t. Stored the cluster labels in a new column called kmeans_2.

What I found:
The model divided the colleges into two main groups.

## Visualised the clusters Date: 21/02/2026
Created a scatter plot of Full-Time Undergraduates against Out-of-State Tuition and coloured the points by cluster.

What I found:
The two clusters were mainly separated by student population size.
One group contained mostly smaller colleges.
The other group contained mostly larger universities.

note:
There was still overlap in tuition, so the clustering was more strongly based on size than on tuition.

## Comparing different K means Date: 21/02/2026

Created plots for aK = 1 to K = 5 to compare how the clustering changed.

What I found:
As K increased, the data was split into more groups, but the main pattern did not change much. The extra clusters mostly created smaller subgroups.

Decision made:
This supported keeping K = 2 as the clearest and simplest choice.

## Conclusions Date: 21/02/2026

Summarised the results of the notebook.

Final conclusion:
The analysis showed that K-Means could group the colleges into two main clusters.
The main difference between the clusters was college size, especially the number of full-time undergraduates.
Feature scaling was necessary to make the clustering fair and reliable.
Overall, K = 2 gave the clearest result.

# Why scikit-learn?

1. I chose Scikit-learn since it is the most widely-used
   Python library for traditional machine learning. It
   provides consistent APIs for classification, regression,
   clustering and preprocessing which is perfect for working with K-means.

2. There are provided preprocessing tools that I have worked with such as StandardScaler, MinMaxScaler, and other transformers
   are built into sklearn.preprocessing.

# Why K-Means ?

1. K-Means produces clear and non-overlapping clusters with
   where each data point belongs to exactly one cluster which 
   makes results easy to explain.

2. It scales well to large datasets. DBSCAN and hierarchical clustering can be
   significantly slower on large data.

# Why US College Data as my main dataset?
1. This dataset contains statistics for US colleges
   and universities, with 18 features covering admissions, costs, academics,
   and outcomes. Perfect for realistic data science challenges: mixed scales,
   potential outliers and cluster interpretations.

2. The dataset has features measured in very different units
   (percentages, counts, dollar amounts) which makes using StandardScaler essential.

# Findings:
During this project and after analysing The results we see that the colleges can be grouped into two main clusters.
- The main difference between the clusters is student population size, especially the number of full-time undergraduates.
- One cluster contains mostly smaller colleges, while the other contains larger universities.
- There is some overlap in out-of-state tuition, so tuition alone does not fully separate the groups.
- Overall, the clustering shows a clear pattern of small vs large institutions, and K = 2 gives the clearest overall grouping.

# References:
- Kodinariya, T.M. & Makwana, P.R. (2013). Review on determining number of
Cluster in K-Means Clustering. International Journal of Advance Research in
Computer Science and Management Studies, 1(6).
(Elbow Method and alternatives)

- James, G., Witten, D., Hastie, T. & Tibshirani, R. (2013). An Introduction
to Statistical Learning (ISLR). Springer. Chapter 10: Unsupervised Learning.
(Source of the College dataset)
