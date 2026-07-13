# Iris Flower Classification 🌸

A machine learning project that classifies iris flowers into their species (Setosa, Versicolor, Virginica) based on their sepal and petal measurements. Built as part of the CodSoft Data Science Internship.

## Overview

This project covers a complete, beginner-friendly ML workflow:
- Cleaning and exploring the classic Iris dataset
- Checking for missing values and duplicates
- Feature selection using correlation analysis
- Exploratory data analysis (EDA) with visualizations
- Training a K-Nearest Neighbors (KNN) model to classify species
- Evaluating the model's performance

## Dataset

The dataset (`iris_dataset.csv`) contains 150 rows and 5 columns: `sepal length (cm)`, `sepal width (cm)`, `petal length (cm)`, `petal width (cm)`, and `target` (species).

## Approach

**1. Data Cleaning**
- Checked for missing values — none were found.
- Checked for and removed duplicate rows, reducing the dataset from 150 to 147 rows.

**2. Encoding & Feature Selection**
- Mapped the `target` species (`Iris-setosa`, `Iris-versicolor`, `Iris-virginica`) to numeric values `0`, `1`, `2` and dropped the original text column.
- Used correlation analysis to reduce redundant features:
  - `petal width (cm)` had the strongest correlation with the target (~0.95), so it was kept.
  - `petal length (cm)` was highly correlated with petal width and was dropped.
  - `sepal length (cm)` was highly correlated (~0.81) with petal width and was dropped.
  - Final feature set: `sepal width (cm)` and `petal width (cm)`.
- Visualized correlations using a heatmap.

**3. Exploratory Data Analysis**
- Plotted distributions of petal width and sepal width.
- Used count plots and a pair plot to see how the three species differ — Setosa stood out clearly, while Versicolor and Virginica overlapped somewhat.

**4. Model Building**
- Split the data into training (70%) and testing (30%) sets.
- Applied `StandardScaler` for feature scaling.
- Trained a **K-Nearest Neighbors (KNN)** classifier (k=3) on `sepal width` and `petal width`.

**5. Evaluation**
- Achieved an accuracy of **0.95**.
- Weighted average precision and recall also came out to **0.95**.
- Reviewed results using a confusion matrix and classification report — class 0 (Setosa) was predicted perfectly, with only minor misclassifications between classes 1 and 2.

## Tech Stack

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

## How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/Sneha02sharma/Iris_flower_classification.git
   cd Iris_flower_classification
   ```
2. Install dependencies
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn
   ```
3. Open and run the notebook
   ```bash
   jupyter notebook Iris_data_exploration.ipynb
   ```

> **Note:** This notebook currently loads the dataset from a local path (`C:\Users\Dell\Downloads\iris_dataset.csv`). To run it yourself, download `iris_dataset.csv` from this repo and update that path in the notebook to match where you've saved it on your machine.

## Acknowledgements

Dataset based on the classic [Iris Flower Dataset](https://archive.ics.uci.edu/dataset/53/iris), originally introduced by biologist Ronald Fisher.

---
*This project was completed as part of the CodSoft Data Science Internship.*
