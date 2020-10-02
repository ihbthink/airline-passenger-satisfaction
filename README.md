# airline-passenger-satisfaction
Study of 2015 US airline passenger satifaction

As passengers have a slew of cheap airline seats to choose from in the Covid-19 era, it is more important than ever for airlines to understand 
what factors drive passenger satisfaction so they can maintain or grow share in a struggling industry.

I decided to study a 2015 US airline passenger satisfaction study to determine which services most strongly influence a passenger's satisfaction rating.  The survey dataset
has 100k+ individual survey records, with a rating of "satisfied" or "neutral or dissatisfied" for each record.  Passengers were asked to rate all aspects of flying, including
leg room, onboard service, inflight wifi, food, online boarding, etc.

After using EDA techniques to determine that the model was balanced and to eliminate features with strong collinearity (such as arrival and departure delays), I used Bayes 
optimization to determine the best classification model to use for predicting the passenger satisfaction rating.  

An optimized Light GBM model proved to be more effective than Random Forest and Logistic Regression models. 

Classifier          |   Precision |   Recall |   F1 |   AUC
---------------------+-------------+----------+------+-------
 Light GBM           |        0.96 |     0.96 | 0.96 |  0.95
 Random Forest       |        0.92 |     0.92 | 0.92 |  0.92
 Logistic Regression |        0.87 |     0.87 | 0.87 |  0.87
 Dummy               |        0.32 |     0.57 | 0.41 |  0.5
 
Within that model the most important features were the inflight wifi rating, departure delay, checkin service rating, online boarding rating and seat comfort.

I would like to further study the breakdown of these results between business and personal travelers, as business travelers are significantly more profitable than personal
travelers.  However in today's environment, business travel is down significantly and it feels important not to marginalize the experience of any traveler.

