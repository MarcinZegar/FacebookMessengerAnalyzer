# FacebookMessengerAnalyzer

A library which allows users to you easily run some simple Data Analytics on their Facebook Messenger Data

https://github.com/zegarmm001/FacebookMessengerAnalyzer

### Introduction 

To install simply open your Python Temrinal and pip install

```python -m pip install FacebookMessengerAnalyzer```

### Getting Started

You will need to download your Facebook Messenger Data! Is can be easily done by visiting:

https://www.facebook.com/dyi/?referrer=yfi_settings

MAKING SURE YOU SELECT FORMAT: JSON as this is the data format this library analyzes. You can select whatever data you would like to download but we are most concerned with the "Messages" tab. 

Once you have Selected your desired Date Range, Format =JSON and whatever quality suits you, select Create file. It took me a few hours before I got an email from Facebook saying my data is ready to download, so beware.

Once downloaded, you will need to uncompressed your data using coming like 7Zip or WinRaR.

Now, depending where you uncompresed your data, find your way to that location and navigate to ```.\messages\inbox\```

You will see a long list of folders at this location each corresponding to a different chat! Decide which chat you want to analyze and copy its path. This is all you need to start analyzing!

Now open your favorite python IDE. 

```
from FacebookMessengerAnalyzer import IndividualMesseges

PATH_TO_THE_FACEBOOK_DATA = r'C:\Users\Test\Facebook\messages\inbox\samsmith'

Facebook_messages_object =  IndividualMesseges(PATH_TO_THE_FACEBOOK_DATA )

#Get a quick description of your chat
Facebook_messages_object.describe()
```

There is a tests folder which contains a FacebookMessengerAnalyzer_test.py file with sample data which you can play with! 

### Plotting

```
from FacebookMessengerAnalyzer import IndividualMesseges

PATH_TO_THE_FACEBOOK_DATA = r'C:\Users\Test\Facebook\messages\inbox\samsmith'

Facebook_messages_object =  IndividualMesseges(PATH_TO_THE_FACEBOOK_DATA )

#plot of messages sent each month
Facebook_messages_object.plot_counts()

#plot the sentiment of the conversations aggregated by month
Facebook_messages_object.plot_sentiments()
```

### What is Sentiment Analysis?

VADER Sentiment Analysis. 
        VADER (Valence Aware Dictionary and sEntiment Reasoner) is a lexicon and rule-based sentiment analysis tool that is specifically attuned to sentiments expressed in social media, and works well on texts from other domains. It provides a number between -1 and 1 which indicates the sentiment ("attitude"/"happiness") of the messages.
        The VADER lexicon is an empirically validated by multiple independent human judges, VADER incorporates a "gold-standard"  sentiment lexicon that is especially attuned to microblog-like contexts. 
        
This library will run this and visual your results with on line of code! (assuming you have initialized a object as shown earlier)

```Facebook_messages_object.plot_sentiments()```