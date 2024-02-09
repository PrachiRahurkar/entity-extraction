# Entity Extraction of Airports

The "Twitter US Airline Sentiment" dataset on Kaggle provides a rich source of real-world data for sentiment analysis related to airlines. However, beyond just sentiment, this data can yield valuable insights regarding **operational aspects of airlines (like airport operations)**. 

Download this dataset from here: https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment/download?datasetVersionNumber=4 

## Problem Statement

### Goal:

 * Extract airport mentions from tweet texts and identify the airports where each airline operates.

### Steps:

 * Develop a method to identify and extract mentions of airports from the tweets.
 * Analyze these mentions to determine which airports are associated with each airline. 
 * Generate a final list of airports where each airline operates.

## Solution

**Note**: Before running any notebook, make sure that you’ve modified the path to the dataset with your correct .csv filepath, at the top. All required libraries in the notebook are at the top. If incase you don't have a particular library and the import fails (and I have removed/missed the !pip install statement maybe because I already have it), install all the required imports with the command at the start of the notebook:

```
!pip install ##name of the library##
```

**Dataset**: After doing some exploratory analysis on the dataset, I found out that the columns of our interest are:
```
[‘airline’,’airline_sentiment’,’negativereason’,’text’]
```

In this problem, our goal is to extract airport mentions from tweet texts and identify the airports where each airline operates. Airports are typically denoted in a 3-letter format in capital alphabets. For finding airport mentions using regular expressions and spacy tools, I have used this assumption.

 * **Approach 1**: Using regular expressions
 * **Approach 2**: Using the Named Entity Recognition tool in spaCy
 * **Approach 3**: Using HuggingFace language models: I took an example model of TFBertForTokenClassification but we can use a different available model as well. For tokenization, I used the BertTokenizer. The model name that I used from HuggingFace is called ‘dbmdz/bert-large-cased-finetuned-conll03-english’.

All my comments are also outlined in the Jupyter notebook markdown.