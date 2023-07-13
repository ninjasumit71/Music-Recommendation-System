# Content-Based Song Recommender System

This repository contains code for a content-based song recommender system. The system uses the lyrics of songs to find similar songs and recommends them based on their similarity scores.

## Setup

To run the code, follow these steps:

1. Mount Google Drive by executing the following code:
```
from google.colab import drive
drive.mount('/content/drive')
```

2. Import the required libraries:
- numpy
- pandas
- sklearn
- typing

3. Load the song data:
- Read the 'songdata.csv' file into a pandas DataFrame.
- Sample 5000 songs from the DataFrame and remove the 'link' column.
- Replace newline characters in the 'text' column of the DataFrame.

4. Compute TF-IDF vectors for the song lyrics:
- Create a TfidfVectorizer object with English stop words.
- Transform the song lyrics into a TF-IDF matrix.

5. Calculate cosine similarities between songs:
- Compute pairwise cosine similarities between the TF-IDF vectors.
- Store the similarities in a dictionary, where each song is associated with its most similar songs.

6. Define the ContentBasedRecommender class:
- The class takes the similarity matrix as input during initialization.
- It provides a method to recommend similar songs based on a given song.

7. Create an instance of the ContentBasedRecommender:
- Pass the similarity matrix to the constructor.

8. Make song recommendations:
- Define a dictionary specifying the song and the number of similar songs to recommend.
- Call the `recommend` method of the ContentBasedRecommender instance, passing the recommendation dictionary.

## Example Usage

Here's an example of how to use the recommender system:

```python
recommendation = ContentBasedRecommender(similarities)

song_recommendation = {
 "song": songs['song'].iloc[10],
 "number_songs": 4
}

recommendation.recommend(song_recommendation)
