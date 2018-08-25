---
title: "The Distribution of 'Sports Illustrated' Covers"
author: "The Bikini’d & The Not"
date: '2015-02-24'
slug: the-distribution-of-sports-illustrated-covers-the-bikini-d-the-not
categories:
  - stacked bar charts
tags:
  - athletes
  - data viz
  - gender
  - ggplot2
  - magazines
  - media
  - awards
  - sports
  - representation
---

# Intro

It's that time of year...the time of year when we are all reminded that the Swimsuit Issue of Sports Illustrated exists, a fact that made John Oliver's team recently ask, ["do people not understand they can now just type 'naked ladies' into the internet and see what Google throws at them?"](https://www.youtube.com/watch?v=l8QNDRbjong) On top of being reminded of the Swimsuit Issue's existence, I also recently became reminded of a question that has often popped into my head about Sports Illustrated: **How many female athletes are on the cover of this magazine as compared to the number of swimsuit-clad models?**

# Investigation

In order to address this question, I collected data from the online [SI Covers Archive](http://www.sicovers.com/) for years 2010-2014--a five year time span that consists of 487 covers. Specifically, I counted the number of covers featuring male athletes/coaches (448), other males (4), female athletes/coaches (13), female swimsuit models (7), other miscellaneous women (5), and covers that are featuring no individual or group of individuals in particular (10--these mostly consists of covers that are just text or [pictures of objects](http://cdn.bleacherreport.net/images_root/article/media_slots/photos/000/620/083/ND_original.jpg?1353440056)).^[Breaking the SI covers down into the aforementioned six categories was not always completely straightforward. For instance, there are a few dozen that feature both men and women... or both male athletes and crouching cheerleaders. In order to avoid complaints over underestimation, I count covers with at least one woman (athlete/coach, miscellaneous, swimsuit model) as a cover featuring a woman even if there are, say, three men in the picture but just one woman. However, if the cover is clearly featuring a male athlete but there a collage or background that includes a woman (both of these circumstances usually arise in the "March Madness" covers) I count that as a cover featuring a male athlete since the women who may appear in the background are either tiny or just a piece of a larger anonymous crowd--it would be a misrepresentation of the true nature of the cover to put these types of covers in the category of those featuring women.] Amazingly, the counts illustrate that **just 2.67% of all covers featured female athletes or coaches**. And, out of the 13 that did, only 3 covers featured female athletes of color, which happens to be less than the number of times Kate Upton graced the cover (once in 2012, twice in 2013, and once in 2014)!

In order to better comprehend what this means for women in sports, imagine that you were to pick randomly from all 25 magazines that featured women on the cover. Upon picking randomly, you would have a 28% chance the magazine would feature a swimsuit model, a 20% chance the magazine would feature a woman in the miscellaneous category, and just a 52% chance it would be featuring a female athlete or coach (which includes the minuscule 12% chance it features a female athlete of color)! Meanwhile, 99.12% of covers featuring males are male athletes/coaches.

# Visualization

See the following visualization to get more of a feeling for the aforementioned statistics and note the proximity between the frequency of female athlete covers and that of female swimsuit model covers.^[Data from SI Cover Archives 2010-2014. Visualization made using ggplot2 package in R.]

<img src="/post/the-distribution-of-sports-illustrated-covers-the-bikini-d-the-not_files/si1.png" alt=""/>

It is also interesting to note that if *SI* were to have required the same ratio of athletes/coaches to swimsuit models for men that held for women over this five year time period (7 swimsuit models for every 13 athlete/coach covers) there would have been **241** SI issues with male swimsuit models on the cover from 2010-2014. That is approximately 48 issues with male swimsuit models on the cover per year!

Despite the obviously tiny nature of the slice of *SI* covers that female athletes/coaches occupy, the unfortunate reality of the situation is that these numbers actually overestimate women's importance in the magazine since **only 9--or 1.85% of all the 487 covers of interest--featured a female athlete/coach as the primary or sole imageon the cover**. In other words, even though there are only a paltry 13 covers that feature female athletes/coaches, four of these still feature men in some regard. And while the magazine only managed to feature a female athlete or coach as the sole image 9 times, it managed to feature a female swimsuit model as the sole image 6 times (six swimsuit issue covers). In this case, if you were to pick randomly from the 15 covers of *SI* that feature women as the sole image, you would have a 40% chance of picking a swimsuit issue. 

# SI is not alone

However, it is important to note that *SI* is not unique in its lack of representation of female athletes. No, *SI* is just one of many microcosms within the larger sports universe--a universe in which female athletes were receiving around [1.6% of network news and ESPN Sportscenter airtime in 2009](https://www.motherjones.com/politics/2012/06/charts-womens-athletics-title-nine-ncaa/). Given the time that commercials take up, I would not be surprised if female models eating juicy, dripping hamburgers get more screen time than female athletes on these very sports channels. And, if that is true, then *Sports Illustrated* covers might actually possess a higher female athlete/coach to female model ratio compared to the major sports networks!

Make of that what you will... I'm off to eat a cheeseburger in a bikini.

---

# Update: New Data, New Graphs [July 2015]

*Sports Illustrated* just released 25 different covers to celebrate the World Cup-Winning US Women's Soccer Team--one for each of the 23 players, one for coach Jill Ellis, and one for a group of the teammates. In other words, Sports Illustrated just released 25 covers featuring female athletes/coaches, which is almost twice the number of such covers released over the past five years combined. (During the period 2010-2014, just 13 covers featured female athletes and/or coaches).

This surge in female athlete representation majorly affects the graphs that I had previously made on this subject, so I decided to make a new visual to communicate the remarkable nature of the year of 2015 for "The *Sports Illustrated* Female Athlete." See below:

<img src="/post/the-distribution-of-sports-illustrated-covers-the-bikini-d-the-not_files/si2.png" alt=""/>

---

# Code/Data

If you're curious, see my ["SportsIllustrated" Github repo](https://github.com/apalbright/SportsIllustrated) for the raw data as well as the R script necessary to create the stacked bar charts.