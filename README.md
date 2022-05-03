# US-traffic-fatalities
This project analyzes the US fatal traffic accident data obtained from the National Highway Traffic Safety Administration (NHTSA), specifically from the Fatality Analysis Reporting System ([FARS](https://www.nhtsa.gov/file-downloads?p=nhtsa/downloads/FARS/)).

The original [FARS user manual](https://crashstats.nhtsa.dot.gov/Api/Public/ViewPublication/813254) contain the full set of data element definitions and keys. I curated only the relevent definitions and codes for our dataset in this data description file [here](https://github.com/jessicasyau/US-traffic-fatalities/blob/db57961853729978feb385b5c7aed729ac4afa44/description_fields/0.%20Data_descriptions.md).

## Exploratory Analysis of a Specific Year's Data
Here is a data visualization of the 2019 fatal traffic data with a few quick insights. Click on the image to view the interactive version in Tableau Public.

<a href="https://public.tableau.com/views/USFatalTrafficAccidents/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link">![](tableau.jpg)</a>

## Analysis of Fatal Traffic Accident Data From 2000 to 2020
The code for this analysis is documented in this [Jupyter notebook](https://github.com/jessicasyau/US-traffic-fatalities/blob/9dcc3e60dd595c1cdaf236ecdb74c9696da9f0f9/us-fatal-traffic-accidents.ipynb).

We started by exploring if the following factors correlated with the number of fatal traffic accidents.

### Day of the Week
![Fatal traffic accident distribution by the day of the week](/assets/dayweek_trend.jpg)

It's clear that there is a weekly seasonality for the number of fatal traffic accidents. The number of fatal accidents that occur on weekends (DAY_WEEK codes of 1 and 7) appears to be around 30% higher than the number of fatal accidents that occur on weekdays, especially between Monday and Thursday (DAY_WEEK codes of 2-5). The number of fatal traffic accidents also seems to be higher on Fridays compared to other weekdays. This trend holds true for all years from 2000 to 2020. A possible explanation of this trend could be that drivers are more careless on weekends because their routes and driving habits are different than the way they routinely drive on weekdays. However, we would have to consider the traffice density and pattern for weekdays compared to weekends.

Let's further investigate this trend by analyzing the time distribution of fatal accidents segmented into weekdays and weekends.

**Time - Weekdays**
![Fatal traffic accident distribution by weekday hour](/assets/weekday_hour_trend.jpg)

We see that the distribution of fatal accidents across the different times of the day on weekdays (measured in hours) is quite uniform across all years from 2000 to 2020. Most accidents occur between 3pm-10pm, whith some peaks from 3pm-4pm, 5pm-6pm, and 6pm-7pm. There are also peaks from 6-8am and from 2-3am. A possible explanation for this trend is that these peaks somewhat correlate to rush-hour traffic.

**Time - Weekends**
![Fatal traffic accident distribution by weekend hour](/assets/weekend_hour_trend.jpg)

There is a peak from 2am-3am. There is also a steady increase from 10am to 6pm, then it stays pretty steady after that.

In conclusion, the time of day does seem to correlate with the number of accidents.

### Lighting Condition
![Fatal traffic accident and lighting condition](/assets/lighting_trend.jpg)

The majority of accidents seem to have occured during daylight (LGT_COND code of 1), followed by Dark or not lighted (code of 2), then Dark but lighted (code of 3), then Dusk (code=5) and Dawn (code=4). This is surprising since intuitively we may predict that fewer accidents would occur during daylight. However, this pattern may be influenced by the time most cars are on the road. For example, perhaps most people drive during daylight, so the proportion of accidents that occur during daylight would be higher. Further investigation is required.

### Weather
![Fatal traffic accident vs Weather](/assets/weather_trend.jpg)

There appears to be a relationship between weather and accident -- the majority of fatal accidents occured on clear days (WEATHER code of 1), followed by cloud (code = 10), rain (code = 2), snow (code = 4), and fog or smoke (code = 5). Again, this is surprising since intuitively we may predict that fewer accidents would occur when the weather condition is clear, and more accidents would occur when the conditions are poor. However, the correlation between clear weather and accidents may be due to the high frequency of clear weather days. Further investigation is required.

### State
![Fatal traffic accident state trend](/assets/state_trend.jpg)

We see that the distribution of fatal traffic accidents by state is quite uniform from the year 2000 to 2020. This would make sense as long as the fluctuation in state population is uniform across most states as well. Further investigation is required.

### First Harmful Event
![Fatal traffic accident and first damage/injury producing event](/assets/harm_trend.jpg)

The most common first injury or damage producing events are:

- motor vehicle in transport (code: 12)
- pedestrian (code: 8)
- rollover/overturn (code: 1)
- tree (code: 42)
- curb (code: 33)
- ditch (code: 34)
- utility/light pole (code: 30)
- guardrail face (code: 24)
- pedalcyclist (code: 9)
- embankment (code: 35)

**Clarification**: these are the things that the vehicle first came into contact with in the accident. These things did not necessarily cause the accident.

Although there may appear to be a pattern here, further investigation is required to determine if the availability of each thing on the HARM_EV list contributes to the frequency we see here

## Accident Prediction
This [Jupyter notebook](https://github.com/jessicasyau/US-traffic-fatalities/blob/1e1e22f8878331fa0153b7f131cbfc181dbf06c3/us-traff-predict.ipynb) doocuments a model that predicts the total number of US fatal traffic accidents by day. This is a basic model that only takes into account the seasonality of traffic accidents by day of the year and day of the week, using 1 Fourier feature pair.

![traffic prediction](/asset/traffic_pred.jpg)

We can greatly improve this model by considering more input features based on the trends we observed above, such as day of the week, time of the day, state, lighting condition (perhaps we can combine this with time of the day), and weather condition.


## Further Questions to Investigate
- Which states have more accidents per capita?
- What's the relationship between drinking and traffic accidents? which states have the most drunk-driver-caused accidents as a percent of all accidents?
- What's the relationship between road type and accidents?
- What's the break-down of accident types?
