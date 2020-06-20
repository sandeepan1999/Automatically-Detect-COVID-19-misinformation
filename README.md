# Automatically Detect COVID-19 misinformation: NLP Project Overview
* Created a tool that automatically detects whether an article is Genuine or Fake.
* Explored over 1,100 news articles and social network posts on COVID-19 from a variety of new sources.
* Engineered features from the title and text of each article.
* Optimised a Support Vector Machine (SVM) model with a linear kernel and 10-fold cross-validation to prevent overfitting.

## Code and Resources Used:
__Python Version:__ 3.7 

__Packages:__ nltk, sklearn, seaborn, textblob, plotly, pandas, numpy 

__References:__ https://towardsdatascience.com/@actsusanli 

## Data:
The dataset used has the following columns:
* Title - The title of the article.
* Text - The main body of the post.
* Source - The source site from which the article is extracted.
* Label - Labelling of the article as genuine or fake.

## Data Cleaning:
* First I converted all the rows in 'label' column to uppercase.
* Labelled the missing values as 'missing'.

## Feature Engineering:
After cleaning the data, I created the following variables.
* Calculated the number of capital letters, stop words, Proper nouns in each title.
* Computed the percentage of capital letters, stop words in each article body rather than simply counting the number, because the length of the articles are very different.
* Used part-of-speech tagger and keep a count of how many times each tag appears in the article.
* Number of negations, interrogatives in the article body.
* Used a Python library — textstat to calculate statistics from text to determine readability, complexity and grade level of any article. 
* Computed Type-Token Ratio (TTR).
* Number of power words, casual words, tentative words, emotion words in the article body.

## EDA
Below are a few highlights after performing Exploratory Data Analysis:
![alt text](https://github.com/sandeepan1999/Automatically-Detect-COVID-19-misinformation/blob/master/stop_words.PNG "stop words")

![alt text](https://github.com/sandeepan1999/Automatically-Detect-COVID-19-misinformation/blob/master/ttr.PNG "TTR")

![alt text](https://github.com/sandeepan1999/Automatically-Detect-COVID-19-misinformation/blob/master/corrplot.png "Corrplot")
## Model Building
For the first attempt, I decided to use all of them to fit a a Support Vector Machine (SVM) model with a linear kernel and 10-fold cross-validation to prevent overfitting.

I evaluated the model using Accuracy Score. I chose it because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.

## Model Performance
              precision    recall  f1-score   support

        FAKE       0.88      0.83      0.85       119
        TRUE       0.83      0.88      0.85       114

    accuracy                           0.85       233
 



