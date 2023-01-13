# ChatGPT_Trading_Bot

This is the code for the "ChatGPT Trading Bot" Video by Siraj Raval on Youtube

## Overview

This is the code for this video on Youtube by Siraj Raval on building a ChatGPT trading bot. First, a disclaimer - Do NOT invest any money in any type of trading bot or algorithmic engine that you are not willing to lose. I gave this trading bot $2000 because I was willing to lose $2000 to make a great video for my AI Wizards out there. The entire codebase is contained in a single iPython notebook file, first published by the FinRL team as an example. Inside the notebook, 5 steps are performed.

1. Pull 30 days of trading data for (Insert your stock or crypto) with Yahoo Finance Downloader API
2. Create a simulated trading environment using real trading data with FinRL
3. Train an neural network to predict that Stock Price using reinforcement learning inside this simulation with FinRL
4. Once trained, backtest the predictions on the past 30 days data to compute potential returns with FinRL
5. If the expectd returns are above a certain threshold, buy, else hold. If they're below a certain threshold, sell. (using Alpaca API)

In order to have this Colab run automatically once a day, we can deploy it to a hosting platform like Vercel with a seperate file that repeatedly executes it. [This](https://vercel.com/guides/how-to-setup-cron-jobs-on-vercel) explains how to do that.

## Dependencies 

- Python 3.7 
- Alpaca SDK
- FinRL 
- Vercel (Optional)

## Setup Instructions

1. Download the iPython notebook in this repository and upload it to [Colab](colab.research.google.com) to try it out.
2. To set up a cron job for a Flask app deployed on Vercel that executes a Google Colab notebook at a given link every hour, you can use the built-in Vercel cron feature. Here are the steps to follow:
3. In your Flask app, import the necessary modules to run the Colab notebook, such as gdown or pyngrok
4. Create a new endpoint in your Flask app that triggers the execution of the Colab notebook, using the link to the notebook file.
5. Go to the Vercel project settings for your app and navigate to the "Cron" tab.
6. Create a new cron job that runs every hour by adding the endpoint you created in step 2 to the "Cron Job" field and select the frequency you want to run the job.

Here is a sample code snippet for step 2:

```python

from flask import Flask, jsonify
import gdown
app = Flask(__name__)

@app.route('/run-colab')
def run_colab():
    gdown.download('https://drive.google.com/file/d/<colab_notebook_id>', 'colab.ipynb', quiet=False)
    return jsonify(message='colab notebook ran successfully')

```

## Credits & More Resources

Credits for the notebook go to the AI4FinanceFoundation, and for the API go to Alpaca.
