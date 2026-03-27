# Support Vector Machines (SVM) — Classification with Iris & Digits Datasets

- Student Name   : Temur Rustamov
- Student Number : C00280204
- Module         : Data Science & Machine Learning 2

# Dairy logging:
## Loaded and explored the datasets Date: 22/03
Loaded the Iris and Digits datasets using scikit-learn.
Viewed the data structure, class labels, and sample records/images.
Result:
This helped me understand the features, classes, and overall dataset size before training the model.

## Visualised the Iris data Date: 22/03
Created scatter plots for Iris features.
Result:
The petal features showed clearer class separation than the sepal features.
This suggested that SVM should classify Iris well.

## Split the data and trained the first SVM models Date: 22/03
Split both datasets into training and test sets.
Trained a default SVM model on Iris and compared RBF and linear kernels on Digits.
Result:
The models achieved high accuracy on both datasets.

## Tuned the SVM hyperparameters Date: 22/03
Tested different values of C, gamma, and different kernels.
Result:
The performance changed depending on the parameter values.
This showed that SVM accuracy depends strongly on good parameter tuning.

## Built the final model and reviewed results Date: 25/03
Selected the best-performing settings and trained the final SVM model.
Reviewed accuracy, classification report, and overall results.


# Why SVM?
1.  SVM has a strong theoretical foundation since it finds
   the max margin hyperplane, which provably minimises generalisation error

2. SVM can handle non-linearly separable data through mapping data to a higher-dimensional space where it becomes linearly
   separable.

3. SVM works well with limited training data
   like Iris dataset unlike deep learning which requires thousands
   or millions of samples. 

# Why these datasets?
- Iris is is small enough to fully understand separable
  versicolor and virginica overlap in feature space.

- Digits is a more challenging dataset since it tests whether the SVM concepts
  learned on Iris scale to higher dimensional and more complex data.

# Findings:
-  SVM achieves 93-100% accuracy on Iris depending on hyperparameters and the
   train/test split. Both linear and RBF kernels
   perform well because the classes are (nearly) linearly separable.
- SVM achieves 98-99% accuracy on the Digits dataset with proper tuning. The high dimensionality provides
   enough information for SVM to find effective decision boundaries.
# Conclusion:
- SVM is a powerful classifier that works effectively on both
   small Iris and moderate as Digits datasets without requiring GPU hardware
   or deep learning frameworks. 


# References:
- Scikit-learn SVC Documentation.
   https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html

- Scikit-learn Digits Dataset.
   https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_digits.html