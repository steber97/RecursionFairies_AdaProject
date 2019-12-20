# [Where to live in USA? A "good" developmental index as a tool to choose it!](https://steber97.github.io/)





## Abstract
It is always difficult to find the right place to live. Many aspects could influence our choice (prices, income, education, life expectancy...), and each person could give more importance to some aspects, and less to other.
There is already a Human Development Index, created by the UN to measure the quality of life based on different criteria ("Long and healthy life", "Knowledge", "A decent standard of living"). [1]
But this is a static index! You cannot give more importance to the features you really want to!
We would like to improve this index, and make it personalizable!
We looked for different data concerning the different aspects taken into account in HDI, referring to the 50 states of US. The goal is to create a map of USA where we can select the importance level to give to each of these aspects, in order to find the best place to live in USA according to our desires!

## Research questions
- Can we create a new index based on our desires and expectations?
- Are we able select the right datasets to implement this index?
- Are the selected features used to substitute the 3 areas of HDI meaningful? Is it really useful to generate such an index with this data?
- Do our index correspond to our expectancies? Are there some areas that are better than others?
- Changing the importance of our parameters, are there striking differences? It is possible to select places that are generally better than others?

## Datasets
- Life expectancy (csv to upload in the repository)
A dataset of the life expectancy in each county of USA and in different years.
- Personal Income (csv to upload in the repository)
A dataset of personal income per state. The population of each state is mentioned too. It will be useful to do our statistics!
- Institution details (csv to upload in the repository)
Number of students enrolled in each university.
- National university ranking (csv to upload in the repository)
- Crime dataset (http://archive.ics.uci.edu/ml/datasets/Communities+and+Crime)
Everything about crimes in US.
- Average price of high school and elementary school for each state(https://www.privateschoolreview.com/tuition-stats/private-school-cost-by-state)
- McDonald’s (https://eu.usatoday.com/story/money/business/2018/09/13/mcdonalds-states-most-stores/37748287/)
Number of McDonald's per state and adult obesity rate for each country, with other interesting informations.
- Homeless per state (https://www.usich.gov/tools-for-action/map/#fn[]=100&fn[]=200&fn[]=500&fn[]=800&fn[]=1100&all_types=true&homeless_rate=true&year=2018)
- US Adult Income Dataset (https://www.kaggle.com/johnolafenwa/us-census-data/download)
- US Rent Data (https://www.apartmentlist.com/rentonomics/rental-price-data/)
- Oil price (https://gasprices.aaa.com/state-gas-price-averages/)
- General data about the USA economy, health, diversity, education, houses (https://datausa.io/profile/geo/united-states#education)
- US Alcohol, Life expectancy and Health Statistics (http://www.healthdata.org/us-health/data-download)
We found some interesting datasets, we could not use them all (or add something else if needed!)

## A list of internal milestones up until project milestone 2
For each dataset, we will extract the data of interest. We will create different maps and statistics for each of these aspects, after recollecting all the information required. The idea is to "merge" the different aspects into an interactive index, in which you can select with sliders the amount of importance to attribute to each feature, in order to create an interactive map of which state is perfect for your desires!
Our work for milestone 2 will be divided in two parts:
- First two weeks: loading, cleaning datasets and extracting data of our interest
- Last two weeks: analysis on the extracted data, visualization of the results, preparation of our interactive index

## Questions for TAs
- Is the datasets list for the project odd? Are there too few, or too many datasets?
- Do you think the project is too ambitious, or too poor? For example, the final dataset will just have 50 rows: is it too little? We decided to focus only on USA as we found more easily the interesting datasets, and because differences in the states make our research interesting
- Do you know if there are some other datasets that we could use?

[1] http://hdr.undp.org/en/content/human-development-index-hdi


# Milestone 2 checklist: 

### Data cleaning and analysing :

Once we had all the data, our first task was to clean it. We came across a variety of challenges during this task:
- The first dilemme was to decide on which locations we were going to apply the prediction. USA is a big and complex country. It is composed of states, federal districts, territories, ... After discussion, we decided to apply our data analysis on all the 50 states and the District of Colombia to have more global results.
- The most frequent challenge was missing data. For example the state of Hawaii was missing in the rent dataset or life expectancy was missing for Maine and Wisconsin. We found all the missing data on internet, allowing to have a precise recovery (since otherwise we would have had to drop this features or approximate the missing values.
- Another challenge was to select meaningful information for our model. Since we had to predict the HDI for only 51 locations (50 states and 1 district), we decided to be quite selectif to avoid overfiting problems with our machine learning prediction.

Given the high number of datasets that we have analyzed, we decided to perform the data cleaning process in separate files, in order to avoid one single notebook with a huge amount of lines of code, all independent from each other.

The notebook that we have written in order to clean and analyze the datasets are:
- `crime.ipynb`: a crime dataset is analyzed, we hope to extract good insights on the quality of life given the number of crimes committed in all states
- `McDonalds.ipynb`: a dataset of alimentation quality (number of fast food restaurants per state, obesity rate, people eating unhealthy).
- `school_dataset.ipynb`: a dataset with tuition fees of private schools and elementary schools. 
- `homelessData.ipynb`: We extracted homeless people figure from 2007 to 2018.
- `rentData.ipynb`: We selected the rent price of 2018 for 4 types of rents: 1, 2, 3 and 4 bedrooms, and studios.
- `csv_datasets.ipynb`: we analyze and extract features related to University rankings, life expectancy and personal income.
- `diabetes_physical_activity_alcohol_obesity.ipynb` : We extract and analyse prevalence of physical activity, alcohol, diabetes and obesity.

### What comes next?

Now that we have all datasets cleaned and analyzed, we can further proceed in the realization of our project: firstly, we need to train a model which will enable us to predict the HDI index of every state of the USA, based on the dataset that we have created.

This task is going to pose some challenges: in fact, our dataset has many dimensions and a few samples. Therefore, there is going to be the risk of overfitting.

We can try to counter this effect by performing some dimensionality reduction algorithms like PCA, Factor Analysis or Independent Component Analysis.

As soon as we manage to reduce the dimension of our dataset, we can train the model using any regression technique like SVM or Ridge Regression.

Once we compute the weights for our model, then we can build our index by adjusting the weights of our model to personalize it to the users' needs. We will offer a visual representation of it using sliders, so that the user can adjust the weights in an intuitive manner.

Further, we may try to split our features into meaningful subsets (health, crime, education, monetary) in order to gauge their impact on our final HDI score. Moreover, we may try to investigate the relation among the above subsets and the actual features used to compute the UN HDI index (personal income, life expectancy and average years of education).

To conclude, a further improvement could be trying to test the robustness of our model: it means that, whenever we drop any column (for instance if it happens that any of the organizations computing our metrics fails), we are still able to learn a good enough predictor for the HDI. The fact that our dataset has so many correlated features means that probably we can manage the loss of some columns, without losing much accuracy.

# Milestone 3 checklist: 

### Data preprocessing:

As discussed, the features belong to 4 categories. So we splitted the dataset accordingly, applied normalization for some features (for example number of homeless people per 10'000 citizen seems more meaningful than the raw number of homeless), computed correlations between some features and other data analyse were applied.


### machine learning regression:

We were finally able to apply machine learning techniques to our data to see if a regressor would give a good prediction of the HDI with our features.\
We applied linear regression, ridge regression and SMR. For the 3 algorithms, we compared the performances of standard data or normalized data and with/without polynomial expansion. Then we applied the same algorithms but also applying PCA on the entire features or on the 4 precomputed classes (i.e. education, health, security and economy) separately. The results are shown in the `ADA_project_final_notebook.ipynb` file. The main conclusion of all this computation is that ridge regression with polynomial expansion is the most accurate regressor on the entire dataset and still close to the best when applied on fewer features.\
One of our goals was to be able to modify the HDI based on one of the 4 classes, allowing to have a personalised score for each state. For this, we take a weight vector for the above 4 classes and appropriately weigh the coefficients of the linear regression model for HDI to predict our new personalized HDI.

### website creation:

### Structure of the repo:

- `Data`: all the files we analysed
- `Pickles`: repository for all the pickles files
- `plotlySave`: repository for all the plotly files (as HTML)
- `ADA_project_final_notebook.ipynb`: ***principal notebook; all the analysis is in it***
- `crime.ipynb`: cleaning and analysing of crime features
- `csv_datasets.ipynb`: cleaning and analysing of csv table features
- `data_story_and_maps.ipynb`: 
- `DataAnalysis_Milestone3.ipynb`: 
- `diabetes_physical_activity_alcohol_obesity.ipynb`: cleaning and analysing of diabetes, physical activity, alcohol and obesity features
- `HDIOutputAndInputs.ipynb`: copy of `ADA_project_final_notebook.ipynb` to have interactive graphs
- `homelessData.ipynb`: cleaning and analysing of homeless features
- `Life_expectancy_alcohol_diabetes.ipynb`: cleaning and analysing of life expectancy, alcohol and diabetes features
- `LinearRidgeRegressionAndSVR.ipynb`: comparisons of various ML algorithms
- `McDonalds.ipynb`: cleaning and analysing of McDonalds features
- `Milestone2.ipynb`: notebook from milestone 2
- `rentData.ipynb`: cleaning and analysing of rent features
- `school_dataset.ipynb`: cleaning and analysing of school features
- `toHaveNormalData.ipynb`: to save the pickle file with all the features
- `README.md`: a README

### Goals:

1. Our first goal was to show the feasibility to predict the Human Development Index based on non-official parameters.\
This objective has been proved.\
2. Our second objectif was to be able to have a more personalized index.\
As shown on the website, we reached this objective, even if it can only be validated empirically.

### Contribution list:

- Angelo Sciullo: research of data related to HDI, data cleaning, analysis and preprocessing.
- Harshvardhan: research of data related to HDI, data cleaning and analysis. ML and weighted prediction implementation.
- Loris Pilotto: research of data related to HDI, data cleaning and analysis. ML implementation.
- Stefano Huber: research of data related to HDI, data cleaning and analysis. Creation of the data story website.




## You can find our data story on the USA Human Development Index [here](https://steber97.github.io/) !