# PyBer Analysis

# Overview
The purpose of this analysis is to view how data differs by city type and how those differences can be used by decision-makers at PyBer. Below you will find that in order to get this information and analyze it thoroughly, it will require `Python`, `Pandas` and `Motplotlib`. The endstate is to simply create and present a multiple line plot that shows the total weekly of the fares for each type of city. Before we can do that, there are some steps to take before the chart can be made. 

### Data Resources
This analysis was ran with `ride_data.csv` and `city_data.csv`

# Results
## Merge the Data Frames
First order of business is to combine the two data resources mentioned above. The common collumns between the two are `city`.  So we'll conduct a `left merge` using the `pd.merge` function and end up with the result below.

![Screen Shot 2022-07-15 at 01 24 25](https://user-images.githubusercontent.com/105962575/179164019-55d5c684-9f1f-4926-a58c-9f30ca461b47.png)

## Pyber Summary DataFrame 
Next is building out the Pyber's initial dataframe and printing the results. You will see how the three differnt city types are categorized as `Rural`, `Suburban`, and `Urban` types. To ensure the data is presentable, the data was then cleaned and formatted accordingly. 

![Screen Shot 2022-07-15 at 01 29 54](https://user-images.githubusercontent.com/105962575/179164804-792377a7-a088-4a04-904e-bd02b0c1bfd5.png)

Provided this information, it is no surprise that Urban city types had the most total rides above Suburban and Rural cities respectively. The more urban the city type the larger number of drivers, because demand is high. So it's no suprise that total fares for each city type align with the demand. What is interesting is the average fare per driver. In the city, the average fare per driver is significanly lower than those from the rural city type. This is a true measure of supply and demand. The more supply, the cheaper the fares and vice versa. So Rural drivers have a higher average fare per driver, but their demand is significanly lesser than that of both urban and suburban cities. 

## Total Weekly Fares by City
Now that we have the above mentioned dataset, we can dig a little deeper. Since we know what the data looks like for rides, drivers and city types, we'll now analyze this data to show what the fares look like from a weekly perspecitve. With this information we will create a `multiple line plot` to visualize the data. 

In order to view this data the merged data frame is read in. We create another dataframe use the `groupby()` function for each date. Additoinally, the use of the `sum` function was implemented on the fares where the indices are the city `type` and `date`. The output of that raw data looked like this. 

![Screen Shot 2022-07-15 at 01 46 33](https://user-images.githubusercontent.com/105962575/179167178-2a2b09a1-0622-48bc-bf43-bbde9994b3c1.png)

After cleaning up the datetime frames from above, a pivot table is created that breaks down `fare`, `date` and  `type` for the following dates: `'2019-01-01':'2019-04-29'`. A new dataframe is built of off the dataframe to using the `resample` function by week `W`, in order to get the fares for each week by date. 

![Screen Shot 2022-07-15 at 02 00 59](https://user-images.githubusercontent.com/105962575/179169625-d1de89c8-0d70-44fb-a600-1f83753f050a.png)

In order to create the plot, the resample dataframe function `df.plot` was used to incorporate the `y axis` and `x axis for `Fare` in USD and `Total Fare by City Type`. 

![fares_by_city_type](https://github.com/hastyjr/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)

## Last but not least...


![Screen Shot 2022-07-15 at 02 02 13](https://user-images.githubusercontent.com/105962575/179169847-af1a2826-f06b-4403-9ad1-e6ca4c929070.png)

There is a description of the differences in ride-sharing data among the different city types. Ride-sharing data include the total rides, total drivers, total fares, average fare per ride and driver, and total fare by city type

# Summary
There is a statement summarizing three business recommendations to the CEO for addressing any disparities among the city types.


