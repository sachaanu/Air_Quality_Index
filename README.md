# Air_Quality_IndexCSE891 
Project Progress Report


The goal of the project is to develop and compare few Data Mining algorithms with each other and apply appropriate modeling techniques to identify key aspects of air pollution in multiple cities in Taiwan, India, and the USA. The data has been accumulated from multiple sources & Kaggle.com. 

As of October 22nd, I have performed the following steps:
•	I accumulated the data, cleaned, re-organized, and created calculated fields to summarize the data and document the pollution index for each city so that would work with it and perform the necessary calculations / modeling techniques.
•	I calculated the similarity (and a few different calculations of distance) of several cities as a means of comparing the pollutants in the air between various cities (pm2.5. so2, no2). I plan to create a chart in hopes of displaying some interesting differences between cities in different countries.
•	I created a correlation matrix to identify any highly correlated variables. Some variables that were linearly correlated with AQI (air quality index) were AMB_Temp, O3 and PM2_5. Some other variables that seemed to be realted with each other included; THIC, CH4, CO, SO2, NO, etc.







•	I created Regplots to further expand on our correlation matrix and identify linear relaitonships between several dependent variables and our outcome variable. The significant variables shown below include: CH4, CO, O3, PM10, SO2, and PM2_5. 



•	I created a Parallel Coordinates Graph that shows the AQI (in color below by category) arcoss multipe variables. Even though the AQI is calculated by only 4-5 columns, this plot displays the trend of how the independent variables (like NMHC) have interesting relationships with AQI and also impact the final classification. O3 has the clearest organized pattern, which is consent with some of results above. 


•	I created several initial models with Taiwan dataset to see which models might be significant with the rest of our data. These models included:
o	Linear Discriminant Analysis – which predicted the training dataset with 100% accuracy and the test set with 92% accuracy. 
o	Principle Component Analysis – I could explain a significant amount of the variance in model with around 5-6 components, as shown in the graph below: 

o	Naïve Bayes – I was able to create a model with the prediction accuracy of 97%. 
o	KNN – with K = 3, I was able to create a model with a 87% accuracy on the training set (using cross validation) and 78% on the test dataset. 
o	Decision Tree – I created the decision tree below that achieved a 78%: 

•	I plan to apply these modeling techniques with the USA and India datasets and then compare our results. 

Challenges faced with Data: 
•	The taiwan dataset has a lot of columns with black values.
•	Few of the observation were denoted with # or *  - Indicating these are incorrect measurments at the source by Human error, Machine error, Scale Variance.
•	The datset is so unworthy of analysis that even in Kaggle most of the Kernels available are only for vizualization.

Solution:
Application of regex is the only methods availabe to remove trailing symbols as $,#,* from observations – However, as of now the csv was cleaned manually by replacing mentioned characters with space.
Values with Blanks were removed with dropna() & only reveant columns were used for analysis.

Challenges with calculating AQI:
Each region in the world follows its slightly different metrics for calculating Air Quality Index.
Exhaustive research was carried to find a generally accepted formula across regions for calculating AQI, as I aim to deal with data from various continents.

https://www3.epa.gov/airnow/aqi-technical-assistance-document-may2016.pdf

Table 4 – Used to classify air quality for each pollutant

Unit of O3 was changed from parts per billion (ppb) to parts per billion (ppm)

Next Steps :

Though, I get great predictive accuracy by few of the above algorithms.
I can see there are gaps in the modelling process, as the Outcome variable is clearly plagued with class imbalance issue – which I aim to analyze & tackle.
Also, Models need to be verified for overfitting & bias.


Source of Data:
The data for the project is collected from Kaggle Dataset Repository provided below:
https://www.kaggle.com/shrutibhargava94/india-air-quality-data
https://www.kaggle.com/nelsonchu/air-quality-in-northern-taiwan
https://www.kaggle.com/epattaro/eda-usa-air-pollution-data-python/data

