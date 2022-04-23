1. Title: Johns Hopkins University Ionosphere database

2. Source Information:
   -- Donor: Vince Sigillito (vgs@aplcen.apl.jhu.edu)
   -- Date: 1989
   -- Source: Space Physics Group
              Applied Physics Laboratory
              Johns Hopkins University
              Johns Hopkins Road
              Laurel, MD 20723 

3. Past Usage:
   -- Sigillito, V. G., Wing, S. P., Hutton, L. V., \& Baker, K. B. (1989).
      Classification of radar returns from the ionosphere using neural 
      networks. Johns Hopkins APL Technical Digest, 10, 262-266.

      They investigated using backprop and the perceptron training algorithm
      on this database.  Using the first 200 instances for training, which
      were carefully split almost 50% positive and 50% negative, they found
      that a "linear" perceptron attained 90.7%, a "non-linear" perceptron
      attained 92%, and backprop an average of over 96% accuracy on the 
      remaining 150 test instances, consisting of 123 "good" and only 24 "bad"
      instances.  (There was a counting error or some mistake somewhere; there
      are a total of 351 rather than 350 instances in this domain.) Accuracy
      on "good" instances was much higher than for "bad" instances.  Backprop
      was tested with several different numbers of hidden units (in [0,15])
      and incremental results were also reported (corresponding to how well
      the different variants of backprop did after a periodic number of 
      epochs).

      David Aha (aha@ics.uci.edu) briefly investigated this database.
      He found that nearest neighbor attains an accuracy of 92.1%, that
      Ross Quinlan's C4 algorithm attains 94.0% (no windowing), and that
      IB3 (Aha \& Kibler, IJCAI-1989) attained 96.7% (parameter settings:
      70% and 80% for acceptance and dropping respectively).
        
      Download dataset : https://github.com/rotimi2020/Ionosphere-prediction/blob/main/Ionosphere.csv
            
            
4. Relevant Information:
   This radar data was collected by a system in Goose Bay, Labrador.  This
   system consists of a phased array of 16 high-frequency antennas with a
   total transmitted power on the order of 6.4 kilowatts.  See the paper
   for more details.  The targets were free electrons in the ionosphere.
   "Good" radar returns are those showing evidence of some type of structure 
   in the ionosphere.  "Bad" returns are those that do not; their signals pass
   through the ionosphere.  

   Received signals were processed using an autocorrelation function whose
   arguments are the time of a pulse and the pulse number.  There were 17
   pulse numbers for the Goose Bay system.  Instances in this databse are
   described by 2 attributes per pulse number, corresponding to the complex
   values returned by the function resulting from the complex electromagnetic
   signal.

5. Number of Instances: 351

6. Number of Attributes: 34 plus the class attribute
   -- All 34 predictor attributes are continuous

7. Attribute Information:     
   -- All 34 are continuous, as described above
   -- The 35th attribute is either "good" or "bad" according to the definition
      summarized above.  This is a binary classification task.

8. Missing Values: None



## -------Ionosphere Data Prediction-------

<br> The First part of notebook deals with checking out </br> 
1. Nunique
2. Duplicated rows


<br> Also the Second part of notebook deals with  </br> 
1. EDA
2. Feature Selection  using Mutual Info Classification
3. preprocessing like RobustScaler not require for all ensemble Algorithms

<br> Finally the Third part of notebook deals with training/prediction </br> 
For this prediction, we will try out the following ensemble algorithm

1. AdaBoost Classifier
2. ExtraTrees Classifier
3. Random Forest Classifier
4. Gradient Boosting Classifier
5. Light GradientBoosting Classifier
6. CatBoost Classifier



# ***Boxplot Diagram***
* ****Linear/Non Linear Algorithms***. 
1. Logistic Regression
2. DecisionTree Classifier
3. KNeighbors Classifier
4. Linear Discriminant Analysis
5. GaussianNB
6. SVC

* ****Ensemble Algorithms***. 
1. AdaBoost Classifier
2. ExtraTrees Classifier
3. Random Forest Classifier
4. Gradient Boosting Classifier
5. Light GradientBoosting Classifier
6. CatBoost Classifier

* The Boxplot above show Logistic Regression and Linear Discriminant Analysis with outlier and very low mean score (neg_mean_absolute_error)
* All ensemble ALgorithm show a promising and high mean score (neg_mean_absolute_error) with no outlier
* Hence Ensemble algorithm should be use for my predictive modelling
* preprocessing like Standardized will be require

BEST MODEL :
Model : -------- Extreme GradientBoosting Classifier -------- 
Best: 0.932143 using {'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 75}

* TEST SET EVALUATION :
* accuracy score: 0.9857142857142858
* roc auc score: 0.98
* f1 score: 0.9795918367346939
* precision score 1.0
* recall score 0.96

* TRAIN SET EVALUATION :
* accuracy score: 0.9964285714285714
* roc auc score: 0.995
* f1 score: 0.9949748743718593
* precision score 1.0
* recall score 0.99

