# ChatGPT_Trading_Bot

This is the code for the "ChatGPT Trading Bot" Video by Siraj Raval on Youtube

## Overview

This is the code for this video on Youtube by Siraj Raval on building a ChatGPT trading bot. First, a disclaimer - Do NOT invest any money in any type of trading bot or algorithmic engine that you are not willing to lose. I gave this trading bot $2000 because I was willing to lose $2000 to make a great video for my AI Wizards out there. The entire codebase is contained in a single iPython notebook file, first published by the FinRL team as an example. Inside the notebook, 5 steps are performed.

1. Pull 30 days of trading data for (Insert your stock or crypto) with Yahoo Finance Downloader API
2. Create a simulated trading environment using real trading data with FinRL
3. Train an neural network to predict that Stock Price using reinforcement learning inside this simulation with FinRL
4. Once Trained, backtest the predictions on the past 30 days data to compute potential returns with FinRL
5. If the expectd returns are above a certain threshold, buy, else hold. If they're below a certain threshold, sell. (using Alpaca API)

In order to have this Colab run automatically once a day, we can deploy it to a hosting platform like Vercel with a seperate file that repeatedly executes it. [This](https://vercel.com/guides/how-to-setup-cron-jobs-on-vercel) explains how to do that.

## Dependencies 

- Python 3.7 
- Alpaca SDK
- FinRL 
- Vercel (Optional)

## Setup Instructions

1. Download the iPython notebook in this repository and upload it to [Colab](colab.research.google.com) to try it out.
2. If you want to run this daily, create a vercel account and add a cron job to this repository to run the notebook once a day

## Credits & More Resources

Credits for the notebook go to the AI4FinanceFoundation, and for the API go to Alpaca.
