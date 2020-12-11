# HousePriceRegressions

Firstly, we had an overview and perform and exploratory data analysis on the dataset giving us essential insights. Information such as variables being skewed, missing values, relation between dependent and independent variables and outliers was evaluated. This activity was rather extensive but it gave us some necessary domain knowledge and a better feeling regarding the type of data we were working with - numerical, ordinal, categorical.

We then take a look at the correlation matrix and perform label encoding for the categorical variables. The top 5 most correlated features with SalePrice are OverallQual (0.79), GrLivArea (0.71), GarageCars (0.64), GarageArea (0.62) and TotalBsmtSF (0.61). We also perform an ANOVA on two independent varibles to see if they have statistically significance on the final Sale Price (is actually good idea to run this after you have the model results). This was to show some of the tools we can we in EDA prior to transforming our dataset.

Afterwards we treated the missing data. Before imputing values into the dataset we first removed the independent variables which a value that was dominant above the others (> 99 %), thus removing variables that did not present any variance (don't tell us anything about the final SalePrice). Some of the imputed data was obtained by using subtypes of other independent variables, using mean, mode or fulfil the categorical data with 'None'.

It was time for feature creation. From the original variables, we created YearsinceRemodel, TotalSF and TotalHomeQuality. We also took advantage of the natural order of some of the categorical variables, transforming them into numbers and thus giving them more meaning ('None' -> 0, 'Poor' -> 1, ..., 'Excelent' -> 5). Everything was ready to go in the oven, but first one hot encoding! (there is actually a slightly difference between get pandas get_dummies and sklearn.preprocessing.OneHotEnconder)

For modeling, the idea was to get to know a couple of supervised learning algorithms used for regression problems. For this kernel the ridge, lasso, svr, gradient boost, xgboost algortihms were implemented. To optimize the base models a blendend model regressor was used on top of the stacking regressor. 

On an ending note, one could also have a look at the inflation in house prices in the upcoming years of the release of this dataset to make some adjustments. Another topic of interset is to see if the purchasing power of the families in that area managed to keep up the inflation and if that reflected the final SalePrice of the houses. 

Also, understanding how the different sale types influence the overall prediction is a good option to explore. This affects sale prices between family members which tend to be lower than actual market prices and thus, its influence on the final prediction should be take into account (maybe consider disgarding thise values).   

Lastly, I recommend to take a look at these two kernels, which discuss the interpretabilty of linear models, as well the process of validating your results through statistical inference.

https://towardsdatascience.com/wrangling-through-dataland-modeling-house-prices-in-ames-iowa-75b9b4086c96

https://medium.com/diogo-menezes-borges/project-2-predicting-house-prices-on-kaggle-989f1b0c4ef6
