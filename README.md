# Feature Selection Algorithms on Iris Dataset

This repository contains implementations of various feature selection algorithms applied to the Iris dataset. The goal is to identify the most optimal subset of features that yield the best accuracy when using a RandomForestClassifier.

## Dataset

The Iris dataset is used for this analysis. It contains measurements for 150 iris flowers from three different species. The features are:

-   sepal length (cm)
-   sepal width (cm)
-   petal length (cm)
-   petal width (cm)

## Algorithms Implemented

1.  **Branch and Bound:**
    - A systematic search method that explores feature subsets while pruning branches that cannot lead to better solutions.
    - The objective is to maximize the accuracy of a RandomForestClassifier.
2.  **Greedy Forward Selection:**
    - A heuristic algorithm that iteratively adds the feature that provides the most significant improvement in accuracy.
    - It starts with an empty set and adds one feature at a time until all features are considered.
3.  **Ant Colony Optimization (ACO):**
    - A probabilistic technique inspired by the foraging behavior of ants.
    - Ants explore different feature subsets, and pheromone levels are updated based on the accuracy of the solutions.
    - This implementation has been tested with the iris data set, it is better suited for larger data sets.

## Dependencies

-   scikit-learn
-   pandas
-   numpy

## Code Overview
1. **load_iris():**
   - Loads the Iris dataset from scikit-learn.
2. **train_test_split():**
   - Splits the dataset into training and testing sets.
3. **RandomForestClassifier():**
   - A machine learning model used for classification.
4. **accuracy_score():**
   - Calculates the accuracy of the model's predictions.
5. **objective_function():**
   - A function that trains a RandomForestClassifier using selected features and returns the accuracy.

### Branch and Bound Implementation:
 Uses a `while` loop to explore feature subsets.
 Applies branching and bounding to find the optimal subset.
### Greedy Forward Selection Implementation:
 Iteratively adds the best feature to the selected set.
 Uses a `while` loop to continue until all features are considered.
### Ant Colony Optimization Implementation:
Uses a nested loop to simulate ant movement and pheromone updates.
feature_slection() function to let the ant select the features.

## Results
The script outputs the best feature subsets and their corresponding accuracies for each algorithm.

## Notes
1. The Iris dataset is relatively simple, and many feature subsets can achieve high accuracy.
2. The ACO algorithm can be further tuned by adjusting parameters like `num_ants`, `evaporation_rate`, `alpha`, and `beta`.
3. The ACO algorithm is better suited for data sets with many features.
4. The branch and bound algorithm will return the first best solution that it finds.
