# “Why” ? Documentation

1) Why this project ?

This is a series of projects on Time Series where we are exploring the possibilities of various Time Series models. We wanted to see when classical statistical models remain sufficient and when more adaptive approaches become necessary.

The first one “Time Series Forecasting with Holts-Winters” explored the 3 basic variants of Holt-Winters models with a dataset which had a steady trend and seasonality. While giving a good understanding on the premises of each of these models, this project concluded with a conviction to explore Time series by contrasting Holt–Winters with alternative forecasting approaches on more challenging datasets.

The second project “Insights into Adversarial Time Series” explored a challenging dataset in full depth and we could see that ARIMA – with all its  capabilities – was insufficient to handle an adversarial time series where there was no structure in place for Classical time series models.

This Project “Why ML Sometimes Wins and Sometimes Embarrasses Itself” – as the title suggests took a twin goal for itself. First, we wanted to check the same adversarial dataset in full depth with Linear Model and ML model. The second and most important goal of this project was to see the limits of these General models though they seem to be better than the simple time series models.

2) Why evaluation was done in two aspects ?

We attempted both Single-step evaluation as well as data splits for both Linear and ML models because the former is better for understanding volatile processes while the latter helps to review the future performance and reporting

3) Why both ‘dense’ and ‘sparse’ lags were tried ?

We tried both dense lags (13 continuous weeks) as well as sparse lags (week 1,4,12 and 52) While dense let the model smoothly interpolate noise, sparse lags force the model to commit to real structure. The intention was to ensure that we test the models sufficiently before reaching any conclusion.

4) Why we did not attempt transformations on the dataset ?

Since we decided to use XGBoost for our further exploration after a minimal testing on Gradient Booster, we did not try Log transformation as the volatility structure is additive and tree-based learners do not rely on variance-stabilizing transformations.

5) Why we decided to review Illusion of success ?

Typically such exploratory projects will test various failure modes to ensure the robustness of models under review. Since conventional performance improvements were absent, we intentionally shifted focus to exploring illusion modes

6) Why we used categorical encoding for our Data Leakage experiment ?

When we did a study about illusions of success with data leakage, we had introduced a categorical encoding to indicate the target magnitude instead of choosing ordinal values since XG Boost model is capable of utilizing the signal from categorical feature quite effectively.

7) Why we did two experiments on Illusions of success ?

We wanted to pick up on regular kind of failure mode like data leakage and another one with common mistakes that can creep in during model design. In fact we picked up a very common mistake that happens in real world (recursive data instead of actual data) to see the impact on the model behavior

8) Why Oracle plot ?

We were tempted to look at an experimental view of the ML model with perfect knowledge on extreme deviation weeks.  The oracle pot further showed that this model would need baby sitting to predict future.
