# Twitter Bot with Raspberry Pi and Tweepy

This guide will walk you through the process of creating a simple Twitter bot using a Raspberry Pi and the Tweepy library. The bot will post a random joke to your Twitter account every hour.

## Prerequisites

- Raspberry Pi set up with an operating system (e.g., Raspberry Pi OS).
- Twitter Developer account with API keys and access tokens.
- Python and pip installed on your Raspberry Pi.

## Instructions

### 1. Set up a Twitter Developer account

```shell
# Visit the Twitter Developer portal (developer.twitter.com) and sign up for a Twitter Developer account.
# Create a new Twitter app and generate the necessary API keys and access tokens.
```

### 2. Install the required libraries

Open a terminal on your Raspberry Pi and run the following command to install the Tweepy library:
pip install tweepy


### 3. Create the Bot Script

```python3
import tweepy

consumer_key = 'your_consumer_key'
consumer_secret = 'your_consumer_secret'
access_token = 'your_access_token'
access_token_secret = 'your_access_token_secret'

# Authenticate with Twitter API
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)


```python3
import pyjokes
import time


def tweet_joke():
    # Get a random joke
    joke = pyjokes.get_joke()

    # Post the joke as a tweet
    api.update_status(joke)

# Tweet a joke every hour
while True:
    tweet_joke()
    time.sleep(3600)  # Sleep for an hour


### 4. Test, run, deploy
```shell
# Save the script and run it on your Raspberry Pi:
python twitter_bot.py
```shell
# To keep the bot running continuously, you can deploy it on a cloud server or set it up to run automatically on Raspberry Pi startup.
# For cloud deployment, services like Heroku, AWS, or DigitalOcean can be used to host your bot script.
# For Raspberry Pi, you can configure it to run the bot script automatically on startup by adding an entry in the `rc.local` file or using a tool like `systemd`.

