# Communicate Data Findings
 
>> 2018 Bay Wheels Ride Data Exploration and Visualization
|| Ahmed Hefnawy


## Dataset

[Bay Wheels](https://en.wikipedia.org/wiki/Bay_Wheels) 
(formerly known as Ford GoBike) is a metropolitan public bike sharing scheme in the San Francisco Bay Area, California. Bay Wheels is the first localized and large-scale cycling transportation scheme to be deployed in California and the West Coast of the United States with almost 500,000 trips since its introduction in 2017 and with about 10,000 annual users as of January 2018. The dataset used for this exploratory analysis shall consist of [monthly individual trip data](https://www.lyft.com/bikes/bay-wheels/system-data) Also available in CSV format from January 2018 to December 2018, covering the greater San Francisco Bay area. [here](https://s3.amazonaws.com/baywheels-data/index.html).

______________________________________________________
##### ______Data wrangling process:

- fix multiple fields that are not in the correct dtype, i.e. `start_time`, `end_time` should be datetime type, `user_type` and `member_gender` should be categorical data type, etc

- add new columns for trip duration in minute, trip start date in yyyy-mm-dd format, trip start hour of the day, day of week and month
- add a new column calculating riders' age from 'member_birth_year'
- filter out outlier ages from visual examination of the member age distribution and statistical percentile
- cast 'member_birth_year' and 'member_age' to integer instead of float type
- cast 'start_dayofweek' to category dtype
- cast 'start_month' to category dtype for easy plotting
- filter out outlier trip records where the duration was very long

_____________________________________________________
## Summary of Findings

The number of trips peaked around 8-9 a.m. and 17-18 p.m. during the day, there were more workday trips (Mon-Fri) than weekend trips. Summar time was the most common season of the year, possibly due to the weather. Riding journeys tend to be shorter on Monday through Friday than on weekends. It implies a reasonably consistent and effective usage of the bike sharing scheme on regular working days, while a more relaxed, versatile use on weekends.

Many of the passengers were male subscribers who did not use the bike share on all the rides. Much of the participants were between 25 and 40 years of age, as the age grows older, the use of bicycles fell dramatically. While not a big difference, male riders appear to have shorter trips compared to female riders, both a smaller median and a shorter IQR. Riders who rented bikes Monday through Friday are marginally older than those who ride on weekends, which complements the work-by-travel use that has been found in some of the invariable exploration plots.

There's a lot more subscriber consumption than consumers in general. The riding habit/pattern ranges a great deal between subscribers and consumers. Subscribers use the bike sharing system to work together, but most trips were on working days (Mon-Fri) and particularly during rush hours (when they go to work in the morning and get off work in the afternoon), while customers prefer to ride for fun in the afternoon or early evenings on weekends. Subscriber consumption peaks on traditional rush hours as people go to work in the morning and get off work in the afternoon, which confirms their intent and aim of cycling. A similar trend has not been found among customers who appear to travel the most in the afternoon or early evening for a different purpose than the subscribers.

____________________________________________________
### Key Insights for Presentation

The exploration reveals various trends of use/habit between the two styles of riders. Subscribers use the device extensively on working days, i.e. Monday through Friday, though customers ride a lot on weekends, particularly in the afternoon. Most trips clustered around 8-9 a.m. and 17-18 p.m. on working days for subscribers, but consumers appear to use more in the late afternoon around 17 p.m. Monday to Friday. The efficient/short duration of usage for subscribers relates to their high concentration on peak hours from Monday to Friday, suggesting that the use is mainly for work journeys. The more calming and versatile trend of consumer use shows that they are making the most of the bike sharing scheme.te differently from the subscribers, heavily over weekends and in the afternoon, for city tour or leisure purpose probably.
