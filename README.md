# Addressing Questions from Deliverable 1 
## Linear Regression to Predict MPG
### 1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset? 
The vehicle_length and the ground_clearance variables appear to be the most significant variables to keep in the linear model, based on the model above.  The vehicle_weight appears to have a 0.05 level of significance, which is fairly significant, but I would opt to keep in the length and clearance before looking at the vehicle weight. 

![Model Summary](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/lm.summary.PNG)

### 2. Is the slope of the linear model considered to be zero? Why or why not? 
I would say yes because the regression model plots that are used to check the conditions of a linear regression model show that the residual fitted plot hovers roughly around zero, there is some variation with data that may need to be looked at. 

![Residual Fitted](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/lm.residual_fitted.PNG)

### 3. Does this linear model predict mpg of MechCar prototypes effectively? Why or why not? 
I would not trust this model for predicting a MechCar's prototype mpg because nothing additional was checked.  I would rather trust a model created by an all subsets, forward regression, backwards regression or stepwise regression model.  Adding all the variables into one regression model can be a start, but we don't know if it's an efficient model or not.  By this point, we don't know if there are outliers skewing the model, influential points, multicollinearity, or even if the data itself fits a linear model.

# Deliverable 2

![Total Summary](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/total_summary.PNG)

![Lot Summary](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/lot_summary.PNG)

# Addressing Questions from Deliverable 2
### 1. The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?
Lots 1 and 2 fall into the design specifications, but Lot 3 is 70 points over.  Looking at the histograms of the grouped data, it appears that Lot3 has some data on both the extreme low and extreme high side of PSI.  These are most likely outliers that are causing the jump in variance for Lot3.

![Total Histogram](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/hist.car.sus.PNG)

![Lot 1 Histogram](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/hist.lot1.PNG)

![Lot 2 Histogram](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/hist.lot2.PNG)

![Lot 3 Histogram](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/hist.lot3.PNG)

# Deliverable 3 
We want to know if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

![T-Test Results](https://github.com/awar2170/R_Bootcamp/blob/main/Challenge/Results/t.tests.PNG)

# Addressing Questions from Deliverable 3
## T-Tests on Suspension Coils
Based on an alpha level of 0.05, Lot 1 and Lot 2 have p-values under 0.05 that suggest we reject the Ho and have evidence to support that the true mean is not equal to 1498.78.  Lot 3 has a p-value of 0.1589, which is greater than 0.05, which means that we fail to reject the null hypothesis and have evidence to support that the true mean is equal to 1498.78.

I think what this really shows is how much skew Lot 3 has on the data.  I think if we removed Lot3 from the data and did the same test on it, we would find that Lots 1 and 2 would have evidence to support the true mean.

# Deliverable 4 
# Addressing Questions from Deliverable 4
## Study Design: MechaCar vs Competition
### 1. Write a short description of a statistical study that can quantify how the MechaCar performs against the competition. 
We can quantify how certain cars perform against eachother by collecting data on the cost, mpg, and safety ratings of two cars and run a two sample t-test to test which is better. 

### 2.In your description, address the following questions:
### - What metric or metrics are you going to test?
The study would most likely test initial cost, mpg, maintenance costs, and safety ratings.  Using these statistics we could compare these to competitors and create visualizations so that consumers could easily compare between one company and the other. 

### - What is the null hypothesis or alternative hypothesis?
Ho: There is a difference between Toyota's and Competitor's [X]
Ha: There is no difference between Toyota's and Competitor's [X]

### - What statistical test would you use to test the hypothesis? And why?
I would use a two sample t-test because that test is used to determine if the population means between two samples are equal or not. 

### - What data is needed to run the statistical test?
I would need market data for the initial prices and maintenance data, crash test data for safety rating data, and mpg data of Toyota vehicles vs the Competitor.