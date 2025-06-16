# 📦 Amazon Product Recommendation System

## 📖 Overview

This project focuses on building a recommendation system using the **Amazon Electronics Product Ratings Dataset**. The goal is to recommend relevant products to users based on their previous ratings while exploring multiple collaborative filtering techniques. The dataset includes user-product interactions (ratings), and all product descriptions and reviews have been intentionally removed to avoid content-based bias.

## 🌍 Context

With the exponential growth of online information, users are faced with an overwhelming number of choices. Recommender Systems help alleviate this by providing **personalized suggestions** that improve user experience and drive business outcomes.

Major e-commerce platforms like **Amazon, Walmart, Target**, and **Etsy** invest heavily in recommender systems to optimize customer engagement. Amazon, in particular, leverages **item-to-item collaborative filtering** at scale to power its product recommendations.

## 🎯 Objective

As a Data Science Manager at Amazon, your task is to:
- Build a **recommendation system** using historical user-product ratings.
- Extract **meaningful insights** from user interaction data.
- Compare multiple **recommendation algorithms**.
- Evaluate model performance using industry-standard metrics.

## 📂 Dataset

The dataset contains:
- `userId`: Unique ID for each user
- `productId`: Unique ID for each product
- `Rating`: User’s rating for the product (target variable)
- `timestamp`: Time of rating (not used in this project)

## 📌 Recommendation System Concepts

- **Relevant Item**: Actual rating is above a set threshold
- **Recommended Item**: Predicted rating is above the threshold
- **False Positive (FP)**: Irrelevant item recommended
- **False Negative (FN)**: Relevant item not recommended

### 📊 Evaluation Metrics

- **Precision@k**: Proportion of top-k recommended items that are relevant
- **Recall@k**: Proportion of relevant items present in top-k recommendations
- **F1-score@k**: Harmonic mean of Precision@k and Recall@k

These metrics help assess how effectively the system delivers relevant recommendations to users.

## 🧪 Models Implemented

The following recommendation techniques were explored:

1. **Rank-Based Recommendation**  
   - Based on average product ratings across all users.

2. **User-User Collaborative Filtering**  
   - Finds users similar to the active user and recommends products they liked.

3. **Item-Item Collaborative Filtering**  
   - Recommends items similar to those the user has already liked.

4. **Model-Based Collaborative Filtering (Matrix Factorization)**  
   - Utilizes **Singular Value Decomposition (SVD)** via the `Surprise` library.

Each method involved hyperparameter tuning using **Grid Search with Cross-Validation** for optimal performance.

## 🏁 Conclusion & Recommendations

- **Best Performing Models**:
  - **SVD** and **optimized User-User Collaborative Filtering** achieved the highest F1@k score of **0.869**.
  - **SVD** outperformed others with better generalization and lowest **RMSE**: `0.8822` vs. `0.9530`.

- **Insights**:
  - The model performs well on users/products with sufficient historical data.
  - Performance drops with **cold-start problems** (new users/products).
  - Incorporating **content-based features** (e.g., product metadata) may help address data sparsity.

- **Recommendations**:
  - Deploy the **SVD model** for real-world applications due to its predictive power and scalability.
  - Explore **hybrid models** combining collaborative and content-based filtering.
  - Consider **deep learning approaches** (e.g., neural collaborative filtering) for further gains.

## 🛠️ Tools & Libraries

- Python
- Pandas, NumPy
- `surprise` library for recommender systems
- Scikit-learn for evaluation
- Matplotlib & Seaborn for visualization

## 🚀 Future Work

- Integrate product metadata for hybrid modeling.
- Experiment with deep learning-based recommenders (e.g., AutoRec, NCF).
- Build a web interface for live recommendations.

## 📄 License

This project is for educational and research purposes only.
