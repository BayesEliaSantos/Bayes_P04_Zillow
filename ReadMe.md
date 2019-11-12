Zillow Project README

# Zillow Clustering Test- Kevin Eliasen, Matt Santos

Goal: Improve our original estimate of the log error by using clustering methodologies.
Using previous knowledge from a Regression modeling project, we are tasked with improving upon that using clustering. 

Hypothesis: Location is the  biggest driver of price and also the biggest driver of the Zestimate error (logerror).


### Prerequisites
The code was written in Python 3.7.3 and you will need to have pandas, numpy, matplotlib,seaborn, and sklearn installed. Additionally, you will need access to the Zillow dataset which can be found at https://www.kaggle.com/c/zillow-prize-1/data


Project Github link: https://github.com/BayesEliaSantos/Bayes_P04_Zillow
Files needed from repo:
•	acquire.py
•	clusterfunctions.py
•	debug.py
•	dfo.py
•	evaluate.py
•	explore.py
•	model.py
•	prepare.py
•	wranglezillow.py
## Getting Started
Acquire and prepare:
-Acquire data from mySQL using the python module to connect and query. You will want to end with a single dataframe. Make sure to include: the logerror, all fields related to the properties that are available. You will end up using all the tables in the database.

Explore:
-	use visualizations to come up with possible variations of the data to use in your model

Split and Scale:
-	Prepare your dataframe for the models, splitting yoiur data into a test and train data, and scale your data as needed. 

Modeling:
-	We recommend using clustering to narrow your data to find the drivers of the logerror (dependent variable)
-	Use many different models: linear regression, logistic regression, Decision tree, etc. with this data set to improve the model.
Test:
-	Test your model using the split data sets to see if you’ve improved the model.

Our process:

Cluster:
We clustered the data by latitude, longitude, and price per square feet (more weighted) to isolate those houses by location in order to find the other drivers beyond location-based variables. 


Baseline: We used linear regression against basic variables to establish a baseline for comparison. 

Independent variables: Bathrooms, Bedrooms, and square feet
Dependent Variable: Logerror

Baseline Model= RMSE= .178



Linear Regression with Clusters:

We ran the Linear Regression for all the clusters where the p-value was under .05.

4 of the 8 clusters met this criteria.

We ran a model for cluster 6

We used the same independent variables from the baseline

Independent variables: Bathrooms, Bedrooms, and square feet
Dependent Variable: Logerror

Cluster 6 RMSE= .141


With these results of the separate clusters, we added 

“price per square foot” to the model to improve:

Independent variables: Bathrooms, Bedrooms, square feet, and structuredollarpersqft

Dependent Variable: Logerror



Cluster with Decision tree
Independent variables: Bathrooms, Bedrooms, square feet, and structuredollarpersqft
Dependent Variable: Logerror


Decisioj Tree= RMSE .175



