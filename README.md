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

# Fit in Python

Python has methods for finding a relationship between data points and drawing a regression function that can be both linear and non-linear. In statistics, we say that regression is linear when it’s linear in the parameters. Fitting linear models is an easy task, we can use the least squares method and obtain the optimal parameters for our model.  However, not all problems can be solved with pure linear models. So nonlinear model has required that guarantee useful mathematical properties and are also highly interpretable. A nonlinear model is a mathematical model that fits an equation to certain data using a generated line such as a curve that is not a straight line. The regression problems are generally solved using curve fit and machine learning methods. Curve fitting examines the relationship between one or more predictors (independent variables) and a response variable (dependent variable), intending to define a "best fit" model of the relationship. Using the curve fitting makes our outcomes much more interpretable and even guarantees some mathematical property on our model output.  Here, to perform the regression, we use the curve fit methods. Besides these, we use Matplotlib and Numpy. These are the main libraries we’ll use for fitting purposes.

In python, the curve fit can be formed using several modules such as Scipy and lmfit based on least-squares minimization. A common use of least-squares minimization is curve fitting, where one has a parametrized model function meant to explain some phenomena and wants to adjust the numerical values for the model so that it most closely matches some data. Here, we make rigorous use of Scipy module from the Python. Scipy stands for Scientific Python. It is the scientific computing module of Python providing in-built functions on a lot of well-known Mathematical functions.  With scipy, curve fitting problems are typically solved with scipy.optimize.curve_fit, which is a wrapper around scipy.optimize.leastsq. Like scipy.optimize.curve_fit, lmft   uses a function that is meant to calculate a model for some phenomenon, and then uses that to best match an array of supplied data.  In curve fitting, the uncertainties of the fitted parameters are a measure of how strongly the parameter depends on the data.

## Least Squares Fitting

The method of least squares is a standard approach in regression analysis to approximate the solution of over-determined systems (sets of equations in which there are more equations than unknowns) by minimizing the sum of the squares of the residuals (a residual being the difference between an observed value and the fitted value provided by a model) made in the results of each equation.

Let $y_{i}$ be the observed set of  n data points, and $f(x_{i}, a_{1}, a_{2}, \dots , a_{n})$ be the function that is fitted to the data set. The square of the reside ( $R^{2}$ ) is calculated as
 $$R^{2} = \sum_{i}^{n} \left[ y_{i} - f(x_{i}, a_{1}, a_{2}, \dots , a_{n}) \right]^{2}$$
 
 The $R^{2}$ is minimized and the condition for $R^{2}$ to be a minimum is that
  $$\frac{\partial R^{2}}{\partial a_{i}} = 0 \quad \forall  \quad i = 1, 2, \dots, n$$
  
   For a linear fit,
   
   $$f(a,b) = ax + b$$
   
   Then,
    $$R^{2}(a,b) = \sum_{i}^{n} \left[ y_{i} - (ax_{i} + b) \right]^{2}$$
    $$\frac{\partial R^{2}}{\partial a} = - 2 \sum_{i}^{n} \left[ y_{i} - (ax_{i} + b) \right] = 0$$
    $$\frac{\partial R^{2}}{\partial b} = - 2 \sum_{i}^{n} \left[ y_{i} - (ax_{i} + b) \right]x_{i} = 0$$
    
     
 These lead to the equations
 $$na + b \sum_{i}^{n}x_{i} = \sum_{i}^{n}y_{i}$$
 $$na\sum_{i}^{n}x_{i} + b \sum_{i}^{n}x_{i}^{2} = \sum_{i}^{n}x_{i}y_{i}$$
 
 In the matrix form:
 $$n & \sum_{i}^{n}x_{i} \\
     n\sum_{i}^{n}x_{i} & \sum_{i}^{n}x_{i}^{2}$$ 
     
     
 Similarly
 $$covariance(x,y) = \frac{\sum_{i}^{n} (x_{i} - \Bar{x})(y_{i} - \Bar{y})}{n}$$
 
 # Result
 
