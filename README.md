## Introduction:

According to the World Health Organization, one out of six people in Tanzania lack access to safe drinking water.  Women and children must walk long distances to find water.  In rural Tanzania resdients walk 2 to 3 km daily in search of water from public sources or natural streams.  They must carry heavy containers for the water on their heads which weigh about 20 to 25 liters.  When the residents find the water they must wait in line at the water source or boreholes for hours for their turn.  The water shortage has been caused by population growth, high level consumption and climate change which has reduced the water resources.  Water shortages lead to poor sanitation, lack of safe drinking water and overcrowding at the water sources. 

The Tanzania Ministry of Water is seeking to solve the ongoing water crisis in Tanzania by increasing the number of functioning water wells.  It is crucial to the health and safety of communities that its residents have access to safe drinking water.  Tanzania has a lot of water wells that are non-functioningor in need of repair. 

## Business Problem:
The Tanzanian Water Ministry is seeking to solve the water crisis in Tanzania by increasing the number of functioning wells.  Predictive models can be used to aid in solving this problem.  The objective is to build classification models which will predict the functionality of the water wells in Tanzania.  I will concentrate on the models' accuracy in predicting whether the wells are functioning, not functioning or functioning but in need of repairs.  These predictions will provide the Tanzania Minstry of Water with information regarding the overall status of the wells.  I will also include an analysis of the data to provide information regarding the relationship between various features such as funders and waters and the functionality of the wells.  The analysis will provide some insights regarding whether certain features are contributing to the non-functioning of the wells.  Also, which areas to concentrate on in order to increase the number of functioning wells.

## The Data
The dataset was obtained from the Tanzania Ministry of Water and Taarifa.  Taarifa is an open-source API.  The dataset consists of 59,400 rows and 40 features.  The features range from which entities funded construction of the water wells, location of the wells to quality of the water.  The dataset also includes a target label which consists of 3 categories regarding the functionality of the water wells: functioning, non-functioning, functioning but needs repairs.  

## Methods
I used the OSEMN framework for this project.
1.  I obtained the data as indicated above.
2.  Scrubbed the data.  There were 3 main issues with the data that needed to be addressed
    NaN values - several features had NaN values.  I addressed the NaN values by either imputing the NaN values with the median value of the feature or renamining       the category 'Unknown'.
    Duplicate Features - Several features are duplicates of other features.  The duplicates were dropped from the dataset.  

