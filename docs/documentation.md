<p align="left">
<img width="221" height="275"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/findOUT_logo.png">
</p>
  
Developed by [**Peter Skelsey**](mailto:peter.skelsey@hutton.ac.uk?subject=findOUT), James Hutton Institute, Dundee

# USER GUIDE

## Table of Contents
* [Background](#background)
* [Basic operation](#basic-operation)
* [Upload your data](#upload-your-data)
* [Train and test an algorithm](#train-and-test-an-algorithm)
* [Check your results](#chek-your-results)
* [Make future predictions](#adjust-the-plot)
  
  
## Background
The app uses anomaly detection algorithms to determine a decision boundary separating outliers and inliers in your data. Any instances that fall inside the decision boundary that contains the least anomalous events will trigger a risk alert. least anomalous values in your datagridded crop distribution and climate change data, and allows you to build a weather-dependent model from your own data that is a function of one- or two-climate variables, and apply it in selected crop grid cells under various climate change scenarios. A unique feature of the app is the ability to define spatial relationships (e.g. risk of pest or pathogen dispersal) among grid cells via various dispersal options. These spatial relationships can be used to modify projected values. 

## Basic operation
*Tabs*: The app has two 'tabs' - 'Model' and 'Climate.' To switch from one tab to the other just click on their name.  
*Switches*: Drag the circluar switch to the left or right, or just click in the empty space.  
*Buttons*: Click the button.
*Drop down lists*: Click on the downward pointing arrow to reveal the list. Click to select a list member.
*Numeric fields*: Click in the white box to change the numerical value. Then hit enter or click outside the box.  
*Knobs*: Drag the control to around your selection, or click on your selection.  
*Spinners*: Use the up and down arrows to increase a value by increments.
*List box*: Click on desired option.
Note: Selection of certain options will result in others becoming 'greyed out' and unavailable to edit. This is normal and is there to ensure conflicting choices are not made.

## Upload your data
Use the 'No. of variables' switch to select a model that is a function of one- or two-weather variables. Certain options will become greyed out and unavailable depending on what you select here. Click the 'Load data' button to upload your data. This will open up a file selection dialog box. Your datafile must be an ASCII delimited text file or CSV file with the data stored in columns. If your data have one weather variable, this should be stored in the first column and your 'response' or dependent variable in the second. If your data have two weather variables, these should be stored in the first two columns and your response variable in the third. Replicates should be placed in rows. If your file does not meet these requirements then a warning will occur. Two example datasets ('exampleData1Var.txt & exampleData2Var.txt') have been provided to help you get you up and running. Your data will be plotted automatically once it has loaded successfully, and the axis limits of the plot pane will adjust according to the lower and upper values in your data. You can change

## Train and test an algorithm
Use the 'Type of fit' switch to select a polynomial or spline fit. To fit a polynomial to your data, select the degree of the polynomial curve p(x) or surface p(x,y) using the 'degree-x' and 'degree-y' spinners. The method of least squares (linear or nonlinear) is used used for fitting. The spline option uses spline interpolation to fit a curve or surface to your data. If you have selected one variable, a smoothing spline model will be fit to your data with the option to adjust the smoothness of the fit using the 'smoothing' numeric field (a value between 0 and 1). If you have selecte two variables then thin-plate spline interpolation will be used and the option for adjusting the smoothness will be greyed out. Click the 'Fit model' button to fit the model. The model will be plotted automatically together with your data.The goodness of fit statistics will be displayed in the 'GoF'pane. 

## Check your results
Use the 'x-range', 'y-range' and 'z-range' numeric fields to visualise or extrapolate your model across a different range of values on a particular axis. The format required is min:max, e.g. to plot from 0 to 10 you would enter 0:10. Then hit Return on your keyboard or click your mouse outside of the numeric field. Note that this is for visualisation purposes only and does not affect model fit.

## Make future predictions
Click the 'Save' button to open up a file save dialog box, where you can name your results file and save to any location. Note that for the poly option, details of the fit (formula, coefficients etc.) and the GoF statistics will be saved, but for spline only the GoF statistics will be saved, as this is considered a non-parametric fit.
