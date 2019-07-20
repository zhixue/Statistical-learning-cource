<h2 style="text-align:center">Statistical Methods in Data Science

Homework 5  

</h2> 

* > Chapter 4: Exercises 2, 4, 6, 8, 10, 12

> 2 It was stated in the text that classifying an observation to the class 
for which (4.12) is largest is equivalent to classifying an observation
to the class for which (4.13) is largest. Prove that this is the case. In
other words, under the assumption that the observations in the kth
class are drawn from a N(μk, σ2) distribution, the Bayes’ classifier
assigns an observation to the class for which the discriminant function
is maximized.

##### Proof:  
`$p_k(x)$`and `$\delta _k(x)$`are as following(`$k=1,...,K$`)
```math
p_k (x) = \frac{\pi _k \frac{1}{\sqrt{2\pi} \sigma }exp(-\frac{1}{2 \sigma ^2}(x-\mu _k)^2)}{\sum _{i=1} ^K \pi _i \frac{1}{\sqrt{2\pi} \sigma }exp(-\frac{1}{2 \sigma ^2}(x-\mu _i)^2)}

\delta _k(x) = x \frac{\mu _k}{\sigma ^2}-\frac{\mu _k ^2}{2 \sigma ^2}+log(\pi _k)
```
Suppose `$\delta _{n}(x)$` is max(`$n\epsilon\{1,...,K\}$`),we can get 
```math
\delta _n(x) = x \frac{\mu _n}{\sigma ^2}-\frac{\mu _n ^2}{2 \sigma ^2}+log(\pi _n) \geq \delta _k(x) = x \frac{\mu _k}{\sigma ^2}-\frac{\mu _k ^2}{2 \sigma ^2}+log(\pi _k)
```
with exp change
```math
exp(x \frac{\mu _n}{\sigma ^2}-\frac{\mu _n ^2}{2 \sigma ^2})\pi _n \geq exp(x \frac{\mu _k}{\sigma ^2}-\frac{\mu _k ^2}{2 \sigma ^2})\pi _k
```
multipy a positive constant`$exp(\frac{-x^2}{2 \delta ^2})$` in left and right
```math
exp(\frac{-x^2}{2 \delta ^2}+x \frac{\mu _n}{\sigma ^2}-\frac{\mu _n ^2}{2 \sigma ^2})\pi _n \geq exp(\frac{-x^2}{2 \delta ^2}+x \frac{\mu _k}{\sigma ^2}-\frac{\mu _k ^2}{2 \sigma ^2})\pi _k
```

```math
exp(-\frac{1}{2 \delta ^2}(x- \mu _n)^2)\pi _n \geq exp(-\frac{1}{2 \delta ^2}(x- \mu _k)^2)\pi _k

C p_n(x) \geq C p_k(x)
```
where `$C$` is a positive constant, and we can get   `$p_n(x)$`  is the max. Similar apporach proof from `$p_n(x)$` to `$\delta _n(x)$`.


> 4  When the number of features p is large, there tends to be a deterioration
in the performance of KNN and other local approaches that
perform prediction using only observations that are near the test observation
for which a prediction must be made. This phenomenon is
known as the curse of dimensionality, and it ties into the fact that non-parametric
approaches often perform poorly when p is large. We mensionality
will now investigate this curse.  
>>(a) Suppose that we have a set of observations, each with measurements
on p = 1 feature, X. We assume that X is uniformly
(evenly) distributed on [0, 1]. Associated with each observation
is a response value. Suppose that we wish to predict a test observation’s
response using only observations that are within 10 % of
the range of X closest to that test observation. For instance, in
order to predict the response for a test observation with X = 0.6,
we will use observations in the range [0.55, 0.65]. On average,
what fraction of the available observations will we use to make
the prediction?

(a) 10%(Due to uniform distribution)

