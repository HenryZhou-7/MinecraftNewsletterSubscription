#  Minecraft Newsletter Subscription: Analysis of Player Characteristics

## Project Overview

This project analyzes Minecraft player data to explore whether certain behavioral and demographic traits can predict newsletter subscription. Specifically, we ask:

> **Can a player's experience level, total playtime, and age predict their likelihood of subscribing to a Minecraft newsletter?**

The goal is to help developers better target marketing and engagement strategies using insights from player behavior.

---

## Key Features Analyzed

- `played_hours` – total hours played by each user  
- `experience` – categorical variable converted to numeric scale (Beginner to Pro)  
- `age` – player age in years  
- `subscribe` – binary target variable (`TRUE`/`FALSE`)  

---

## 🛠Methods Used

- **Data Cleaning**: Handled missing values and standardized variable names  
- **Feature Engineering**: Converted categorical variables, scaled and centered predictors  
- **Visualization**:
  - Scatterplot: `played_hours` vs `experience`, color-coded by `subscribe`
  - Boxplot: Age distribution by subscription status  
- **Modeling**:
  - K-Nearest Neighbors (K-NN) classification
  - 5-fold cross-validation across \( k = 1 \) to \( k = 25 \)
  - Compared models with and without `experience` as a predictor

---

## Key Findings

- Subscribed players tend to:
  - Play significantly more hours
  - Be slightly younger
- `experience` was **not** a strong predictor and **reduced** model accuracy
- Model accuracy improved from **66.7%** to **~79.5%** after removing `experience`

---

## Results

- **Best performing model**: K-NN with \( k = 11 \)
- **Final accuracy on test data**: ~79.5%
- **Confusion matrix** shows:
  - True positives (subscribers): well identified
  - False negatives and positives were moderate

---

##  Dataset Summary

- **Observations**: 196 players
- **Variables**:
  - Categorical: `experience`, `gender`, `subscribe`
  - Numerical: `played_hours`, `age`
- **Issues Noted**:
  - Skewed distribution in `played_hours`
  - 2 missing values in `age`
  - Experience level categories are loosely defined

---

##  Future Work

- Include other in-game behavior metrics (e.g. achievements, social interaction)
- Try additional models (logistic regression, decision trees)
- Explore effects of different Minecraft modes or genres
- Consider ethical implications of behavioral targeting

---
