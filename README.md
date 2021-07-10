# The Masked Politic
![country](images/county_conf_by_pop.png)

**Project Contributors**:  Joseph Marx, Steven Yan

## Business Problem:
Political polling has become more difficult in recent years to accurately predict election outcomes in the United States. These elections have dramatic implications for society and its citizens, and broader implications for the global community. Being able to accurately predict upcoming election results is a vaulable tool that can be leveraged by activists, non-profits, politicians, and businesses alike. Finding new indicators of political sentiment, ones that can kept up to data and make political election models more accurate, would add significant value to political pollsters.

## Business Proposal:
This project has been structured as a pitch to political analysts to fund a large scale survey of mask wearing habits. We intend to show a strong correlation between mask wearing in a given county and how the people of that county voted in the 2020 presidential election. Since the dataset we have to work with is limited to a proportion of counties in the nation, we are unable to test our model on the whole country, but with more resources to gather county-level data, we may be able to build an even stronger model and predict voting habits with greater accuracy than with traditional modeling features.

## Data Collection:
There are two existing studies that have explored or are exploring mask wearing through self-reporting. New York Times in conjunction with an outside firm conducted a one-time study in July asking respondents about how likely they are to wear mask in public settings. Through their analysis, they calculated an estimate by county an estimate of the likelihood you would encounter someone wearing a mask in the next 5 encounters based on a survey conducted back in July:

<a href="https://public.tableau.com/views/NYTMask-WearingStudyVisualization/NYTMaskStudy?:language=en-US&:display_count=n&:origin=viz_share_link"><img src="images/Facebook Mask Study.png"></a>

While this dataset provides data on every county in the United States, this dataset only provides a snapshot at one very specific time of every county in the United States.  

There is an ongoing study being conducted by Carnegie Mellon and the same third-party firm delivered through the Facebook platform that captures county-level data about, among other things, mask-wearing behavior. It is worth realizing that one must be not only be willing to use the Facebook platform but also be willing to participate in a Facebook survey.  All models built therefrom have a built in assumption that the data weighted by the study facilitators appropriately accounts for this sampling method:

<a href="https://public.tableau.com/views/COVIDCastMaskWearingVisualization/COVIDCast?:language=en-US&:display_count=n&:origin=viz_share_link"><img src="images/COVIDCast.png"></a>

We looked into some databases that was able to address the different aspects of society that COVID has impacted, ranging from issues such as governance (i.e. declarations of state of emergencies and lockdowns), racial (i.e. racial disparities in cases and deaths, access to healthcare and testing), socio-economic (i.e. impact on food supply, impact on manfucturing, education, service, hospitality due to social distancing), and public health related (i.e. mask mandates, testing and contact tracing, vaccination rollout). 

In parallel to this we looked through election data, interested in ways the results could be modeled. It was hypothesized that there is a correlation between how a person votes and their compliance with CDC and local health ordinances for wearing masks and social distancing. It became the objective of this project to be able to model that relationship through combining the datasets we had been exploring.

## Modeling Process
After performing exploratory data analysis, the data we sourced required a bit of reconfiguring to appropriately merge, clean, and feature engineer. Data imputation was first attempted to see if a model could be built without collection more county-level data, but this proved inneffective since the available counties surveyed were both not randomly sampled and a minority of total counties.

To test our hypothesis, we modeled in parallel a dataset with features conventionally used to predict on voting habits, and then a dataset with those baseline features plus the mask compliance data from the Carnegie Mellon study. Several classication models were used, with evaluation metrics available to allow for comparison of performance.

## Analysis and next steps:
There is an improvement in model scoring metrics when including community mask habit features. The consistency of model improvement suggests that this data is worthwhile to gather for anyone interested in being able to model the 2020 election. With a dataset pipeline providing up-to-date data for each county in the country, a full model could be built and tested. If the pandemic is still active in 2022, the model could then be tested for predictive power in future elections as well.

## Folder Structure:
```
├── README.md                      <- the top-level README for reviewers of this project
├── EDA_notebook.ipynb             <- data cleaning, EDA, feature engineering/selection
├── modeling_notebook.ipynb        <- notebook containing all elements of model
├── data                           <- dataset files
├── summary_presentation.pdf       <- a pdf of the project presentation
└── images                         <- both sourced externally and generated from code
```

## Questions:
Joe Marx—jmarx@hash.fyi
- <a href='https://www.linkedin.com/in/joe-marx-260a64102/'>Joseph Marx</a>

Steven Yan—stevenyan@uchicago.edu
- <a href='https://www.linkedin.com/in/examsherpa/'>Steven Yan</a>

## Sources

Carnegie Mellon Study
Data from Delphi COVIDcast. Obtained via the Delphi Epidata API. <br>
https://cmu-delphi.github.io/delphi-epidata/api/covidcast.html

Data from US Department of Agriculture <br>
https://www.ers.usda.gov/data-products/rural-urban-continuum-codes/documentation/#referencedate

Data from Kaggle<br>
https://www.kaggle.com/etsc9287/2020-general-election-polls

Johns Hopkins COVID Database
Data from ArcGIS:<br>
https://opendata.arcgis.com/datasets/4cb598ae041348fb92270f102a6783cb_0.geojson

