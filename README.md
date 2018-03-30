# pyTweetCleaner
Python module to clean twitter json data and remove unnecessary tweet data

**Usage1:**
```python
from pyTweetCleaner import TweetCleaner

tc = TweetCleaner(remove_stop_words = True)
tc.clean_tweets(input_file='data/sample_input.json', output_file='data/sample_output.json')
```

**Usage2:**
```python
from pyTweetCleaner import TweetCleaner

tc = TweetCleaner(remove_stop_words = True)
print(tc.get_cleaned_text('I played the Sandy Caps mini game in Paradise Island 2. #GameInsight #ParadiseIsland2'))
>>> played sandy caps mini game paradise island game insight paradise island2
```


<hr>

**Requirements:**
1. nltk>=3.2.4
```
pip install -r requirements.txt
```

<hr>

**Data Removed and Kept:**
```
REMOVE      TWEETS THAT HAVE in_reply_to_status_id !=null i.e. COMMENTS ON SOMEONE ELSE'S TWEETS
            TWEETS THAT HAVE lang != en i.e. NOT IN ENGLISH LANGUAGE
            DATA ABOUT DELETED TWEETS
            NON-ASCII CHARACTERS FROM text
            links FROM text
            HASH(#) SYMBOLS BUT KEEP HASHTAG AS NORMAL TWEET TEXT BUT SPLIT HASHTAG AT UPPERCASE LETTERS 
            @name MENTIONS IN TEXT
  
KEEP        created_at
            id
            text IN LOWERCASE AFTER SPLITTING COMPOUND WORDS, REMOVING STOPWORDS AND WORDS OF LENGTH 1
            user_id
            user_name
            user_screen_name
            geo
            coordinates
            place
            retweet_count
            entities
```

**Note:** If you want only some of these data fields then comment others in _pyTweetCleaner.py_ file.
<br>If you want other fields also then add them in _pyTweetCleaner.py_ 
