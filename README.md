# Recommendation-System
Amazon Book Review-Recommendation with Collaborative Filtering 
## Overview 
With the rapid growth of data collection, more efficient systems are created based on the big data. Recommendation system is one of information filtering systems which could improve the quality of search results and provide items that are more relevant to the search item or are related to the search history of the user. Almost every major tech company has applied recommendation systems in some form or the other: YouTube uses it to decide which video to play next on autoplay; Spotify uses it to provide users "Made for you" daily mixes etc.

In terms of this project, we try to learn from data and recommend best books to users, based on self & others behavior. This dataset contains book reviews from Amazon, with columns User ID, Book ID, Rating (1 to 5) and Date they gave the ratings (timestamp Unix). Because of the huge data size, the ratings_Books_sample.csv used is sampled from the original dataset with 200K records.

![CollaborateFiltering](https://user-images.githubusercontent.com/43686840/54166860-5cec1d00-4424-11e9-8210-c80f971931cc.png)

## Technique 
In the total pool, there are 134,697 books and 73,600 users. Firstly, the bar chart is made to give us a first look on how the data spread. We can see that the rating tends to be relatively positive (83% of the ratings > = 4), which may be due to the fact that unhappy readers tend to just leave instead of making efforts to rate. As a result, it indicates that low rating books are generally very bad. 
![barchart](https://user-images.githubusercontent.com/43686840/54166891-91f86f80-4424-11e9-8de7-d56ffdf17e1f.png)
Before building the model, to improve the data quality, the following two steps are done: remove books with too less reviews (they are relatively not popular); remove users who give too less reviews (they are relatively less active). After trimming down the data, the data size changes from 200K records to 130K.

To create collaborative filtering recommendations, Surprise library is utilized here to implement SVD. Collaborative filtering matches persons with similar interests and provides recommendations based on this matching. Collaborative filters do not require item metadata like its content-based counterparts. 

The result of 3-fold RMSE, MAE of algorithm SVD is as follows. We get a mean Root Mean Square Error of 0.99 approx. Then, we could use the model to predict one specific user’s preferences. For instance, we focus on the user A00006923FEAFJLE7GHEL and the top 10 books he or she would love to read are shown below based on the model estimation.
![image](https://user-images.githubusercontent.com/43686840/54166899-9ae94100-4424-11e9-9b29-53915ca0c3c8.png)
![image](https://user-images.githubusercontent.com/43686840/54166906-a2104f00-4424-11e9-80e9-230a95c807f1.png)
## Conclusion 
Based on Amazon book reviews data, SVD is implemented to create the collaborative filtering recommendation and such recommendation system could estimate book ratings for users and recommend 10 books a user would love to read which have the highest estimated ratings.

However, one of the limitations of this project comes from the sampled Amazon book review data. Because the original dataset is too big, I just sampled 200K records from it. As a result, there are a large number of books which do not have many reviews. (Remember although I have removed books with too less reviews using 0.8 quantile, the book minimum times of review are still 1.) The data quality would influence the accuracy and efficiency of the recommendation system to some degree.  If we could find a dataset within which each book has many reviews and each user rates many books, the model is expected to be better. In addition, the dataset only has book id but does not have the corresponding book names, which increases the difficulty for us to check the recommendation results and get insights from it.


