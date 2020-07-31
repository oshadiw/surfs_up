# surfs_up

## Purpose of Analysis
  
  An analysis of Oahu, Hawaii's seasonal weather data was conducted to determine key statistics during the winter and summer seasons. The data was taken from the hawaii.sqlite database and analyzsed using sqlalchemy in Jupyter Notebook. Weather data from the months of June and December (for all years and weather stations) were analyzed and the results are shown in the following report. 

## Analysis

  In order to view the month specifc data, a query was created to import the .sqlite database into jupyter notebook:
```
results = []
results = session.query(Measurement.date, Measurement.prcp, Measurement.tobs, Measurement.station).all()
print(results)
```
These values were then added to a data frame with the columns as 'date','precipitation','tobs', and 'station'. After the index of the data frame was set as the date, the df.loc method was used to separate the specific months in question. For example:
```
june_df=df.loc[df.index.month == 6]
```

  Then, the .describe() function was used to identify the summary statistics for each month.
  
  June Stats:

![June](https://github.com/oshadiw/surfs_up/blob/master/june_data.png)
  
  December Stats:

![Dec](https://github.com/oshadiw/surfs_up/blob/master/december_data.png)

## Results

### Precipitation

  In the month of June (summer season) the average rainfall was 0.136 inches, with a min of 0in, max of 4.43in and a standard deviation of 0.336in. In December (winter season) the average rainfall was 0.215 inches, with a min of 0in, max of 6.42in and a standard deviation of 0.541in. Although the average rainfall is fairly similar in both months, there are some days in December where the rainfall is mich higher than in June. 

### Temperature

  In June, the average temperature is 74.9 degrees. The max temp is 85, min temp is 64, with a standard deviation of 3.25 degrees. The average temperature in December is 71 degrees, with a max of 83, mine of 56 and a standard devitation of 3.74. 
