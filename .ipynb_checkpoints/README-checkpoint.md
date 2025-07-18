# Spotify Data Project: Recent Trends and Relationships

## **Purpose:**

As the parent of children who are full-fledged members of what one might call "the Spotify generation," I was intrigued when I encountered [this recent dataset](https://www.kaggle.com/datasets/devdope/200k-spotify-songs-light-dataset/data) containing a wide range of characteristics of about 237K songs on that platform.

Upon closer inspection, there seemed to be enough data to ask and possibly answer such questions as:

1. How have some of the core features of music changed over time?

2. How has the likelihood that a song contains explicit lyrics changed over time?

Finally, I thought the "Spotifiers" themselves might be as interested in the answers to these questions as I was.

## Exploratory Data Analysis:

The raw data, in CSV format, contains 236,988 rows and 18 columns. The names and data types of the columns are:

Artist               object
Song                 object
Emotion              object
Variance            float64
Genre                object
Date                  int64
Key                  object
Tempo                 int64
Loudness            float64
Explicit             object
Popularity            int64
Energy                int64
Danceability          int64
Positiveness          int64
Speechiness           int64
Liveness              int64
Acousticness          int64
Instrumentalness      int64

There were no missing or null values aside from 8 in the Song column. Since this column contains 159,730 unique values, these were ignored.

The categorical data was displayed in these ![bar graphs](https://musicproject1.carrd.co/assets/images/image01.jpg?v=603f91ef)




# [Detailed ReadMe of the Project](https://musicproject1.carrd.co/ "Spotify Dataset Project")
