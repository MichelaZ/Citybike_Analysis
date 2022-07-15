# Citibike Analysis
## Purpose
I created a data story using Tableau to present to potential investors in a bike share service. The project used data from a similar service in New York City, but the new company will be in Des Moines. Citibike subscribers pay a monthly fee for unlimited 45-minute classic bike rides, early access and discounts on ebikes and 3 free guest passes to share. Citibike customers pay per ride or per day to rent a bike. Users pick up a bike from a bike station. When they are done they leave the bike at another bike station. 

## Deliverable 1

1. Import dependencies and load data into Dataframe.
```
import pandas as pd
from datetime import datetime as dt
citibike_df = pd.read_csv('C:/Users/Sebba/Desktop/UMN Data bootcamp/Homework/Week 14 - Tableau/submission/201908-citibike-tripdata.csv')
citibike_df.head()
```
2. Use to_datetime to conver to datetime.
```
citibike_df['tripduration'] = pd.to_datetime(citibike_df['tripduration'],  unit='s', origin='unix')
```
3. export as CSV.
```
citibike_df.to_csv('C:/Users/Sebba/Desktop/UMN Data bootcamp/Homework/Week 14 - Tableau/submission/NYC_Citibike_Data.csv', index=False, header=True)
```

![CSV of NYC citibike data](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/NYC_Citibike_Data.png)

## Deliverable 2
Using the data from deliverable one and tableau public I created the following visualizattions for deliverable 2
![Tripdutation](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/Trip_Duration.png)
![Tripduration by Gender](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/Checkout_times_for_users_by_Gender.png)
![Trips per weekday per hour](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/Trips_by_Weekday_per_hour.png)
![number of trips by Weekday per hour by gender](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/Trips_by_Gender_by_Weekday_per_hour.png)
![trips by weekday by usertype and gender](https://github.com/MichelaZ/Citybike_Analysis/blob/main/submission/Trips_by_Weekday_per_hour.png)

## Deliverable 3
You can see my NYC Cikibike: August 2019 data story [here]( https://public.tableau.com/app/profile/michela.ziemer/viz/NYCCitibikeAugust2019/CitibikeUse?publish=yes).
### Who uses Citibike?
The number of trips taken by male users also more than doubles that of female users. This fits the general trend in the research on gender differences in cycling behavior. Some research suggests that this is due to women not feeling safe(Explaining gender difference in bicycling behavior). Users in their 40's and 20's make the most trips. They are working age and citibike doubles as both affordable transportation and a gym membership. Users born in 2000's make up the least number of users. This is probably because users must be 16 to use Citibike and subscriptions for minors must be purchased by a parent or guardian.

### When do Users Ride Citibikes?
Trips occur more during common commuting times and throughout the day on the weekends. Subscribers take the most trips 4:00PM to 7:00PM Monday through Friday. Customers take most trips on Saturday and Sunday. This indicates that subscribers tend to use bikes most for at least part of their daily commute and to get around on the weekends. Customers most likely tourist or locals who use a different commuting means normally. Users whose gender is unknown are more likely to be customers then subscribers. Usage times seems to be more correlated with usertype than gender. Older users tend to take less trips in the morning than younger users. This could be because younger people are more likely to be required to work overtime. Older users may be retired or have more flexibility in their commuting schedules than younger users.

### Tripduration:
The average trip duration is 13.7 minutes. Subscribers have shorter average trip duration (12.179 minutes) than customers (20.226 minutes). This could be because subscribers make more trips maybe their cycling fitness is better. It could also be that the use case leads to the longer duration. Female users tend to have longer trip duration (14.55 minutes) then men (12.487 minutes). Unknown gendered users trip length (19.73 minutes) is highly correlated with the trip length of customers. Users who are younger make more trips with shorter, while older users tend to take fewer, but longer trips. 

### Des Moines VS. NYC
The Citibike data is only part of the story. To prove to investors that Des Moines is a good place to invest in a bike share company you need to prove to them that you can get people to buy into cycling as a primary commuting method. Des Moines is only in the bronze tier on the League of American bicyclist’s biker friendly community ranking, while New York is a Silver ranked city. In Lawnstart’s list of “Best Biking Cities in America.” Des Moines Comes in 65th to New York City’s third place. 

These rankings are based on state and city public education, laws to protect cyclists on the road, bike lane counts, community engagement, etc. Cities with high community engagement tend to score high in access as well. While cities with Low engagement tend to score low in access and safety. Roads with more access are safer. Safer roads means more community engagement. 

Unlike Iowa City, the city in Iowa with the highest ranking in the League of American bicyclist’s biker friendly community ranking, Des Moines doesn’t have any one person or specific department dedicated to pedestrian and cycling traffic, so there is no one in city government to advocate for these issues. Generally city council officials who opposed to increasing the number of bike lanes  due to price and low utilization. Only 15% of arterial streets have bike lanes making commuting safely by bike difficult which leads to low community engagement.


### Recommendations:
- To attract subscribers partner with local Businesses. Bike rental apps can be marketed as good physical activity and a greener commuting method. Bike stations should be near large apartment complexes and partnering businesses.
- To attract customers partner with hotels or popular events as an affordable "way to get around." Bike stations should be near hotels and popular tourist areas.
- trips start from more substations then they end at. Substations where more trips end (business/tourist locations) should have more parking than substations where more trips start (residential areas).
-seniors or tourists during low traffic times may increase users during those times.
- Track the most used an lease used bikes. For the most used bikes wear and tear may accumulate more quickly. The least used bikes may be avoided by customers because there is an issue that needs to be resolved for the bike to be used.
- Track end station use . It may be good to move bikes from lower use areas to higher use areas to promote more even wear.
- Work with community/govornment to build infrastructure, promote bicycling events and education.

__References:__

*2022’s Best Biking Cities in the U.S.* Lawnsarter. https://www.lawnstarter.com/blog/studies/best-biking-cities/#rankings. May 25th 2022

Emond, C., Tang,W., & Handy, S.L. (2009). Explaining gender difference in bicycling behavior. *Transport. Res. Rec.: Journal of the Transportation Research Board*, 2125, 16–25.


Meinch, T. *Why Iowa isn't as bike friendly as you might think.* Des Moines Register. https://www.desmoinesregister.com/story/money/business/2015/09/10/iowa-des-moines-slipping-bike-friendly-trend/32286821/. September 10, 2015.

