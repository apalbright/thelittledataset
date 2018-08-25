---
title: 'The Rise of the New Kind of Cabbie'
author: 'A Comparison of Uber and Taxi Drivers'
date: '2015-03-30'
slug: the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers
categories:
  - bar charts
  - stacked bar charts
tags:
  - age
  - comparisons
  - data viz
  - demographics
  - gender
  - ggplot2
  - R
  - race
  - taxi
  - uber
  - ride share
  - apps
---

# Intro

One day back in the early 2000's, I commandeered one of my mom's many spiral notebooks. I'd carry the notebook all around Manhattan, allowing it to accompany me everywhere from pizza parlors to playgrounds, while the notebook waited eagerly for my parents to hail a taxicab so it could fulfill its eventual purpose. Once in a cab, after clicking my seat belt into place (of course!), I'd pull out the notebook in order to develop one of my very first spreadsheets. [Not the electronic kind, the paper kind.](https://www.npr.org/sections/money/2015/02/25/389027988/episode-606-spreadsheets) I made one column for the date of the cab ride, another for the driver's medallion number (5J31, 3A37, 7P89, etc.) and one last one for the driver's full name--both the name and number were always readily visible, pressed between two slabs of Plexiglas that intentionally separate the back from the front seat. Taxi drivers always seemed a little nervous when they noticed I was taking down their information--unsure of whether this 8-year-old was planning on calling in a complaint about them to the Taxi and Limousine Commission. I wasn't planning on it.

Instead, I collected this information in order to discover if I would ever ride in the same cab twice...which I eventually did! On the day that I collected duplicate entries in the second and third columns, I felt an emotional connection to this notebook as it contained a time series of yellow cab rides that ran in parallel with my own development as a tiny human.^[Or maybe I just felt emotional because only children can be desperate for friendship, even when it’s friendship with a notebook.] After pages and pages of observations, collected over the years using writing implements ranging from dull pencils to thick Sharpies, I never would have thought that one day yellow cabs would be eclipsed by something else...

# Something else

However, today in 2015, according to Taxi and Limousine Commission data, there are officially [more Uber cars in New York City than yellow cabs](http://nypost.com/2015/03/17/more-uber-cars-than-yellow-taxis-on-the-road-in-nyc/)! This is incredible not just because of the speed of Uber's growth but also since riding with Uber and other similar car services (Lyft, Sidecar) is a vastly different experience than riding in a yellow cab. Never in my pre-Uber life did I think of sitting shotgun. Nor did I consider starting a conversation with the driver. (I most definitely did not tell anyone my name or where I went to school.) Never did my taxi driver need to use an iPhone to get me to my destination. But, most evident to me is the distinction between the identities of the two sets of drivers. It is undoubtedly obvious that compared to traditional cab service drivers, Uber drivers are **younger, whiter, more female, and more part-time**. Though I have continuously noted these distinctions since growing accustomed to Uber this past summer, I did not think that there was data for illustrating these distinctions quantitatively. However, I recently came across the paper ["An Analysis of the Labor Market for Uber’s Driver-Partners in the United States,"](https://irs.princeton.edu/sites/irs/files/An%20Analysis%20of%20the%20Labor%20Market%20for%20Uber%E2%80%99s%20Driver-Partners%20in%20the%20United%20States%20587.pdf) written by (Economists!) Jonathan Hall and Alan Krueger. The paper supplies tables that summarize characteristics of both Uber drivers and their conventional taxi driver/chauffeur counterparts. This allows for **an exercise in visually depicting the differences between the two opposing sets of drivers—allowing us to then accurately define the characteristics of a new kind of cabbie.**

# The rise of the younger cabbie

The figure below illustrates that Uber drivers are noticeably younger than their taxi counterparts.^[From here on, when I discuss taxis I am also implicitly including chauffeurs. If you'd like to learn more about the source of the data and the collection methodology, refer directly to the [paper](https://irs.princeton.edu/sites/irs/files/An%20Analysis%20of%20the%20Labor%20Market%20for%20Uber%E2%80%99s%20Driver-Partners%20in%20the%20United%20States%20587.pdf).] 

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/age2.png)

For one, the age range including the highest percentage of Uber drivers is the 30-39 range (with 30.1% of drivers) while the range including the highest percentage of taxi drivers is the 50-64 range (with 36.6% of drivers). While about 19.1% of Uber drivers are under 30, only about 8.5% of taxi drivers are this young. Similarly, while only 24.5% of Uber drivers are over 50, 44.3% of taxi drivers are over this threshold. This difference in age is not very surprising given that Uber is a technological innovation and, therefore, participation is skewed to younger individuals.

# The rise of the more highly educated cabbie

The figure illustrates that Uber drivers, on the whole, are more highly educated than their taxi counterparts.

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/educ2.png)

While only 12.2% of Uber drivers do not possess a level of education beyond high school completion, the majority of taxi drivers (52.5%) fall into this category. The percentage of taxi drivers with at least a college degree is a mere 18.8%, but the percentage of Uber drivers with at least a college degree is 47.7%, which is even higher than that percentage for all workers, 41.1%. Thus, Uber’s rise has created a new class of drivers whose higher education level is superior to that of the overall workforce. (Though it is worth noting that the overall workforce boasts a higher percentage of individuals with postgraduate degrees than does Uber--16% to 10.8%.)

# The rise of the whiter cabbie

On the topic of race, conventional taxis boast higher percentages of all non-white racial groups except for the "Other Non-Hispanic" group, which is 3.9 percentage points higher among the Uber population.

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/race2.png)

