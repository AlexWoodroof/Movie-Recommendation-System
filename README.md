# Movie Recommendation System

## Overview

This project involves creating a movie recommendation system using data from The Movie Database (TMDb). The system integrates various data processing techniques to deliver insightful visualizations and a content-based movie recommendation engine.

## Datasets

The project uses two datasets:

1. **Movie Credits**: Contains information about movie credits, including cast and crew.
   - **File**: `tmdb_5000_credits.csv`
   - **Columns**: `id`, `title`, `cast`, `crew`

2. **Movie Details**: Includes detailed information about movies.
   - **File**: `tmdb_5000_movies.csv`
   - **Columns**: `id`, `budget`, `genres`, `original_language`, `popularity`, `release_date`, `revenue`, `runtime`, `status`, `title`, `vote_average`, `vote_count`

3. **Movie Data**: This is the file build from merging the most relevant coloumns from the above files.
   - **File**: `tmdb_5000_data.csv`
   - **Columns**: `id`, `title`, `overview`, `genres`, `original_language`, `popularity`, `keywords`, `cast`, `runtime`, `weighted_score`

## Steps and Processing

### 1. Data Loading and Merging

The datasets are loaded and merged based on the `id` column to consolidate movie information into a single dataframe.

### 2. Data Cleaning

- **Removing Unreleased Movies**: Movies that have not yet been released are filtered out of the dataset.
- **Dropping Unnecessary Columns**: After calculating the weighted scores, columns related to votes are removed as they are no longer needed.

### 3. Weighted Rating Calculation

A weighted rating is computed for each movie to provide a more balanced rating, taking into account the number of votes and average rating, as well as the overall average across all movies. This helps in adjusting for movies that have a high number of votes versus those with fewer votes.



### 4. Visualization

- **Budget vs Popularity**: Explores the relationship between a movie’s budget and its popularity.
- **Revenue vs Popularity**: Examines how revenue correlates with popularity.
- **Budget vs Revenue**: Analyzes the connection between a movie’s budget and its revenue.
- **Genre Frequency**: Creates a bar chart to visualize the frequency of each genre across all movies in the dataset.

### 5. Content-Based Recommendation System

- **TF-IDF Vectorization**: Uses TF-IDF vectorization to transform movie overviews into numerical data, which helps in assessing the textual similarity between movies.
- **Cosine Similarity**: Computes the cosine similarity between movies based on their overviews to recommend similar movies.
- **Recommendation Function**: Provides a function to generate movie recommendations based on the input title by finding the most similar movies.

## Running the Project

1. **Setup**:
   - Ensure all required libraries are installed: `pandas`, `numpy`, `seaborn`, `matplotlib`, `scikit-learn`.
  
```python
pip install pandas numpy seaborn matplotlib scikit-learn
```

2. **Execution**:
   - Run the provided Jupyter Notebook to process data, generate visualizations, and use the recommendation function to find movie suggestions based on titles.

## Contributing

Contributions are welcome! You can improve the recommendation algorithm, enhance data visualizations, or add new features. Please submit pull requests for any changes or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
