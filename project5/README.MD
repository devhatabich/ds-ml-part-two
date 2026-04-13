# Toxic Comment Classification

- Student Name: Temur Rustamov
- Student Number: C00280204
- Module: Data Science & Machine Learning 2
- Project: NLP Implementation
- Description: toxic comment classifier using a Bidirectional LSTM trained on a comment classification dataset

## Technologies used

- Python + TensorFlow/Keras: for building sequential models
- Bidirectional LSTM: toxicity cues in language often depend on both preceding and following context within a sentence
- TextVectorization layer: keeps tokenisation inside the model graph

## Dairy

> Loaded and explored the dataset Date: 28/03
Downloaded a dataset from Kaggle and loaded the train.csv file using pandas. Viewed the data structure.

> Checked class distribution Date: 28/03
Summed the label columns to see how many positive samples exist for each class.

> Preprocessed the text Date: 29/03
Used the Keras TextVectorization layer. Adapted the vectoriser on the full comment column so it learns the vocabulary.

> Built the tf.data pipeline Date: 29/03
Created a tf.data.Dataset with cache, shuffle, batch and prefetch then split the data into 70% train, 20% validation and 10% test. As a result got the cached pipeline sped up each epoch and this clean split gave me a separate test set for unbiased evaluation.

> Built the first LSTM model Date: 30/03
Stacked an Embedding layer, a Bidirectional LSTM, Dense ReLU layers and a final Dense with sigmoid activation. Compiled with Adam and BinaryCrossentropy.

> Trained the model Date: 30/03
Trained for 5 epochs then plotted training and validation loss using matplotlib.

> Tested predictions on example comments Date: 01/04
Ran the model on a deliberately toxic example 'you are an idiot and I hate you, go kill yourself' and on a batch from the test set. Applied a threshold to convert sigmoid outputs into binary labels. As a result, the model correctly flagged the obvious toxic example which confirmed that it is working. it scored 99.7% tocicity and insult 79.8%

> Evaluated with Precision, Recall and Accuracy Date: 02/04
Looped through the test set and updated Keras Precision, Recall and CategoricalAccuracy metrics. As a result, the model achieved strong precision and recall even after a single epoch. This showed the Bidirectional LSTM was well suited to the task.

> Retraining Date: 05/04
Experimented with different embedding sizes and LSTM units and tested whether adding a Dropout layer reduced overfitting on longer runs. As a result, I noticed that the larger LSTM slightly improved recall on the rare classes, while Dropout helped stabilise validation loss.
