# Sales Prediction: Different Models Comparison

This project investigates various machine learning models for predicting sales performance based on a synthetic dataset containing customer information. It aims to identify the model that yields the most accurate predictions for lead conversion (converted vs. unconverted).

**Note:** Due to privacy concerns, the actual dataset used in this project is not publicly available. If you'd like to explore replicating this analysis with your own data, please contact me at avdeep2001@gmail.com for further guidance.

## Data Cleaning and Preprocessing

The raw data was loaded from a CSV file (`Book2.csv`) and explored to understand its shape, content, and data types. Missing values were handled using a suitable strategy (e.g., imputation with appropriate techniques depending on the data and modeling approach).
Categorical features like "Qualification", "Employment Status" etc were mapped to numerical representations using dictionaries (`Qualification_dic`, `Employment_Status_dic`, etc.). This step facilitates model training with these features.

## Feature Engineering

Exhaustive feature selection (EFS) was employed in this project to identify the optimal subset of features that maximizes model accuracy. EFS evaluates all possible feature combinations and selects the set that yields the best performance on a defined scoring metric (e.g., accuracy). This technique helps to:

* **Reduce model complexity:** By eliminating irrelevant or redundant features, EFS can lead to simpler models that are less prone to overfitting.
* **Improve model performance:** Focusing on the most informative features can potentially enhance the model's ability to learn patterns from the data and make accurate predictions.

This project utilized EFS with an XGBoost classifier as the scoring model. It's important to note that the optimal feature set might vary depending on the chosen machine learning algorithm.

## Model Selection and Training

Several machine learning models were employed for sales prediction:

* **XGBoost Classifier (Gradient Boosting)**
* **Random Forest Classifier**
* **Logistic Regression**

For each model, a grid search or other optimization technique could be employed to tune hyperparameters (not shown here) to potentially improve performance. 

## Model Evaluation

The models were evaluated using accuracy score as the primary metric. Train-test splits were used to ensure unbiased evaluation. The process involved:

1. Splitting the data into training and testing sets (80%/20% split commonly used).
2. Training the models on the training set.
3. Making predictions on the unseen testing set.
4. Calculating accuracy score to compare model performance.

Both scenarios were explored - with and without feature selection - to assess the impact of feature reduction on model accuracy.

## Results

The project explored the effectiveness of various machine learning models for sales prediction. Interestingly, the **XGBoost model without feature selection** emerged as the most accurate model in this dataset, achieving an accuracy score of **85%** on the held-out testing set.

Here's a summary of the accuracy scores for all models with and without feature selection:

| Model | With Feature Selection | Without Feature Selection |
|---|---|---|
| XGBoost | 41% | **85%** |
| Random Forest | 41% | 76% |
| Logistic Regression | 44% | 46% |

As evident, feature selection had a significant impact on the performance of XGBoost, reducing its accuracy from 85% to 41%. Conversely, Random Forest exhibited a similar accuracy score (around 76%) with and without feature selection in this specific case. Logistic Regression showed a slight improvement without feature selection.

It's important to remember that these results are specific to the dataset used in this project. The optimal model and the impact of feature selection can vary depending on the data characteristics and chosen algorithms.
 
## Conclusion

This project provided a comparative analysis of various machine learning models for sales prediction. By leveraging feature engineering and selection techniques, the analysis aimed to optimize model performance for the given dataset.

## Next Steps

* Explore additional feature engineering techniques.

While this project utilized synthetic data, the overall approach can be adapted to real-world sales prediction scenarios with appropriate data considerations.
