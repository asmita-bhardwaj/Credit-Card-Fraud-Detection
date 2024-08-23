# Credit-Card-Fraud-Detection

This repository contains a machine learning project focused on detecting fraudulent credit card transactions using a variety of techniques. The dataset is highly imbalanced, and this project explores 2 different methods of handling this imbalance: undersampling and oversampling. Two machine learning models, Logistic Regression and Decision Tree Classifier, are used to perform the classification.

## Purpose

The primary goal of this project is to develop a machine learning model capable of accurately classifying transactions as either legitimate or fraudulent. Credit card fraud detection is a critical task for financial institutions, and the ability to detect fraud in real-time can save significant resources. 

To tackle the challenge of imbalanced data, this project employs techniques like undersampling, oversampling (SMOTE), and compares the performance of Logistic Regression and Decision Tree Classifier models in these different settings.

## Dataset

The dataset used in this project contains transactions made by European cardholders in September 2013. It has 284,807 transactions, of which only 492 (0.17%) are fraudulent. This imbalance makes it a perfect case study for exploring techniques to handle imbalanced datasets.

## Project Structure

- **Data Exploration and Preprocessing:** The dataset is loaded, and initial exploration is done to understand its structure, check for missing values, and handle duplicates. The 'Time' feature is dropped, and the 'Amount' feature is standardized.
  
- **Class Imbalance Handling:** 
    - **Undersampling:** Legitimate transactions are reduced to match the number of fraudulent ones.
    - **Oversampling (SMOTE):** Synthetic Minority Over-sampling Technique (SMOTE) is used to generate synthetic examples of the minority class (fraudulent transactions) to balance the dataset.
  
- **Model Training and Evaluation:**
    - **Logistic Regression:** A simple yet effective model for binary classification.
    - **Decision Tree Classifier:** A more complex model that can capture non-linear relationships in the data.
  
- **Real-Time Application:** Finally, the notebook demonstrates how the trained model can be used in real-time to classify new transactions as either normal or fraudulent.

## Results & Analysis

The performance of Logistic Regression and Decision Tree Classifier models was evaluated under three different conditions: no sampling, undersampling, and oversampling (SMOTE). The results provide insight into the trade-offs between different methods of handling imbalanced data.

### No Sampling

In the case of no sampling, where the dataset remains imbalanced, Logistic Regression achieved the following performance:
- **Accuracy:** 99.93%
- **Precision:** 0.8906
- **Recall:** 0.6264
- **F1 Score:** 0.7354

While the accuracy is high, this is misleading due to the heavily imbalanced dataset. Precision is also decent, but recall is quite low, indicating that many fraudulent transactions were missed.

### Undersampling

Undersampling reduced the number of legitimate transactions to match the fraudulent ones, which helped balance the data but led to some loss of information. The performance of Logistic Regression and Decision Tree Classifier under this method was as follows:

- **Logistic Regression:**
  - **Accuracy:** 94.73%
  - **Precision:** 0.9792
  - **Recall:** 0.9216
  - **F1 Score:** 0.9495
  
- **Decision Tree Classifier:**
  - **Accuracy:** 88.94%
  - **Precision:** 0.9175
  - **Recall:** 0.8725
  - **F1 Score:** 0.8944

The results show that while the models' accuracy dropped compared to the no-sampling case, the recall and F1 score improved significantly for Logistic Regression. This demonstrates that while undersampling reduces overall accuracy, it helps improve the detection of fraudulent transactions.

### Oversampling (SMOTE)

Oversampling using SMOTE (Synthetic Minority Over-sampling Technique) improved the performance of the models by generating synthetic examples of fraudulent transactions to balance the dataset. The results were as follows:

- **Logistic Regression:**
  - **Accuracy:** 94.52%
  - **Precision:** 0.9737
  - **Recall:** 0.9151
  - **F1 Score:** 0.9435
  
- **Decision Tree Classifier:**
  - **Accuracy:** 99.81%
  - **Precision:** 0.9974
  - **Recall:** 0.9988
  - **F1 Score:** 0.9981

The Decision Tree Classifier with SMOTE produced the best overall performance, achieving near-perfect precision, recall, and F1 score. This shows that SMOTE effectively handled the class imbalance, allowing the Decision Tree to excel in detecting fraudulent transactions while maintaining high accuracy.

### Conclusion

- **No Sampling:** The high accuracy was misleading due to the imbalance, as the model failed to detect many fraudulent transactions.
- **Undersampling:** Improved the detection of fraudulent transactions at the cost of some accuracy.
- **Oversampling (SMOTE):** Produced the best overall performance, particularly for the Decision Tree Classifier, which achieved near-perfect recall and precision.

Overall, the Decision Tree Classifier combined with SMOTE proved to be the most effective model for detecting credit card fraud, balancing high accuracy with excellent recall and precision.
