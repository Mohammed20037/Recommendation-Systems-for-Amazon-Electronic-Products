# Recommendation Systems for Amazon Electronic Products

This project focuses on developing and analyzing various recommendation systems tailored for Amazon's electronics products. By leveraging real-world datasets and advanced algorithms, the project showcases how personalized and effective recommendations enhance user experiences and satisfaction.

## Overview

E-commerce platforms like Amazon rely on robust recommendation systems to connect users with products that meet their preferences and needs. In this project, we implemented three types of recommendation systems:

1. **Popularity-Based Recommender**  
   A simple model that ranks products by overall popularity.

2. **Collaborative Filtering**  
   A personalized system using user-product interactions to predict preferences.

3. **Hybrid Recommender**  
   A combination of collaborative filtering and product similarity techniques to provide refined recommendations.

The objective is to explore the strengths and limitations of each approach and demonstrate how they can be applied to real-world datasets.

## Dataset

We used the **Amazon Product Reviews Dataset**, specifically focusing on the electronics category. The dataset can be downloaded from Kaggle:

[Amazon Product Reviews Dataset on Kaggle](https://www.kaggle.com/datasets/saurav9786/amazon-product-reviews)

### Dataset Features

- **userId**: Unique identifier for each user.
- **productId**: Unique identifier for each product.
- **Rating**: User-provided rating for a product.
- **timestamp**: The time the rating was given (not used in this analysis).

The dataset contains over 7 million rows, making it ideal for large-scale recommendation system analysis.

## Features and Methodology

### Popularity-Based Recommender

- **Description**: Ranks products based on their popularity, calculated using a weighted scoring system.
- **Methodology**:
  - Utilized IMDB's **Weighted Rating Formula**:
    \[
    \text{Weighted Rating (WR)} = \left(\frac{v}{v + m} \cdot R\right) + \left(\frac{m}{v + m} \cdot C\right)
    \]
    Where:
    - **v**: Number of ratings for the product.
    - **m**: Minimum number of ratings required to qualify.
    - **R**: Average rating of the product.
    - **C**: Mean rating across all products.
  - Sorted products based on their weighted scores.
- **Output**: A universal list of the top-10 most popular products, shared across all users.

### Collaborative Filtering

- **Description**: A personalized approach that uses user-product interactions to recommend products.
- **Methodology**:
  - Implemented using the **Surprise Library**, a Python toolkit for recommendation systems.
  - Employed **Singular Value Decomposition (SVD)** to reduce dimensionality and uncover latent factors in the user-item matrix.
  - Evaluated performance using **Root Mean Square Error (RMSE)** and **K-Fold Cross-Validation**.
- **Output**: Predicted personalized ratings for users, achieving an RMSE of ~1.29.

### Hybrid Recommender

- **Description**: Combines collaborative filtering with product similarity techniques for a balanced and robust recommendation system.
- **Methodology**:
  - Used the **`corrwith()`** method to compute Pearson correlation coefficients for product similarity.
  - Integrated collaborative filtering to predict ratings for similar products.
  - Designed to take a **userId** and **productId** as input and suggest up to 5 similar products tailored to the user.
- **Output**: Highly refined recommendations combining product similarity and personalized ratings.

## Implementation Steps

1. Clone the repository and navigate to the project folder:
   ```bash
   git clone https://github.com/Mohammed20037/Recommendation-Systems-for-Amazon-Electronic-Products.git
   cd Recommendation-Systems-for-Amazon-Electronic-Products
   pip install -r requirements.txt
   jupyter notebook recommendation-system-for-electronic-dataset.ipynb

## Results

- **Popularity-Based Recommender**: Produced a generalized list of the top-10 most popular products.
- **Collaborative Filtering**: Delivered personalized recommendations with an RMSE of ~1.29.
- **Hybrid Recommender**: Suggested products tailored to individual user preferences, combining product similarity and predicted ratings.

## Future Enhancements

- **Content-Based Filtering**: Incorporate product descriptions, features, and categories for more refined recommendations.
- **Deep Learning Models**: Explore advanced techniques such as Autoencoders or Neural Collaborative Filtering for enhanced accuracy.
- **Implicit Feedback**: Include user interactions such as clicks, views, and time spent on products to improve recommendations.

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute this project, provided you include the original license file and attribution to the author.

See the [LICENSE](LICENSE) file for more details.


