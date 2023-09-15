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


