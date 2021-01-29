# Movie-Recommendation-System
Recommendation System Project - Flatiron Phase 4
Prepared and Presented by:  **_Sarah Zoeller_**, **_Crissy Bruce_**, **_Joe Resis_**

### Business Case   
Netflix has hired SCJ consulting to build a movie recommendation system to use for customers who first join the platform. The system asks users to rate five movies they have seen and returns five tailored movie recommendations. The system will use a collaborative filtering model to create the recommendations.

### The Data
- Data was sourced from [Movielens](https://movielens.org/) and [IMDB](https://datasets.imdbws.com/)
- Dataset included more than 100,000 ratings  by 610 users for 9,700 movies
- Ratings are on a scale of 0.5 - 5, with 5 being the best rated
- Features of the dataset included User IDs, Movie IDs, Ratings, Release Year, Runtime, Director(s), and Genre(s)
- The mean rating is 3.50, and the standard deviation is 1.04.

### Exploratory Data Analysis (EDA)
<img src="https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/num_v_rating.png" width="400" height="400"/>
- Frequently rated movies were rated higher on average

<img src="https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/top_mov.png" width="400" height="400"/>
- Over 6000 movies had less than 5 ratings, while others had upwards of 300, potentially resulting in popularity bias


### Modeling Process
- KNN Basic from the Surprise library was used as a baseline
  - Baseline RMSE: 0.97 
- Final model was SVD model from Surprise library that has been tuned with GridSearch
  - Final RMSE: 0.87
  - Model is off by 0.87 points on average

![Predicted Average Rating per User vs Actual Average Rating per User](https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/act_pred.png)

### Recommendation Function
![Recommendation Function Sample](https://github.com/swzoeller/Movie-Recommendation-System/blob/main/Images/recommend_fx.png)

### Conclusions
- The final model is not a perfect fit based on the RMSE (0.87), but is less than the standard deviation of the original ratings dataset (1.05)
- Recommendations appear to be more accurate when genre is specified

### Future Steps and Limitations
- Obtain reviews for movies that do not have a sufficient amount of reviews to be deemed reliable to the dataset or consider removing from model
- Investigate approaches to deal with popularity bias so to increase the representation of less popular movies (considering including weights in model)
- Create a more robust model with LightFM by incorporating movie features into weighting
- Calculate similarity metric between recommended movies and highest rated movies to better validate recommendations

