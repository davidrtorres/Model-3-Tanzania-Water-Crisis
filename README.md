### Introduction

According to the World Health Organization, one out of six people in Tanzania lacks access to safe drinking water. Women and children must walk long distances to find water. In rural Tanzania residents walk for 2 to 3 km daily in search of water from public taps  or natural streams. They must carrying heavy containers for the water on their heads which weigh about 20 to 25 litres. When the residents find water they will find long lines at the point of water tap or boreholes where they must wait hours for their turn. The water shortage has been caused by population growth, high level consumption and climate change which has reduced the resources of water. Water shortages lead to poor sanitation, lack of safe drinking water, and overcrowding at water sources. projectzawadi.org.

The Tanzanian Ministry of Water is seeking to solve the ongoing water crisis in Tanzania by increasing the number of functioning water wells. It is crucial to the health and safety of communities that its residents have access to drinking water. Tanzania has a lot of water wells that are non-functioning or in need of repair. Predictive modeling can be used to aid in solving this problem.


### Business problem:
The Tanzanian Water Ministry is seeking to solve the water crisis in Tanzania by increasing the number of functioning water wells. Build classification models Here is where you state the business problem you were trying to solve. Tanzania has a lot of water wells that are non-functioning or in eed of repair.

### Data
The dataset was obtained from from Taarifa and the Tanzanian Ministry of Water. The dataset consists of 59400 rows and 40 features. The features range from which entities funded construction of the water wells, location of the wells, regions, quantity of water in wells to quality of water. The dataset also included a target label which consisted of 3 categories regarding the operational status of the water wells: well is functioning, non-functioning, functioning but needs repairs.

### Objective
The objective is to build classification models which based on certain features will predict whether wells are functionig, non-fucntioning or in need of repairs. Specifically, I am seeking to concentrate on the models' accuracy in predicting whether wells are non-functioning. These predictions will provide the Tanzania Ministry of Water with information regarding the overall status of the wells. Also, provide critical information regarding how features such as funders and installers relate to operating status of the wells. Which features are contributing to non-functioning wells. Further, which areas to concentrate on in order to increase the oeprating levels of the wells.

### Methods
The classification models I created had an accuracy score that ranged from 58% to 78%. The Logistic Regression models didn't perform particularly well. Without default parameters the logisitc regression model's accuracy was 58% and with parameters it was 62%. With parameters the logistic regression was only 55% accurate in predicting whether a well was non-functioning. When I created a GridSearch with Logistic Regression the model improved a little to 59% in predciting that a well was non-functioning.
I created visualizations to show the distrbution of the data and to show how the features are related to the target. This is impotant because it shows what can be expected when we look at how, for example, a funder relates to the target. We can see from the graph that certain funders will have more functional well points and some will have fewer. These graphs give us immediate insights of what can be expected from the data. If I needto know quickly which regions have the most non-functioning wells the graphs will demonstrate this. Sentence about visualization.
I used the following prcoess to create the model and provide recommendations about the data: 
Obtained the data
Conducted Exploratory data analysis
Preprocessed the data
Created classification models
Used metrics to evaluate the models' overall performance.

