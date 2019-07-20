# 2.4 Exercises
> 2. Explain whether each scenario is a classification or regression problem, and indicate whether we are most interested in inference or prediction. Finally, provide n and p.  
> (a) We collect a set of data on the top 500 firms in the US. For each firm we record profit, number of employees, industry and the CEO salary. We are interested in understanding which factors affect CEO salary.   
(b) We are considering launching a new product and wish to know whether it will be a success or a failure. We collect data on 20 similar products that were previously launched. For each product we have recorded whether it was a success or failure, price charged for the product, marketing budget, competition price, and ten other variables.  
(c) We are interest in predicting the % change in the USD/Euro exchange rate in relation to the weekly changes in the world stock markets. Hence we collect weekly data for all of 2012. For each week we record the % change in the USD/Euro, the % change in the US market, the % change in the British market, and the % change in the German market.

(a)	regression, inference
n: 500 firms	p: profit, number of employees, industry

(b)	classification, prediction
n: 20 similar products 	p: price charged, marketing budget, competition price, ten other variables

(c)	regression, prediction
n: int(365/7) weeks of 2012	p: % change in US market, % change in British market, % change in German market

> 4. You will now think of some real-life applications for statistical learning.   
(a) Describe three real-life applications in which classification might be useful. Describe the response, as well as the predictors. Is the goal of each application inference or prediction? Explain your answer.   
(b) Describe three real-life applications in which regression might be useful. Describe the response, as well as the predictors. Is the goal of each application inference or prediction? Explain your answer.   
(c) Describe three real-life applications in which cluster analysis might be useful.

(a) 	recognize rubbish email. response: text of email, predictor: whether it is a rubbish email, goal: prediction    
recognize emotion. response: image, predictor: happy or sad or others, goal: prediction  
job-hopping. response: salary, working time and so on.. predictor: demission or not, goal: inference   
	
(b)	relationship of student’s GPA with attendance and homework score. response: every class’s attendance, homework score, predictor: GPA, goal: inference  
	stock. response: past time stock index, predictor: future stock index, goal: prediction  
	expression of genes. response: key genes’ expression, predictor: the target gene’s expression, goal: inference
	
(c) 	put similar market products in the same cabinet. response: size, type, brand and so on  
	differ cell types. response: tissue source, cell cycle, size, function and so on  
	recommendation in social network. response: area, interest, sex, age, job and so on 
	
> 6. Describe the differences between a parametric and a non-parametric statistical learning approach. What are the advantages of a parametric approach to regression or classification (as opposed to a nonparametric approach)? What are its disadvantages? 

Parametric model: With an assumption about the function form or shape of f, and then we use a set of estimated parameters to fit or train the regression or classification model.
* Advantage: 		simplify the problem of estimating f with a set of parameters  
allow a little noise and error in data  
easy to explain the relations and rules if model fits well  
	less observations also can fit the model than non-parameter model
* Disadvantage: 	the model we choose(always too easy model) may not match the true unknown form of f  
				the complex model with too many parameters may lead overfitting which catches too much noise 


Non-parametric model: Without explicit assumptions about function form of f, but we estimate f that gets as close to the data points as possible without too rough or wiggly to fit or train the regression or classification model.
* Advantage: 		avoiding the assumption of a particular functional form for f, they have the potential to accurately fit a wider range of possible shapes for f
* Disadvantage: 	a very large number of observations (far more than is typically needed for a parametric approach) is required  
				overfitting is also a problem in non-parametric model

> 8. This exercise relates to the College data set, which can be found in the file College.csv. It contains a number of variables for 777 different universities and colleges in the US. The variables are..
Before reading the data into R, it can be viewed in Excel or a text editor.

(a) Use the read.csv() function to read the data into R.  
(b) Try the following commands:  
(c) …

> 10. This exercise involves the Boston housing data set.

See the next page
