---
layout: post
title: "Introduction of Python in Data Science"
date: 2016-03-31
---


### Python basics
1. Get financial data
%matplotlib inline
import matplotlib.pyplot as plt
import matplotlib.patheffects as PathEffects
import matplotlib
from sklearn import datasets, preprocessing
import numpy as np
import datetime as dt
import pandas as pd
import pandas.io.data as web
import urllib2
import csv


start_dt=dt.datetime(2015,1,1)
end_dt = dt.datetime(2016.3.24)
symbol = 'AMZN'
daily_data = web.DataReader(symbol,"yahoo",start_dt,end_dt)
daily_data.shape
daily_data.ix[:,['High','Low']].plot()

daily_data.ix[0]
daily_data.ix[0,'Open']
types = daily_data.columns.tolist()
types
pd.rolling_mean(daily_data['Close'],window=12).plot(style='-g')
pd.rolling_corr(daily_data['Open'],daily_data['Close'],window=120).plot(style='-g')
close_change_df = daily_['Close'].pct_change(1)
close_change_df.plot(style='-g')


freqs = range(1,20)
for freq in freqs:
	for t in types:
		daily_data['i_'+t+'_'+str(freq)] = daily_data[t].pct_change(periods=freq)
daily_data.columns







### Reference
[Introduction of Python in Data Science](https://youtu.be/eermjNGj9-M)