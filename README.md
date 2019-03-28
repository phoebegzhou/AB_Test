# AB_Test

**Introduction**

This project is about an AB test to help an e-commerce company to decide if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.

**What do you need to install?**

Python and its libraries:
1. Pandas
2. Numpy
3. Random
4. Matplotlibs

I recommend using Anaconda and Jupyter Notebooks to work on the project.

**Process**

1. Read in the ab_data.csv data. Store it in df. Use Python functions to look for the number of times the new_page and treatment don't match.
For the rows where treatment does not match with new_page or control does not match with old_page, we cannot be sure if this row truly received the new or old page, so
remove all these rows. Store the new dataframe into df2. Remove duplicated rows with the same user_id. 

2. Assume that the old page is better unless the new page proves to be definitely better at a Type I error rate of 5%, get your null and alternative hypothesis.
Perform the sampling distribution for the difference in converted between the two pages over 10,000 iterations of calculating an estimate from the null. 

3. Calculate the number of conversions for each page, as well as the number of individuals who received each page. Now use stats.proportions_ztest to compute your test statistic and p-value.

4. Perform a Logistic regression. First you need to create in df2 a column for the intercept, and create a dummy variable column for which page each user received. Use statsmodels to instantiate your regression model on the two columns you created. 
Look at the p-value for the regression. 
