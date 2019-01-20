# yelp_NLP_project
The project of using yelp dataset to make NLP analysis
# Introduction
This project used dataset published by yelp which contains recent 10 years information about 'business', 'checkin', 'reivew', 'tip', 'user' on this platform. Project mainly focused on the users' review for the business and did sentiment analysis, business clustering and business recommendation. 
### language
Python, Sql
### libraries
Scikit_learn, Pandas, Numpy, Seaborn, Scipy, Matplotlib, Os
# Poreprocessing and EDA
Extracted the recent two years data of Las Vegas which has the most business_id in this dataset. 
Dropped the instance with missing values since few missing values. 
PLotted the correlation matrix to find some correlations between the features to prevent the collinarity and overfitting. Plotted the distributions of users' star rating for businesses and the average star rating gotten by the businesses to see the difference. 
Plotted distribution of the number of reviews gotten by the businesses  which is a Power Law distribution as result, that made sense. 
# Clustering and PCA
Used 'NLTK' tool kit to process the user review. Definded positive/negative by the star rating of users and lables were balanced, no need to sampling. Applied Tokenization, stopwords, stemming and Tf-Idf to convert the review from word spce to vector space to be used by the clustering. 
