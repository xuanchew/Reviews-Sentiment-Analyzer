# Reviews Sentiment Analyzer
- [Reviews Sentiment Analyzer](#reviews-sentiment-analyzer)
  - [1. Introduction](#1-introduction)
  - [2. Data](#2-data)
  - [3. Models](#3-models)
  - [4. Findings](#4-findings)
  - [5. Conclusion and Other Notes](#5-conclusion-and-other-notes)


## 1. Introduction
In Computational Linguistics, many models and methods have been devised to do sentiment analysis. A sentiment is defined as a view or attitude towards a certain thing which is essentially a personal opinion. With the internet, a never-ending stream of data is being generated, better sentimental analsysis capabilities plays a key role since it is beyond any human capability to parse these data by hand.

In this project, we will focus on review data. Being able to quickly process large amounts of review data allows company to have a quick overview on the state of their products and offerings. The insights could be used for data-driven decision making when planning future products or enhancements.

## 2. Data
I used a collection of movie reviews from the [Cornell Movie Dataset](https://www.cs.cornell.edu/people/pabo/movie-review-data/). The data has a binary label, marked as either pos for Positive and neg, for Negative.

Some data cleaning steps were taken in an effort to achieve better performance. Some examples include :
  
- Removing Punctuation
- Removing filler words
- Removing non-alphabetical characters
- Removing stop words

## 3. Models
- Baseline Model
  - Basic score-based model that uses the NRC EmoLex Lexicon.
  - Simple, naive assumption that text with more positive words would carry a positive sentiment, and vice versa.
- Logistic Regression Models
  - liblinear
  - lbfgs
- Machine Learning
  - Baseline Model
    - Naive Bayes Classifier
    - Good as a baseline supervised model
  - Linear Support Vector Classifier (SVC)

## 4. Findings
- Based on the results I got from the models, the baseline score model seems to perform quite well especially considering how simple the score model is. The accuracy when predicting positive labels are way higher and this might have to do with how the model might be more biased towards words with positive connotation.
- The baseline machine learning model utilizes a basic machine learning classifier which is Naïve Bayes. While it is also a very simple
model, it is also able to achieve decent results. Naïve Bayes has its weaknesses, especially on how it assumes the shape of the data distribution, essentially seeing each feature ass independent given the output class. There is also an issue with data scarcity, since it heavily relies on how frequently a label is seen. 
- The more complex classifiers like both variants of Logistic Regression, Linear SVC were all able to make significantly better predictions, mostly with an accuracy falling around 85% or so.
- It seems that the model improves marginally when a higher k-value is given, in this case, 10,000. The model was able to achieve 87% or so accuracy across the board except for the baseline model.
- Based on the most informative features, the top 15 most informative words do have a strong indication of its sentiment. For example, “awful” is clearly a negative sentiment in most contexts.

## 5. Conclusion and Other Notes
- This college level project allowed me to attempt an implementation on different models in order to complete a rather useful task of sentiment analysis. It is definitely interesting to see how these classifiers and models work and compute these predictions that overall has a pretty good accuracy.
- A potential improvement I could think of would be to focus more on adjectives, which would require parts of speech tagging since adjectives tend to carry a lot of sentiment with them.
- Perhaps when I do have the time, I will clean up this old code and add Yelp reviews analysis as well.