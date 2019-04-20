# Twitter-Sentiment-Analysis
Sentiment analysis of any topic by parsing the tweets fetched from Twitter using Python

Sentiment Analysis is the process of ‘computationally’ determining whether a piece of writing is positive, negative or neutral. It’s also known as opinion mining, deriving the opinion or attitude of a speaker.

### Installation:

#### Python package to fetch tweets through Twitter API
pip install tweepy
#### Textblob is the python library for processing textual data
pip install textblob
#### Install some NLTK corpora using following command:
python -m textblob.download_corpora

### Authentication:
In order to fetch tweets through Twitter API, one needs to register an App through their twitter account.
Follow the steps:

Open this [link](https://twitter.com/login?redirect_after_login=https%3A%2F%2Fdeveloper.twitter.com%2Fapps) and click the button: ‘Create New App’
Fill the application details. You can leave the callback url field empty.
Once the app is created, you will be redirected to the app page.
Open the ‘Keys and Access Tokens’ tab.
Copy ‘Consumer Key’, ‘Consumer Secret’, ‘Access token’ and ‘Access Token Secret’.

### Understanding the code:
First of all, we create a TwitterClient class. This class contains all the methods to interact with Twitter API and parsing tweets. We use __init__ function to handle the authentication of API client.

In **get_tweets** function, we use:
`fetched_tweets = self.api.search(q = query, count = count)`
to call the Twitter API to fetch tweets.

In **get_tweet_sentiment** we use textblob module.
`analysis = TextBlob(self.clean_tweet(tweet))`
TextBlob is actually a high level library built over top of NLTK library. 
First we call **clean_tweet** method to remove links, special characters, etc. from the tweet using some simple regex.

Then, as we pass tweet to create a TextBlob object, following processing is done over text by textblob library:

- Tokenize the tweet ,i.e split words from body of text.
- Remove stopwords from the tokens.(stopwords are the commonly used words which are irrelevant in text analysis like I, am, you, are, etc.)
- Do POS( part of speech) tagging of the tokens and select only significant features/tokens like adjectives, adverbs, etc.
- Pass the tokens to a sentiment classifier which classifies the tweet sentiment as positive, negative or neutral by assigning it a polarity between -1.0 to 1.0 .

Here is how sentiment classifier is created:

- TextBlob uses a Movies Reviews dataset in which reviews have already been labelled as positive or negative.
- Positive and negative features are extracted from each positive and negative review respectively.
- Training data now consists of labelled positive and negative features. This data is trained on a Naive Bayes Classifier.
- Then, we use sentiment.polarity method of TextBlob class to get the polarity of tweet between -1 to 1.
