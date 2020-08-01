## CitiBike Data:Jan 2019 - Aug 2019

### Goal
Analyze CitiBike data between January and August 2019 for trends and build a [dashboard](https://public.tableau.com/profile/surabhi.sood3293#!/) using Tableau Public. 

### Data Cleaning
Before doing any visualizations, I downloaded data from [Citi Bike Data](https://www.citibikenyc.com/system-data) webpage for each month of 2019. I used union on Tableau to append monthly data get one file.I deleted rows with trip duration <= 90 seconds and the starting and ending stations were the same. This was done to weed out any instances of a faulty bike.

Then, trip duration was converted from seconds to minutes, which is personally easier to understand at first glance, and all trips over 24 hours (1440 minutes) dropped. Under CitiBike’s current pricing model, bikes can be used an unlimited amount of times (under the day passes and subscriptions) but in 30- or 45-minute intervals. Trips longer than that, are charged an extra $2.50 or $4.00 every 15 minutes. Therefore, all bikes that were not docked for over 24-hours were most likely stolen, and not legitimate rides. This was still a conservative assumption, as bike rides up to 24 hours would still cost the user between $232.50 and $376.

Next, I converted the gender column (which was originally numerically coded) into strings using a list comprehension, and added an extra column for ride id to uniquely identify each ride. Then, I calculated the distance for each trip, and the ages of each rider. Finally, I dropped all rows where riders were above the age of 90, assuming these were fake ages (some riders even gave ages over 130), and divided the riders into age bins. Like trip duration, I again made a conservative estimate, as it is unlikely that users in their 80s would be riding bikes in a large city.

I used MS Excel and python-pandas for my analysis.

### Analysis

My preliminary analysis showed me that while there are *117 end stations* there are only *53 start stations* which I depicted on the map using red squares. The sizes of these squares vary based on the *count of bikes* being ridden between the stations. Based on these *counts* we can clearly see that for the majority of CitiBike users (approx 31%) prefer GroveSt Path, Hamilton Park ,Sip Ave,Harborside and NewPort Path as the start and end station for their journey. The Bar plot confirms the same phenomenon.

Another interesting phenomenon is the growth of cutomers during the year 2019. It is clearly visible that the popularity of CitiBikes reach at its peak during july, august and september and comes down in the consecutive months. I strongly believe that this has a strong correlation with the weather conditions. However, to further confirm this theory I will have to check on previous years as well.

Furthermore, my analysis focused on user types (customer or subscriber).Annual subscribers make up over 90% of total riders. An interesting phenomenon takes place if we track the growth between customer/subscriber at the peak business month,September to the start of year-January. We see higher growth rate in customers (1803%) than subscribers(219%).I strongly feel that this happened due to aix of conditions like weather,tourists and holidays. To test this theory we will have to look at other years data.

Further analysis on age demographic reveals that CitiBike is more popular between the age-group of 30-35! Looks like CitiBike is also popular amongst the age group of 51.However a large population in this age group hasnt identified their Gender.The reason remains a mystery!!

Interestingly, the higher average of trip duration was found in age group of 18-22 alongwith the elderly's of specific age of 51 and 72! This could be an intereting hidden trend about fitness! 



