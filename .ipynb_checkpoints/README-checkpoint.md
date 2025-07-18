# Spotify Data Project: Recent Trends and Relationships

## **Purpose**

As the parent of children who are full-fledged members of what one might call "the Spotify generation," I was intrigued when I encountered [this recent dataset](https://www.kaggle.com/datasets/devdope/200k-spotify-songs-light-dataset/data) containing a wide range of characteristics of about 237K songs on that platform.

Upon closer inspection, there seemed to be enough data to ask and possibly answer such questions as:

1. How have some of the core features of music changed over time?

2. How has the likelihood that a song contains explicit lyrics changed over time?

Finally, I thought the "Spotifiers" themselves might be as interested in the answers to these questions as I was.

## Exploratory Data Analysis

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

### Categorical Data

The categorical data was displayed in these bar graphs:

![bar graphs](https://musicproject1.carrd.co/assets/images/image01.jpg?v=603f91ef)

Perhaps the most noteworthy point here is that we have one binary variable, Explicit; two variables with just a handful of unique values, Emotion and Key; and three other variables with many thousands of unique values.

To check whether there are any interesting correlations between 'Emotion' and 'Key', the following crosstab visualization was created:

![emokey](https://musicproject1.carrd.co/assets/images/image02.jpg?v=603f91ef)

C Maj seems to correlate well with both Joy and Sadness, while C# Maj correlates well with Joy. Also, D Maj and G Maj correlate well with Joy. The association of the major chords with Joy is certainly not surprising, but the connection between C Major and Sadness might be unexpected.

Another question that suggests itself is, "Is there a relationship between Emotion and Explicitness?" Let's check the visualization:

![emoexp](https://musicproject1.carrd.co/assets/images/image25.jpg?v=603f91ef)

Not unexpectedly, songs classified as expressing Joy or Sadness show a high likelihood to be non-explicit. More surprising is the fact that songs expressing Anger and Joy have equal likelihoods of being explicit.

### Numerical Data

Turning to the numerical columns, we first created histograms for them. Each histogram shows the trend line, the mean, and the standard deviation of the column.

![histo1](https://musicproject1.carrd.co/assets/images/image03.jpg?v=603f91ef)

A few observations on the above:
- The mean Date of the songs is 2008, with a left-skew distribution.
- Tempo is roughly bi-modal, with a mean of 121, the "disco" tempo.
- Popularity is not far from bell-shaped, except for the slight surge of very unpopular songs.
- Energy has a very interesting shape, left-skewed but nearly following the "3 standard deviation" rule.

![histo2](https://musicproject1.carrd.co/assets/images/image04.jpg?v=603f91ef)

An observation on the 'Instrumentalness' histogram:

The extreme skewness of this column reminds one of the many times members of the "Spotify generation" may be heard to ask, "Where are the words?" -- in extreme wonder at hearing a song that was extremely popular in the past and yet contained not a single vocal.

Let's look at the heatmap of the linear correlations among the numerical columns:

![heat](https://musicproject1.carrd.co/assets/images/image05.jpg?v=603f91ef)

Observations on the heatmap:

The strongest positive linear correlations are between Date and Variance, Energy and Loudness,
and Positiveness and Danceability. The latter two pairs seem obvious and to be expected. As for Date and Variance, this may be due to the increase, over time, in the use of devices and "instruments" capable of producing more exotic and previously-unknown variations of sound. The advent of synthesizers and, later, computer-generated music, are examples of these.

The strongest negative linear correlations are between Acousticness and Loudness and between Acousticness and Energy, neither of which is surprising.

After looking at the heatmap and a heavily downsampled pairplot of all the columns (1 dot = 235 values), we found some plots worth examining in more detail:

Here we have Popularity over Date, shading for Explicitness:

![popdate](https://musicproject1.carrd.co/assets/images/image06.jpg?v=603f91ef)

There is no clear correlation between the plotted columns (r = 0.04, see above), but increasing explicitness is clearly visible beginning in the late 1990s.
This is an answer to one of our initial questions, regarding the way music has changed over time.

Here is Energy over Date, shading for Explicitness:

![enerdate](https://musicproject1.carrd.co/assets/images/image07.jpg?v=603f91ef)

Again, there is no clear linear correlation between the plotted columns (r = 0.09, see above), but increasing explicitness is clearly visible beginning in the late 1990s. Also, note that the explicit songs tend to be higher on the Energy axis. This suggests another relationship which will be examined in what follows.

Plot Energy Over Loudness, Shading for Explicitness:

![enerloud](https://musicproject1.carrd.co/assets/images/image08.jpg?v=603f91ef)

Here we have a clear positive correlation (r = 0.75, see above) and, interestingly, the explicit songs tend to be on the upper-right part of the scatterplot, indicating that they tend to be louder and more energetic. This will also be examined below.



















# [Detailed ReadMe of the Project](https://musicproject1.carrd.co/ "Spotify Dataset Project")
