# DALI Data Challenge 22W
### Jack Gnibus



## Data Challenge Part 1

The following visualizations were created with Tableau using data from WIID from 2000-2017. The visualizations intend to 
paint a picture of world income inequality in the 21st century.

what measuring
design
filters
explanation of topics?

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

