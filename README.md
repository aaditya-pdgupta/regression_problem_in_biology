# Introduction

A model is a mathematical description of a physical, chemical, or biological state or process whose part are mathematical concepts such as constant, variables, function, equation, inequalities, etc. Using a model help us to think about such processes and their mechanisms, so we can design better experiments and comprehend the results. 
Models are tools that assist in theory development. Criteria for selecting a model include the goodness of fit, freedom from systematic error and simplicity. To fit the model we need regression. The regression model is an equation that defines the outcome, or dependent variable Y, as
a function of an independent variable X, and one or more model parameters. The regression model determines a relationship between an independent variable and a dependent variable by providing a function. Regression analysis is often used to demonstrate association among variables believed to be biologically related. Linear and non-linear regression fit a mathematical model to the data to determine the best values of the parameters of the model.

For this, we need to select the best model to obtain our maximum output result. Model selection is the task of selecting a statistical mode from a set of candidate models, given data. There are different criteria for the selection of data such as Final Prediction Error (FPE), Alkaike's Information Criterion (AIC), F-test, Shortest Data Descriptor (SDD), Residuals, Parameter Variance Statistics, Determinant Comparison, Zero Pole-Zero Cancellation, etc. Applying these criteria we have a different test to select the best model. In this manuscript, we perform the chi-square test for the goodness of fit. However, there are other tests such as the Exact Test of goodness-of-fit, Power analysis, G-test of goodness-of-fit, Chi-square test for independence, G-test of independence, Fisher's exact test, Small numbers in chi-square and G-tests, Repeated G-tests of goodness-of-fit and Cochran-Mantel-Haenszel test, etc but we use Chi-square test of goodness-of-fit for our manuscript. The Chi-square goodness of fit test is a test that determines whether the variable is likely to come from a specified distribution or not. It was proposed by Pearson (1900). It is also known as statistical tests. Modeling has been widely used in biological research. 

# Regression Problem in Biology

Regression involves the determination of the degree of relationship in the patterns of variation of two or more variables through the calculation of the coefficient of correlation. The regression problem is how to model one or several dependent variables/responses, y, using a set of predictor models. It typically corresponds to very different biological questions. Evolution regression across species is one of the major statistical procedures used to study the evolutionary relationship between biological variables and test hypotheses. In biology, compartmental analysis models are used in radio-active tracers to study metabolic disorders. Over the last decades, sophisticated statistical models have been developed. Most of these developments have been focused on solving statistical problems and biological interpretations. assumptions made to solve statistical problems are often incompatible with biological processes. So both biological and statistical considerations are necessary to obtain meaningful evolutionary and allometric regression model observation or measurement error is a serious concern for most comparative studies.

# Data

The dataset for this model is retrieved from a book named "Fitting Models to Biological Data using Linear and Nonlinear Regression". In this model, various doses of a drug were injected into three animals, and the change in blood pressure for each animal was recorded. The data for this model is fitted with nonlinear regression. The dataset includes 2 variables along with 4 parameters. The variables used in this dataset are shown below in table.

| log(dose) | $Y_{1}$ | $Y_{2}$ | $Y_{3}$ |
| --------- | ------- | ------- | ------- |
| -7.0      | 1       | 4       | 5       |
| -6.5      | 5       | 4       | 8       |
| -6.0      | 14      | 14      | 12      |
| -5.5      | 19      | 14      | 22      |
| -5.0      | 23      | 24      | 21      |
| -4.5      | 26      | 24      | 24      |
| -4.0      | 26      | 25      | 24      |
| -3.5      | 27      | 31      | 26      |
| -3.0      | 27      | 29      | 25      |

In the above table, log (doses) denotes the logarithm of doses of drug given to the animals whereas $Y_{1}$, $Y_{2}$, and $Y_{3}$ are the change in blood pressure to whom various doses were injected. $Y_{1}$ is the value for the minimal curve asymptote (theoretically, the level of response, if any, in the absence of a drug), $Y_{3}$ is the value for the maximal curve asymptote (theoretically, the level of response produced by an infinitely high concentration of drug), and $Y_{2}$ is the value produces the response halfway between the Top and Bottom response levels (commonly used as a measure of drugs' potency).

# Fit in python

Python has methods for finding a relationship between data points and drawing a regression function that can be both linear and non-linear. In statistics, we say that regression is linear when it’s linear in the parameters. Fitting linear models is an easy task, we can use the least squares method and obtain the optimal parameters for our model.  However, not all problems can be solved with pure linear models. So nonlinear model has required that guarantee useful mathematical properties and are also highly interpretable. A nonlinear model is a mathematical model that fits an equation to certain data using a generated line such as a curve that is not a straight line. The regression problems are generally solved using curve fit and machine learning methods. Curve fitting examines the relationship between one or more predictors (independent variables) and a response variable (dependent variable), intending to define a "best fit" model of the relationship. Using the curve fitting makes our outcomes much more interpretable and even guarantees some mathematical property on our model output.  Here, to perform the regression, we use the curve fit methods. Besides these, we use Matplotlib and Numpy. These are the main libraries we’ll use for fitting purposes.
