# DALI Data Challenge 22W
### Jack Gnibus



## Data Challenge Part 1

The following visualizations were created with Tableau using data from WIID from 2000-2017. The visualizations intend to 
paint a picture of world income inequality in the 21st century.


### Visualization 1: Global Gini Coefficients

![Global Gini Coefficients](/visualization_images/global_gini_coefficients.png)

The above visualization illustrates the average Gini coefficient of individual countries from 2000-2017. The Gini coefficient 
is a measure of the distribution of income across a population. A higher Gini coefficient indicates more income inequality.
I chose to represent the Gini coefficients on a world map because I wanted to illustrate such a measure of income distribution 
on a country-by-country basis. The world map also allows for visual comparisons between countries: for instance, it is evident 
that South Africa, based on the WIID, has the highest level income inequality in the world. The world map also lends itself 
well to identifying broader regional trends in income distribution. Displaying the same information on, for instance, a bar 
chart, would make it more difficult to analyze said regional trends.

I chose one color gradient for the world map visualization to make it easier for viewers to determine what countries have higher
Gini coefficients than others. Lighter shades correspond to smaller Gini coefficients, and darker shades correspond to larger Gini coefficients.
This makes it easier for viewers to identify countries with greater income inequality than it would be on multicolored world map.

When analyzing the WIID, I found variability in Gini coefficient data based on the `areacovr` column, which the WIID defines 
to be land area included in sample surveys. `areacovr` switches between `Urban`, `Rural`, and `All`. Not all countries included 
Gini coefficients for urban and rural regions, instead opting for Gini values strictly describing the entire country. 
Because I am measuring the Gini coefficient for the entire country, and not distinguishing between parts 
of an individual country, I filtered the dataset such that only the Gini coefficients for the entire population is averaged 
over the time period. This helps remove extraneous data that is not measuring what I am intending to portray.


### Visualization 2: Quintiles by Subregion

![Quintiles by Subregion](/visualization_images/quintiles_subregion.png)

This visualization demonstrates the quintile groups for each subregion of the world. The quintile groups represent the share
of total income held by each fifth of the population. Quintiles decrease from left to right, with the richest quintile (`Q5`)
on the very left, and the poorest quintile (`Q1`) on the very right. The percentage of income each quintile possesses is averaged
over the time period and by subregion of the world (which composes each row of the bar graph). The resulting graph paints 
a picture of income inequality by subregion in the 21st century: subregions where the top fifth of the population has a greater
percentage of income than the top fifth of the population has in other subregions have more income inequality than their counterparts.

Because each quintile represents the percentage of income a fixed portion of the population has, I chose to visualize this 
data on a bar chart. This is because the percentage of income must sum to 100%, and thus a bar chart allows for easy 
comparisons of income percentages for respective subpopulations between subregions. I wanted to include quintile data 
for each subregion so viewers can more accurately identify regions of the world with higher levels of income inequality.

The colors between each quintile help viewers quickly distinguish between quintiles of an indvidual country, as well as compare
quintile income percentages across subregions by comparing the size of bars that have the same color. 

I also chose to filter data based on `areacovr` to include quintile data only collected for the entire country for the same
reason as I did in Visualization 1.


### Visualization 3: Average GDP by Subregion

![Average GDP by Subregion](/visualization_images/avg_gdp_subregion.png)

This visualization demonstrates the average GDP for each subregion of the world over the 21st century. GDP per capita is a measure of how wealthy
a nation is relative to the size of its population, as it captures the average economic production of each citizen. Extrapolating 
this to subregions, this visualization represents the relative production of each subregion of the world. WIID defines 
its GDP values as GDP converted to 2017 USD per capita - thus, the data comes preadjusted for currency and country population. 
From there, I averaged GDP values over the time period and countries within a given subregion to arrive at an average GDP per 
subregion. Larger squares indicates a higher GDP, which translates to a subregion with more production per person.

I chose to represent this data on a packed rectangle chart to indicate the relative magnitudes of subregion's GDPs in a visually 
appealing way. I also included the average GDP values in each rectangle to provide a more empirical metric of comparison 
between subregions, as two distinct squares do not necessarily have the same width (as they would on a vertical bar chart).
This allows viewers to identify subregions that have more economic production than others. 

The intention of this graph is to demonstrate GDP differences across regions. Although it does not offer analysis of income
inequality within subregions, it does show income inequality between subregions. For instance, it is clear from the size of 
the rectangles that Western Europe has a significantly higher GDP per capita than Western Africa, which demonstrates income
inequality between those two regions of the world.


