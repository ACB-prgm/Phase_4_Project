# Sentiment Analysis of Twitter Data

## Introduction
This project aims to develop a machine learning model for predicting sentiment about various products on Twitter. Social media platforms like Twitter provide valuable data for analyzing consumer opinions, but manual analysis can be time-consuming and resource-intensive. Machine learning automates sentiment analysis, enabling businesses to quickly and accurately analyze social media data and gain valuable insights. By leveraging machine learning algorithms, businesses can make data-driven decisions, improve customer satisfaction, and stay competitive in the marketplace.  

The data science steps used in this project include data collection, data cleaning, text processing, feature engineering, and machine learning model development and evaluation.  

The goals for this project were to:  
1. Develop a machine learning model to predict sentiment about apple products on Twitter
2. Demonstrate the effectiveness of the model in predicting sentiment
3. Outline the benefits and limitations of using a sentiment analysis model for business consumer opinion research

Sources used in this project are included in the jupyter notebook and this README  

### Navigating This Repository
analyze.ipynb: Jupyter notebook / code  
presentation.pdf: PDF of the project presentation  
Data folder: contains the data  

## Methods
### Data Collection
Two datasets were combined and filtered resulting in ~6,000 tweets about various products and services
1. CrowdFlower
 - Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.
2. Sentiment Analysis: Emotion in Text
 - Kaggle Dataset with >25k tweets
 - filtered for those with reference to products and services (the products used as filters can be found in the jupyter notebook)


### Text Processing


## Feature Engineering
The pre-processed text data was then used to develop machine learning models for sentiment analysis. Two models were developed: a binary classification model for predicting positive or negative sentiment, and a multiclass classification model for predicting sentiment across multiple categories.

## Model Development and Evaluation
The machine learning models were trained and tested on a sample dataset using appropriate evaluation metrics such as accuracy, precision, and recall. The performance of the models was evaluated and compared to determine their effectiveness in predicting sentiment about products on Twitter.

## Model Deployment
The machine learning models were deployed to a production environment, where they could be used to analyze sentiment about products on Twitter in real-time.

## Results
The binary classification model achieved an accuracy of 90%, indicating that it can accurately predict whether a tweet expresses positive or negative sentiment. The multiclass classification model had an accuracy of 63%, indicating that it performed less effectively.

Visualization of the most common words by sentiment was used to help inform the feature engineering process and machine learning model development. Bar graphs of model metrics were used to present the performance of the machine learning models. Example images of tweets that the models classified were also included.

## Conclusion
In conclusion, this project demonstrates the value of sentiment analysis for businesses looking to gain insights into consumer opinion and improve decision-making. By accurately predicting sentiment about products on Twitter, businesses can identify areas for improvement, respond to customer feedback, and increase customer satisfaction and loyalty.

The machine learning models developed in this project provide a proof of concept for the effectiveness of sentiment analysis in consumer opinion research. Further work can be done to improve the accuracy and robustness of the models and to apply them to larger datasets and in more complex scenarios.