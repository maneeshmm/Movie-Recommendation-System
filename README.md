# Project Report: Movie Recommendation System

## 1. Introduction

The Movie Recommendation System is designed to provide users with personalized movie suggestions based on their input. The project leverages a collaborative filtering approach using k-Nearest Neighbors (k-NN) to identify similar movies based on user preferences. The final model is deployed as an interactive web application using Gradio.

## 2. Dataset Overview

The system utilizes two datasets:

movies.csv: Contains movie information, including movieId and title.

ratings.csv: Includes user ratings for different movies with columns userId, movieId, and rating.

## 3. Data Preprocessing

The ratings data is transformed into a matrix using the pivot function, where rows represent movieId, columns represent userId, and values are the corresponding ratings.

Missing values in the matrix are filled with 0 to maintain consistency.

Users who have rated fewer than 50 movies and movies that received fewer than 10 ratings are removed to enhance recommendation accuracy.

The final dataset is converted into a Compressed Sparse Row (CSR) Matrix to optimize performance.

## 4. Exploratory Data Analysis (EDA)

Several visualizations were generated:

Distribution of user ratings: Plotted to understand the voting patterns.

Movies vs. Number of Ratings: Showed that some movies are rated more frequently than others.

A threshold of 50 votes per user and 10 votes per movie was applied to remove outliers and improve model efficiency.

## 5. Building the Recommendation Model

The k-Nearest Neighbors (k-NN) algorithm is used to find similar movies based on cosine similarity:

Brute-force search is used as the algorithm for distance computation.

The number of neighbors (n_neighbors) is set to 20.

The kneighbors() function is applied to find the 10 most similar movies for a given input movie.

The recommendation function works as follows:

Searches for a movie in the dataset based on the input title.

Retrieves its corresponding movieId.

Uses kneighbors() to find similar movies.

Returns a list of recommended movies ranked by similarity.

## 6. Deploying the Model using Gradio

The recommendation function is integrated into a Gradio web application:

User Input: Users enter a movie name.

Backend Processing: The model finds the most similar movies.

Output: The application displays the recommended movies in a user-friendly format.

## 7. Conclusion

This project successfully implements a collaborative filtering-based movie recommendation system. By leveraging k-NN and cosine similarity, users can receive movie suggestions based on their preferences. The integration with Gradio makes the system accessible via a web interface. Future improvements may include incorporating content-based filtering and deep learning techniques for enhanced recommendations.

