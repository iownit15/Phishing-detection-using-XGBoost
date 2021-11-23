# Phishing-detection-using-XGBoost
Creating a Phishing detection model using Xtreme Gradient Boosting which will be trained to detect phishing websites 
by analysing the characteristics of the input URL provoded by the user. 

First I defined a function that analyses various characteristics of an input URL (17 to be precise)
like is the URL having IP address in it, does it use URL Shortening Services like TinyURL, does it have
a HTTPS token, age of the URL’s domain, does it have a trusted Certificate Authority, etc. and generates
a 2D numpy array corresponding to the input URL which contains 17 elements where each element can
be a -1, 0 or 1 based on whether the corresponding characteristic is phish/unsafe, suspicious or safe.
In the second part, I built a XGBoost model and obtain a dataset from kaggle to
train it and validate its performance. The dataset is split into training and testing sets with 20% of the 
dataset being used for testing and validating the performance.
Then I created an instance of the XGBoost Classifier and fit it on the training sets. Then after the model
is trained, use the testing set and get its classification from the model and compare it with the original
testing set classifications.
Finally, the 2D numpy array generated in the first part can be passed to our trained model to get the
prediction whether the URL is of a phishing website or not from our model.
