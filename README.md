## What drives a track's popularity? And exploratory data analysis

THis repository contains an exploratory data analysis of this Spotify data: https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks

Findings are summarized in this Medium post (still in draft): https://medium.com/@louisbrutton/what-drives-a-tracks-popularity-on-spotify-b4b10e9554c

This contains over 160K tracks from Spotify, each with their 'audio features' - kpis measured by Spotify such as 'danceability' and 'speechiness'. It also has a bunch of meta information about each tracks (the name, release year and artist). And perhaps most importantly, it has a popularity score, based on how often and how recently the track has been listened to.

Our primary motivation for this project is to look at what predicts track popularity? Can we build a model that can accurately predict a track's popularity based on known data and the Spotify's audio features?

## Contents of the repository:

- data.csv: main dataset with all Spotify track info
- data_by_artist.csv: secondary dataset with artist information
- data_by_genre.csv: secondary dataset with genre information
- data_by_year.csv: yearly dataset
- data_w_genre.csv: data_by_artist dataset with genres added 
- eda_notes.ipynb: basic notes for this project, might delete later
- spotify_eda.ipynb: main jupyter notebook with all code for this EDA!

## Business questions:

We wanted to answer the following questions:
- Looking at the audio features, which ones influence popularity?
- Does this influence change over time? Ie: do we see different correlations between features and popularity for tracks released in the 60s, compared to tracks released in in 2020?
- Does this change based on the musical genre of the track? 
- How accurately can we predict a track's popularity score using its metadata and its audio features?

## Conclusions:

In summary, we found that we can indeed build a pretty accurate (r-squared > 0.75) linear model to predict track popularity. However, it seems that the main factor influencing popularity is the track's release year, with audio features such as danceability (positive impact) and speechiness (negative impact) influencing the result to a lesser degree. 
This is mostly constant over time, although we do see that explicitness becomes more important as we get closer to 2020, as does danceability. 
Regarding the musical genres, we found that restricting ourselves to a specific genre makes our models less accurate, and conclusions are harder to draw. 

## Libraries used:

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

## Acknowledgements:

- I used this solution to be able to break up the genre column into manageable chunks: https://github.com/softhints/python/blob/master/notebooks/pandas/Pandas_count_values_in_a_column_of_type_list.ipynb
- This article (which I came across after I finished the work here) offers a different perspective, with some similar conclusions: https://towardsdatascience.com/what-makes-a-song-likeable-dbfdb7abe404
- I re-used a few functions and code snippets from the Udacity course: Introduction to Data Science
