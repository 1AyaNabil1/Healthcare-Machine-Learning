# Diabetes Diagnose using Machine Learning
### Data introduction:

<p  style="text-align:justify">
Acccording to NIH, **Diabetes** is a disease that occurs when your blood glucose, also called blood sugar, is too high. Blood glucose is your main source of energy and comes from the food you eat. Insulin, a hormone made by the pancreas, helps glucose from food get into your cells to be used for energy. Sometimes your body doesn’t make enough—or any—insulin or doesn’t use insulin well. Glucose then stays in your blood and doesn’t reach your cells.
<p  style="text-align:justify">
Over time, having too much glucose in your blood can cause health problems. Although diabetes has no cure, you can take steps to manage your diabetes and stay healthy.
<p  style="text-align:justify">
Sometimes people call diabetes “a touch of sugar” or “borderline diabetes.” These terms suggest that someone doesn’t really have diabetes or has a less serious case, but every case of diabetes is serious.<p  style="text-align:justify">

**What are the different types of diabetes?**
The most common types of diabetes are type 1, type 2, and gestational diabetes.<p  style="text-align:justify">

**Type 1 diabetes**
If you have type 1 diabetes, your body does not make insulin. Your immune system attacks and destroys the cells in your pancreas that make insulin. Type 1 diabetes is usually diagnosed in children and young adults, although it can appear at any age. People with type 1 diabetes need to take insulin every day to stay alive.<p  style="text-align:justify">

**Type 2 diabetes**
If you have type 2 diabetes, your body does not make or use insulin well. You can develop type 2 diabetes at any age, even during childhood. However, this type of diabetes occurs most often in middle-aged and older people. Type 2 is the most common type of diabetes.<p  style="text-align:justify">

**Gestational diabetes**
Gestational diabetes develops in some women when they are pregnant. Most of the time, this type of diabetes goes away after the baby is born. However, if you’ve had gestational diabetes, you have a greater chance of developing type 2 diabetes later in life. Sometimes diabetes diagnosed during pregnancy is actually type 2 diabetes.<p  style="text-align:justify">

**Other types of diabetes**
Less common types include monogenic diabetes, which is an inherited form of diabetes, and cystic fibrosis-related diabetes .
<p  style="text-align:justify">


<h3>The dataset is available through the University of California, Irvine Machine learning repository.</h3>
  Here is the URL:

https://archive.ics.uci.edu/ml/datasets/Diabetes

----------------------------------------------------------------------

# OUR Work: 
- First: Clean the Data.
  - Removed rows that contains the value zero in those features (Glucose, BP, Skin thickness,Insulin & BMI) as they can not be = 0
  - Split the data according to the outcome of 0s and 1s
  - Visualize each feature to: find the distribution of each one, help in analysis, and detrmine the outliers 

- Second: apply statistical analysis (Normality test)
  - Retrieving p value from normality test function
  - Apply pair plot, Pearson Correlation and heatmap for better understanding the relation between features.

- Third: Apply the EDA (Exploratory Data Analysis) to explore data
  - Here we decided to explore the data more 
    - We calculated **The Nutritional status**
    - Then calculated **The Interpretation of Glucose level**
    - Calculate the **Homeostatic Model Assessment for Insulin Resistance**
    - 

- Fourth: Extarct and decide the dependent and independent variables. 

- Fifth: Build our model:

  5.1- **K-Nearest Neighbors (KNN):**
    - The k-NN algorithm is arguably the simplest machine learning algorithm. Building the model consists only of storing the training dataset. To make a prediction for a new data point, the algorithm finds the closest data points in the training dataset—its “nearest neighbors.”

      - Accuracy of K-NN classifier on training set: **0.79**
      - Accuracy of K-NN classifier on test set: **0.78**

  5.2- **Logistic Regression:**
    - Logistic regression is one of the most common classification algorithms.
      - Training set accuracy: **0.778**
      - Test set accuracy: **0.771**
  
  5.3- **Decision Tree Model:**
    - First we found that the tree is overfitting the data so we need to apply pre-pruning to the tree
    - We set the max_depth to 3 and then got the accuracy equals:
    - Accuracy on training set: **0.773**
    - Accuracy on test set: **0.740**
    - Then we checked for the **"feature importance rates"** which tells us how important each feature is for the decision a tree makes.
      - It is a number between 0 and 1 for each feature, where 0 means “not used at all” and 1 means “perfectly predicts the target.” The feature importances always sum to 1.
      - We got that the feature **"Glucose"** is by far the most important feature.and then **"BMI"** is at second place
  
  5.4- **Random Forest Model:**
    - We will apply a random forest consisting of **100 trees** on the diabetes dataset
    - When we applyed the **"feature importance rate  got that the feature"** to the randome forest we got that the **"Glucose"** is by far the most important feature and then **"BMI"** is at second place, like we got from the Decision tree.
    - Accuracy on training set: **0.800**
    - Accuracy on test set: **0.755**
    - The result being that: **the random forest captures a much broader picture of the data than a single tree.**

5.5- **Gradient Boosting Model:**
  - We found that the model **overfit** the data as same as the decision tree does.
    - *We will obtain 2 methods to reduce over fitting:*
      1. By limiting the maximum depth:
        - Accuracy on training set: **0.804**
        - Accuracy on test set: **0.781**
      2. By lowering the learning rate:
        - Accuracy on training set: 0.802
        - Accuracy on test set: 0.776
      > Both methods of decreasing the model complexity reduced the training set accuracy, as expected. In this case, none of these methods increased the generalization performance of the test set.

5.6- **Support Vector Machine Model:**
  - Accuracy on training set: **0.944**
  - Accuracy on test set: **0.724**

5.7- **Neural Networks Model:**
- We rescaled the data then we got the accuracy:
  - Accuracy on training set: **0.823**
  - Accuracy on test set: **0.802**

### Finally we got that the Multiple Neural Networks(MLP) optained the highest accuracy
