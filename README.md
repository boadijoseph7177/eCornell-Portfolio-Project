# eCornell-Portfolio-Project: Airbnb Market Segment Analysis

## Project Overview
This project uses unsupervised machine learning to discover and analyze distinct market segments within the Airbnb ecosystem. By applying **K-Means clustering** to a large dataset of listings, this analysis moves beyond simple metrics to identify natural groupings and "personas" of properties. The final output is a set of **5 well-defined market segments** (e.g., "Luxury Group Stays," "Budget Long-Term Rentals"), providing **actionable insights** for hosts and for **targeted marketing strategies**.

---

## The Business Problem
For a platform like Airbnb, understanding the composition of its listings is crucial for growth. While data on individual properties is abundant, there are no predefined labels to categorize them into meaningful market segments. The goal of this project is to answer the question:

> **What distinct types of Airbnb listings exist in the market, and what are their defining characteristics?**

Solving this enables value creation through:

- **Targeted Marketing**: Creating campaigns aimed at specific user needs.
- **Dynamic Pricing**: Building smarter pricing tools for hosts.
- **Market Gap Analysis**: Identifying underserved niches in the rental market.

---

## Methodology & Pipeline
The project follows a standard machine learning workflow, from raw data to actionable insights.

### 1. Data Cleaning & Preparation
- Cleaned a dataset of 28,000+ listings, addressing missing values in `review_scores_rating`, `bedrooms`, and other key columns.
- Handled extreme outliers in numerical features like `price` and `minimum_nights` by capping them at the 99th percentile.

### 2. Feature Engineering & Selection
- Selected a curated set of relevant features to describe each listing.
- Applied **one-hot encoding** to categorical features such as `room_type`.
- Parsed the complex `amenities` column and engineered the **35 most common amenities** into binary features (e.g., `has_wifi`, `has_pool`).

### 3. Modeling with K-Means Clustering
- Scaled all features using `StandardScaler` to ensure equal contribution to the clustering model.
- Used the **Elbow Method** to determine the optimal number of clusters (**K=5**).
- Trained a **K-Means model** to segment all listings into one of five distinct clusters.

---

## Results: The 5 Market Segments

### Cluster 0: Premium Long-Term Rentals
- High `minimum_nights`
- Equipped with amenities for extended stays (e.g., washer, dryer)

### Cluster 1: Standard Extended Stays
- Mid-tier long-term rentals
- Fewer premium amenities

### Cluster 2: Basic & Budget Long-Stay Rooms
- Budget-friendly
- Lowest review scores
- Lacks essential amenities

### Cluster 3: Luxury Group & Family Stays
- Highest prices and capacities
- Excellent reviews
- Suited for group or family travel

### Cluster 4: Top-Rated Tourist Hotspots
- Low `minimum_nights`
- High review frequency and scores
- Ideal for short-term vacation stays

---

## Technologies Used
- **Python**: Core programming language
- **Pandas**: Data manipulation and cleaning
- **Scikit-learn**: Feature scaling (`StandardScaler`) and modeling (`KMeans`)
- **Matplotlib & Seaborn**: Data visualization (e.g., Elbow Method plot)
