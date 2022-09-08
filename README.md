# Housing Rental Analysis for San Francisco

The purpose of this repository is to use data visualization skills, including aggregation, interactive visualizations, and geospatial analysis, to find properties in the San Francisco market that are viable investment opportunities.

## Technologies Installation Guide

Before running the application first install the following dependencies.

```python
pip install Jupyter lab
pip install pandas
```

## Usage 

Anable invester or users to visualize and analyze the real-estate data to make investment decisions.

 For the purpose our analysis SFO neighborhoods census data was used and following three steps were taken to prepare data for visualization.

## To Calculate and Plot the Housing Units per Year

 First part is to visualize the changes in housing market overtime by using
 
1. Use the groupby function to group the data by year. Aggregate the results by the mean of the groups.

2. Use the hvplot function to plot the housing_units_by_year DataFrame as a bar chart.

![Housing units](/Starter_Code/housing_units.png)

There increasing trend in housing market overtime but at a very slow pace. Around 0.51% increase in housing units every year.

## Calculate and Plot the Average Sale Prices per Square Foot and gross rent

 Next step is visualize the average sale price per square foot 

1. Group the data by year, and then average the results.

![gross rent](/Starter_Code/sale_price_gross_rent.png)

2. Create a new DataFrame named prices_square_foot_by_year by filtering out the “housing_units” column.

3. Use hvPlot to plot the prices_square_foot_by_year DataFrame as a line plot.

![sale price gross rent](/Starter_Code/sale_price_gross_rent_plot.png)

Both sale price square foot and gross income has incresing trend. But sale price have more flater slope and even have a dip in 2011 than rental income which is soring upward slope. 

## Compare the Average Sale Prices by Neighborhood

 Lastly, we will compare every neighborhood in San Fransico

1. Created a new DataFrame that groups the original DataFrame by year and neighborhood. Aggregate the results by the mean of the  groups.

2. Filter out the “housing_units” column to create a DataFrame that includes only the sale_price_sqr_foot and gross_rent averages per year.

3. Create an interactive line plot with hvPlot that visualizes both sale_price_sqr_foot and gross_rent. 

![neighborhood](/Starter_Code/neighborhood-plot.png)

4. Using hvPlot with GeoViews enabled, creating a points plot for the all_neighborhoods_df DataFrame. 

```python
# Create a plot to analyze neighborhood info
all_neighborhoods_df.hvplot.points(
    'Lon', 
    'Lat', 
    geo=True,
    scale=2,
    tiles='OSM',
    size= 'sale_price_sqr_foot',
    color="gross_rent",
    frame_width=700,
    frame_height=500,
   hover_cols=['Neighborhood'],
    title="San Francisco neighborhood map for avg sale price sqr Foot vs gross rent"
)
```

![geo neighborhood plot](/Starter_Code/geo_neighborhood_plot.png)

## Analysis Outcome

## What insights can you share with your company about the potential one-click, buy-and-rent strategy that they're pursuing? Do neighborhoods exist that you would suggest for investment, and why?

As per the analysis we have learned that over time from 2010 to 2016 rental income has increased from 1239 to 4390. There is an increasing trend across all neighborhoods. Some neighborhoods like Bayview heights,Excelsior, Visitacian valley, Silver terrace, westwood highlands and inner parkside have an average gross rent of more than $3000. Such an increasing trend sounds to be more lucrative option for investment but gross rent is just one aspect of analysis. We need to consider sale price per square foot too.

Whereas sale price per square foot over time have increased from $369.37 to 697.64. Over all it shows an upward slope but there are neighborhoods like Almo square, Anza Vista, Hayes Valley, Oceanview, Ingleside showing declining slope. Also, % increase in average sale price square foot trend is way less than increase in average gross rent which is pointing to interesting investment opportunities.

However, there is not much increase in housing units’ overtime hence there is condition of low inventory in the market. There are other factors which need to be considered such as median household income, taxes and other expenses to come up with the decision about potential one-click, buy and rent strategy.

There are neighborhoods which are worth investing such as:
Silver Terrace which is having an average gross rent of $3528 where as sale price per square foot is $170.29. 
Visitacion Valley with an average gross rent $3657 and average sale price sqaure foot is $301.470.

## Contributors

Amrita Prithiani- amritaprithiani@icloud.com