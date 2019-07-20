<h2 style="text-align:center">Statistical Methods in Data Science

Homework 7  

</h2>

> Chapter 6:Exercises 2, 4, 6, 8, 10

#### Chapter 6
> 2. For parts (a) through (c), indicate which of i. through iv. is correct. Justify your answer.  
(a) The lasso, relative to least squares, is:  
i. More flexible and hence will give improved prediction accuracy when its increase in bias is less than its decrease in variance.  
ii. More flexible and hence will give improved prediction accuracy when its increase in variance is less than its decrease in bias.  
iii. Less flexible and hence will give improved prediction accuracy when its increase in bias is less than its decrease in variance.  
iv. Less flexible and hence will give improved prediction accuracy when its increase in variance is less than its decrease in bias.  
(b) Repeat (a) for ridge regression relative to least squares.  
(c) Repeat (a) for non-linear methods relative to least squares.  

(a) iii  
(b) iii  
(c) ii  

> 4. Suppose we estimate the regression coefficients in a linear regression
model by minimizing
```math
\sum_{i=1}^n (y_i - \beta _0 - \sum _{j=1}^p \beta _j x_{ij})^2 + \lambda \sum _{j=1}^p \beta _j ^2
```
>for a particular value of λ. For parts (a) through (e), indicate which of i. through v. is correct. Justify your answer.  
(a) As we increase λ from 0, the training RSS will:  
i. Increase initially, and then eventually start decreasing in an
inverted U shape.  
ii. Decrease initially, and then eventually start increasing in a
U shape.  
iii. Steadily increase.  
iv. Steadily decrease.  
v. Remain constant.  
(b) Repeat (a) for test RSS.  
(c) Repeat (a) for variance.  
(d) Repeat (a) for (squared) bias.  
(e) Repeat (a) for the irreducible error.  

from FIGURE 6.8  
(a) iii  
(b) ii  
(c) iv  
(d) iii  
(e) v 

* Question 6, 8 & 10 are in the next page.
> 6. We will now explore (6.12) and (6.13) further.  
(a) Consider (6.12) with p = 1. For some choice of y1 and λ > 0,
plot (6.12) as a function of β1. Your plot should confirm that
(6.12) is solved by (6.14).  
(b) Consider (6.13) with p = 1. For some choice of y1 and λ > 0,
plot (6.13) as a function of β1. Your plot should confirm that
(6.13) is solved by (6.15).


------------------
> 8. In this exercise, we will generate simulated data, and will then use
this data to perform best subset selection.
(a) Use the rnorm() function to generate a predictor X of length
n = 100, as well as a noise vector  of length n = 100.
(b) Generate a response vector Y of length n = 100 according to
the model
```math
Y = \beta _0 + \beta _1X + \beta_2X^2 + \beta _3 X^3 + \epsilon 
```
> where β0, β1, β2, and β3 are constants of your choice  
(c) Use the regsubsets() function to perform best subset selection
in order to choose the best model containing the predictors
X, X2,...,X10. What is the best model obtained according to
Cp, BIC, and adjusted R2? Show some plots to provide evidence
for your answer, and report the coefficients of the best model obtained.
Note you will need to use the data.frame() function to
create a single data set containing both X and Y .  
(d) Repeat (c), using forward stepwise selection and also using backwards
stepwise selection. How does your answer compare to the
results in (c)?  
(e) Now fit a lasso model to the simulated data, again using X, X2,
...,X10 as predictors. Use cross-validation to select the optimal
value of λ. Create plots of the cross-validation error as a function
of λ. Report the resulting coefficient estimates, and discuss the
results obtained.  
(f) Now generate a response vector Y according to the model
```math
Y = \beta _0 + \beta _7X^7 + \epsilon 
```
> and perform best subset selection and the lasso. Discuss the
results obtained.

-----------------------

> 10. We have seen that as the number of features used in a model increases,
the training error will necessarily decrease, but the test error may not.
We will now explore this in a simulated data set.
(a) Generate a data set with p = 20 features, n = 1,000 observations,
and an associated quantitative response vector generated
according to the model
```math
Y =  X\beta  + \epsilon 
```
> where β has some elements that are exactly equal to zero.   
(b) Split your data set into a training set containing 100 observations
and a test set containing 900 observations.  
(c) Perform best subset selection on the training set, and plot the
training set MSE associated with the best model of each size.  
(d) Plot the test set MSE associated with the best model of each
size.  
(e) For which model size does the test set MSE take on its minimum
value? Comment on your results. If it takes on its minimum value
for a model containing only an intercept or a model containing
all of the features, then play around with the way that you are
generating the data in (a) until you come up with a scenario in
which the test set MSE is minimized for an intermediate model
size.  
(f) How does the model at which the test set MSE is minimized
compare to the true model used to generate the data? Comment
on the coefficient values.  
(g) Create a plot displaying `$\sqrt{\sum _{j=1}  ^p (\beta _j+\widehat{\beta _j ^r})^2}$` for a range of values
of r, where `$\widehat{\beta _j ^r}$` is the jth coefficient estimate for the best model
containing r coefficients. Comment on what you observe. How
does this compare to the test MSE plot from (d)?