>> (b) Now suppose that we have a set of observations, each with
measurements on p = 2 features, X1 and X2. We assume that
(X1, X2) are uniformly distributed on [0, 1] × [0, 1]. We wish to
predict a test observation’s response using only observations that
are within 10 % of the range of X1 and within 10 % of the range
of X2 closest to that test observation. For instance, in order to
predict the response for a test observation with X1 = 0.6 and
X2 = 0.35, we will use observations in the range [0.55, 0.65] for
X1 and in the range [0.3, 0.4] for X2. On average, what fraction
of the available observations will we use to make the prediction?

(b) 10% * 10% = 1%

>> (c) Now suppose that we have a set of observations on p = 100 features.
Again the observations are uniformly distributed on each
feature, and again each feature ranges in value from 0 to 1. We
wish to predict a test observation’s response using observations
within the 10 % of each feature’s range that is closest to that test
observation. What fraction of the available observations will we
use to make the prediction?

(c) `$0.1^{100}$`

>> (d) Using your answers to parts (a)–(c), argue that a drawback of
KNN when p is large is that there are very few training observations
“near” any given test observation.

(d) With p features increasing KNN needs lots of data(`$N^P$`) to make sure that near observations exist.

>> (e) Now suppose that we wish to make a prediction for a test observation
by creating a p-dimensional hypercube centered around
the test observation that contains, on average, 10 % of the training
observations. For p = 1, 2, and 100, what is the length of
each side of the hypercube? Comment on your answer.

(e) 
```math
p=1, length = 0.1

p=2, length = 0.1^{1/2}

...

p=N, length = 0.1^{1/N}

p=100,length = 0.1^{1/100}
```

> 6 Suppose we collect data for a group of students in a statistics class
with variables X1 = hours studied, X2 = undergrad GPA, and Y =
receive an A. We fit a logistic regression and produce estimated
coefficient, βˆ0 = −6, βˆ1 = 0.05, βˆ2 = 1.
>> (a) Estimate the probability that a student who studies for 40 h and
has an undergrad GPA of 3.5 gets an A in the class.
##### Answer
```math
p(X) = \frac{e^{\beta_0 + \beta_1X_1 + \beta_2X_2}}{1+e^{\beta_0 + \beta_1 X_1+\beta_2 X_2}}
```
where `$\widehat{\beta}_0$`=-6,`$\widehat{\beta}_1$`=0.05,`$\widehat{\beta}_2$`=1

when `$X_1=40$`,`$X_2=3.5$`,`$X=(X_1,X_2)$`
```math
p(X)=0.37754
```

>> (b) How many hours would the student in part (a) need to study to
have a 50 % chance of getting an A in the class?

`$X_2=3.5$`
```math
p(X_1)= \frac{e^{-6 + 0.05 X_1 + 1 * 3.5}}{1+e^{-6 + 0.05 X_1 + 1 * 3.5}} \geq 0.5
```
`$X_1{min}=50$` . In other words,`$X_1$` must be not smaller than 50.

> 8 Suppose that we take a data set, divide it into equally-sized training
and test sets, and then try out two different classification procedures.
First we use logistic regression and get an error rate of 20 % on the
training data and 30 % on the test data. Next we use 1-nearest neighbors
(i.e. K = 1) and get an average error rate (averaged over both
test and training data sets) of 18 %. Based on these results, which
method should we prefer to use for classification of new observations?
Why?

##### Answer
* Logistic Regression: training error - 20% , test error - 30%  
* KNN(K=1): training error - 0 , test error - 18*2 %  

Conclusion: using logistic regression because of better performance in test data.

##### Qustion 10 and 12 are in the next page
> 10 This question should be answered using the Weekly data set, which
is part of the ISLR package. This data is similar in nature to the
Smarket data from this chapter’s lab, except that it contains 1, 089
weekly returns for 21 years, from the beginning of 1990 to the end of 2010.  
(a)-(i)

> 12 This problem involves writing functions.  
(a)-(f)