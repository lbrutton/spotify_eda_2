An exploratory data analysis of this Spotify data: https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks

This contains over 160K tracks from Spotify, each with their 'audio features' - kpis measured by Spotify such as 'danceability' and 'speechiness'. It also has a bunch of meta information about each tracks (the name, release year and artist). And perhaps most importantly, it has a popularity score, based on how often and how recently the track has been listened to.

Our primary motivation for this project is to look at what predicts track popularity? Can we build a model that can accurately predict a track's popularity based on known data and the Spotify's audio features?

We wanted to answer the following questions:
- Looking at the audio features, which ones influence popularity?
- Does this influence change over time? Ie: do we see different correlations between features and popularity for tracks released in the 60s, compared to tracks released in in 2020?
- Does this change based on the musical genre of the track? 
- How accurately can we predict a track's popularity score using its metadata and its audio features?

In summary, we found that we can indeed build a pretty accurate (r-squared > 0.75) linear model to predict track popularity. However, it seems that the main factor influencing popularity is the track's release year, with audio features such as danceability (positive impact) and speechiness (negative impact) influencing the result to a lesser degree. 
This is mostly constant over time, although we do see that explicitness becomes more important as we get closer to 2020, as does danceability. 
Regarding the musical genres, we found that restricting ourselves to a specific genre makes our models less accurate, and conclusions are harder to draw. 

Libraries used:
import pandas as pd
import matplotlib.pyplot as plt
import sklearn as sc
from sklearn.model_selection import train_test_split
import numpy as np
import ast
from scipy import stats
import seaborn as sns
from sklearn.linear_model import LinearRegression
from collections import Counter

