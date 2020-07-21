<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/findOUT/blob/gh-pages/findOUT_logo.png">
</p>


# DOCUMENTATION

# Table of Contents
* [Background](#background)
  * [Climate data](#climate-data)
  * [Crop data](#crop-data)
* [Basic operation](#basic-operation)
* [Model Tab](#model-tab)
  * [Upload your data](#upload-your-data)
  * [Fit a model](#fit-a-model)
  * [Adjust the plot](#adjust-the-plot)
  * [Save your fit results](#save-your-fit-results)
* [Climate tab](#climate-tab)
  * [Climate and crop panel](#climate-and-crop-panel)
  * [Dispersal panel](#dispersal-panel)
    * [Choose the type of dispersal](#choose-the-type-of-dispersal)
    * [Set to no dispersal](#set-to-no-dispersal)
  * [Plots panel](#plots-panel)
    * [Making maps](#making-maps)
    * [Plotting projected values](#plotting-projected-values)
    * [Saving results](#saving-results)
  

# Background
The app uses gridded crop distribution and climate change data, and allows you to build a weather-dependent model from your own data that is a function of one- or two-climate variables, and apply it in selected crop grid cells under various climate change scenarios. A unique feature of the app is the ability to define spatial relationships (e.g. risk of pest or pathogen dispersal) among grid cells via various dispersal options. These spatial relationships can be used to modify projected values. 

### Climate data
The app uses raw seasonal 12 km gridded (65 x 112 cells) climate data from the UK Met Office Climate Projections database ([UKCP18](http://ukclimateprojections.metoffice.gov.uk/)) 12-member ensemble of regional projections for the emissions scenario RCP8.5. These data provide the best estimates for modelling and summarising the potential effects of future climates on spatial processes in GB as they have full spatial and temporal coherence. This is important when analysing climate risks at different geographical locations at the same time and if there is physical connection between the locations. RCP8.5 is a high emissions scenario that is frequently referred to as 'business as usual', meaning it is the likely outcome if society does not make concerted efforts to reduce greenhouse gas emissions. The regional projections provide 12 equally plausible snapshots of climate change; i.e. a range of 12 future values are provided for each climate variable in each grid cell. UKMO baseline data for 1981-2000 are also included for comparison, i.e. for computing a change relative to the current climate.

### Crop data
Polygon data defining the spatial coverage of crops and land-use types were derived from [IACS](https://ec.europa.eu/info/food-farming-fisheries/key-policies/common-agricultural-policy/financing-cap/controls-and-transparency/managing-payments_en) and [JACS](https://www2.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus). These data cover Scotland only. The vector data were rasterised to 12 km grids matching the resolution of the climate change data. Information on the location and area of each crop is available for use in the app.

# Basic operation
*Tabs*: The app has two 'tabs' - 'Model' and 'Climate.' To switch from one tab to the other just click on their name.  
*Switches*: Drag the circluar switch to the left or right, or just click in the empty space.  
*Buttons*: Click the button.
*Drop down lists*: Click on the downward pointing arrow to reveal the list. Click to select a list member.
*Numeric fields*: Click in the white box to change the numerical value. Then hit enter or click outside the box.  
*Knobs*: Drag the control to around your selection, or click on your selection.  
*Spinners*: Use the up and down arrows to increase a value by increments.
*List box*: Click on desired option.
Note: Selection of certain options will result in others becoming 'greyed out' and unavailable to edit. This is normal and is there to ensure conflicting choices are not made.

# Model Tab
The risk models you create here can be a function of one- or two-weather variables, g = f(x) or g = f(x,y); e.g. yield production as a function of temperature, infection risk as a function of temperature and humidity, etc. Note that if you do not create a model here, you will not be able to produce any climate change projections.

<p align="left">
  <img src="https://github.com/pskelsey/4C-model-lite/blob/gh-pages/riskModelScreenshot.PNG">
</p>

### Upload your data
Use the 'No. of variables' switch to select a model that is a function of one- or two-weather variables. Certain options will become greyed out and unavailable depending on what you select here. Click the 'Load data' button to upload your data. This will open up a file selection dialog box. Your datafile must be an ASCII delimited text file or CSV file with the data stored in columns. If your data have one weather variable, this should be stored in the first column and your 'response' or dependent variable in the second. If your data have two weather variables, these should be stored in the first two columns and your response variable in the third. Replicates should be placed in rows. If your file does not meet these requirements then a warning will occur. Two example datasets ('exampleData1Var.txt & exampleData2Var.txt') have been provided to help you get you up and running. Your data will be plotted automatically once it has loaded successfully, and the axis limits of the plot pane will adjust according to the lower and upper values in your data. You can change

### Fit a model
Use the 'Type of fit' switch to select a polynomial or spline fit. To fit a polynomial to your data, select the degree of the polynomial curve p(x) or surface p(x,y) using the 'degree-x' and 'degree-y' spinners. The method of least squares (linear or nonlinear) is used used for fitting. The spline option uses spline interpolation to fit a curve or surface to your data. If you have selected one variable, a smoothing spline model will be fit to your data with the option to adjust the smoothness of the fit using the 'smoothing' numeric field (a value between 0 and 1). If you have selecte two variables then thin-plate spline interpolation will be used and the option for adjusting the smoothness will be greyed out. Click the 'Fit model' button to fit the model. The model will be plotted automatically together with your data.The goodness of fit statistics will be displayed in the 'GoF'pane. 

### Adjust the plot
Use the 'x-range', 'y-range' and 'z-range' numeric fields to visualise or extrapolate your model across a different range of values on a particular axis. The format required is min:max, e.g. to plot from 0 to 10 you would enter 0:10. Then hit Return on your keyboard or click your mouse outside of the numeric field. Note that this is for visualisation purposes only and does not affect model fit.

### Save your fit results
Click the 'Save' button to open up a file save dialog box, where you can name your results file and save to any location. Note that for the poly option, details of the fit (formula, coefficients etc.) and the GoF statistics will be saved, but for spline only the GoF statistics will be saved, as this is considered a non-parametric fit.

# Climate Tab
<p align="left">
  <img src="https://github.com/pskelsey/4C-model-lite/blob/gh-pages/projectionsScreenshot.PNG">
</p>

## Climate and crop panel
Select your climate variables (Temp = temperature, RH = relative humidity), future time-period, season (Spr = spring (MAM), Sum = summmer (JJA), Aut = autumn (SON), and Win = winter (DJF)), and region of the country using the knobs. Select the crop species of interest using the drop down list (OSR = oilseed rape). The climate change data are probabilistic, therefore a range of climate values will be provided for each grid cell containing the selected crop in the specified region of interest (see [Climate data](#climate-data)).

## Dispersal panel
The features in this panel are used to define spatial relationships among grid cells. Dispersal is incorporated as a weighting factor called the 'Connectivity' that is used to modify the projected values from your risk model. It is a single number ranging from 0 to 1 that characterises dispersal among all crop species cells in the entire landscape. More specifically, it describes the overall probability that a mobile agent dispersed from any crop species cell will land on the same or any other cell of that species. For those who are interested in how this is calculated, see the 'Host connectivity' section in the Appendix of [Skelsey et al. 2013](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0075892).

### Choose the type of dispersal
To change the dispersal function use the 'Dispersal' knob:  Fat = fat-tailed (square-root negative exponential kernel), Thin = thin-tailed (negative exponential kernel), Gauss = Gaussian kernel. These three kernels are all derived from the exponential-power distribution and all have a different shape (see [Skelsey et al. 2013](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0075892) for a thorough explanation). Fat-tailed kernels are often used for processes that operate at broad spatial scales, such as long-distance dispersal by wind, whereas thin-tailed kernels are often used for processes that operate at fine spatial scales, such as splash- or insect-dispersal. The kernel is parameterized using the 'Mdd' numeric field = mean dispersal distance. Enter a number for the average distance that a mobile agent can disperse - this is in units of 12 km grid cells, therefore entering 1 will give an mdd of 12 km, 2 gives an mdd of 24 km etc. 1D slice through your dispersal kernel (i.e. a dispersal gradient) is automatically displayed in the 'Dispersal gradient' plot pane. The connectivity of the landscape is automatically computed and displayed in the 'connectivity' field. All projected values from your risk model will be multiplied by this value. 

### Set to no dispersal
If you do not want to incorporate spatial relationships among cells, set mdd = 0. Then the 'Connectivity' field will display 'NA' (not applicable). This is the default setting when you open the app. 

## Plots panel

### Making maps
Click the 'Plot' button in the 'Map' panel. Switch between a map of the selected climate variable and a map of the selected crop distribution using the 'Plot' list box. 

### Plotting projected values
Once your future scenario has been defined, click the 'Plot' button in the 'Projections' panel. This will produce a boxplot of projected values for that scenario. Each boxplot is a 'super-ensemble' of projected values from your model (using 12 potential future climate values x *n* selected grid cells). All projected values are presented as a percentage change relative to the results produced by your model and selections using the baseline climate (1981-2000). Boxes extend from the first to the third quartile, medians are marked in each box, and whiskers extend to 1.5 times the interquartile range. You can display multiple boxplots (i.e. multiple scenarios, such as a different season of the year / decade / risk model / crop distribution, etc.) together in the plot pane. Click the 'Clear' button to clear the plot pane.   

### Saving results
Click the 'Save' button to save your results. This will open up a file save dialog box, where you can name your results file and save to any location. Note that only the results for the boxplots displayed in the plot pane will be saved - if you click the 'Clear' button then these results will be lost. Your results will be saved to a CSV file, and the projected values for each scenario you define (each boxplot) will be stored in a separate column. Each column will contain 87,360 values (65 x 112 cells x 12 potential climates). Only a small proporition of these values will be numerical, pertaining to the grid cells you selected for your projections. The rest will be NaN (not a number), representing the grid cells (land and sea) not selected. 

