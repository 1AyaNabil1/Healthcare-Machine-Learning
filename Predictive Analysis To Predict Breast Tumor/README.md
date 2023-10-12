# Using Predictive Analysis To Predict Diagnosis of a Breast Tumor
### Data introduction:
The Breast Cancer (Wisconsin) Diagnosis dataset contains the diagnosis and a set of 30 features describing the characteristics of the cell nuclei present in the digitized image of a fine needle aspirate (FNA) of a breast mass.

<h3>The dataset is available through the University of California, Irvine Machine learning repository.</h3>
  Here is the URL:

https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic


Ten real-valued features are computed for each cell nucleus:
- radius (mean of distances from center to points on the perimeter);
- texture (standard deviation of gray-scale values);
- perimeter;
- area;
- smoothness (local variation in radius lengths);
- compactness (perimeter^2 / area - 1.0);
- concavity (severity of concave portions of the contour);
- concave points (number of concave portions of the contour);
- symmetry;
- fractal dimension (“coastline approximation” - 1).


The mean, standard error (SE) and “worst” or largest (mean of the three largest values) of these features were computed for each image, resulting in 30 features.


### OUR Work
* First: Clean the Data 
* Second: Apply the EDA (Exploratory Data Analysis) to explore data
* Third: Apply some visualizations to the unimodal data. We used (histogram, density plot and box plot). 
* Fourth: Apply some visualizations to the multimodal data. we used (heat map) to know the correlation between features. Then we used the scatter plot to better know the correlation between features (plot the : positive correlation, negative correlation and uncorrelated feature)
* Fifth: Start Preprocessing Data by:
    1- Statistical analysis --> To remove the outliers using IQR 
    2- Split the available data into a training set and a testing set --> 70% training, 30% test
    3- Feature Standardization --> mean of 0 and a standard deviation of 1
    4- Feature decomposition using Principal Component Analysis(PCA) 
    5- Deciding How Many Principal Components to Retain --> we found that k will equal 3
    6- Calculate the Cumulative Variance 
* Sixth: Machine Learning Classification
    1- Building Feature Set
    2- Support Vector Machine
    3- Kernel Selection Using Learning Curve
    4- Selection of Regularization parameter(C)
* Seventh: Print the final accuracy of our model which is equal 97.94% S