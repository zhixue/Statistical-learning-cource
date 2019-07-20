<h2 style="text-align:center">Statistical Methods in Data Science

Homework 6  

018080910011 薛泓嶂</h2>
> Chapter 5:Exercises 2, 4, 6, 8

#### Chapter 5
> **2** We will now derive the probability that a given observation is part of a bootstrap sample. Suppose that we obtain a bootstrap sample from a set of n observations.
>> (a) What is the probability that the first bootstrap observation is not the jth observation from the original sample? Justify your answer. 

```math
1-\frac{1}{n}
```

>> (b) What is the probability that the second bootstrap observation is not the jth observation from the original sample?  

```math
1-\frac{1}{n}
```

>> (c) Argue that the probability that the jth observation is not in the bootstrap sample is (1 − 1/n)^n.  

Every sampling with replacement is i.i.d with the same probaility 1/n.

>> (d) When n = 5, what is the probability that the jth observation is in the bootstrap sample?  
```math
P=1-(1-\frac{1}{5})^{5} = 1-0.32768 = 0.67232
```

>>(e) When n = 100, what is the probability that the jth observation is in the bootstrap sample?  
```math
P=1-(1-\frac{1}{100})^{100} = 0.63397
```
>> (f) When n = 10, 000, what is the probability that the jth observation
is in the bootstrap sample?  

```math
P=1-(1-\frac{1}{10000})^{10000} = 0.63214
```

>> (g) Create a plot that displays, for each integer value of n from 1 to 100, 000, the probability that the jth observation is in the
bootstrap sample. Comment on what you observe.  

```{R 5.2.g}
f = function(n){
    return(1-(1-1/n)^n)
}

# quickly fall near 1 - 1/e
x = 1:100000
plot(x,f(x))
```

>> (h) We will now investigate numerically the probability that a bootstrap
sample of size n = 100 contains the jth observation. Here
j = 4. We repeatedly create bootstrap samples, and each time
we record whether or not the fourth observation is contained in
the bootstrap sample.

```{R 5.2.h}
store=rep(NA, 10000)
for(i in 1:10000) {
store[i]=sum(sample (1:100, rep=TRUE)==4) >0
}

# 0.6375 (the result is near the value above)
mean(store)
```

> **4** Suppose that we use some statistical learning method to make a prediction
for the response Y for a particular value of the predictor X.
Carefully describe how we might estimate the standard deviation of
our prediction.

* bootstrap method  
By repeatedly sampling observations from dataset N times with replacement, we can get a model and compute standard deviation from subdataset every time. Use these to get the esimate.

##### Question 6 and 8 are in the next page.
> **6** We continue to consider the use of a logistic regression model to
predict the probability of default using income and balance on the
Default data set. In particular, we will now compute estimates for
the standard errors of the income and balance logistic regression coefficients
in two different ways: (1) using the bootstrap, and (2) using
the standard formula for computing the standard errors in the glm()
function. Do not forget to set a random seed before beginning your
analysis.

> **8** We will now perform cross-validation on a simulated data set.
