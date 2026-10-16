# SC5002 Lab Assignment: Classical Search & Regularized Regression

Nanyang Technological University, SC5002 Artificial Intelligence Fundamentals & Applications.

## Overview
This repository contains the code for **Part 2** of the lab assignment: comparing Linear Regression and Ridge Regression on the California Housing dataset using Google Colab and Scikit-Learn. Part 1 (A* and BFS search, 8-puzzle) is solved by hand and documented in the PDF report.

## Files
- `Untitled0.ipynb`: the Google Colab notebook (code, comments and outputs).
- `README.md`: this file.

## Dataset
California Housing dataset (`fetch_california_housing`), randomly sampled to 1,000 rows (`random_state=42`).
- **Target variable:** `MedHouseVal` (median house value, in units of $100,000).
- **Input features (8):** MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude.

## Method
1. Load the dataset and take a random sample of 1,000 rows.
2. Split into features (X) and target (y).
3. Scale the features with `StandardScaler` so they are on a comparable scale.
4. Split into 80% training and 20% test data.
5. Evaluate Linear Regression and Ridge Regression (alpha = 0.1, 10, 1000) with 5-fold cross-validation, using R² as the score.
6. Plot the mean R² scores in a bar chart.

## Results (mean 5-fold cross-validation R²)
| Model | Alpha | Mean R² |
|---|---|---|
| Linear Regression | n/a | 0.6457 |
| Ridge Regression | 0.1 | 0.6457 |
| Ridge Regression | 10.0 | 0.6443 |
| Ridge Regression | 1000.0 | 0.3574 |

## Key findings
- Linear Regression and Ridge with a small or moderate alpha perform almost identically, so Ridge did not improve the average score here.
- With a very high alpha (1000), the penalty shrinks the coefficients too much and the model **underfits**, so R² drops to 0.3574.
- Good regularisation balances underfitting and overfitting, and the best alpha should be chosen with cross-validation, not training error.

## How to run
1. Open `Untitled0.ipynb` in Google Colab (File > Open notebook > GitHub, or upload the file).
2. Run the cell with Runtime > Run all.
3. The notebook prints the first 5 rows, the cross-validation scores and the comparison chart.

## Use of Generative AI
Generative AI tools (ChatGPT, Claude) were used as learning partners: to explain concepts (admissible heuristics, feature scaling, regularisation, cross-validation), to check calculations, and to help write code comments. All AI prompts and syntheses are logged in the PDF report.

## Group members
- Name 1: contribution
- Name 2: contribution