### Visualization 4: Average Median Income by Subregion

![Average Median Income by Subregion](/visualization_images/avg_med_income_subregion.png)

This visualization shows the average median income (converted to USD) for each subregion of the world over the 21st century.
I wanted to include this metric to show income inequality for the median person across subregions. Discrepancies in average
median income across subregions represent income inequality between said subregions.

This graph is similar to Visualization 3 in what it effectively represents. There is a rough correlation between average GDP 
per capita and average median income amongst subregions. However, when analyzing the relative sizes, the data implies the 
median person in poorer subregions earns less than the median person in richer subregions relative to the economic 
production of said poorer subregion compared to the economic production of said richer subregion. This shows a greater level
of income inequality in subregions where this situation occurs. I understand that this would be more evident if both 
visualizations were displayed on the same type of graph, but wanted to provide some variety in the visualizations the sake 
of the data challenge.

I chose to represent this graph on a horizontal bar chart to make comparisons of average median income between subregions
easy for viewers. Because the height of the bar is constant, relative size of avergae median income is a function of 
proportional length between bars. I also chose to keep the color consistent across all bars, because the measurement is the same
for each bar and there are no distinguishing populations in an individual bar (as there were for the quintiles).


## Data Challenge Part 2


### Summary

For Part 2 of the challenge, I decided to make a model to predict whether someone will default on a loan.

Here is the link to the dataset I used: https://www.kaggle.com/rupakroy/credit-data

And a link to my model: https://www.kaggle.com/jgnibo/credit-data-model


### Model Selection and Metrics

I analyzed the dataset to help inform what model I should use. The dataset has three independent variables: `income`, `age`,
and `loan`. Income represents the income of a particular client, age represents that client's age, and loan represents the
loan amount that client is requesting.

These three variables are indicators of whether a particular client will default on their loan. I chose to use logistic 
regression because my target output boils down to a binary classification problem (whether someone will default or not). Either
they will default on their loan, or they will not default on their loan. I found that I could implement such a model with ease
using logistic regression, as whether someone will default on their loan is based on the three independent variables discussed
earlier.


### Assumptions

I'd also like to address the basic assumptions of my model. The first is that there is limited correlation between the independent variables
used as predictive measures for loan default status. I verified this assumption by looked at the standard correlation (Pearson) 
between the independent variables. From this, I found there was very little correlation between income, age, and loan amount, 
and thus decided to proceed with logistic regression.

I also assume that this sample size (initially 2000 entries, trimmed to 1972) is large enough to have predictive accuracy. Finally,
I assumed that the data entries are independent of each other.


### Basic Cleaning

Aside from selecting what algorithm to use, there was a tiny bit of work to be done on the data itself. I found that there
were a few entries without age information, and thus trimmed those from the dataset. The dataset also included an additional
column `clientid` that simply assigns each client a unique identifying number. I deleted that column from the dataset as well
so I would only be working with the independent variables that are predictive of default status.


### Outliers

With the dataset roughly cleaned, it was then time to look for outliers. The first outlier I encountered were three age values
less than 0. It is impossible to have negative age, so I removed these values from the dataset. I also checked the legal age
to get a loan, which turned out to be 18. The remaining age values were all greater than 18, with a mean of 40.93 and a max
of 63.97. I am no expert on loans but figured that these numbers sounded reasonable, as middle-aged people are probably taking
out the most loans and there are probably not that many people taking out loans as they get closer to retirement. Thus, I felt
comfortable with the outliers I had removed from the age data.

I then looked at the descriptive data for income. As mentioned before, I am no financial expert, but saw that the max income
of a client was $69,995.67. This seemed reasonable, as I figured people with higher incomes probably do not require as many loans.
Considering the max income is close to the average household income in the United States, I did not find any glaring upper 
outliers in the income data. The minimum income was $20,014.49, which roughly translates to the yearly salary of someone working
the minimum wage. Thus, I felt sufficient with the lower bound of the income data, as I figured banks would likely only give out
loans in the first place to employed individuals.

Finally, I looked at the loan data and found that there were 22 loans taken out under $100. Although none of these clients defaulted,
with a mean loan of $4443.24, I decided to remove loans under $100 from the dataset.


### Performance

The model has a predictive accuracy ranging from 90.6% to 94.7% over several tests (variability attributed to randomly selected 
subsets for training and testing). I used scikit-learn to help implement the logistic regression model and the splitting, 
training, and testing of the model. 





