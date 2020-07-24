<p align="left">
<img width="221" height="275"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/findOUT_logo.png">
</p>
  
Developed by [**Peter Skelsey**](mailto:peter.skelsey@hutton.ac.uk?subject=findOUT), James Hutton Institute, Dundee

## Basic overview
A standalone desktop app for developing your own disease risk forecasting tool using unsupervised anomaly detection algorithms.
* Upload your own data (2 predictor variables) or use our example data.
* Choose an anomaly detection algorithm.
* Set the fraction of inliers required.
* Train and test your algorithm using *k*-fold cross-validation.
* Save your results for forecast accuracy and frequency of alerts issued.
* View the decision boundary.
* Make future predictions.

## Example
Daily weather data corresponding to 200 crop disease outbreaks has been loaded. The two predictor variables are: (1) the number of hours of relative humidity >90% per day, and (2) the daily minimum temperature. The data span a 28-day period prior to the date each outbreak was reported, and are used to relate weather conditions for infection to the dates at which disease was observed in the crop. A one-class support vector machine has been trained and tested using 10-fold cross-validation. It has identified the envelope of weather conditions most commonly associated with disease (black markers) and those that are anomalous (blue markers). Any events that fall inside the decision boundary delineated by the black markers will trigger a risk alert, otherwise no alert is issued. If a risk alert is issued on any day in the 28-day window leading up to the outbreak of disease, then that is considered a successful forecast. The performance results give the percentage accuracy in forecasting outbreaks and the percentage of days on which an alert was issued in each of the test folds. The results can be saved to your PC. 

<p align="left">
  <img src="https://github.com/pskelsey/findOUT/blob/gh-pages/screenShot.PNG">
</p>

## Motivation
The app can be used for any 'unsupervised anomaly detection' problem, where you don't have 'labelled' data that identify normal and abnormal cases, but  was inspired to aid in the development of crop disease prediction models. There are an abundance of data from crop disease surveillance programs and outbreak investigations that provide real-world information about the drivers of epidemics, but are unsuitable for the derivation of tools to forecast risk. Such data are unsuitable because only information on outbreaks is collected and data from surrounding healthy crops is omitted. It is therefore not possible to label the data as 'healthy' versus 'diseased,' and thus problematic to develop classifiers that can forecast risk / no-risk of disease. The task then is to explore these data using anomaly detection algorithms to find the feature values (e.g., weather variables) most commonly associated with disease occurrence and those that are less common or anomalous, in order to derive rules that can be used to predict risk of disease (or no risk) in the future. See the [Documentation](https://github.com/pskelsey/findOUT/blob/master/docs/documentation.md) for information on how to set up your own data for use.     

### Installation and loading
The app is freely available to download and install on any dekstop PC. To download the app for the first time, click the green "Code" button and then select 'download ZIP' from the dropdown menu:

<p align="left">
  <img src="https://github.com/pskelsey/findOUT/blob/gh-pages/downloadScreenshot.png">
</p>

Then unzip the contents. There are two executable files you can run to install this app - which one you choose depends on whether or not you have MATLAB installed on your computer. If you do not have a MATLAB license, or the version you have is not R2020a (see [prerequisites](https://github.com/pskelsey/findOUT/blob/master/prerequisites.txt)), then run 'findOUT_And_Runtime.exe' to install the app. This is a web-based installer that will simultaneously install the app and download 'MATLAB Runtime' to your computer. MATLAB Runtime is a completely free, standalone set of shared libraries that enables the execution of MATLAB applications on computers that do not have MATLAB installed. This all happens 'behind the scenes' and once it is installed then MATLAB apps will run like any other piece of software, using the desktop shortcuts etc. provided. Then you can download and use thousands of other freely available MATLAB apps. You will need an internet connection, and MATLAB Runtime requires approximately 1.7GB of disk space so it may take some time to install. If you already have MATLAB R2020a, then you can simply double click 'findOUT.exe' to run the app. To check for a new release of this app, click on the 'release' button near the top of the page.

NOTE: When the app is loading the splash screen may disappear for a brief interval before the app opens - there is no need to try and load it again, just give it a few seconds. The GUI is 'responsive' and can be scaled to any size, however this will change the layout of the controls. 

### Documentation
A full guide on how to use the app to build your own crop disease forecasting tool is provided in the [Documentation](https://github.com/pskelsey/findOUT/blob/master/docs/documentation.md)

### References
[Skelsey, P. 2020. Forecasting risk of crop disease with anomaly detection algorithms. Phytopathology, *in press*.

### License
The MIT License (MIT) 2020 - Peter Skelsey. For more details, please have a look at the [LICENSE](https://github.com/pskelsey/findOUT/blob/master/LICENSE).
