Module 3 Final Project

The Operational Status of Water Points in the Country of Tanzania
Only 57 percent of Tanzania’s population of 57 million has access to an improved source of safe water. People living under these circumstances, particularly women and girls, spend a significant amount of time traveling long distances to collect water. In Tanzania, demand for water is high and the market for water products (storage tanks, pipes, rain harvesting facilities, etc.) and suppliers is increasing.

Business problem:
The Tanzanian Water Ministry is seeking to solve the water crisis in Tanzania by increasing the number of functioning water wells. Build classification models Here is where you state the business problem you were trying to solve. Tanzania has a lot of water wells that are non-functioning or in eed of repair.

Data
The dataset was obtained from from Taarifa and the Tanzanian Ministry of Water. The dataset consists of 59400 rows and 40 features. The features range from which entities funded construction of the water wells, location of the wells, regions, quantity of water in wells to quality of water. The dataset also included a target label which consisted of 3 categories regarding the operational status of the water wells: well is functioning, non-functioning, functioning but needs repairs.

Objective
The objective is to build classification models which based on certain features will predict whether wells are functionig, non-fucntioning or in need of repairs. Specifically, I am seeking to concentrate on the models' accuracy in predicting whether wells are non-functioning. These predictions will provide the Tanzania Ministry of Water with information regarding the overall status of the wells. Also, provide critical information regarding how features such as funders and installers relate to operating status of the wells. Which features are contributing to non-functioning wells. Further, which areas to concentrate on in order to increase the oeprating levels of the wells.

Methods
The classification models I created had an accuracy score that ranged from 58% to 78%. The Logistic Regression models didn't perform particularly well. Without default parameters the logisitc regression model's accuracy was 58% and with parameters it was 62%. With parameters the logistic regression was only 55% accurate in predicting whether a well was non-functioning. When I created a GridSearch with Logistic Regression the model improved a little to 59% in predciting that a well was non-functioning.
I created visualizations to show the distrbution of the data and to show how the features are related to the target. This is impotant because it shows what can be expected when we look at how, for example, a funder relates to the target. We can see from the graph that certain funders will have more functional well points and some will have fewer. These graphs give us immediate insights of what can be expected from the data. If I needto know quickly which regions have the most non-functioning wells the graphs will demonstrate this. Sentence about visualization.
I used the following prcoess to create the model and provide recommendations about the data: 
Obtained the data
Conducted Exploratory data analysis
Preprocessed the data
Created classification models
Used metrics to evaluate the models' overall performance.

