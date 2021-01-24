An exploratory data analysis of this Spotify data: https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks

This contains over 160K tracks from Spotify, each with their 'audio features' - kpis measured by Spotify such as 'danceability' and 'speechiness'. It also has a bunch of meta information about each tracks (the name, release year and artist). And perhaps most importantly, it has a popularity score, based on how often and how recently the track has been listened to.

We want to answer the following questions:
- Which genres are mostly represented within this dataset?
- Looking at the audio features, which ones influence popularity?
- Does this influence change over time? Ie: do we see different correlations between features and popularity for tracks released in the 60s, compared to tracks released in in 2020?
- Does this change based on the musical genre of the track? 
- How accurately can we predict a track's popularity score using its metadata and its audio features?