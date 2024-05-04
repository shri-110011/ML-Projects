## Movie Recommender System:

  

**Dataset Overview:**

TMDB 5000 Movie Dataset from Kaggle. The dataset has 2 CSV files.
1. tmdb_5000_movies.csv: It contains movie features data. It has 4803 rows and 20 columns.
2. tmdb_5000_credits.csv: It contains credit information for both the cast and crew. It has 4803 rows and 4 columns.

**Objective:**

To create a Content-Based Movie recommender system that could suggest movies based on the exact movie name or some movie query provided by the user.

**Approach:**
1. Checked for duplicate values in both movies and credits data frames(No duplicates found).

2. Analyzed the features of both data frames to figure out the relevant features for building the recommender system and also to find a common column using which we can merge the 2 data frames.

- This analysis leads to the following conclusion:
**'genres', 'id', 'keywords', 'original_language', 'overview', 'release_date', 'runtime', 'spoken_languages', 'tagline', 'title', 'cast', 'crew'** are the significant features for this task.

- But since we do not have user profile information in this project therefore we would not use **'original_language', 'spoken_languages', 'runtime'**.

- We are dropping 'tagline' because over 17% missing values are there. And imputing them based on **'overview'** means increased complexity of the recommender system.

- Dropping the rows having null value for **'release_date'** and **'overview'**.

3. Applied transformations to the following columns:
-  **'genres'**: Extracted the genre names for each movie from the 'genres' columns put them into a list and then replaced the 'genres' column with this list.
- **'keywords'**: Extracted the keyword names for each movie from the 'keywords' columns put them into a list and then replaced the 'keywords' column with this list.
- **'cast'**: Extracted the main 4 casts from the 'cast' column. According to the metadata, casts are listed in the order
they appear in the credits.
- **'crew'**: Extracted the director name for each film from the 'crew' column.
- **'release_date'**: Extracted the movie release year for each film from the 'release_date' column and then replaced the 'release_date' column with this release year.
- **'overview'**: Applied text pre-processing to the 'overview' column and created a list of normalized tokens and then replaced the 'overview' column with this list.

4. Created a column named **'Context'** which contains the attributes of each corresponding movie. These attributes are: **'genres', 'keywords', 'overview', 'release_date', 'cast', 'crew'**

5. Used **CountVectorizer** to create a token count matrix.

6. Used **cosine similarity** to get a similarity matrix that contains the similarity scores for each movie compared against each other movie.

7. Created high-level functions to get similar movies based on the content.

**search_related_movies_by_name(movie_name, count):**
- movie_name: a valid movie name that should be there in the dataset
- count: specifies the number of similar movies to be recommended as per the movie_name
- Print movies similar to the movie_name

**search_related_movies_by_query(query, count):**
- Print movies similar to the query

**movie_recommender(query, is_movie_name=True, count=5):**
- If is_movie_name = True then query is treated as exact movie name and **search_related_movies_by_name(movie_name, count)** is called.
- Else if is_movie_name = False then the query is treated as some movie-related query and **search_related_movies_by_query(query, count)** is called.