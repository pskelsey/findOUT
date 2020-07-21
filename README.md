<p align="left">
<img width="212" height="212"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/icon_big.png">
</p>
   
# findOUT
A desktop app for developing your own crop disease forecasting tools using anomaly detection algorithms

## Basic overview
A desktop app for performing climate change risk assessments in real crop locations in Great Britain. 
* Build your own risk model from your own data in a few easy clicks.
* Choose a raster distribution of crops to apply your model in.
* Select your climate variables and greenhouse gas emissions scenario.
* Define the level of connectivity among grid cell locations, if desired.
* Hit the run button, visualise your results, and save them to create your own graphics. 

## Example
A surface polynomial risk function is selected and fit to data uploaded by the user for the proportion of plants infected as a function of temperature and relative humidity. The results of the fit are saved to the user's specified directory.

<p align="left">
  <img src="https://github.com/pskelsey/4C-model-lite/blob/gh-pages/riskModelScreenshot.PNG">
</p>
Now that the model has been fitted, the risk assessment can proceed in the Climate Tab. Temperature and humidity are selected as the variables of interest, for summer in the 2060s, and barley crops are selected from the list of available crop species. That selection is narrowed further to locations in the north of Scotland (map shown). In order to adjust projected values from the model according to the connectivity of the crops (e.g. for pest/pathogen dispersal), dispersal is switched on and the mean dispersal distance is set to 1 grid cell (12 km). The three boxplots show the distribution of projected model values for the three types of dispersal kernel. Results are presented as the percentage increase in risk compared to the current (baseline) climate. 
<p>
</p>
<p align="left">
  <img src="https://github.com/pskelsey/4C-model-lite/blob/gh-pages/projectionsScreenshot.PNG">
</p>

## Motivation
This app was developed as a tool to help non-modellers perform state-of-the-art climate change risk assessments. At your fingertips are real crop / land-use data from [IACS](https://ec.europa.eu/info/food-farming-fisheries/key-policies/common-agricultural-policy/financing-cap/controls-and-transparency/managing-payments_en) and [JACS](https://www2.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and the latest [UKCP18](http://ukclimateprojections.metoffice.gov.uk/21678) probabilistic climate change data. This model is a 'light' version of the previous [4C model](https://github.com/pskelsey/4C-model) that makesthe whole process of performing a climate change risk assessment even easier; creating a risk model and defining your future scenarios is just a matter of hitting a few switches and twiddling a few knobs. I've used this framework to produce [peer-reviewed journal articles](#references), and you can too. 

### Installation and loading
To download the app for the first time, use the green "Clone or download" button to obtain a ZIP file:

<p align="left">
  <img src="https://github.com/pskelsey/4C-Lite-model/blob/gh-pages/donwloadScreenshot.png">
</p>

Then unzip the contents. There are two executable files you can run to install this app - which one you choose depends on whether or not you have MATLAB installed on your computer. This is because the app was made in MATLAB and requires 'MATLAB Runtime' to work. MATLAB Runtime is a completely free, standalone set of shared libraries that enables the execution of MATLAB applications on computers that do not have MATLAB installed. This all happens 'behind the scenes' and once it is installed then MATLAB apps will run like any other piece of software, using the desktop shortcuts etc. provided. And then you can download and use as many of the thousands of available MATLAB apps as you like, free of charge. So, if you do not have MATLAB or an up-to-date version of Runtime installed (see [prerequisites](https://github.com/pskelsey/4C-Lite-model/blob/master/prerequisites.txt)) installed, then run 'MyAppInstaller_web.exe' to install the app. This is a web-based installer that will download MATLAB Runtime to your computer and install the app, so you will need an internet connection. MATLAB Runtime requires approximately 750MB of disk space so it may take some time to install. If you already have MATLAB or an up-to-date version of Runtime, then run 'cropConnectivityUnderClimateChange_Lite.exe' to install the app. If you already have this app and want to check for a new release, click on the 'release' button near the top of the page.

NOTE: When the app is loading the splash screen may disappear for a brief interval before the app loads - there is no need to try and load it again, just give it a few seconds. Due to the many controls and features of the app, the GUI is a fixed size (12") and not 'responsive,' i.e. it will not scale to fit the screen of your device. This means it may not be suitable for notebooks with smaller screens and is best suited for desktop PCs. 

### Documentation
A full guide on how to use the app to perform climate change risk assessments is provided in the [Documentation.md](https://github.com/pskelsey/4C-Lite-model/blob/master/docs/documentation.md)

### References
[Skelsey, P. et al. 2017. Potential impacts of climate change on the threat of potato cyst nematode species in Great Britain. Plant Pathology, DOI: 10.1111/ppa12807.](http://onlinelibrary.wiley.com/doi/10.1111/ppa.12807/full)

[Skelsey, P. et al. 2016. Crop connectivity under climate change: future environmental and geographic risks of potato late blight in Scotland. Global Change Biology 22:3724–3738.](http://onlinelibrary.wiley.com/doi/10.1111/gcb.13368/full)

[Skelsey, P., and Newton, A.C. 2015. Future environmental and geographic risks of Fusarium head blight of wheat in Scotland. European Journal of Plant Pathology 142:133–147.](https://link.springer.com/article/10.1007/s10658-015-0598-7)

### License
The MIT License (MIT) 2020 - Peter Skelsey. For more details, please have a look at the [LICENSE](https://github.com/pskelsey/4C-Lite-model/blob/master/LICENSE).
