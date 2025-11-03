# Swearing in English variants on Twitter

## Dependencies

Top level dependencies are specified in requirements.txt - this should work in any version of Python >= 3.9.

## Data collection workflow

The following are the expected order of steps we will take to create representative corpora for each national English.

1. Seed users via geographically tagged tweets, using Twitter search affordances for country.
2. Snowball from seed users by some combination of the following:
	- Follower/followee relationships
	- Outbound interactions from their complete timelines on the reference day
	- Inbound interactions (mentions, retweets and replies by other users)
	- Conversation thread following
3. Using user profile objects from the candidate set, apply filters to select geographically relevant users + their tweets for inclusion in the corpus.
4. Collect timelines for included users on the target data.
5. Prepare an analytical database using [the twittersphere tool](), and an output CSV for downstream convenience.


## Data Files

data.zip - the raw as collected Twitter JSON data
processed_data.zip - transformed CSV and SQLite data files derived from the JSON data
sample_data.zip - small CSV samples of Twitter data, files ending in random_sample.csv contain 10000 randomly selected tweets, files ending in swearing_sample.csv contain 1000 randomly selected tweets that contain either of the strings 'fuck' or 'shit'.

## CSV file schema

The csv files are organised as one file per country. There is one row per
tweet collected in the dataset, containing the attributes of the collected
tweet, and some associated rows for the user who made the tweet. The user who
made the tweet is always represented by the latest seen record for that user
in the dataset - all tweets by the same user will have the same user
attributes.

tweet_id: The twitter identifier for the tweet

tweet_created_at: ISO8601 datetime of when the tweet was created.

tweet_retrieved_at: ISO8601 datetime of when the tweet was retrieved from the API

conversation_id: The twitter identifier for the conversation this tweet is part of (this is the same as the tweet_id at the start of the thread)

retweeted_tweet_id: The twitter identifier for the tweet this is a retweet of, or null if not a retweet

quoted_tweet_id: The twitter identifier for the tweet quoted, or null if not a quote tweet

replied_to_tweet_id: The twitter identifier for the tweet this is in reply to, or null if not a reply

text: The HTML unescaped text of the tweet

transformed_text: The same as text, but with #hashtags, @mentions and urls removed, and a standardised tokeniser applied to allow splitting on whitespace

lang: the autodetected language of the tweet

source: the application used to post the tweet

possibly_sensitive: auto applied setting to mark potentially "sensitive" tweets

reply_settings: who can reply to this tweet (as of tweet_retrieved_at)

like_count: number of likes of this tweet

quote_count: number of times this tweet has been quoted

reply_count: number of replies to this tweet

retweet_count: number of times this tweet has been retwitted

withheld_copyright: if not null, this tweet has been withheld for copyright

withheld_country_codes: if withheld_copyright is not null, the countries it is withheld in as a json array of strings

tweet_url: the link to the live tweet on Twitter

user_id: The twitter identifier for the user

user_created_at: ISO8601 datetime for when the account was created

user_retrieved_at: ISO8601 datetime for when the user profile was retrieved

name: the profile's display name

username: the handle of the tweet account, used for @mentions of that specific user

location: The location free text field in the twitter user bio

verified: boolean - whether the account is "verified" by Twitter

followers_count: Number of accounts this account is followed by

following_count: Number of accounts this account is following

tweet_count: number of tweets made by this account

listed_count: number of lists including this account

withheld_country_codes: if present, the countries this account is withheld from due to legal reasons, as a json array of strings

user_url: link to the user's profile on Twitter
