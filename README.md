# yelp_NLP_project
The project of using yelp dataset to make NLP analysis
# Introduction
This project used dataset published by Yelp which contains recent 10 years information about 'business', 'checkin', 'reivew', 'tip', 'user' on this platform. Project mainly focused on the users' review for the business and did sentiment analysis, business clustering and business recommendation. 
### language
Python, Sql
### libraries
Scikit_learn, NLTK, Pandas, Numpy, Seaborn, Scipy, Matplotlib, Os
# Preprocessing and EDA
Extracted the recent two years data of Las Vegas which has the most business_id in this dataset. 
Dropped the instance with missing values since few missing values. 
PLotted the correlation matrix to find some correlations between the features to prevent the Multicollinarity and overfitting. 
Plotted the distributions of users' star rating for businesses and the average star rating gotten by the businesses to see the difference. 
Plotted distribution of the number of reviews gotten by the businesses  which is a Power Law distribution as result, that made sense. 
# Clustering and PCA
Used 'NLTK' tool kit to process the user review. Definded positive/negative by the star rating of users and lables were balanced, no need to sampling. Applied Tokenization, stopwords, stemming and Tf-Idf to convert reviews from word spce to vector space to be used by the clustering. Trained K-means with 8 clusters and printed 10 main words for each centroid. Inspecting the words in each centroid could roughly figure out the categories for the business_id. Did PCA with 50 principle components for the training set and plotted ratio of variances explained by these principle components. Compared the results of the model trained by raw data and PCA processed data. The accuracy on the test set model with raw data is higher than the model with PCA processed data, however, there was no overfitting on the later model. Thus, the PCA could reduce the feature dimensionality to prevent the overfitting and improve efficiency, it also harms the accuracy of the model and features importance are hard to understand.
# Sentiment Analysis
Implemented the Cosine_Similarity to do the review search engine, most of the top 5 similar reviews gotten by the engine have same sentiments as the original one. Built Naive-Bayes and Logistic Regression classifiers to do the sentiment analysis and used Cross-Validation, regularization to tune the hyperparameter and cure overfitting. Gotten 0.86 accuracy by Logistic Regression. Inspected the top 10 words determining positive reviews and top 10 words determining negative reviews, which were very accurate. 
# Recommender
Designed the utility matrix of businesses and users to be used by the recommender. Built Item-item Collaborative Filtering Recommender, NMF Recommender, UVD Recommender. 
# Summary 
Clustering is a good unsupervised learning way to find some potential attributes which could be useful to make business decision. PCA is double-edged, since it reduces the dimensionality, at the same time, harms the accuracy. Because the principle components that explain much variance are possible less important to the prediction model. In this project, Logistic Regression did good job on the sentiment analysis. Next step I could try the Spark ALS to dessign the recommeder and RNN to do the sentiment analysis. 
