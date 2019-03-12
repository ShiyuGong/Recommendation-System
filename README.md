# Recommendation-System
Amazon Book Review-Recommendation with Collaborative Filtering 
## Overview 
With the rapid growth of data collection, more efficient systems are created based on the big data. Recommendation system is one of information filtering systems which could improve the quality of search results and provide items that are more relevant to the search item or are related to the search history of the user. Almost every major tech company has applied recommendation systems in some form or the other: YouTube uses it to decide which video to play next on autoplay; Spotify uses it to provide users "Made for you" daily mixes etc.

In terms of this project, we try to learn from data and recommend best books to users, based on self & others behavior. This dataset contains book reviews from Amazon, with columns User ID, Book ID, Rating (1 to 5) and Date they gave the ratings (timestamp Unix). Because of the huge data size, the ratings_Books_sample.csv used is sampled from the original dataset with 200K records.

![CollaborateFiltering](https://user-images.githubusercontent.com/43686840/54166860-5cec1d00-4424-11e9-8210-c80f971931cc.png)

## Technique 
In the total pool, there are 134,697 books and 73,600 users. Firstly, the bar chart is made to give us a first look on how the data spread. We can see that the rating tends to be relatively positive (83% of the ratings > = 4), which may be due to the fact that unhappy readers tend to just leave instead of making efforts to rate. As a result, it indicates that low rating books are generally very bad. 

