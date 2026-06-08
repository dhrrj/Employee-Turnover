# Employee-Turnover
I have created a ML file on the no of employees who left the company
1. Project Overview
The primary objective of this project is to analyse and predict employee turnover using a dataset of human resources metrics. By identifying patterns among employees who leave and developing a predictive model, the organisation can take proactive measures to improve retention and mitigate the costs associated with recruitment and onboarding.
2. Data Exploration and Insights
The project began with an Exploratory Data Analysis (EDA) of the HR_comma_sep.csv dataset, which includes features such as satisfaction levels, evaluation scores, project counts, and monthly hours. Key findings from the EDA include:
•	Data Integrity: A check for missing values confirmed that the dataset was clean, with zero null values across all columns.
•	Correlation Analysis: A heatmap of numerical features revealed a significant negative correlation (-0.39) between satisfaction level and leaving the company, suggesting that lower satisfaction is a strong indicator of turnover.
•	Workload Impact: An analysis of project counts showed that employees assigned either very few (2) or many (6 or 7) projects were more likely to leave. Conversely, those with a moderate workload (3 to 5 projects) were more likely to stay.
3. Employee Clustering	
To understand the different "types" of employees who leave, a K-Means Clustering algorithm was applied specifically to the subset of employees who had already left the organisation.
•	Features Used: satisfaction_level and last_evaluation.
•	Results: The algorithm identified three distinct groups (clusters) of departing employees. This segmentation allows for more tailored retention strategies based on whether an employee is a high-performer (high evaluation) or highly dissatisfied (low satisfaction).
4. Predictive Modelling and Methodology
The project employed several machine learning techniques to predict the likelihood of an employee leaving:
•	Preprocessing: Categorical variables like department ("sales") and salary level were transformed using one-hot encoding. Data was also standardised using a StandardScaler.
•	Handling Imbalance: To address potential class imbalance (more employees staying than leaving), the SMOTE (Synthetic Minority Over-sampling Technique) was used to balance the training data.
•	Model Performance: Three models were evaluated using 5-fold cross-validation:
o	Logistic Regression: Achieved an accuracy of approximately 76.6%.
o	Random Forest: Showed high training accuracy of 98.8%.
o	Gradient Boosting: Delivered strong performance with 97.8% accuracy.
5. Model Selection and Evaluation
While multiple metrics were tracked, the project prioritised Recall. This is because the cost of a "False Negative" (failing to predict an employee will leave) is high, resulting in lost productivity and recruitment expenses.
Gradient Boosting was identified as the best model for this task. Despite varying results in ROC/AUC testing, it provided a robust framework for calculating turnover probabilities.
6. Risk Categorization and Conclusion
Using the Gradient Boosting model, employees were categorised into four Risk Zones based on their turnover probability:
•	Safe Zone (Green): Probability < 20%
•	Low-Risk Zone (Yellow): 20% – 60%
•	Medium-Risk Zone (Orange): 60% – 90%
•	High-Risk Zone (Red): > 90%
In the final test sample, the model identified 1,202 employees in the High-Risk Zone and 1,798 in the Safe Zone. This clear categorisation provides management with an actionable list of employees who may require immediate intervention to ensure retention

