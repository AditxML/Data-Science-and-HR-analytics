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
