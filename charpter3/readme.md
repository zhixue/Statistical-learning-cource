<h2 style="text-align:center">Homework 4</h2>
##### zhixue
##### Charpter 3 Exercise 
###### 3.2 
**KNN classifier** first identifies the neighbors
K points in the training data that are closest to `$x_0$`, represented by `$N_0$`.
**It then estimates the conditional probability for class j as the fraction of
points in set `$N_0$`** whose response values equal j:
```math
Pr(Y=j|X=x_o) = \frac{1}{K} \sum_{i \epsilon  N_{0}} I(y_i = j)
```
Finally, KNN applies Bayes rule and classifies the test observation x0 to
the class with the largest probability, and class of `$x_0$` can be got.

But **K-nearest neighbors regression** has some difference: first identifies the K training observations that are closest to
`$x_0$`, represented by `$N_0$`. **It then estimates `$f(x_0)$` using the average of all the training responses in `$N_0$`** as
```math
\widehat f(x_0) = \frac{1}{K} \sum_{x_i \epsilon N_0} y_i
```
And quantitative value `$\widehat f(x_0)$` can be got.
###### 3.4
* (a) lower training RSS in cubic regression. Because more parameters `$\beta _2 ,~ \beta _3$` can be used to minimize RSS which may fit better in trainning set.

* (b) higher training RSS in cubic regression. Because the relationshop beteen X and Y is linear, cubic regression is overfitting.

* (c) lower training RSS in cubic regression. Reason is similar with (a).

* (d) There is not enough information. Because we don not know how far it is from linear.


###### 3.6 
To minimize RSS, we have 
```math
\widehat \beta _1 = \frac{\sum _{i=1} ^n (x_i- \overline x)(y_i - \overline y)}{\sum _{i=1} ^n {(x_i- \overline x)}^2} 

\widehat \beta _0 = \overline y - \widehat \beta _1 \overline x
```
Where `$(\overline x, \overline y)$` is a solution of 
```math
Y=\widehat \beta _0 + \widehat \beta _1 X
```
###### 3.8
See nextpage