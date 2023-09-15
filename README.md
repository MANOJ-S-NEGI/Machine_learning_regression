# Machine_learning_regression


---
---
## Linear Regression:
 
 - Linear regression is a statistical method that models the relationship between a dependent variable (often denoted as y) and one or more independent variables (often denoted as x).
 -  It assumes that the relationship between the variables can be approximated by a linear function.

```
Expressed as:  y=mx+b

y is the dependent variable (the one we're trying to predict)
x is the independent variable (the one we're using to make predictions)
m is the slope of the regression line, representing the change in y for a unit change in x
b is the intercept of the regression line, representing the predicted value of y when x is 0
```
- linear regression aims to find the best-fitting line (or hyperplane in higher dimensions) through the data points. This is done by minimizing the sum of squared differences (or residuals) between the actual and predicted values of y.

**Equation of the Straight line:**
  
- y = mx+b can be written as:  
y = β<sub>0</sub>+ β<sub>1</sub>x


|Where:|
|:-|
|y is the dependent variable (the one we're trying to predict)|
|x is the independent variable (the one we're using to make predictions)|
|β<sub>0</sub>is the intercept term.|
|β<sub>1</sub> is the coefficient associated with the independent variable x|



let's assume that intercept = 0

the graph will be like:

![intercept_0_image](https://github.com/MANOJ-S-NEGI/Machine_learning_regression/assets/99602627/b858d628-4fb5-43d2-9c57-f4c7ca2e8d92)


<br><br>

---
## **Cost function:**

1. The expression, <h2>J(θ<sub>0</sub>θ<sub>1</sub>) = <sup>n</sup>∑<sub>i=1</sub> (h<sub>0</sub>(x<sub>i</sub>) - y<sub>i</sub>)<sup>2</sup></h2> represents the cost function for a linear regression model, 

   |Where:|
   |:-|
   |J(θ<sub>0</sub>θ<sub>1</sub>) is the cost function|
   |θ<sub>0</sub>θ<sub>1</sub> are the parameters (intercept and slope) of the linear regression model|
   |n is the number of data points|
   |h<sub>0</sub>(x<sub>i</sub>) is the predicted value for the i-th data point|
    |y<sub>i</sub> is the actual target value for the i-th data point|

2.  This cost function is also known as the Mean Squared Error (MSE) and is commonly used for evaluating the performance of a linear regression model.

3. The goal of training a linear regression model is to find the values of 
θ<sub>0</sub> and θ<sub>1</sub>  that minimize this cost function. This is typically done using optimization techniques like gradient descent.

4. In practical terms, the cost function measures how well the model's predictions (h<sub>0</sub>(x<sub>i</sub>)) align with the actual target values (y<sub>i</sub>). 
   - It quantifies the discrepancy between predicted and actual values, with larger discrepancies resulting in higher cost values.

5. The process of training the model involves adjusting the parameters (θ<sub>0</sub> and θ<sub>1</sub>) iteratively to minimize this cost function. 
   - When the cost function reaches a minimum, the model provides the best fit to the data.

|<h3>Cost_Function</h3>||
|:-:|:-:|
|Mean_Square_Error|<h4>MSE = <sup>n</sup>∑<sub>i=1</sub> (Y<sub>i</sub> - &#374;<sub>i</sub>)<sup>2</sup> / n </h4>|
|Mean_Absolute_Error|<h4>MAE = <sup>n</sup>∑<sub>i=1</sub> IY<sub>i</sub> - &#374;<sub>i</sub>I / n</h4>|
|Root_Mean_Squared_Error|<h4>RMSE = √(MAE)</h4>|
where, n = (number of datapoints)

<br>
<br>

#### 1. MSE [Mean_Square_Error]

**Advantages**

1. MSE equation is differentiable:
  - Because the MSE is a quadratic function (ax<sup>2</sup>+by+c) of the differences between actual and predicted values, it is differentiable.
  - This means that its derivative can be computed with respect to the parameters (e.g., the model's weights or coefficients).
  - This property enables the use of gradient-based optimization methods to find the set of parameters that minimize the MSE, leading to an accurate model.

2. MSE always has a Global minima:
   - This is because the MSE is a continuous and convex function with respect to the model parameters.
   - global minimum is the lowest value of a function over its entire domain. It means that no other point in the function's domain has a lower value.

     
![global minima](https://github.com/MANOJ-S-NEGI/Machine_learning_regression/assets/99602627/f035d464-c3a1-4f5c-acf9-fff76fbc4ef0)
global minima is a convex function

![local minima](https://github.com/MANOJ-S-NEGI/Machine_learning_regression/assets/99602627/025ce040-bb53-4ca2-8395-ba805420585a)
local minima is a nonconvex function

why local minima is a disadvantage while global minima not?
 - As plotted above, there are two depths in the local minima plot, the one with extreme depth is the global minima and the smaller depth is the local minima as the slope
   keep getting updated to reach the global minima (i.e. to reduce the error margin and increase the accuracy) meanwhile, some functions get stuck and
   unable to get an update due to the negligible change in weights so unable to reach the global minima or we can say unable to reduce the error margin rate.

- convex function does not have this problem
   
**Disadvantages**
  - MSE is not robust to outliers
  - MSE function penalizes the error.


#### 2. MAE [Mean_Absolute_Error]
|Advantages:| Disadvantages|
|:-|:-|
| Robust to Outliers|Convergence usually takes more time (more computational time to reach minima)|
|Always in the same unit(+ve)|May Mask the Scale of Errors: If there are a few very large errors in the dataset, the average might not accurately represent the typical error. In such cases, a metric that penalizes larger errors more (like MSE) might provide a better assessment.|


#### 3. RMSE [Root_Mean_Squared_Error]
|Advantages:| Disadvantages|
|:-|:-|
|- Interpretability: RMSE is in the same unit as the dependent variable, which makes it easy to interpret. For example, if you're predicting house prices in dollars, the RMSE will also be in dollars |- sensitive to outliers|
|Smoothness of Optimization Landscape: It is a smooth function that is differentiable almost everywhere, which makes it well-suited for mathematical optimization procedures.|Non-Negative Values Only: RMSE doesn't work well if your data can have negative values, as it squares the errors.|


---

## Performance metric for LinerRegression:
|<h3>Performance_matric</h3>|
|:-:|
|R<sup>2</sup>|
|Adjusted R<sup>2</sup>|


 ## 1. **R<sup>2</sup> [R_Square]:**
   - is calculated as the ratio of the explained variance to the total variance. It is often computed as 
```
 R^2 = 1-(Sum of Squared Errors (SSE)/Total Sum of Squares (SST))

​where
   SSE is the sum of the squared differences between the actual and predicted values,
   SST is the total sum of squared differences between the actual values and the mean of the dependent variable.
```


|**Interpretation of (R<sup>2</sup>)**|
|:-|
|An (R<sup>2</sup>) value ranges from 0 to 1,|
|* 0 means that the model does not explain any of the variability in the target variable.|
|* 1 means that the model perfectly predicts the target variable.|
|* if  R<sup>2</sup> is negative than it is worst model


## 2. **Adjusted (R<sup>2</sup>)**
- Adjusted R-squared addresses a limitation of regular R-squared. R-squared tends to increase as more predictors are added to the model, even if those predictors do not significantly improve the model's explanatory power. Adjusted R-squared penalizes excessive use of predictors that do not add value.
- The formula for adjusted R-squared is:  1 − ((1-R<sup>2</sup>)(n-1) /(n−p−1))
    - where n is the number of observations and p is the number of predictors in the model.

- Interpretation:
    - R<sup>2</sup>ranges from −∞ to 1.
    - A higher R<sup>2</sup> indicates a better fit.
    - A negative R<sup>2</sup> implies that the model is worse than a model that simply predicts the mean of the dependent variable for all observations.
    - Adjusted R-squared will be less than or equal to R-squared.
    - If adding a new predictor improves the model, both R-squared and adjusted R-squared will increase. If the new predictor does not improve the model, R-squared may increase but adjusted R-squared will stay the same or decrease.

​
 




---

Example:

since, h<sub>0</sub>(x<sub>i</sub>) = θ<sub>0</sub> + θ<sub>1</sub>x  (if intercept is 0)

then, h<sub>0</sub>(x<sub>i</sub>) =  θ<sub>1</sub>x

if θ<sub>1</sub> = 0.5 and x = [1,2,3]


|x|h<sub>0</sub>(x<sub>i</sub>) = θ<sub>1</sub>x||
|:-|:-|:-|
|For x<sub>1</sub> =1:| 0.5 * 1| = 0.5|
|For x<sub>2</sub> = 2:|0.5 * 2| = 1.0|
|For x<sub>3</sub> = 3:|0.5 * 3| = 1.5|


![example theta](https://github.com/MANOJ-S-NEGI/Machine_learning_regression/assets/99602627/28035a49-2680-4602-aa85-4b7c7b37c941)

 j(θ<sub>1</sub>) = ((0.3-1)<sup>2</sup> + (1-2)<sup>2</sup>  + (1.5-3)<sup>2</sup> /3)

  j(θ<sub>1</sub>) = (0.49+1+2.25)/3

 j(θ<sub>1</sub>) ≈1.25

---


