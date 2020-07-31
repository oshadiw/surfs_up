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

