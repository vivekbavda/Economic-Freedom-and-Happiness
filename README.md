# p5_FreedomHappiness

#### Introduction
The United States has been and will continue to be the leader of the world. Both domestically and internationally, our cornerstone value has been freedom. This has driven our policy and government for which we hold responsibility. Implied in this ideal of freedom is that it leads to happiness for us and the world. Given the importance of this assumption to all of us, SAVC Consulting has taken on a multipart project to study the link between happiness and freedom. In thinking about freedom, most people agree that personal freedom leads to happiness. Freedom of Speech, Religion, Association, and Press have few critics. It is economic freedom where the political divide in the U.S. severs the views of Americans. Economic Freedom is Part 1 of this project. Based on the Heritage Foundation’s data of American and international economic freedom and the World Happiness Report using Gallup Polling data, this study seeks to determine if one of our cornerstone values, economic freedom, leads to happiness.  Using Linear Regression(L1 and L2 Regularization) and Random Forest Regressors to model this data, we have used the correlation coefficient or R2 to measure how much of happiness is explained by economic freedom or the lack thereof.


#### Problem Statement
In order to identify and further explore societal/economic traits that correlate to happiness SACV Consulting will first identify which of the ML models listed above can explain the highest degree of variance through it's happiness predictions. This will allow for iterative feature engineering and fine-tuning of the model.


## Contents: 

- Background
- Outside Research
- Data Workflow:
    - Collection & Cleaning
    - Exploratory Data Analysis
    - Modeling
- Conclusions and Recommendations


### Background: 

As introduced above, as Americans, we elect the people who run the world. This responsibility should not be taken lightly. Not only do our leaders make policy choices that effect our happiness, the U.S. exports our values that go a long way towards effecting change around the world.  With this in mind SACV Consulting is conducting a multipart analysis on freedom. While most personal freedoms do not divide us, economic freedom choices do. The sources of our data have divergent views and represent two ways to look at the world. Our first source is the Heritage Foundation.

