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

|Mean_Square_Error|
|:-:|
|<h4>MSE = <sup>n</sup>∑<sub>i=1</sub> (Y - &#374;)<sup>2</sup> / (number of datapoint)</h4>|






