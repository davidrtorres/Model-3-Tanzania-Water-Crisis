## Introduction:

According to the World Health Organization, one out of six people in Tanzania lack access to safe drinking water.  Women and children are mainly responsible for obtaining water and must walk long distances to find the water.  In rural Tanzania residents walk 2 to 3 km daily in search of water from public sources or natural streams.  They must carry heavy containers for the water on their heads which weigh about 20 to 25 liters.  When the residents find the water they must wait in line at the water source or boreholes for hours for their turn.  The water shortage has been caused by population growth, high level consumption and climate change which has reduced the water resources.  Water shortages lead to poor sanitation, lack of safe drinking water and overcrowding at the water sources. 

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
3.  Exploratory Data Analysis.  I created plots to see the relationship between certain features and the target variable.  I conducted EDA to see if we could get
    insights on factors like whether the location of well or quality of water had an impact on the functionality of a well.  Are there any patterns or trends in the     data?<br>
4.  I built Logistic Regression and KNearest Neighbors models to make the predictions.  I used the metrics accuracy along with the Classification Report and
    Confusion Matrix to evaluate the performance of the models.  I utilized the GridSearchCV method for hyperparameter optimization.<br>   
5.  Interpret the data.<br> 

## Exploratory Data Analysis
I performed EDA on the dataset to get insights about the data overall and to see how the features related to the target labels.  Here are some highlights of features for which I performed an analysis.<br>  
I wanted to explore whether the quality of the water impacted a well's functionality.  The below plot shows that there are 6 categories for water quality. The majority of the wells are in the category of good which constitutes 50,818 of the wells. Of this category around 28,760 are functioning, 18154 are non-functioning and 18154 in need of repairs. If the well has 'good' water quality there is a higher chance that it is functioning but there is still a high probability it's not functioning. If the water quality is salty or unknown it's probably non-functioning. This information is critcal for the government and organizations to know which wells have good water quality and just need the functioning issue addressed and which ones require not only the functioning issue but also the water quality issue which is completely different and more complicated issue.

<img src="/data/water_quality.png" width="700" height="500">

Does region_code impact functionality?
By grouping the features we can see how region and water quality are realted to functionality.  It's crucial to see which districts have the highest number of wells and their status.  The plot gives us a quick summary of the number of wells in each district and their status.  Region 11 has highest number of wells with 5300; around 4,200 are functioning, around 1,000 are non-functioning and around 100 are in need of repairs.  Region 17 has the second largest with 5,100 wells; around 3,000 are functioning wells and 1,500 are non-functioning.  In constrast it  shows that regions 8,9,40, 60, 80, 90 and 99 have very few wells and most are non-functioning.

Region 8 has among the lowest number of wells and most are non-functioning.  We can in the below chart when we grouped 'target', 'region_code','quality_group' for functioing we see that most of the water quality is 'salty' which isn't good.  Whereas, region 11 has the most number of wells and 4120 of the wells have 'good' water quality which as explained below contributes to a functioning well. 

<p align="center">  
    <img src="/data/region_code.png" width="600" height="400">
</p>
<p align="center">  
    <img src="/data/groupby_target_quality.png" width="400" height="200">
</p>

## Modeling
I created KNearest Neighbors and Random Forest models for the multi-class classification problem.  I used the method GridSearchCV for hyperparameter optimization.
The metrics used to evaluate the model's performance were accuracy, Classification Report and Confusion Matrix.  The RandomForestClassifier performed the best with a 79% accuracy.
Precision is  the ratio between the True Positives and all the Positives. For our problem statement, that would be the measure of wells that were correctly predicted  as functioning out of all the wells that are actually functioning.  When the model predicts that the well is functioning, it is correct around 82% of the time.  This is important because an organization needs to be able to rely on our predictions and does’t want to start spending time and money on repairing a well because the model predicted it as non-functioning when in fact it's actually functioning.  The model has done a pretty good job with this prediction.
  
<p align="center">  
    <img src="/data/classification_report.png" width="500" height="300">
</p>

## Findings
1.  The RandomForestClassifier was the highest performing model with an accuracy of 79%.
2.  In EDA we explored the relationship between important features and the target.  Regarding payment, it appears that whether payment is required to use well does it does impact functionality.  The largest group of wells is no payment where 11379 of the wells are functioning and 12062 are not functioning. The wells where some payment is required function better. For category 'annually' far more wells were functioning (2740), than non-functioning(655) and 247 in need of repair. Where a 'monthly fee' is required there were 5482 functioning wells, 1891 non-functioing wells and 927 in need of repairs.

3.  Water quality does impact functionality of well.  If the water quality is good there is a higher probability that well is functioning.  However, even if water quality is good there still a good chance it's non-functioning.  Water quality of good is by far the largest group of wells and constitutes 50,818 of the wells.  Of this category around 28,760 are functioning, 18154 are non-functioning and 18154 in need of repairs.  Water quality is a good status check so governments and organizations know whether they have to deal with just functionality status and/or water quality.<br>
4.  Age of well does impact functioning of the well. Most were built within the last 16 years from the most recent year of the dataset and the majority within these years were functioning but still a high number are not functioning.<br>
5.  Longitude and latitude were the features that had the most importance on the model in making predictions.
    