The most represented race among taxi drivers is black, while the most represented race among Uber drivers is white. 19.5% of Uber drivers are black while 31.6% of taxi drivers are black, and 40.3% of Uber drivers are white while 26.2% of taxi drivers are white.^[I would be curious to compare the racial breakdown of Uber's drivers to that of Lyft and Sidecar's drivers as I suspect the other two might not have populations that are as white (simply based on my own small and insufficient sample size).]

# The rise of the female cabbie

It has been [previously documented](https://www.theatlantic.com/business/archive/2014/08/how-uber-helps-women-break-into-the-taxi-industry/376127/) how Uber has helped women begin to "break into" the taxi industry. While [only 1% of NYC yellow cab drivers are women](http://www.nyc.gov/html/tlc/downloads/pdf/2014_taxicab_fact_book.pdf) and 8% of taxis (and chauffeurs) as a whole are women, an impressive 14% of Uber drivers are women--a percentage that is likely only possible in the driving industry due to the safety that Uber provides via the information on its riders.

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/gender4.png)

# The rise of the very-part-time cabbie

A whopping 51% of Uber drivers drive a mere 1-15 hours per week though only 4% of taxis do so.

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/hours2.png)

This distinction in driving times between the two sets of drivers makes it clear that Uber drivers are more likely to be supplementing other sources of income with Uber work, while taxi drivers are more likely to be working as a driver full-time (81% of taxis drive more than 35 hours a week on average, but only 19% of Uber drivers do so). In short, it is very clear that Uber drivers treat driving as more of a part-time commitment than do traditional taxi drivers.

# Uber by the cities

As a bonus, beyond profiling the demographic and behavioral differences between the two classes of drivers, I present some information about how Uber drivers differ city by city. While this type of comparison could also be extremely interesting for demographic data (gender, race, etc.), hours worked and earnings are the only available pieces of information profiled by city in Hall and Krueger (2015).

## Uber by the cities: hours

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/city.png)

New York is the city that possesses the least part-time uberX drivers.^[This data is only looking at hours worked for uberX drivers in October 2014.] Only 42% work 1-15 hours while the percentage for the other cities ranges from 53-59%. Similarly, 23% of NYC Uber drivers work 35+ hours while the percentage for other cities ranges from 12-16%. Though these breakdowns are different for each of the six cities, the figure illustrates that Uber driving is treated pretty uniformly as a part-time gig throughout the country.

## Uber by the cities: earnings

Also in the report was a breakdown of median earnings per hour by city. An important caveat here is that these are gross pay numbers and, therefore, they do not take into account the costs of driving a Taxi or an Uber. If you'd like to read a quick critique of the paper’s statement that "the net hourly earnings of Uber’s driver-partners exceed the hourly wage of employed taxi drivers and chauffeurs, on average," read [this](https://www.huffingtonpost.com/2015/01/22/uber-drivers-pay-study_n_6527470.html). However, I will not join this discussion and instead focus only on gross pay numbers since costs are indeed unknown.

![](/post/the-rise-of-the-new-kind-of-cabbie-a-comparison-of-uber-and-taxi-drivers_files/earning_by_city.png)

According to the report's information, NYC Uber drivers take in the highest gross earnings per hour ($30.35), followed by SF drivers ($25.77). These are also the same two cities in which the traditional cabbies make the most, however while NYC taxi counterparts make a few dollars more per hour than those in other cities, the NYC Uber drivers make more than 10 dollars per hour more than Boston, Chicago, DC, and LA Uber drivers.

# You've reached your destination

There is no doubt that the modern taxi experience is different from the one that I once cataloged in my stout, spiral notebook. Sure, Uber drivers are younger than their conventional cabbie counterparts. They are more often female and more often white. They are more likely to talk to you and tell you about their other jobs or interests. But, the nature of the taxi industry is changing far beyond the scope of the drivers. In particular, information that was once unknown (who took a cab ride with whom and when?) to those not in possession of a taxi notebook is now readily accessible to companies like Uber. Now, this string of recorded Uber rides is just one element in an all-encompassing set of (technologically recorded) sequential occurrences that can at least partially sketch out a skeleton of our lived experiences...No pen or paper necessary.

---

# Code

The R notebook for replicating all visuals is available [here](http://rpubs.com/apalbright/uber-v-taxi). See full [github repo](https://github.com/apalbright/uber_taxi_new) for the data as well.^[Both updated 7-27-17.]

# Future work (all of which requires access to more data)

- Investigate whether certain age groups for Uber are dominated by a specific race, e.g. is the 18-39 group disproportionately white while the 40+ group is disproportionately non-white?
- Request data on gender/race breakdowns for Uber and Taxis by city
- Looking at the racial breakdowns for NYC would be particularly interesting since the NYC breakdown is likely very different from that of cabbies throughout the rest of the country (this data is not available in the Taxicab Fact Book)
- Compare characteristics by ride-sharing service: Uber, Lyft, and Sidecar
- Investigate distribution of types of cars driven by Uber, Lyft, and Sidecar (Toyota, Honda, etc.)