# Depression_Detection_via_Twitter
Mental illness such as depression can be life threatening, with suicide as a possible outcome. In this project, a LSTM with Convolutional Neural Network is built using Keras to determine whether social platform users are depressive based on their Twitter posts. The accuracy of the model is evaluated and compared to a binary classification baseline model using logistic regression. It is discovered that the model has a 99.02% accuracy after 6 epochs, while the base line model has a much lower accuracy of 83.755%.
### Retrieving Test Data
#### Warning to Researchers
The test data described below is extremely biased as it's scrapped with the keyword `depression`, for research purposes I recommend looking at the dataset Reddit Self-reported Depression Diagnosis (RSDD) and Self-reported Mental Health Diagnoses (SMHD) from Georgetown University [here](http://ir.cs.georgetown.edu/resources/#__sid=js0). This is also not an actively maintained project thus inquiries are discouraged.

There are two kinds of tweets that are needed for this project: random tweets that do not indicate depression and tweets that show the user may have depression. The random tweets dataset can be found from the Kaggle dataset [twitter_sentiment](https://www.kaggle.com/ywang311/twitter-sentiment/data). It is harder to get tweets that indicate depression as there is no public dataset of depressive tweets, so in this project tweets indicating depression are retrieved using the Twitter scraping tool [TWINT](https://github.com/haccer/twint) using the keyword `depression` by scraping all tweets in an one day span. The scrapped tweets may contain tweets that do not indicate the user having depression, such as tweets linking to articles about depression. As a result, the scrapped tweets need to be manually checked for better testing results.
#### Test Data Split
Collected tweets are split into training, testing, and validation sets with a ratio of 60% : 20% : 20%.

|               | Depressive Tweets           | Normal Tweets  |
| ------------- | --------------------------- | -------------- |
| Training      | 1384                        | 7146           |
| Validation    | 462                         | 2382           |
| Testing       | 462                         | 2383           |
| Total         | 2308                        | 11911          |

### Required Libraries
* ftfy - fixes Unicode that's broken in various ways
* gensim - enables storing and querying word vectors
* keras - a high-level neural networks API running on top of TensorFlow
* matplotlib - a Python 2D plotting library which produces publication quality figures
* nltk - Natural Language Toolkit
* numpy - the fundamental package for scientific computing with Python
* pandas - provides easy-to-use data structures and data analysis tools for Python
* sklearn - a software machine learning library
* tensorflow - an open source machine learning framework for everyone

In addition, the pretrained vectors for the Word2Vec model can be downloaded from [here](https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit).
