# Classification-models-on-Customer-Churn-dataset
I trained four traditional classification ML models on a Customer Churn dataset. 
# Customer Churn Prediction Using Machine Learning

## Project Overview

Customer retention is a critical challenge for businesses, as acquiring new customers is often more expensive than retaining existing ones. This project focuses on predicting customer churn using machine learning techniques, enabling organizations to proactively identify customers at risk of leaving and implement targeted retention strategies.

The objective was to build and compare multiple classification models, evaluate their performance using industry-standard metrics, and optimize the best-performing model through hyperparameter tuning.


## Dataset Description

The dataset contains customer information, service usage patterns, account details, and churn status. The target variable is:

* **Churn**

  * 0 = Customer did not churn
  * 1 = Customer churned

### Class Distribution

| Class    | Count |
| -------- | ----- |
| No Churn | 2,278 |
| Churn    | 388   |

The dataset exhibits class imbalance, with approximately 85.5% non-churners and 14.5% churners. Because of this imbalance, model evaluation relied not only on Accuracy but also on Precision, Recall, and F1 Score.


## Project Workflow

### 1. Data Preprocessing

The preprocessing phase involved:

* Handling categorical variables
* Converting binary categorical features into numerical values
* Applying One-Hot Encoding where appropriate
* Splitting data into training and testing sets
* Feature scaling for algorithms requiring normalization

### 2. Exploratory Data Analysis (EDA)

EDA was conducted to better understand customer behavior and identify factors influencing churn. This included:

* Distribution analysis
* Correlation analysis
* Feature relationship exploration
* Class imbalance assessment

### 3. Model Development

The following classification models were developed and evaluated:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier
* Tuned Random Forest Classifier


## Model Evaluation Metrics

The following metrics were used:

### Accuracy

Measures the overall percentage of correctly classified observations.

### Precision

Measures how many customers predicted as churners actually churned.

### Recall

Measures how many actual churners were correctly identified.

### F1 Score

Provides a balance between Precision and Recall and is particularly useful for imbalanced datasets.

## Model Performance Comparison

| Model               | Accuracy   | Precision  | Recall     | F1 Score   |
| ------------------- | ---------- | ---------- | ---------- | ---------- |
| Logistic Regression | 84.08%     | 43.18%     | 24.05%     | 30.89%     |
| Decision Tree       | 91.01%     | 79.25%     | 53.16%     | 63.64%     |
| Random Forest       | 92.70%     | 97.62%     | 51.90%     | 67.77%     |
| Tuned Random Forest | **94.38%** | **92.98%** | **67.09%** | **77.94%** |

## Model Comparison

### Logistic Regression

Logistic Regression served as the baseline model. While computationally efficient and interpretable, it struggled to capture the complex relationships within the dataset. The model produced the lowest Recall and F1 Score, indicating limited effectiveness in identifying customers likely to churn.

### Decision Tree

The Decision Tree significantly improved performance by capturing non-linear relationships in the data. It achieved higher Precision, Recall, and F1 Score than Logistic Regression, demonstrating its ability to model more complex customer behavior patterns.

### Random Forest

The Random Forest model improved upon the Decision Tree by combining multiple trees into an ensemble. It achieved the highest Precision, meaning that nearly every customer predicted to churn was indeed a churner. However, Recall remained moderate, indicating that some churners were still missed.

### Tuned Random Forest

After hyperparameter optimization, the Tuned Random Forest emerged as the strongest model. It achieved the highest Accuracy, Recall, and F1 Score, making it the most balanced and reliable solution for churn prediction.


## Hyperparameter Tuning

To further improve model performance, GridSearchCV was used to systematically search for the optimal combination of Random Forest hyperparameters.

### Parameters Tuned

* n_estimators
* max_depth
* min_samples_split
* min_samples_leaf
* max_features

### Why Hyperparameter Tuning?

Default model settings do not always provide optimal performance. Hyperparameter tuning helps identify the best configuration for the dataset, improving generalization and predictive accuracy.

The optimization process focused on maximizing the **F1 Score**, ensuring a balance between identifying churners and minimizing false positives.

### Results of Hyperparameter Tuning

| Metric    | Before Tuning | After Tuning |
| --------- | ------------- | ------------ |
| Accuracy  | 92.70%        | 94.38%       |
| Precision | 97.62%        | 92.98%       |
| Recall    | 51.90%        | 67.09%       |
| F1 Score  | 67.77%        | 77.94%       |

The most significant improvement occurred in Recall and F1 Score, demonstrating that the tuned model became substantially better at identifying customers likely to churn.

## Confusion Matrix Analysis

Confusion matrices were generated for all models to visualize prediction performance.

### Logistic Regression

The confusion matrix revealed a high number of False Negatives, indicating that many actual churners were incorrectly classified as non-churners.

### Decision Tree

The Decision Tree reduced False Negatives and improved churn detection while maintaining reasonable Precision.

### Random Forest

The Random Forest minimized False Positives and achieved exceptional Precision, though some churners were still missed.

### Tuned Random Forest

The tuned model produced the best balance between False Positives and False Negatives, resulting in superior overall performance and stronger churn detection capabilities.

## Challenges Encountered

Several challenges were encountered during the project:

### Class Imbalance

The dataset contained significantly more non-churners than churners. This made Accuracy a potentially misleading metric and required careful consideration of Precision, Recall, and F1 Score.

### Data Encoding

Categorical features such as State and service plan indicators required transformation into numerical representations before model training.

### Feature Scaling

Certain algorithms required feature scaling, and errors were encountered due to non-numeric values remaining in the dataset. These issues were resolved through proper preprocessing and encoding.

### Model Selection

Different algorithms exhibited different strengths and weaknesses. Selecting the final model required balancing predictive performance with business objectives.

## Key Insights

* Customer churn prediction is highly sensitive to class imbalance.
* Accuracy alone is insufficient for evaluating churn models.
* Ensemble methods significantly outperform individual models.
* Hyperparameter tuning can substantially improve model performance.
* Recall and F1 Score are critical metrics when identifying customers at risk of leaving.


## Conclusion

This project demonstrates the application of machine learning techniques to solve a real-world business problem. By comparing multiple classification algorithms and optimizing the best-performing model through hyperparameter tuning, a robust customer churn prediction system was developed.

The Tuned Random Forest model achieved the best overall performance, with an Accuracy of 94.38% and an F1 Score of 77.94%, making it the recommended model for deployment in customer retention initiatives.


## Author
Asante-Dapaah Theophilus.

Developed as part of my machine learning and data analytics journey, with a focus on applying predictive modeling techniques to business problems and generating actionable insights from data.
