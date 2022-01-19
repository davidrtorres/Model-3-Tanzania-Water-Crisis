## Introduction:

According to the World Health Organization, one out of six people in Tanzania lack access to safe drinking water.  Women and children must walk long distances to find water.  In rural Tanzania resdients walk 2 to 3 km daily in search of water from public sources or natural streams.  They must carry heavy containers for the water on their heads which weigh about 20 to 25 liters.  When the residents find the water they must wait in line at the water source or boreholes for hours for their turn.  The water shortage has been caused by population growth, high level consumption and climate change which has reduced the water resources.  Water shortages lead to poor sanitation, lack of safe drinking water and overcrowding at the water sources. 

The Tanzania Ministry of Water is seeking to solve the ongoing water crisis in Tanzania by increasing the number of functioning water wells.  It is crucial to the health and safety of communities that its residents have access to safe drinking water.  Tanzania has a lot of water wells that are non-functioningor in need of repair. 

## Business Problem and Objective:
The Tanzanian Water Ministry is seeking to solve the water crisis in Tanzania by increasing the number of functioning wells.  Predictive models can be used to aid in solving this problem.  The objective is to build classification models which will predict the functionality of the water wells in Tanzania.  I will concentrate on the models' accuracy in predicting whether the wells are functioning, not functioning or functioning but in need of repairs.  These predictions will provide the Tanzania Minstry of Water with information regarding the overall status of the wells.  I will also include an analysis of the data to provide information regarding the relationship between various features such as funders and waters and the functionality of the wells.  The analysis will provide some insights regarding whether certain features are contributing to the non-functioning of the wells.  Also, which areas to concentrate on in order to increase the number of functioning wells.

## The Data:
The dataset was obtained from the Tanzania Ministry of Water and Taarifa.  Taarifa is an open-source API.  The dataset consists of 59,400 rows and 40 features.  The features range from which entities funded construction of the water wells, location of the wells to quality of the water.  The dataset also includes a target label which consists of 3 categories regarding the functionality of the water wells: functioning, non-functioning, functioning but needs repairs.  The data types are numeric and objects.<br>

## Methods:
I used the OSEMN framework for this project.
1.  I obtained the data as indicated above.
2.  Scrubbed the data.  There were 3 main issues with the data that needed to be addressed:
    NaN values - several features had NaN values.  I addressed the NaN values by either imputing the NaN values with the median value of the feature or renamining       the category 'Unknown'.<br>
    Duplicate Features - Several features are duplicates of other features.  The duplicates were dropped from the dataset. 
    Feature categories with value of 0.  If the 0 value constituted a large percentage of the of feature I dropped the feature.  However, in some instances like         construction 0 was 34% of the values.  I imputed the median value of the feature for the 0 value.<br>
3.  Eploratory Data Analysis.  I created plots to see the relationship between certain features and the target variable.  I conducted EDA to see if we could get
    insights on factors like whether the location of well or quality of water had an impact on the functionality of a well.  Are there any patterns or trends in the     data?<br>
4.  I built Logistic Regression and KNearest Neighbors models to make the predictions.  I used the metric accuracy along with the Classification Report and
    Confusion Matrix to evaluate the performance of the models.  I utilized the GridSearchCV method for hyperparameter optimization.<br>   
5.  Interpret the data.<br> 

## Exploratory Data Analysis
![This is an image](/assets/images/quality_group.png)

## Modeling

## Findings
1.  The RandomForestClassifier was the highest performing model with an accuracy of 79%.
2.  In EDA we explored the relationship between important features and the target.  Regarding payment, it appears that whether payment is required to use well does it does impact functionality.  The largest group of wells is no payment where 11379 of the wells are functioning and 12062 are not functioning. The wells where some payment is required function better. For category 'annually' far more wells were functioning (2740), than non-functioning(655) and 247 in need of repair. Where a 'monthly fee' is required there were 5482 functioning wells, 1891 non-functioing wells and 927 in need of repairs.
<br>
3.  Water quality does impact functionality of well.  If the water quality is good there is a higher probability that well is functioning.  However, even if water quality is good there still a good chance it's non-functioning.  Water quality of good is by far the largest group of wells and constitutes 50,818 of the wells.  Of this category around 28,760 are functioning, 18154 are non-functioning and 18154 in need of repairs.  Water quality is a good status check so governments and organizations know whether they have to deal with just functionality status and/or water quality.<br>
4.  Age of well does impact functioning of the well. Most were built within the last 16 years and the majority within these years were functioning but still a high number not functioning.<br>
5.  Longitude and latitude were the feature that had the most importance on the model in making predictions.
    

