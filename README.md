<p align="center">
<img width="221" height="275"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/findOUT_logo.png">
</p>
  
Developed by [**Peter Skelsey**](mailto:peter.skelsey@hutton.ac.uk?subject=findOUT), James Hutton Institute, Dundee
<p align="center">
[**Peter Skelsey**](mailto:peter.skelsey@hutton.ac.uk?subject=findOUT)
</p>

## Basic overview
A standalone desktop app for developing your own crop disease forecasting tools using anomaly detection algorithms.
* Upload your own two-dimensional data (two predictor variables), or use our example data.
* Choose an anomaly detection algorithm.
* Set the fraction of inliers required - this determines the frequency of risk alerts.
* Train and test your algorithm using k-fold cross-validation.
* Results for forecast accuracy and frequency of alerts issued are automatically saved.
* View the decision boundary.
* Make future predictions.

## Example
Daily weather data corresponding to 200 disease outbreaks has been loaded. The two predictor variables are (1) the number of hours of relative humidity >90% per day, and (2) the daily minimum temperature. The data span a 28-day period prior to the date each outbreak was reported, and are used to relate weather conditions for infection to the dates at which disease was observed in the crop. A one-class support vector machine has been trained and tested using 10-fold cross-validation. It has identified the envelope of weather conditions most commonly associated with disease (black markers) and those that are anomalous (blue markers). Any events that fall inside the decision boundary delineated by the black markers will trigger a risk alert, otherwise no alert is issued. If a risk alert is issued on any day in the 28-day window leading up to the outbreak of disease, then that is considered a successful forecast. The performance results give the percentage accuracy in forecasting outbreaks and the percentage of days on which an alert was issued in each of the test folds. The results are saved automatically to the root directory.

<p align="left">
  <img src="https://github.com/pskelsey/findOUT/blob/gh-pages/screenShot.PNG">
</p>

## Motivation
Information from crop disease surveillance programs and outbreak investigations provide real-world data about the drivers of infection epidemics events. In many cases, however, only information on outbreaks is collected and data from surrounding healthy crops is omitted. Use of such data to develop models to forecast risk of disease is therefore problematic, as information relating to the ‘no-risk’ status of crops is missing. The task then is to explore these data using anomaly detection algorithms to find the feature values (e.g., weather variables) most commonly associated with disease occurrence and those that are less common or anomalous, in order to derive rules that can be used to predict risk of disease (or no risk) in the future.

### Installation and loading
To download the app for the first time, click the green "Code" button and then select 'download ZIP' from the dropdown menu:

<p align="left">
  <img src="https://github.com/pskelsey/findOUT/blob/gh-pages/downloadScreenshot.png">
</p>

Then unzip the contents. There are two executable files you can run to install this app - which one you choose depends on whether or not you have MATLAB installed on your computer. This is because the app was made in MATLAB and requires 'MATLAB Runtime' to work. MATLAB Runtime is a completely free, standalone set of shared libraries that enables the execution of MATLAB applications on computers that do not have MATLAB installed. This all happens 'behind the scenes' and once it is installed then MATLAB apps will run like any other piece of software, using the desktop shortcuts etc. provided. And then you can download and use as many of the thousands of available MATLAB apps as you like, free of charge. So, if you do not have MATLAB or an up-to-date version of Runtime installed (see [prerequisites](https://github.com/pskelsey/4C-Lite-model/blob/master/prerequisites.txt)) installed, then run 'findOUT_And_Runtime.exe' to install the app. This is a web-based installer that will download MATLAB Runtime to your computer and install the app, so you will need an internet connection. MATLAB Runtime requires approximately 750MB of disk space so it may take some time to install. If you already have MATLAB or an up-to-date version of Runtime, then run 'findOUT.exe' to install the app. If you already have this app and want to check for a new release, click on the 'release' button near the top of the page.

NOTE: When the app is loading the splash screen may disappear for a brief interval before the app loads - there is no need to try and load it again, just give it a few seconds. The GUI is 'responsive' and can be scaled to any size, however this will change the layout of the controls. 

### Documentation
A full guide on how to use the app to build your own crop disease forecasting tool is provided in the [Documentation.md](https://github.com/pskelsey/findOUT/blob/master/docs/documentation.md)

### References
[Skelsey, P. 2020. Forecasting risk of crop disease with anomaly detection algorithms. Phytopathology, in press.

### License
The MIT License (MIT) 2020 - Peter Skelsey. For more details, please have a look at the [LICENSE](https://github.com/pskelsey/findOUT/blob/master/LICENSE).
