# Project Proposal

* **Project Title:** Deep Learning for Iberian Climate-Resilient Agriculture: LSTM Networks for Multivariant Crop Yield Forecasting in Portugal
* **Project Category:** Tabular Data / Time-Series Deep Learning
* **Team Members:** Samuel Ayomide Olaniyan (Student ID: 29386)

---

## Problem Statement & Motivation
Anthropogenic climate change introduces severe volatility into southern European agricultural production, with Portugal facing escalating risks from prolonged droughts and shifting precipitation patterns. Accurate long-term crop yield forecasting is a vital component of green data science to protect local food security and economic stability. Traditional statistical methods often fail to capture the complex, non-linear relationships and temporal dependencies between evolving climate variables and agricultural outputs. This project implements a Deep Learning framework specifically optimized to forecast future agricultural yields ($hg/ha$) in Portugal utilizing historical climate and agronomic indicators.

## Technical Challenges
Building a robust predictive model presents several rigorous engineering hurdles:
1. **Temporal Disruption:** Ensuring the model respects chronological order during cross-validation without causing "data leakage" (using future insights to predict the past).
2. **High-Dimensional Categorical Embedding:** Effectively encoding categorical variables (such as specific crop types) so a neural network can extract spatial relationships.
3. **Sequence Dependencies:** Mapping irregular time series where environmental impacts (like a drought year) have lagging effects on subsequent harvests.

## Dataset & Collection Plan
The study utilizes an integrated tabular dataset filtered specifically for Portugal, compiled from historical records from the Food and Agriculture Organization (FAO) and the World Data Bank. The data consists of multi-variate features spanning multiple decades, including year, specific local crop varieties (e.g., potatoes, wheat, or grapes), average precipitation, pesticide utilization, and average annual temperatures, with crop yield serving as the continuous target variable.

## Methodology & Deep Learning Architecture
We propose a deep learning pipeline constructed natively in **PyTorch**. The architecture will feature an initial embedding layer for categorical features, concatenated with standardized numerical climate variables. This sequence will be processed through an **LSTM (Long Short-Term Memory) Recurrent Neural Network** layer to capture temporal dependencies. The LSTM hidden states will feed into fully connected linear layers to map the final regression output. We will benchmark this architecture against a standard `scikit-learn` Random Forest Regressor to prove the superior value of deep learning.

## Evaluation
The dataset will be chronologically partitioned into explicit training, validation, and testing subsets (e.g., training on historical years up to 2018, validating on 2019-2022, and testing on future unseen years 2023+). Predictive performance will be rigorously evaluated using Root Mean Squared Error ($RMSE$), Mean Absolute Error ($MAE$), and the Coefficient of Determination ($R^2$ score).
