# Assignment 5: Health Data Classification Results

This file contains your manual interpretations and analysis of the model results from the different parts of the assignment.

## Part 1: Logistic Regression on Imbalanced Data

### Interpretation of Results

In this section, provide your interpretation of the Logistic Regression model's performance on the imbalanced dataset. Consider:

- Which metric performed best and why?
- Which metric performed worst and why?
- How much did the class imbalance affect the results?
- What does the confusion matrix tell you about the model's predictions?

* accuracy: 0.9167803547066848
* precision: 0.6615384615384615
* recall: 0.3006993006993007
* f1: 0.4134615384615384
* auc: 0.6420352134637849
* confusion_matrix: [[1301   22],[ 100   43]]

The model had high accuracy (~ 91.7%), meaning it was able to correctly predict most cases overall. Recall was much lower (~30%), as it missed many positive cases. This is likely due to class imbalance, where the model favors the majority negative class and struggles to detect the minority positive cases. The confusion matrix further shows that while true negatives are high, there are many false negatives, demonstrating that the model under-predicts positives. 

## Part 2: Tree-Based Models with Time Series Features

### Comparison of Random Forest and XGBoost

In this section, compare the performance of the Random Forest and XGBoost models:

- Which model performed better according to AUC score?
- Why might one model outperform the other on this dataset?
- How did the addition of time-series features (rolling mean and standard deviation) affect model performance?

* Random Forest: 0.9735
* XGBoost: 0.9953

XGBoost performed better than Random Forest with an AUC of 0.9953 versus 0.9735, meaning it does better at distinguishing classes. This may be due to XGBoost’s gradient boosting approach, which can handle more complex patterns more effectively. Adding time-series features like rolling mean and standard deviation improved both models by providing valuable temporal information for better predictions.


## Part 3: Logistic Regression with Balanced Data

### Improvement Analysis

In this section, analyze the improvements gained by addressing class imbalance:

- Which metrics showed the most significant improvement?
- Which metrics showed the least improvement?
- Why might some metrics improve more than others?
- What does this tell you about the importance of addressing class imbalance?

* accuracy: 0.8274215552523875
* precision: 0.34011627906976744
* recall: 0.8181818181818182
* f1: 0.48049281314168374
* auc: 0.9089481946624803
* confusion_matrix: [[1096, 227], [26, 117]]

After balancing the data, recall improved the most (0.82), showing the model became much better at identifying positive cases. Precision showed the least improvement, staying relatively low at 0.34, meaning the model still produced many false positives. This occurs because balancing helps the model focus on the minority class, improving sensitivity (recall), but may increase false alarms, limiting precision gains.

## Overall Conclusions

Summarize your key findings from all three parts of the assignment:

- What were the most important factors affecting model performance?
- Which techniques provided the most significant improvements?
- What would you recommend for future modeling of this dataset?

Handling class imbalance and incorporating time-series features were the most important factors for improving model performance. The addition of rolling mean and standard deviation features significantly boosted accuracy and AUC scores, especially for XGBoost. Balancing the dataset using SMOTE significantly improved recall, helping the model better detect minority class cases. For future modeling, it would be useful to continue to engineer meaningful features from the time-series data, and class imbalances should be continued to be addressed.