<h2 style="text-align:center">Statistical Methods in Data Science

Homework 8  

</h2>

> Chapter 7: Exercises 2, 4, 6, 8, 10, 12

#### Chapter 7
> 2.Suppose that a curve `$\widehat{g}$` is computed to smoothly fit a set of n points using the following formula:
```math
\widehat{g} = \mathop{\arg\min}_{g} (\sum _{i=1} ^n (y_i - g(x_i))^2 + \lambda \int[g^{(m)}(x)]^2 dx)
```
> where g(m) represents the mth derivative of g (and g(0) = g). Provide
example sketches of `$\widehat{g}$` in each of the following scenarios.  
(a) λ=∞,m=0.  
(b) λ=∞,m=1.  
(c) λ=∞,m=2.  
(d) λ=∞,m=3.  
(e) λ=0,m=3. 

a. g=C where C is a constant because area under g(0) will be minimized.  
b. g=ax^2 where a is a constant(not 0) because area under g(1) will be minimized.  
c. g=ax^3 where a is a constant(not 0) because area under g(2) will be minimized.  
d. g=ax^4 where a is a constant(not 0) because area under g(3) will be minimized.  
e. g is a function which minimizes RSS without penalty term.

 
> 4.Suppose we fit a curve with basis functions `$b_1(X) = I(0 ≤ X ≤ 2) − (X − 1)I (1 ≤ X ≤ 2)$`, `$b_2 (X ) = (X − 3)I (3 ≤ X ≤ 4) + I (4 < X ≤ 5)$`. We fit the linear regression model
```math
Y = \beta _0 + \beta _1 b_1 (X) + \beta _2 b_2 (X) + \epsilon
```
> and obtain coefficient estimates `$\widehat{\beta}_0 = 1,\widehat{\beta}_1 = 1,\widehat{\beta}_2 = 3$`. Sketch the estimated curve between X = −2 and X = 2. Note the intercepts, slopes, and other relevant information.

f(-2) = 1，f(-1) = 1，f(0) = 2，f(1) = 2，f(2) = 1 
