# K-Nearest Neighbours (KNN) — Classification with Iris & Digits Datasets
- Student Name   : Temur Rustamov
- Student Number : C00280204
- Module         : Data Science & Machine Learning 2

# Diary: 

## Loaded and explored the Iris dataset Date: 21/02
Loaded the Iris dataset using load_iris() and created a pandas DataFrame.

## Trained the first KNN model on Iris Date: 21/02
Trained KNeighborsClassifier using K = 10.

What I found:
The model gave high accuracy on the Iris test set.

## Tested values of K from 1 to 30 and recorded the accuracy.

What I found:
Small values of K were more sensitive.
Moderate values of K gave the best results.
Very large K values reduced performance.
 dataset is more complex than Iris, so it was useful to test KNN on a harder problem.

## Visualised sample digits Date: 21/02
Displayed some sample images from the Digits dataset.

What I found:
The images were small 8x8 grayscale digit images.
This helped confirm what the model would be classifying.

## Split Digits data and trained baseline model Date: 21/02
Split the Digits data into training and test sets and trained a baseline KNN model with K = 5.

What I found:
The baseline model already achieved very strong accuracy.


## Tested different K values for Digits date: 21/02
Tested values of K from 1 to 20 for the Digits dataset.

What I found:
Again, moderate K values performed best and this showed that choosing K carefully is important.

## Evaluated final Digits model Date: 21/02
Trained the final KNN model using the best K and evaluated it with a confusion matrix and classification report.

What I found:
The model classified most digits correctly.
Only a small number of digits were misclassified.

Conclusion:
KNN achieved very high accuracy on the Digits dataset.

## Reviewed misclassified digit examples date: 21/02
Displayed some of the incorrectly predicted digit images.

What I found:
Some digits looked visually similar, which helps explain why the model made mistakes.

## Final reflection Date: 22/02
Summarised the whole KNN project.

Final conclusion:
KNN worked very well on both datasets.
On Iris, the model classified Setosa best and confused Versicolor and Virginica slightly.
On Digits, the model also achieved very high accuracy.
The value of K had a clear effect on performance, so tuning K was important.

# Why scikit-learn?

1. I chose Scikit-learn since it is the most widely-used
   Python library for traditional machine learning. It
   provides consistent APIs for classification, regression,
   clustering and preprocessing which is perfect for working with K-means.

2. There are provided preprocessing tools that I have worked with such as StandardScaler, MinMaxScaler, and other transformers
   are built into sklearn.preprocessing.

# Why KNN ?

1. KNN is the most intuitive ML algorithm — classify
   a new point based on what its neighbours are." This makes it an excellent
   starting point for understanding supervised classification.

2. The algorithm also memorises all training
   data and does all computation at prediction time. 

3.HYPERPARAMETER K: The choice of K is simple to
   understand yet has profound effects on model behaviour since it demonstrates
   the bias-variance trade-off as overfitting and underfitting which is helpful for further usage.

# Why Iris and Digits datasets?
- I chose the dataset because of the digits: KNN scales here to higher-dimensional data and reveals the 
  dimensionality which is a key KNN limitation.

# What i have found ? 
-  KNN achieves approximately 97% accuracy on Iris with K=10. The confusion matrix reveals
   that Setosa is classified perfectly while
   Versicolor and Virginica are occasionally confused which demonstrates this behaviour: classification accuracy depends directly on how
   well separated classes are in feature space.
- KNN achieves high accuracy on digits with optimal K. It shows that KNN works well with similar digits that have similar pixel patterns and if the dataset is clean with no rotation in place
- KNN and SVM achieve similar accuracy on Iris, however, KKN requires no training phase and there is slow prediction while SVM shows slow training but faster prediction.

# Here I have worked with:
- Euclidean distance as a similarity measure
- The role of K in the bias variance tradeoff
- Confusion matrix interpretation for multi-class problems
- Precision, Recall, F1-Score per class
- Testing multiple K values
- The curse of dimensionality 

# References: 
1. Scikit-learn KNeighborsClassifier Documentation.
   https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html

2. Scikit-learn Digits Dataset.
   https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_digits.html