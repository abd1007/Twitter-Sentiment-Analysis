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

Open this [link](https://developer.twitter.com/en/apps) and click the button: ‘Create New App’
Fill the application details. You can leave the callback url field empty.
Once the app is created, you will be redirected to the app page.
Open the ‘Keys and Access Tokens’ tab.
Copy ‘Consumer Key’, ‘Consumer Secret’, ‘Access token’ and ‘Access Token Secret’.
