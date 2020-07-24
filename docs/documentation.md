<p align="left">
<img width="221" height="275"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/findOUT_logo.png">
</p>
  
Developed by [**Peter Skelsey**](mailto:peter.skelsey@hutton.ac.uk?subject=findOUT), James Hutton Institute, Dundee

# USER GUIDE

## Table of Contents
* [Background](#background)
* [Basic operation](#basic-operation)
* [Format your data](#format-your-data)
  * [Upload your data](#upload-your-data)
* [Train and test an algorithm](#train-and-test-an-algorithm)
* [Check your results](#chek-your-results)
* [Make future predictions](#adjust-the-plot)
  
  
## Background
The app uses unsupervised anomaly detection algorithms to determine a decision boundary separating outliers and inliers in your data. Any future instances that fall inside the decision boundary will trigger a risk alert. See the reference at the bottom of the [README](https://github.com/pskelsey/findOUT/blob/master/README.md) for mathematical details on each algorithm.

## Basic operation
*Buttons*: Click the button.
*Check-boxes*: Check the box.
*Switches*: Drag the circluar switch to the left or right.
*Knobs*: Drag the control around to your selection, or click on your selection. 
*Numeric fields*: Click in the white box to change the numerical value. Then hit enter or click outside the box.  
Note: Certain options may be 'greyed out' and unavailable to ensure conflicting choices are not made. For example, you cannot hit the Run button until you have used the Load button to upload your data.

## Format your data
Your data must be stored in an excel file (.xls or .xlsx). You must have two predictor variables, each stored in a separate worksheet in your excel file. Name the worksheets 'var1' and 'var2'. Data corresponding to different events / objects should be stored in rows, and measurements corresponding to the same event should be stored in columns. For example, if you have data on 5000 events where for each event you have 10 measurements of predictor variable A and predictor variable B, then worksheets var1 and var2 will both contain a 5000 x 10 matrix of numbers. Missing data must be entered as 'NaN' (without the quotes) or left as an empty cell. There should be no text entries anywhere in your excel file, i.e., no headers and no text entires for missing data. You can, however, use 'Inf' (without the quotes) to represent infinity. If your file does not meet these requirements then a warning will occur. An example dataset ('exampleWeatherData.txt') has been provided to help you get you up and running. This contains synthetic data for 200 crop disease outbreaks, where for each outbreak there are 28 days Your data will be plotted automatically once it has loaded successfully, and the axis limits of the plot pane will adjust according to the lower and upper values in your data. 

### Upload your data
Click the 'Load data' button to upload your data. This will open up a file selection dialog box. 

## Train and test an algorithm
Use the 'z-score' check-box if you want to standardize your predictor variables to have mean 0 and scaled to have standard deviation 1. This can improve predictive performance. Slide the switch below to select 5-fold or 10-fold cross-validation. Use the circular 'Algorithm' knob to select one of the five anomaly detection algorithms: rcov = robust covariance, ockm = one-class *k*-means, gmm = Gaussian mixture model, kde = kernel density estimation, and ocsvm = one-class support vector machine. Set the fraction of inliers required using the 'fracIn' numeric field. The 'seed' numeric field is used to initialize the random number generator that divides your data into training and test folds: this ensures you can reproduce your results (using the same seed value) and test the effects of different splits (different seed values). Then click the 'Run' button to train and test your algorithm. The results of the cross-validation are given in the 'Performance' display panel (see below). Your selected algorithm is then 'finalized' by retraining using all the data (no cross-validation) and used to plot the inliers (black) and outliers (blue) in your data. The zone of black inliers delineates the decision boundary: any events that fall within that envelope of conditions will trigger a risk alert.

## Check your results
The 'Performance' display panel underneath the plot pane provides the results of the *k*-fold cross-validation for each test fold. The 'acc' (accuracy) is the proportion of events/objects (rows in your data) that were successfully forecasted. Note that a successful forecast occurs when any pair of predictor variables for that event is classified as an inlier. So using the example provided for formatting your data if you have, for example, one of the measurements  Use the 'x-range', 'y-range' and 'z-range' numeric fields to visualise or extrapolate your model across a different range of values on a particular axis. The format required is min:max, e.g. to plot from 0 to 10 you would enter 0:10. Then hit Return on your keyboard or click your mouse outside of the numeric field. Note that this is for visualisation purposes only and does not affect model fit.

## Make future predictions
Click the 'Save' button to open up a file save dialog box, where you can name your results file and save to any location. Note that for the poly option, details of the fit (formula, coefficients etc.) and the GoF statistics will be saved, but for spline only the GoF statistics will be saved, as this is considered a non-parametric fit.