The Heritage Foundation would argue that <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*“For much of human history, most individuals have lacked economic freedom and opportunity, condemning them to poverty and deprivation. Today, we live in the most prosperous time in human history. Poverty, sicknesses, and ignorance are receding throughout the world, due in large part to the advance of economic freedom.”* [source](https://www.heritage.org/index/about)<br><br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*“Economic freedom is the fundamental right of every human to control his or her own labor and property. In an economically free society, individuals are free to work, produce, consume, and invest in any way they please. In economically free societies, governments allow labor, capital, and goods to move freely, and refrain from coercion or constraint of liberty beyond the extent necessary to protect and maintain liberty itself.“*[source](https://www.heritage.org/index/about)<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*“Economic freedom brings greater prosperity. The Index of Economic Freedom documents the positive relationship between economic freedom and a variety of positive social and economic goals. The ideals of economic freedom are strongly associated with healthier societies, cleaner environments, greater per capita wealth, human development, democracy, and poverty elimination.“*[source](https://www.heritage.org/index/about).<br>

In contrast, the [Sustainable Development Solutions Network](https://www.unsdsn.org/), who publishes the World Happiness Report would argue that: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*“People are happier when they trust each other and their shared institutions, and care about the welfare of others. Such caring attitudes are then typically extended to cover those elsewhere in the world and in future generations. This trust also increases social and political support for actions to help secure the futures of those in other countries and future generations. Thus, actions required to achieve the longer-term sustainable development goals are more likely to be met in those countries that have higher levels of social and institutional trust…but these are the countries that already rank highest in the overall rankings of life evaluations, so it is not surprising that actual attainment of SDG(sustainable development goal) targets, and political support for those objectives, is especially high in the happiest countries.”* [source](https://worldhappiness.report/ed/2020/environments-for-happiness-an-overview/)

In assessing which attributes are most important, we have acquired the World Happiness Report Dataset, and the Heritage Foundation’s Index of freedom. As we have defined below, we have looked at several variables including:property rights, government integrity, tax burden, government spending, investment freedom,  fiscal health, business freedom, labor freedom, trade freedom,  financial freedom, monetary freedom, perceptions of corruption log_gdp_per_capita,  social support, healthy life expectancy at birth, generosity, and freedom to make life choices. We have identified the Life Ladder, the score for happiness around the world as our target. This score is based on a question that invites survey participants to imagine their current position on a ladder with steps numbered from 0 to 10, where the top represents the best possible and the bottom the worst possible life for themselves. The higher the score, the higher their happiness is indicated.

With this in mind, SACV Consulting has used several years of data from both sources.  The datasets in our repository have been cleaned and merged. We have attempted to analyze not just the U.S. but other countries around the world. Exploratory Data Analysis has been conducted to see initial links. Histograms on the variables have been conducted. Correlation Heatmaps have been developed to determine relationships with variables. Plots have been created. Since happiness is a continuous variable, we have determined that a regression models are our best estimators. After this was done, several iterations of Linear Regression, Lasso Linear Regression, Ridge Linear Regression, Random Forest Regressors, and a Neural Net Regressor have been used model this data. For Evaluation purposes, the correlation coefficient also known as R2 measured how much happiness ,the life ladder,  is explained by economic freedom and other factors. The closer to 1 suggests greater predictive power. The measure of significance is open as we are attempting to understand and learn. There is no preset perspective.  To be clear though, cross validation was also used to generate model based evaluation.


### Outside Research: 

As mentioned above, half of our data comes from the Heritage Foundation’s Index of Economic Freedom. To those who are unfamiliar with the Heritage Foundation, their mission is “to formulate and promote public policies based on the principles of free enterprise, limited government, individual freedom, traditional American values, and a strong national defense.” [source](https://www.heritage.org/about-heritage/mission)

The other portion of our data come from The World Happinesss Report. To those that are unfamiliar, “The World Happiness Report is a publication of the Sustainable Development Solutions Network, powered by data from the Gallup World Poll and Lloyd’s Register Foundation, who provided access to the World Risk Poll….

The Report is supported by The Ernesto Illy Foundation, illycaffè, Davines Group, The Blue Chip Foundation, The William, Jeff, and Jennifer Gross Family Foundation, The Happier Way Foundation, Indeed, and Unilever’s largest ice cream brand, Wall’s.[source](https://worldhappiness.report/ed/2020/) “The first seven reports were produced by the founding trio of co-editors assembled in Thimphu in July 2011 pursuant to the Bhutanese Resolution passed by the General Assembly in June 2011, that invited national governments to “give more importance to happiness and well-being in determining how to achieve and measure social and economic development.” The Thimphu meeting, chaired by Prime Minister Jigme Y. Thinley and Jeffrey D. Sachs, was called to plan for a United Nations High-Level Meeting on ‘Well-Being and Happiness: Defining a New Economic Paradigm’ held at the UN on April 2, 2012. The first World Happiness Report was prepared in support of that meeting, bringing together the available global data on national happiness and reviewing evidence from the emerging science of happiness.


## Workflow: 

### Data Dictionary
- for complete list of economic and happiness terms and definitions click [here](https://git.generalassemb.ly/campbel94/p5_FreedomHappiness/blob/master/documentation/data_dict.md).
### Collection & Cleaning
##### Data Sources
- Heritage Foundation's [Index of Economic Freedom](https://www.heritage.org/index/explore?view=by-region-country-year&u=637659387053201112) 2008-2020
    -  [Econ report methodology](https://www.heritage.org/index/pdf/2021/book/02_2021_IndexOfEconomicFreedom_METHODOLOGY.pdf)<br>
- World Happiness Report Data 2008-2020 ([Kaggle](https://www.kaggle.com/unsdsn/world-happiness))<br>
    - World Happiness Report [Site](https://worldhappiness.report/)<br>
    - [Helpful guide to Happiness columns](https://www.trackinghappiness.com/happiness-index-2018/)

For the sake of this exercise, and limitations on the World Happiness data available through Kaggle, our analysis utilizes data from 2015 - 2020. For both sources, the data was easily downloadable in CSV format. 

#### Importing / Cleaning:

After reading the two separate CSV files into Pandas dataframes, convert all column headers into snake casing for consistency, and confirming the 2008-2020 data within each of them, we began the process of merging and cleaning the data in one single frame. Knowing the two dataframes would be merged into one, we engineered a new column, `country_years` by concatenating the `country_name` and `year` columns. Merging the dataframes on this column ensured that only data with the appropriate and corresponding rows would be included in the new working dataframe (freedom_happiness_df).<br>
- The table below lists the country naming discrepancies between dataframes that could be accounted for by simply renaming:<br>


| Original  | Updated to  |
|----------|----------|
| 'Bangladesh ' | 'Bangladesh'  |
| 'The Gambia' | 'Gambia'  |
| 'Hong Kong S.A.R. of China' | 'Hong Kong'  |
| 'Kyrgyz Republic' | 'Kyrgyzstan' |
| 'Burma'|  'Myanmar' |
| 'Serbia '|  'Serbia' |
| 'Slovak Republic'| 'Slovakia'  |
| 'Swaziland'|  'Eswatini' |
| 'Taiwan Province of China'| 'Taiwan'  |
| "Côte d'Ivoire"| 'Ivory Coast'  |


- The two tables below list country names that were ultimately dropped during the merge due to inconsistencies between dataframes. You may notice these are primarily African, Caribbean or Oceania islands. Despite the fallout, our new combined dataframe still consists of 158 countries, spanning the six years.

<br><br>
Dropped due to naming discrepancies: <br>
| Country | 
|----------|
| 'Congo' |
| 'Any of the Guineas' |
| 'North Cyprus' |
| 'Palestinian Territories' |
| 'Somaliland region' |
| 'Dominica' |

<br><br>
Lacked corresponding economic freedom or hapiness data: <br>
| Country| 
|----------|
| 'Barbados' |
| 'Brunei Darussalam' |
| 'Verde' |
| 'Cabo Verde' |
| 'Eritrea' |
| 'Fiji' |
| 'Kiribati' |
| 'Liechtenstein' |
| 'Macau' |
| 'Micronesia' |
| 'North Korea' |
| 'Saint Lucia' |
| 'Saint Vincent and the Grenadines' |
| 'Samoa' |
| 'Seychelles' |
| 'Solomon Islands' |
| 'São Tomé and Príncipe' |
| 'The Bahamas' |
| 'Timor-Leste' |
| 'Tonga' |
| 'Vanuatu' |

After merging dataframes and dropping the inconsistent `country_years` rows, we ended up with 1,682 total rows of data across 158 different countries. Two columns in particular, `judicial_effectiveness` and `fiscal_health`, were missing more than half of their rows and were ultimately dropped. For the remaining missing row values, which ranged anywhere from 11-97 per column, we decided to impute rather than drop them.
#### Imputation Process
We evaluated the following imputation methods by writing a for loop that produced a MSE score for each:
- Mean
- Median
- Linear Regression
- Bayesian Ridge
- Decision Tree Regressor
- Extra Trees Regressor
- K Neighbors Regressor

While the differences between scores were nearly zero, the Extra Trees Regressor provided the smallest MSE at -0.301617. With our imputation method selected, we applied it to the rest of the dataframe, removing all null values, and moved on to initial EDA.

### Exploratory Data Analysis
We approached EDA with three goals in mind: general familiarization with the data and the `life_ladder` metric in particular, identify correlations between features, visualize outliers and summary stats pertaining to specific columns of interest.

###### Familiarization
- `life_ladder` score distribution
- Color coded ranking of countries by averaged `life_ladder` score<br>

###### Correlations
- Seaborn heat mapping of economic and world-happiness features in relation to `life_ladder`
- A variety of Matplotlib visualizations focused on the six highest correlated features
    - Vizualizations consisted of:
        - Scatter plots
        - Line plots
        - Bar Charts
        - Histograms
    - Interestingly, three of the six highest correlated features came from the Heritage report:
        - log_gdp_per_capita
        - healthy_life_expectancy_at_birth
        - social_support
        - **government_integrity** *(economic)*
        - **property_rights** *(economic)*
        - **business_freedom** *(economic)*

###### Feature-Specific Summary Stats
- With specific columns in mind we can utilize histograms, boxplots and violin plots to gain a paint a clearer picture of their distributions and outlier countries.

### Modeling
For the sake of baseline comparisons we train/test split the data and derived a R^2 score for each of the models listed below without any additional hyperparameters or fine-tuning, just default settings:

- Linear Regression
    - L1 regularization
    - L2 regularization
- Random Forest Regressor 

The Random Forest Regressor produced the highest R^2 score at 0.88, however it was also the only model with substantial overfitting. The training data R^2 score was 0.98.

In second place was the Linear Regression with Ridge Regularization. That model produced a R^2 score of 0.78. Even though this R^2 score is lower, it does offer simplicity and transparency into the weighted coefficients that makes it appealing for real-world application. 

With both of these scores in mind we continued to play around with Random Forest Hyperparameters and run Linear Regression with subsets of the total features. Scores Below:

| Model  | R<sup>2</sup> Score |
|----------|----------|
| Linear Regression (L1 Regulaization) |0.62|
| Linear Regression (L2 Regulaization) |0.78|
| Linear Regression (World Happiness Features) |0.75|
| Linear Regression (Heritage Features) |0.57|
| Random Forest |0.88|
| Random Forest (with hyperparameters applied) |0.84|


## Conclusions and Recommendations

We used four models. Linear Regression, Linear Regression with Lasso, Linear Regression with Ridge, and Random Forest Regressor. Each model has its strengths. Linear Regression is the easiest to explain. Each coefficient on the variable like the gdp per capita  is able to explain part of the variation in the dependent variable, which in this case is the `life_ladder` score.  This model is also less likely to overfit , and does not generalize well to new data in comparison to the Random Forest Regressor. Moreover, in terms of a political argument, using a simpler model would allow the information contained to be better explained. While Random Forest is a more powerful model, it can best be explained as a game of 20 questions in a decision tree and can be hard to explain. 

In terms of settling on a production ready model, the Random Forest Regressor did the best job of predicting happiness, especially on the train score.  While Random Forest models generally overfit data, which gives it trouble in generalizing to new data, the R<sup>2</sup> score on the test data was higher than all of our other models. We were able to explain around 86% of the variance in the model. It should also be noted that Linear Regression allowed us to identify several variables that showed greater importance in predicting happiness.







