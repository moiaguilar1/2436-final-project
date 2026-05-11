# Chapter 12: Regression — Lab Report

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/10/2026
- **Course:** COSC 2436

## Algorithm Summary

- **How it works:**  
K-Nearest Neighbors (KNN) Regression predicts values by comparing new input data to the 
most similar historical examples. The algorithm finds the `k` closest data points and 
averages their target values to produce a prediction. In this lab, the model predicts how 
many loaves of bread a bakery should prepare based on weather, weekends, holidays, and game days.

- **Time complexity:**  
Training complexity is approximately O(1) because KNN stores the dataset directly, while 
prediction complexity is O(n) because distances to all training samples must be calculated.

- **When to use it:**  
KNN regression is useful for prediction problems where similar conditions tend to produce 
similar outcomes, such as sales forecasting, recommendation systems, weather-based predictions, 
and demand estimation.

## Test Results

| Input | Result | Notes |
|------|------|------|
| Weather = 4 | Predicted ~75 loaves | Good weather |
| Weekend/Holiday = 1 | Increased sales prediction | Weekend traffic |
| Game On = 0 | No sports event effect | Normal demand |

### Sample Program Output

```
Today's conditions:
Weather = 4
Weekend/Holiday = 1
Game = 0

Predicted loaves to bake: 75.0
```

## Reflection Questions

### 1. Why does KNN regression not require traditional “training” like some other machine learning algorithms?

KNN regression stores the training data directly instead of building a mathematical model during 
training. Predictions are calculated later by comparing new inputs to nearby historical examples.

### 2. What effect does changing the value of `k` have on predictions?

A smaller `k` makes predictions more sensitive to nearby data points and noise, while a larger 
`k` produces smoother and more generalized predictions. Choosing the correct `k` balances 
accuracy and stability.

### 3. Why is feature selection important in regression problems?

Features determine what information the model uses to make predictions. Irrelevant or poorly chosen 
features can reduce prediction accuracy and make the model less reliable.

## Challenges Encountered

One challenge was understanding how KNN regression makes predictions without explicitly generating 
an equation. Another difficulty was interpreting how different feature values affected loaf predictions. 
This was resolved by examining the training dataset carefully and observing how similar conditions 
influenced the final averaged prediction.