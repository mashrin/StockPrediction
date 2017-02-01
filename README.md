# StockPrediction
Prediction of the stock trends with the chance of profit as the output indicator

Here, we describe the present the following 6 models that we will use to fit on 6 different stock datasets.

We use logistic regression (from Week 4), a generalized linear model that is well-studied in the statistical community. We test two different variants of logistic regression, one with L2 regularization penalty and one with L1 regularization penalty. Using cross validation, we can determine optimal values of the relevant tuning parameters.

 

Logistic Ridge Regression

sklearn - LogisticRegression
Regularization = L2

Inverse of regularization strength = 5000



Logistic LASSO Regression

sklearn - LogisticRegression
Regularization = L1

Inverse of regularization strength = 500

 

==========

 

We use random forests (from Week 10), which we felt like would complement logistic regression since the method of classification is so different, and does not assume a linear effect of each predictor.

 

Random Forest

sklearn - RandomForestClassifier

n_estimators = 100

 

==========

 

To explore an advanced model that we did not learn in class, we use gradient boosted trees. From reading forums on Kaggle and talking to Kaggle participants, this seems to be a method that performs very well in predictive modeling competitions, so we wanted to give it a try.

 

Gradient Boosted Trees

sklearn - GradientBoostingClassifier

n_estimators = 200

 

==========

 

We use Platt Scaling to blend two or more models togethers. To do this, we generate out of sample predictions for each stock, and then use logistic regression to blend together the predictions to minimize cross-validation score. We choose the two following blends

 

Ridge-RF Blend

Logistic Regression on predictions from Ridge and RF

Regularization = L2

Inverse of regularization strength = 1

 

Ridge-LASSO-RF-GBT Blend

Logistic Regression on predictions from all of our models

Regularization = L2

Inverse of regularization strength = 1

