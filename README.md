# *This dataset involves predicting whether a structure is in the atmosphere or not given radar returns using machine learning :*


# [Dataset]()
   *This radar data was collected by a system in Goose Bay, Labrador. This system consists of a phased array of 16 high-frequency antennas with a total transmitted power on the order of 6.4 kilowatts. See the paper for more details. The targets were free electrons in the ionosphere. **"Good"** radar returns are those showing evidence of some type of structure in the ionosphere. **"Bad"** returns are those that do not; their signals pass through the ionosphere.*

### [Attributes information:]()

   * *Number of Instances: 351.*
   * *Number of Attributes: 34 plus the class attribute.*
   * *All 34 predictor attributes are continuous.* 
   * *The 35th attribute is either "good" or "bad".*
   * *This is a binary classification task.*
   * *Missing Values: None.*


### [Experiment Results:]()
* **Data Analysis**
    * *All columns contain outliers except for N.*
 * **Performance Evaluation**
    * *Splitting the dataset by 80 % for training set and 20 % validation set.*
 * **Training and Validation**
    * *GausianNB gets a higher accuracy score than other classification models.*
    * *GaussianNB ( 99 % accuracy score )*
 * **Fine Tuning**
    * *Model : Extreme GradientBoosting Classifier*
    * *Best: 0.932143 using {'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 75*
 * **Performance Results**
    * *Training Score: 99.64%*
    * *Validation Score: 98.57%*
    * *accuracy score: 0.9857*
    * *roc auc score: 0.98*
    * *f1 score: 0.9795*
    * *precision score 1.0*
    * *recall score 0.96*

 classification_report :

              precision    recall  f1-score   support

         0.0       0.98      1.00      0.99        45
         1.0       1.00      0.96      0.98        25

                                       0.99        70
                   0.99      0.98      0.98        70
                   0.99      0.99      0.99        70







