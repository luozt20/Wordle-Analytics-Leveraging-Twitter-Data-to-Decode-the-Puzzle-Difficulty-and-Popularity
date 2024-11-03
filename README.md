
# Wordle Analytics Project

## Project Overview

This project focuses on analyzing Wordle game results, leveraging Twitter-reported outcomes to examine factors influencing puzzle difficulty, user participation, and performance distribution. Using advanced data analysis techniques, we model Wordle's dynamics, classify word difficulty, predict result distributions, and analyze player participation trends. This analysis offers insights that could help in enhancing user experience, designing puzzles, and better understanding the factors influencing Wordle gameplay.

## Dataset

The dataset used for this analysis includes Wordle game data collected daily from Twitter between January 7, 2022, and December 31, 2022. Key variables in the dataset:

- **Date**: Date of the Wordle puzzle
- **Contest number**: Wordle puzzle identifier
- **Word**: Solution word of the day
- **Number of reported results**: Total reported scores for each day
- **Number in hard mode**: Number of reported scores played in Hard Mode
- **Try Percentages (1-6 tries, X)**: Percentage distribution of the number of tries taken to solve the puzzle

Additionally, several word attributes were computed to assess difficulty, such as word frequency, number of repeated letters, and the presence of rare letters.

## Analysis Overview

1. **Data Cleaning and Preprocessing**:
   - Outliers and inconsistencies were identified and addressed. For instance, certain words with spelling errors were corrected, and percentages were normalized.

2. **Word Difficulty Classification**:
   - Attributes influencing word difficulty were analyzed using Principal Component Analysis (PCA) and K-means clustering. Clusters were used to define difficulty levels for solution words based on attributes like word frequency, similarity to common starting words, and the presence of repeated letters.

3. **Model of User Participation**:
   - An Ordinary Differential Equation (ODE) model captures the fundamental trend of user participation over time.
   - An ARIMA model was applied to explain daily fluctuations in participation.
   - An ARIMAX model was used to analyze the proportion of hard-mode players, with findings indicating that harder words led to increased reporting and higher hard-mode proportions.

4. **Model of Reported Results Distribution**:
   - A Random Forest regression model predicts the percentage distribution of tries taken (1-6 tries, X) for a given word, accounting for the multi-output nature of the prediction task.

5. **Sensitivity Analysis**:
   - An additional sensitivity analysis was conducted using the ODE model to explore variations under different market sizes.

## Key Findings

- **Word Difficulty Classification**: Four levels of word difficulty were identified, with harder words generally leading to higher reporting rates and a greater proportion of hard-mode play.
- **User Participation Trends**: User participation followed a predictable trend but exhibited fluctuations that were effectively modeled with ARIMA techniques.
- **Performance Prediction**: The Random Forest model successfully provided confidence intervals for player performance, predicting the distribution of results accurately.

## Future Directions

- Expand analysis to incorporate additional variables, such as linguistic complexity and gameplay frequency.
- Explore time-series predictions for future words using predictive models for player performance and participation.
