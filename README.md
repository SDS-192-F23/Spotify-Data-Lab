[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/ypNBYwsR)
# lab-3
# Today's Dataset

1. Spotify has an [Application Programming Interface (API)](https://en.wikipedia.org/wiki/API) that allows us to access data about music on the platform.
2. We can access data about specific songs, playlists, and artists.
3. Variables include things such as acousticness, danceability, and speechiness, album information, and key.

# Step 1: Install and Load Packages

In your console install the Spotify R package:

`install.packages("spotifyr")`

Then load the packages for this lab by running the code below. 

```{r}
# Load packages
library(tidyverse)
library(spotifyr)
```

# Step 2: Create a Spotify Developer Account

1. Log-in to Spotify.com or create an account.
2. Go to [https://developer.spotify.com/dashboard](https://developer.spotify.com/dashboard)
3. Create an app named "SDS192 Lab 3". You can indicate that this is "for Lab 3".
4. Click "SHOW CLIENT SECRET".
5. Copy client id and secret into the chunk below to replace the current client id and secret, and then run the code chunk.

```{r}
id <- 'c283abfcc1c94026a6075358ab4ecfbe'
secret <- '3ee9ec4cd1cf433a8d3be549212f2a67'
Sys.setenv(SPOTIFY_CLIENT_ID = id)
Sys.setenv(SPOTIFY_CLIENT_SECRET = secret)
access_token <- get_spotify_access_token()
```

# Step 3: Get Song Features for Your Favorite Artist

Replace the text Janelle Monae below with the name of your favorite artist and then run the code chunk. 

```{r}
artist <- get_artist_audio_features(artist = "Janelle Monae") |>
  select(-c(album_images, artists, available_markets))
```

# Step 4: View the Data Using Two Approaches

View the artist data frame you have created. 

```{r}
# Write your code below

```

```{r}
# Write your code below

```

# Step 5: Create a Histogram Visualizing the Distribution of Values in a Song Feature of Your Choice

(1) Be sure to add labels to your plot.
(2) Set appropriate `binwidth` for bins.
(3) Set the line color for bins.

```{r}
# Write your code below 

```

**Discussion**: How do you interpret this plot?
> Interpreting histograms: (1) Peaks; (2) Spread; (3) Skewed data; (4) Outliers.

**Answer**:

# Step 6: Facet Your Previous Plot by Album Name

Set `nrow` of your choice in the `facet_wrap` function.

```{r}
# Paste the code below and adjust it 

```

**Discussion**: What do the distributions indicate? What do you learn when comparing distributions across albums?

**Answer**:

# Step 7: Create a Stacked, Dodged, or Filled Barplot Visualizing the Frequency of Songs in Each Album and Key Mode for This Artist

Use the `coord_flip()` function to flip the x-axis and the y-axis. Also, be sure to add labels to your plot.  

```{r}
# Write your code below

```

# Step 8: Reorder the x-axis of Your Previous Plot

I want to reorder my x-axis, so I will place the `reorder()` function around my x aesthetic, and assign the following arguments:

* the values to be reordered: `key_mode`
* the values will serve as the basis for reordering: `key_mode`
* and a function to determine how values will be reordered: `length`

```{r}
# Paste the code below and adjust it

```

**Discussion**: What do the frequencies indicate? What do you learn when comparing frequencies across albums?

**Answer**:

# Step 9: Create Grouped Boxplots Visualizing the Distribution of Values in a Song Feature of Your Choice, Grouped by Album Name

Use the `coord_flip()` function to flip the x-axis and the y-axis. Also, be sure to add labels to your plot. 

```{r}
# Write your code below

```

# Step 10: Reorder the x-axis of Your Previous Plot

I want to reorder my x-axis, so I will place the `reorder()` function around my x aesthetic, and assign the following arguments:

* the values to be reordered: `album_name`
* the values will serve as the basis for reordering: `valence` (yours will be the song feature of your choice)
* and a function to determine how values will be reordered: `median`

```{r}
# Paste the code below and adjust it

```

**Discussion**: How do you interpret this plot? 
> Interpreting boxplots: (1) Check for outliers; (2) Compare medians; (3) Compare the ranges; (4) Compare the IQRs; (5) Compare the symmetry. (Questions in Lec 6 Slides Page 14-18 will be a good guide to answer this.)

**Answer**:

# Step 11: Ethical Considerations

**Discussion**: Check out [this article](https://www.vox.com/culture/22814121/spotify-wrapped-2021-algorithm-data-privacy) documenting ethical concerns regarding Spotify’s data collection practices. Should we be concerned about the assumptions that Spotify makes about us based on our music streaming habits? What about the way they curate music for us? What are some of the social consequences to this form of user surveillance? (no more than 150 words) ^[Here is an example footnote to be used as a citation.]

> Use the readings under Lec 10 on our course webpage as references for answering this question.

**Answer**:


