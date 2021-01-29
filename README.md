# Movie-Recommendation-System
Recommendation System Project - Flatiron Phase 4
Prepared and Presented by:  **_Sarah Zoeller_**, **_Crissy Bruce_**, **_Joe Resis_**

### Business Case   
Due to the COVID 19 pandemic, Large Co. employees have been working from home since April. The company has noticed a decrease in productivity, and suspects it may be due to employee burnout. Large Co. would like to create a model that can predict employee burnout based on various factors, in order to identify and provide support to the employees most affected by the current situation. 

### The Data
- Data was sourced from [Movielens](https://movielens.org/) and [IMDB](https://datasets.imdbws.com/)
- Dataset included more than 100,000 ratings  by 610 users for 9,700 movies
- Ratings are on a scale of 0.5 - 5, with 5 being the best rated
- Features of the dataset included User IDs, Movie IDs, Ratings, Release Year, Runtime, Director(s), and Genre(s)
- The mean rating is 3.50, and the standard deviation is 1.04.

### Exploratory Data Analysis (EDA)

### Modeling Process
- KNN Basic from the Surprise library was used as a baseline
  - Baseline RMSE: 0.97 
- Final model was SVD model from Surprise library that has been tuned with GridSearch
  - Final RMSE: 0.87
  - Model is off by 0.87 points on average

![Predicted Average Rating per User vs Actual Average Rating per User]()

### Conclusions
- The best performing model was XGBoost, with an overall accuracy of 73% and a recall for class 5 of 85% (out of all of the actual employees who had level 5 burnout, the model correctly classified 85% of them):

![Model Comparison](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/model_compare.PNG "Model Comparison")

![Matrices](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/matrices_xg.png "Matrices")

- The most important feature in the determination of class was mental fatigue score, followed by resource allocation and designation:

![Feature Importances](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/feature_importances_xg.png "Feature Importances")

- Preview of predictions on new employee data:

![Prediction Function](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/predictions_preview.PNG "Prediction Function")

#### Limitations
- Dataset only had employees that joined between 2008 and 2009 (No data on more recent employees)
- Limited features in dataset
- Blank (Nan) values were imputed using KNN Imputer, possibly skewing results

#### Next Steps and Recommendations
- Collect additional information on employees to use as predictors  (ie performance evaluations, age, marriage/family status, etc.)
- Examine relationship between burnout, loss of productivity, and attrition
- Identify and reach out to managers of all employees who scored a 5 in terms of burnout, and employees who scored a 4 and had high mental fatigue, high resource allocation and high designation


