# movie_recommendation_sys
## What is recommendation system 
Recommendation system predicts relevant items based on previous data like product ratings, watching films. Ex: netflix recoommends similar genre movies based on our previous watches or likes or an e-commerce recommends products based on our previous search.
## Types of recommendation system 
1. Content based filtering : relevant ites are shown based on our context of previous searched items by the user.
2. Colloborative based filtering : recommending the new items to users based on interest and preference of similar users is basically colloborative-based filtering.
ex: amazon recommends saying "customers who bought this also bought these ".

## Project Flow
Data -> Preprocessing -> Model Building -> Website -> deploy 
## Data 
* tmdb_5000 movies dataset is used
* tmdb_credits dataset is used.
* append credits dataset to movies dataset.
* features - budget, genres, homepage, id, keywords, original_language, original_title, overview, popularity, production_companies, production_countries, release_date, revenue, runtime, spoken_languages, status, tagline, title, vote_average, vote_count.
* There are 4809 rows and 20 columns
## Preprocessing 
* Features considered for project are id, genre, keywords, title, overview, release date, cast, crew.
* There are no null values.
* genre is in strings of dictionary format, converting it to dictionary using ast.literal_eval() function.
* from the cast feature, considering only top 3 casts like actor, actress and from the crew director name.
* combining features overview, keywords, genres, cast and crew into tags feature after splitting them into a list of words from string.
* The final dataset has mailnly three features - id, title, tags.
## Vectorization 
1. Using nltk library, Stemming for words in tags feature.
2. apply CountVectorizer with max_features as 5000 and stop words as English.
3. converting them to an array, they got a shape of 4806 rows and 5000 columns.
## Cosine Similarity 
findout similarity between vectors using cosine similarity
## recommended movies
A function defined to get the top 5 similar movies based on a selected movie.
## Implemented in streamlit. http://localhost:8501/
**app.py has the code for streamlit implementation 
**movie-recommender-system contains code for implementation.

