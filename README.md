# Trading Analysis Bot

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

<a href="https://t.me/trading_analysis_bot"><img src="https://github.com/trinhvv/trading-analysis-bot/blob/master/img/avatar.png" align="left" hspace="5" vspace="3" width="90"></a>

**Trading Analysis Bot** is a Telegram chatbot for data-driven analytics of cryptocurrencies market, particularly the Binance exchange. It provides standard technical indicators, social sentiment and developer activities. Market indexes, rankings and statistic metrics based on on-chain transactions across different blockchain networks are also reported.

## Requirements

- Telegram library: python-telegram-bot
- Exchange library: python-binance
- Computational libraries: numpy, TA-lib
- Visualization library: matplotlib
- Database library: psycopg2

## Features

- Technical indicators: RSI, MA, BB, etc
- Order flow: Buy vs sell, Volume profile, Limit orderbook
- Cryptoasset indexes: Bletchley, Bitwise, CRIX
- Cryptoasset metrics: TX vol, NVT ratio, No. active addresses, No. transactions
- Social sentiment and developer activities: Twitter, Reddit, Facebook, GitHub
- Trading sessions
- Customized notifications
- Administrator and user management

## Run on local machine

```
pip install -r requirements.txt
pip install TA-lib
```

```
# For Windows
set TELEGRAM_TOKEN=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX 
set SECRET_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX 
set API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set DB_NAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set DB_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set DB_HOST=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set DB_PASSWORD=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set ADMIN_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
set ADMIN_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
python bot.py
```

```
# For Linux
export TELEGRAM_TOKEN=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX 
export SECRET_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX 
export API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export DB_NAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export DB_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export DB_HOST=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export DB_PASSWORD=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export ADMIN_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
export ADMIN_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
python bot.py
```

## Deployment on Heroku platform

```
heroku create trading-analysis-bot --buildpack heroku/python
heroku buildpacks:add --index 2 https://github.com/numrut/heroku-buildpack-python-talib
heroku config:set TELEGRAM_TOKEN=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set SECRET_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set DB_NAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set DB_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set DB_HOST=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set DB_PASSWORD=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set ADMIN_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
heroku config:set ADMIN_USERNAME=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
git push heroku master
heroku ps:scale bot=1 
```

## Screenshots

### General information
```
/i zrx
```
```
Symbol: ZRX Name: 0x
Community (Reddit, Facebook, Twitter)
- Facebook likes: 1240
- Reddit average comments 48h: 2.5
- Reddit accounts active 48h: 2898
- Twitter followers: 134515
- Reddit subscribers: 13784
- Reddit average posts 48h: 0.417
Developer (Github)
- Forks: 199
- Commit count 4 weeks: 519
- Closed issues: 114
- Pull requests merged: 567
- Subscribers: 86
- Stars: 785
- Pull request contributors: 33
- Total issues: 146
```

### Transactions statistics
```
/t zrx 1
```
```
#ZRXBTC: 0.0001138
Transactions statistics (Last 500 trades)
From 2018-08-17 00:15:34 to 2018-08-17 00:40:52 (UTC)
~ 0$: Buy 35 vs Sell 10
~ 1-10$: Buy 22 vs Sell 22
> 100$: Buy 105 vs Sell 122
> 200$: Buy 77 vs Sell 79
> 500$: Buy 32 vs Sell 25
> 1,000$: Buy 13 vs Sell 15
> 2,000$: Buy 9 vs Sell 11
> 5,000$: Buy 1 vs Sell 6
> 10,000$: Buy 1 vs Sell 1
Total: Buy 261 (85,760$) vs Sell 239 (121,247$)
```
<img src="img/t_zrx_1.png" width="700">

### Order flow
```
/a zrx
```
<img src="img/a_zrx_1h.jpg" width="700">
<img src="img/a_zrx_30m.jpg" width="700">

### Cryptoasset indexes
```
/m
```
<img src="img/bletchley_index.jpg" width="700">
<img src="img/crix_index.jpg" width="700">

### Trading sessions
```
/h
```
<img src="img/h.png" width="700">

## Licence
MIT

## Support and Donation

- Star and/or fork this repository
- Trade on Binance: https://www.binance.com/?ref=13339920
- Trade on Huobi: https://www.huobi.br.com/en-us/topic/invited/?invite_code=x93k3
- BTC tipjar: 1DrEMhMP5rAytKyKXRzc6szTcUX8bZzZgq
- ETH tipjar: 0x3915D216f9Fc6ec08f956555e84385513dE5f214
- LTC tipjar: LX8GJkGTZFmAA7puCyVp48333iQdCN6vca