In regression analysis, curve fitting is the process of specifying the model that provides the best fit to the specific curve in our dataset. Here, we tried the following models represented by equations written below in our fit. Equation first is a linear equation in independent variable x as function of dose and dependent variable y as response. In this model, we have a and b as the parameters.  Similarly, equation second is a quadratic equation that defines the response (dependent variable, y)  and function of dose ( independent variable, x), with the model parameters  a, b and c. Equation third is a cubic equation in x and y defined as in linear and quadratic equation, with the model parameters a, b, c, and d.

The fourth equation shows a standard model named as Hill function. It is used to model density-dependent growth or decline. Here it is used to model a process when various doses of a drug are applied to animals and the corresponding response was measured. The response (also called the independent variable, y) is measured as a function of dose (also called the independent variable, x). The model parameters are Bottom, which denotes the value of y for the minimal curve asymptote (theoretically, the level of response, if any, in the absence of drug, and Top which denotes the value of y for the maximal curve asymptote (theoretically, the level of response produced by an infinitely high concentration of drug), LogEC50 which denotes the logarithm of drug dose (or concentration) that produces the response halfway between the Top and Bottom response levels (commonly used as a measure of drugs' potency), and the Hillslope which denotes the steepness of the drug-response curve (often used as a measure of the sensitivity of the system to increments in drug concentration or doses.
 $$y = ax + b$$
 $$y = ax^{2} + bx + c$$
 $$y = ax^{3} + bx^{2} + cx + d$$
 $$y = Bottom + \frac{Top - Bottom}{1 + \left( \frac{10^{LogEC_{50}}}{10^{x}} \right)^{Hillslope}}$$
 
 Curved relationships between variables are not as straightforward to fit and interpret. In order to fit in the model represented by linear equations, quadratic equation, and cubic equation, we assume bottom as lower error ( $\Delta L$ ), and Top as upper error ( $\Delta U$ ). These two error are asymmetric, and they are made symmetric using error =$\sqrt{\Delta L^{2} + \Delta U^{2}}$. Then the data that is fitted to the model using Scipy and the fitted parameters are determined. 
 
 <p align="center">
  <img src="../main/Regression/data_with_assymetric_error.jpeg"  width="48%" />
  <img src="../main/Regression/data_with_symetric_error.jpeg"  width="48%" /> 
</p>

Figure named as data plot with asymmetric error and figure named as data plot with symmetric error show the data with asymmetric error and symmetric error respectively. Along the x-axis we have a log of the Dose that is applied to the animals and along the y-axis, we have a change in the blood pressure of animals along the y-axis while doses are given to them. Uncertainty has of great importance to avoid biased results. The asymmetric errors are converted to symmetric ones because the least squares algorithm like curve_fit will not be able to calculate the loss function negative error. 

 <p align="center">
  <img src="../main/Regression/linear_function.jpeg"  width="48%" />
  <img src="../main/Regression/quadratic_function.jpeg"  width="48%" /> 
</p>

 <p align="center">
  <img src="../main/Regression/cubic_function.jpeg"  width="48%" />
  <img src="../main/Regression/fit_data_without_error.jpeg"  width="48%" /> 
</p>


The figures above show the plot for both data along with uncertainties and the corresponding model that is fitted to it.  Along the x-axis we have a log of the Dose that is applied to the animals and along the y-axis, we have a change in the blood pressure of animals along the y-axis while doses are given to them.  Figure first shows the straight line fit to the data, while figure second shows the quadratic fit.  Similarly, figure third and figure fourth show the cubic equation fit and Hill function fit respectively. The fitted data formed a curve that is fitting the maximum data and providing us with the best fit for our data. Figure fourth does not have uncertainties in the response value as the Hill function have the parameters to accommodate the lower and the upper values of the change in blood pressures.

| Model        | Chi-square value | Dof  | Reduced chi-square value |
|------------- |----------------| --- |---------------------|
|Hill_function |11.4923         | 7  | 1.6417                  |
|linear        |6.4188          | 7  | 0.9169                  |
|quadratic     |1.0             | 6  | 0.1666                  |
|cubic         |1.0             | 5  | 0.2000                  |
     
    
    
    
