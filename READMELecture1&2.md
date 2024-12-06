What I did and learnt in R for Lectures 1 and 2: 

Downloaded the Rmarkdown file for lecture 1 with Professor Kapoor's code
Learnt how to assign values using <-
Changed the file path for CEO_Diary to the one on my local computer
Learnt how to get a file's file path using right click and then properties 
Learnt how to load files in using read.csv and how to view files using view function but also using right hand side panel on R
Learnt by altering the code that if subset a dataframe with same column number twice then it shows that column twice as colname and colname.1 in the output : CEO_Diary[1:15,c(1:5,37, 39, 39)] 
Learnt that c is a combine function that allows us to create a vector using both ranges like 1:5 and numbers like 37 at the same time
Learnt how to use the apply function to find class of variable
Altered the code to apply(CEO_Diary,3,class) (changed 2 to 3) to realize what the arguments of this function are and that the second argument refers to either rows (1) or columns (2) so any number beyond that wouldn't work
Learnt that nrow functionis used to get number of rows in a dataframe
Learnt that summary function gives descriptive statistics of a dataframe and that it can also be applied to a subset of the dataframe 
Altered code by adding ncol function to learn that this function gives number of columns of a dataframe
Altered code to add nrow[CEO_Diary] to learn that functions require standard brackets () to open and close and not [] or else get error 
Learnt that the prop.table() function coverts frequencies into proportions
Learnt that barplot() function can then plot those proportions
Learnt that R can be used to alter png files 
Learnt that dev.off() function closes the code for making adjustments to png files and png() function opens it
Learnt that par(mar()) functions together allow you to set margins of a plot
Learnt that las=2 in  barplot(prop.table(table(CEO_Diary$type)), las=2), rotates the axis labels to be perpendicular to the axis 
Learnt that can also run code from console 
Altered code to do new barplot with different x-variable: barplot(prop.table(table(CEO_Diary$F_planned)));
Learnt the glm() function is used to fit generalized linear models like regressions in R
Altered code to specify family = binomial to see difference in results: fit <- glm(strategy ~ consultants + politicians, data=CEO_Diary, family = binomial); summary(fit)


Downloaded the Rmarkdown file for lecture 2 with Professor Kapoor's code
Altered code for loading in dataset to load in correct file from my own computer using correct file path: read.csv("C:/Users/aditc/OneDrive/Documents/web-browsers.csv")
Learnt that the dim() function gives rows and columns of dataframe and head() function displays first 6 rows of dataframe
Added tail() function to look at last 6 rows of browser dataframe
Learnt that ; is used as line break and that 1e4 is seen as 10,000 in R
Learnt how to use mean(), var() and sqrt() functions to get average and variance of dataframe column and to take square roots of numbers to get standard deviation for example
Added mean(browser$hispanic) to see proportion of hispanic individuals after noting that this variable is binary
Learnt how to initialize a vector using x <- c()
Learnt how to add values to this initialized vector using x <- c(x, value)
Learnt how to sample with replacement using sample.int(nrow(browser), replace = TRUE)
Learnt how to bootstrap the mean of a column in a dataframe using a for loop and randomly sampled integers from 1 to the number of rows in the column and how to use this to get the standard error of a mean
Adjusted code to try different number of interations in the bootstrap for loop from 50 to 5000 to see effect, noticed diminishing benefits from increasing past certain point 
Adjusted code for mean boostrap to set replacement to FALSE and as expected the standard error I got was 0 cos then just sampling same dataset as original everytime and so same mean computed every time so 0 standard deviation in the bootstrapped mean values
Learnt how to create a histogram in R
Learnt how to scale a normal distribution line of x to fit a histogram of x
Adjusted the lwd parameter in   lines(xfit, yfit, col = "black", lwd = 4) to note that higher values increase the width of the yfit line
Learnt how to do a bootstrapped regression in r using for loop, sample.int() function and glm function and how to collect betas from glm using coef(reg_b) when reg_b <- glm(..) 
Altered bootstrapped regression code to set replace = FALSE to note that now as expected betas obviously aren't 0 but are different to when replace = TRUE
Learnt how to use cov() function to get the covariance of two vectors
Learnt that have to use rbind() function not c() when adding vectors to matrix and c() instead when adding values to vector
Learnt that can also index using "" in [] eg. betas[,"broadband"] instead of betas[,2]
Learnt that can use log() to consider logarithm of a variable like in glm(log(spend) ~ . -id, data=browser)
Learnt that ~ . -id in glm(log(spend) ~ . -id, data=browser) means that the independent variables include all variable columns in browser dataset except for id
Altered code to see what would happen if id was included - as expected all variables' coefficients change but was interesting to note that id coefficient was zero and had a 0 standard error
Learnt how round function works and that can apply it to summary function and this would apply it all values in summary output
Altered last argument in  round(summary(spendy)$coef,2) from 2 to 3 to understand that this is the number of decimal places to round to (and not number of significant figures or etc.) 
Learnt that x[-1,] extracts all values except first so summary(spendy)$coef[-1, "Pr(>|t|)"] extracts all p-values except for intercept
Learnt how the rank function works and how it sorts by doing print(pvalrank)
Learnt how to use an ifelse() function and what it's arguments should be
Learnt that lines() function can be used generally to add any specified line plot to the plot being considered
Learnt how to fit a logistic regression using glm and family = binomial
Changed 4 to 5 in pvals <- summary(full)$coef[-1,4] to note that this takes us out of bounds which taught me that only 4 columns in summary 
Learnt that in hist(pvals, xlab="p-value", main="", col="lightblue"), main ="" means leave title empty
Learnt how to implement BH algorithm in R
Learnt how to initialize function and define it's arguments: fdr_cut <- function(pvals, q=0.1){
Experimented with changing value of q to 0.2 in fdr_cut function and ties.method="max" instead of "min"
Experimented and Learnt that replacing q = 0.1 in argument with just q and then doing fdr_cut(pvals,q=0.5) does not work

