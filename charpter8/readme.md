<h2 style="text-align:center">Statistical Methods in Data Science

Week 11/Homework 9/Chapter 8 

</h2>

> Chapter 8: Exercises 2, 4, 6, 8, 10, 12

> 2. It is mentioned in Section 8.2.3 that boosting using depth-one trees
(or stumps) leads to an additive model: that is, a model of the form
```math
f(X) = \sum _{j=1} ^p f_j (X_j)
```
> Explain why this is the case. You can begin with (8.12) in Algorithm 8.2.

Based on Algorithm 8.2, the first stump will consist of a split on a single variable.
```math
\widehat{f}(x) = 0, r_i = y_i

\widehat{f^1}(x) = \beta_1 I(X_1<t1) + \beta_0

\widehat{f}(x) = \lambda \widehat{f^1}(x)

r_i = y_i - \lambda \widehat{f^1}(x)
```
To maximize the fit to the residuals,
```math
\widehat{f^j}(x) = \beta_{1j} I(X_j<tj) + \beta_{0j}

\widehat{f}(x) = \lambda \widehat{f^1}(x) + ... + \widehat{f^p}(x)

```



--------------------

> 4. This question relates to the plots in Figure 8.12.  
(a) Sketch the tree corresponding to the partition of the predictor
space illustrated in the left-hand panel of Figure 8.12. The numbers
inside the boxes indicate the mean of Y within each region.  
(b) Create a diagram similar to the left-hand panel of Figure 8.12,
using the tree illustrated in the right-hand panel of the same
figure. You should divide up the predictor space into the correct
regions, and indicate the mean for each region.  
![Esvc9J.png](https://s2.ax1x.com/2019/05/07/Esvc9J.png)

![EszMo8.md.png](https://s2.ax1x.com/2019/05/07/EszMo8.md.png)


---------------------------------------
> 6. Provide a detailed explanation of the algorithm that is used to fit a regression tree.
#### Building a Regression Tree
1. Use **recursive binary splitting(RBS)** to grow a large tree on the training
data, stopping only when each terminal node has fewer than some
minimum number of observations.
2. Apply cost complexity **pruning** to the large tree in order to obtain a
sequence of best subtrees, as a function of α.
3. Use **K-fold cross-validation to choose α**. That is, divide the training observations into K folds. For each k = 1,...,K:  
(a) Repeat Steps 1 and 2 on all but the kth fold of the training data.  
(b) Evaluate the mean squared prediction error on the data in the
left-out kth fold, as a function of α.  
Average the results for each value of α, and pick α to minimize the
average error.
4. Return the **subtree** from Step 2 that corresponds to the chosen value
of α.

The goal is to find Ri,...,RJ that minimize the RSS
```math
RSS = \sum _{j=1} ^J \sum _{i \epsilon Rj} (y_i - \widehat{y}_{R_j})^2
```
For each value of α there corresponds a subtree `$T ⊂ T_0$` such that
```math
    \sum _{m=1} ^{|T|} \sum _{x_i \epsilon R_m} (y_i - \widehat{y}_{R_m})^2 + \alpha |T|
```
is as small as possible. Here |T| indicates the number of terminal nodes of the tree T , Rm is the rectangle (i.e. the subset of predictor space) corresponding to the mth terminal node, and `$\widehat{y}_{R_m}$` is the predicted response associated with Rm