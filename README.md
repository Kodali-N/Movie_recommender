
# Project Title

## Overview

A content based movie recommendation system
that recommends movies based on factors such 
as genres, cast, and the overview.

## Dataset:

## Data Cleaning:
- dropping the follwoing columns:
    - Budget
    - Homepage
    - Original_language
    - original Title
    - popularity
    - production companies
    - production companies
    - release Dataset
    - revenue
    - run time
    - spoken languages
    - status
    - tagline
    - vote average
    - vote count

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
    mean the same but the suffix xhanges based on
    sentence and the context. Used'PorterStemmer' from
    nltk for the task.
- To calculate the distance between the vectors,
    I used cosine similarity from sklearn. Store
    the vallues in an array
- To find teh five movies that matched the most, 
    we sort the values along with the movie ID's.

## Website:
- we fetch the posters for the recommended 
    movies using the tmdb API.
    
