
# Movie recommender system

## Overview

A content based movie recommendation system
that recommends movies based on factors such 
as genres, cast, and the overview.

## Dataset:
- [TMDB 5000 Movie dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv)
- [credits dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_credits.csv)


- we merge the movies dataset, and the creadits dataset on title.

## Data Cleaning:
- dropping columns such as Budget, production companies, run time, and other such 
    columns that don't give information about the content of the movie. Columns such as 
    vote count, and vote average are also droped for the same reason.

## Preprocessing:
- taking only first 3 actors from cast column
- choosing only the director from the crew column
- To merge Overview, keywords, cast, crew, genres,
    we convert each record to a list, and append
    them to a new column: 'tags'.

## Text Vectorization:
- To find the similaruty between the tags, we use
    text vectorization.
- Converted the text to vectors using 'Bag of Words'.
- We only take the stem words, as different words 
    mean the same but the suffix changes based on
    sentence and the context. For example, 'acivity'
    and 'activities'. Used'PorterStemmer' from
    nltk for applying stemming.
- To calculate the distance between the vectors,
    I used cosine similarity.
  
## Similarity:
- To find out how similar the movies are, we need to find
    the distance between the vectors.
- We find the cosine distance, i.e, the angle between the vectors.
    based on the angle we get an idea about how similar the movies are. 
    Smaller the value, the more similar the movies are.
- cosine_similarity from sklearn helps us for the task.
- To find the 5 most similar movies, we sort the array of similarity values
    with the movieID

## Website:
- we fetch the posters for the recommended 
    movies using the tmdb API.
- yet to host the website for public


