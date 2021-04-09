# Machine Learning Challenge

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.

To help process this data, create machine learning models capable of classifying candidate exoplanets from the raw dataset.

1. Preprocess the raw data
2. Tune the models
3. Compare models

# Processing
model0_Compare.ipynb - compares nine different models, each with no scaling, standard scaling, and minmax scaling.
model_top3.ipynb - top three models and their best scaling option are further evaluated and compared.
model_final.ipynb – the input_data is trimmed and tuned to a RandomForest model with no scaling.

# Summary
A total of 27 evaluations were made (9 models * 3 scales).  The top three models and their corresponding scaling method were further tuned through feature selection.  Once tuned, all three variations (Support Vector Classifier (SVC) with standard scaling, RandomForest with no scaling, and DecisionTree with standard scaling) had an accuracy during training at over 99.0% and during testing at greater than 98.0%.

With over 5000 training and testing records, the number of false positives outnumbered the confirmed exoplanets by about 2:1.  The top three models were run against candidate data that has not been confirmed as either an exoplanet or a false positive.  One would expect a similiar 2:1 ratio to occur here as well, this was not the result.  However, there could be other factors that allowed easier dismissal of candidates, for example, leaving the bulk of the yet unknown to favor eventually being confirmed.

| Model         | predicted confirmed | predicted false positive | Average accuracy from training and testing |
|---------------|---------------------|--------------------------|--------------------------------------------|
| SVC           | 3                   | 1684                     | 0.9890648567119156                         |
| Random Forest | 1515                | 172                      | 0.9939668174962293                         |
| Decision Tree | 1665                | 22                       | 0.9888134741075918                         |

RandomForest was chosen as the top candidate because it scored the best against known data and had the least bias during prediction.  Even still this model predicts a 1:9 ratio compared to the 2:1 ratio of known data (false positive:confirmed).

More complete documentation can be found at https://github.com/dougbhigh/Machine-Learning-Challenge/blob/main/Documentation.docx