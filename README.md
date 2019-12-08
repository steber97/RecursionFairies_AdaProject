# Where to live in USA? A "good" developmental index as a tool to choose it!

# Abstract
It is always difficult to find the right place to live. Many aspects could influence our choice (prices, income, education, life expectancy...), and each person could give more importance to some aspects, and less to other.
There is already a Human Development Index, created by the UN to measure the quality of life based on different criteria ("Long and healthy life", "Knowledge", "A decent standard of living"). [1]
But this is a static index! You cannot give more importance to the features you really want to!
We would like to improve this index, and make it personalizable!
We looked for different data concerning the different aspects taken into account in HDI, referring to the 50 states of US. The goal is to create a map of USA where we can select the importance level to give to each of these aspects, in order to find the best place to live in USA according to our desires!

# Research questions
- Can we create a new index based on our desires and expectations?
- Are we able select the right datasets to implement this index?
- Are the selected features used to substitute the 3 areas of HDI meaningful? Is it really useful to generate such an index with this data?
- Do our index correspond to our expectancies? Are there some areas that are better than others?
- Changing the importance of our parameters, are there striking differences? It is possible to select places that are generally better than others?

# Datasets
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

# A list of internal milestones up until project milestone 2
For each dataset, we will extract the data of interest. We will create different maps and statistics for each of these aspects, after recollecting all the information required. The idea is to "merge" the different aspects into an interactive index, in which you can select with sliders the amount of importance to attribute to each feature, in order to create an interactive map of which state is perfect for your desires!
Our work for milestone 2 will be divided in two parts:
- First two weeks: loading, cleaning datasets and extracting data of our interest
- Last two weeks: analysis on the extracted data, visualization of the results, preparation of our interactive index

# Questions for TAa
- Is the datasets list for the project odd? Are there too few, or too many datasets?
- Do you think the project is too ambitious, or too poor? For example, the final dataset will just have 50 rows: is it too little? We decided to focus only on USA as we found more easily the interesting datasets, and because differences in the states make our research interesting
- Do you know if there are some other datasets that we could use?

[1] http://hdr.undp.org/en/content/human-development-index-hdi
