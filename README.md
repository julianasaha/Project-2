# Risk of Stroke Prediction 
Author: Juliana Sahagun
## Goal: The goal is to help predict if a person is at high risk for a stroke considering their health conditions.
### Data:
1. Source :
    * https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset
 
### Methods
* Data Cleaning:
    - Dropped the columns id because it was unnecessary towards finding our target
    - Imputed missing value by removing the rows with missing values to not introduce any errors to the datas(less than 1% was missing)
    -Changed the incorrect data types to its correct type : 'age' → integer & 'bmi' → float
    -Removed value 'other' in the gender column as it was insignificant to our data
* Visualizations:
    - Seaborn scatter plots,count plots, boxplots,scatterplots, barplots and heatmaps were all used to visualize the data.
* Preprocessing: 
    - Set target to 'stroke' and split features
    - Validation Split since it is a supervised classification problem
    - OneHotEncoded the categorical features since they were all nominal and StandardScaler the numerical features
    - Made a ColumnTransformer to match the transformation to the type of column
* Testing LogisticRegression, DecisionTree, and KNearestNeighbors:
    - Made three different models and hypertuned them to their optimal potential using GridSearchCV
    - Evaluated each model with 'evaluate_classification' and 'classification_report' 
    - Each model was compared by their predictions times with and without PCA
 
### Results
-Overall, people who have health conditions that are high risk tend to be at higher risk for stroke danger.
- Key Findings: Heart Disease is a high risk indicator for a stroke especially in men. Hypertension on the other hand is a higher risk for females than male.The results demonstrate a drastic difference between at risk people vs not at risk people for each health condition.  People who aren't at risk for stroke tend to have normal glucose levels while people who are have higher glucose levels. The results for BMI are only slightly higher for at risk people therefore it is not a good indicator as glucose levels.
#### Visual 1
![image](https://user-images.githubusercontent.com/104885846/181685229-b388229c-b7e8-47f4-87d2-07409e17822c.png)
 
#### Visual 2
![image](https://user-images.githubusercontent.com/104885846/181685255-4a0be2d9-4e35-4c35-ae96-096206e8caa8.png)
 
 
#### Machine learning Results:
Logistic Model
-  SCORES: Testing Accuracy .948 before tuning →.948 (No change)
-  PCA had no effect on the Logistic Model. Predictions were the same at 16.4 s. 
-  F1 Score:.95


Decision Tree Model
-  SCORES:Testing Accuracy 0.9 before tuning→ after .948
-  PCA made the model faster by 9.6 s. Final Time: 17.2 s.
-  F1 Score: .95


KNN Model
-  SCORES:Testing Accuracy .948 before tuning →.948 (No change)
-  PCA made the model faster by 72.8 ms. Final Time: 96.2ms
-  F1 Score: .95
 
###### Recommendations:
Although all models presented relatively close results, I would highly suggest using the Decision Tree Model because of its high accuracy score and both the testing and training data and for its fast prediction time.When it comes to health, we want a model that makes the best predictions that will be helpful in preventing the occurrence of a stroke in a timely manner.This model would predict less false negatives which is way worse in terms of being more expensive and having more negative effects on people.
# For Further Information:
For any additional questions or concerns in regards to my sales predictions, please contact me at julianas4013@gmail.com. Thank you!
