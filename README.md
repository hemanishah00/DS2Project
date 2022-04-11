# DS2Project
DS2 Project repository
Deep Dive of Housing in India 
Part A - Comprehensive Analysis of India Housing Census Data 2011
•	Visualized and interpreted the correlations of various fields.
o	We find insights like:
	We find a negative correlation between Households using electricity and those using Kerosene - which implies less reliance on Kerosene as electricity distribution increases
•	Comparing the averages of various facilities for India vs. Union Territories vs. States.
o	We find insights like:
	We found that generally the union territories had much better facilities compared to the other states of India and India as a whole.
•	Comparing each facility for a state with the country average.
o	We find insights like:
	Some states like Chandigarh, have much better facilities than India as a whole.
•	Compared the distribution of the facility across the country grouped by state.
o	We find insights like:
	Bihar, Assam, Jharkhand, Meghalaya, Uttar Pradesh and Odisha heavily rely on Kerosene.
•	Created a filtering algorithm which basically answers the question:
 What state should I live in?
o	if the user wants to live in a house with the following conditions :
	For example: Assets like internet connection is very important to the user so they set a threshold of 50%. This means that our algorithm will filter out all the localities in which less then 50% of the houses have internet connection.
o	Once the user decides on all the fields, we will try to find a locality where such houses are typical.
o	Finally we plot the count of localities per state which tell us which states will have high probabilities of having houses like the one the user describes(implemented in filtering_final.ipynb)
o	We have implemented this in our UI : we create a plot by taking the mean of percentage of the features that the user selects for a particular field for all the states.
Part B - Housing Price Prediction from Metropolitan Indian Cities
This dataset comprises data that was scraped. It includes:
•	collection of prices of new and resale houses located in the metropolitan areas of India
•	the amenities provided for each house
Our main.py contains the general pipeline used for our solution:
 
Level 1: Creating Master Data: combining the files for the six cities(using functions defined in CreateMasterDataset file)
Level 2: Cleaning Pipeline(functions defined in pipelineClasses file): 
•	Drops Unecessary Columns
•	Replace NaN Values
•	Add Area Bins
•	Custom Imputer
•	Handle Outliers
•	One Hot Encoder
•	Feature Engineering: Added HQLI
•	Standardization
Level 3: Modelling
•	Linear Regression
•	K-Nearest Neighbors
•	Neural Network
•	Decision Tree
•	Bagging Ensembles
•	Random Forest
•	Gradient Boosting
Code for all the models have been saved in the folder Part B/models. The model weights have been saved in PartB/models/savedModels.
We then find the mse and R2 scores of each model and compare them.
We also visualized local and global feature importance to understand the model better. This code can be found in eda and eda2 files.
