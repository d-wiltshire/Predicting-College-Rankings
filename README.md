# Gaming-College-Rankings

## Summary

The goal of this project was to use supervised machine learning on a college ranking dataset to identify whether some metrics have an outsized influence on the overall ranks. Put another way: **if we were a college president with money to invest and had the goal of improving our college's ranking, which metrics would offer the best ROI?** 

The dataset used was the Fall 2022 Washington Monthly rankings data. The Washington Monthly data <a href="https://washingtonmonthly.com/2022-college-guide/national/">can be found here</a> and is included in the Resources folder of this repository.

This project was presented during 2U's September 2022 Demo Day event. The <a href="https://docs.google.com/presentation/d/1sIsP8V9POlaAX15FoTc-cSyBhuIiCIckmcTLBudotPE/edit?usp=sharing">slide deck can be found here</a>. 


## Tools

- Python
- R
- Supervised Machine Learning models: 
  - Multiple Linear Regression
  - Random Forest Regressor
  - Decision Tree Regression
  - Support Vector Regression

## Process

The data were very clean, so after encoding the single categorical varable, the data were usable for machine learning regression models.

### Overall rank as target, no feature reduction

I first applied the machine learning models using the overall school rank as the target, and without removing any usable features. The R-squared values were high, especially for Random Forest and Linear Regression, which lent confidence to the model fit for the data.

![image](https://user-images.githubusercontent.com/100863488/193072826-04888e78-b73b-417e-9ccb-a3a5728aee40.png)

I applied Random Forest feature importances and R linear regression statistical summaries to learn more about how the individual metrics influence the overall rank.

![image](https://user-images.githubusercontent.com/100863488/193073315-19ce937c-84e6-4aa5-84d1-3f7c941d5f5b.png)

The Random Forest feature importances pointed to 88% of the influence coming from the Social Mobility Rank, which was a feature in the Washington Monthly dataset and also a subrank derived from the other social mobility features, like graduation rate. 

The R statistical summary also pointed to an outsized influence coming from the Social Mobility Rank. 

![image](https://user-images.githubusercontent.com/100863488/193074127-1dda9341-c2c4-42e8-b5d6-765c796541d8.png)


### Attempting feature reduction with overall rank

I then attempted feature reduction to improve the accuracy of the model and learn more about the influence of various factors. However, all feature reduction attempts resulted in significantly less accurate models. Please view the Jupyter Notebooks available in this repository for more information regarding features removed and the resulting levels of model accuracy.


### Social Mobility Rank as target, no feature reduction

The next step was to use the Social Mobility Rank itself as a target to learn more about the feature importances of the social mobility features. The R-squared value was lower for the Random Forest model, but still high enough to be considered significant. Using the Social Mobility Rank as target resulted in a much more even distribution of feature importances, as can be seen in the Random Forest results and R statistical summary:

![image](https://user-images.githubusercontent.com/100863488/193075335-96cfe1e4-882d-41db-b5e1-886fe46604b5.png)

![image](https://user-images.githubusercontent.com/100863488/193075570-783820a5-a9a9-4427-8b13-b61cfeac4f90.png)




## Resources



An explanation of the Washington Monthly methodology: https://washingtonmonthly.com/2022/08/28/a-note-on-methodology-4-year-colleges-and-universities-13/


Forbes: https://www.forbes.com/top-colleges/

Forbes methodology: https://www.forbes.com/sites/emmawhitford/2022/08/30/how-we-rank-americas-top-colleges/?sh=13ffba471b66

US News methodology: https://www.usnews.com/education/best-colleges/articles/how-us-news-calculated-the-rankings


Other questions:
- Change over time? Previous years?
- Can you predict Forbes and US News rankings based on WM data by removing unneeded dimensions?
- Actual vs. reported methodology (using R feature importances as well as machine learning/RandomForestRegressor feature importances)

