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
[analyze.ipynb](https://github.com/ACB-prgm/Phase_4_Project/blob/master/analyze.ipynb): Jupyter notebook / code  
[presentation.pdf](https://github.com/ACB-prgm/Phase_4_Project/blob/master/PDFs/P4_Project_Presentation.pdf): PDF of the project presentation  
[Data](https://github.com/ACB-prgm/Phase_4_Project/tree/master/Data) folder: contains the data  

## Methods
### Data Collection
Two datasets were combined and filtered resulting in ~6,000 tweets about various products and services
1. [CrowdFlower Dataset](https://data.world/crowdflower/brands-and-product-emotions)
 - Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.
2. [Sentiment Analysis: Emotion in Text](https://www.kaggle.com/competitions/tweet-sentiment-extraction/data)
 - Kaggle Dataset with >25k tweets
 - filtered for those with reference to products and services (the products used as filters can be found in the jupyter notebook)

There was a signifficant class imbalance, and the majority class (neutral), was undersampled to address this in part.  Class weights were used to address the remaining imbalances during model training.  

The data was split into Train, Validation, and Test sets.  
 - Models learned on the train set
 - Tweaked using the validation set performance
 - Evaluated on the test set performance

<img src="https://user-images.githubusercontent.com/63984796/228379606-cd223ed4-f4bf-45f8-9747-7f1b5e5d2a56.png" alt="MostCommonWords" width="500" align="center"/>


### Text Processing
1. Cleaning
 - Remove irrelevant data such as URLs, digits, non-ASCII characters, single letter words, capitalization, and punctuation.
 - Replaced filtered swear words denoted with repeating asterisks with the word "cuss"
2. Normalization
 - Removed Stop words via the `nltk` library
 - Lemmatized words to their base form
 - Replaced all references to specific products/services with the word "product"
3. Vectorization
 - Using a technique called bag-of-words, each word is assigned a numerical value.

 <img src="https://user-images.githubusercontent.com/63984796/228379516-09e93837-5050-488f-893f-dcc610c8617e.png" alt="TextProcessing" width="500" align="center"/>

### Model Development and Evaluation
The pre-processed text data was then used to develop machine learning models for sentiment analysis. Two categories of models were developed: a binary classification model for predicting positive or negative sentiment, and a multiclass classification model for predicting sentiment across multiple categories. In each category, four types of models were created and evaluated:, Logistic Regression, SVC, Recurrent Neural Network, Hybrid Convolutional Neural Network.

The machine learning models were trained and evaluated on training and validation datasets respectively. The performance of the models was then evaluated and compared on metrics of accuracy, precision, recall, and macro averaged F1 score to determine their effectiveness in predicting sentiment about products on Twitter.

## Results
### Binary Models
The SVC model performed the best with an accuracy of 90% and an average F1-Score of 81, indicating that it accurately predicts each sentiment. This indicates that the level of complexity of the problem is suited to the level of complexity of the SVC model.  

<img src="https://user-images.githubusercontent.com/63984796/228379627-42c3dd07-11dc-4393-adfd-b8ed54db4155.png" alt="BinaryResults" width="500" align="center"/>

### Multi-Class Models
The SVC model performed the best with an accuracy of 63% and an average F1-Score of 61. The poor performance is due to the difficulty of determining the Neutral class due to the significant overlap as described earlier.  

<img src="https://user-images.githubusercontent.com/63984796/228379639-3fb07f92-ea89-4860-b10b-dd743fa58c7b.png" alt="MultiResults" width="500" align="center"/>

## Value and Deployment
### Use Cases
**Identifying areas for improvement**  
For example, if the model detects a high volume of negative sentiment related to a particular product feature or customer service issue, Apple can investigate the issue and take steps to address it.

**Respond to customer feedback**  
By monitoring sentiment in real-time, Apple can identify and address customer issues and concerns before they escalate, improving customer satisfaction and loyalty.

**Informing product development**  
By understanding which features or products are most commonly associated with positive or negative sentiment, Apple can prioritize development efforts and make more informed decisions about product features and design.

**Monitoring competitors**  
The sentiment analysis model can be used to monitor sentiment about Apple's competitors on Twitter, providing insights into the strengths and weaknesses of competing products and brands.
### Deployment Suggestion
Our binary sentiment analysis model can output a probability score that indicates how confident it is in its prediction. By setting a threshold of 75%, we can include only highly confident tweets, improving the quality and reliability of our predictions. Confidence thresholding ensures that the sentiment analysis model provides valuable insights to businesses.

## Conclusion
In conclusion, this project demonstrates the value of sentiment analysis for businesses looking to gain insights into consumer opinion and improve decision-making. By accurately predicting sentiment about products on Twitter, businesses can identify areas for improvement, respond to customer feedback, and increase customer satisfaction and loyalty.

Binary sentiment classification (positive and negative) achieved higher accuracy compared to the multi-class model. The difficulty in training models in this space is due to a number of factors. Firstly, tweets are a particularly difficult medium to perform NLP on because of the short length, use of slang, and intentional and unintentional grammatical and spelling errors. Second is the size of our dataset. After undersampling the majority class, we were left with less than 6k tweets. Many of the highest performing NLP models are trained on millions if not billions of datapoints. Finally, I believe that the dataset's labeling contains many errors and/or tweets that people may not label into any one category as they contain both positive and negative aspects.

While the results may be limited by the size and diversity of the dataset, sentiment analysis of tweets can provide valuable insights into customer opinions and attitudes towards products or services. This work demonstrates the potential for NLP sentiment analysis to be used in real-world applications for business decision-making. The machine learning models developed in this project provide a proof of concept for the effectiveness of sentiment analysis in consumer opinion research. Further work can be done to improve the accuracy and robustness of the models and to apply them to larger datasets and in more complex scenarios.