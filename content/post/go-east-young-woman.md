---
title: Go East, Young Woman
author: ''
date: '2016-07-27'
slug: go-east-young-woman
categories:
  - line charts
tags:
  - bos
  - boston
  - cambridge
  - data viz
  - ggplot2
  - palo alto
  - R
  - san francisco
  - seasons
  - sf
  - temperature
  - weather
---

# We'll always have Palo Alto^[Sincere apologies to those of you in the Bay Area who have had to hear me make this joke a few too many times over the past few weeks.]

It is 9:30pm PST on Friday evening and my seat beat is buckled. The lights are a dim purple as they always are on Virgin America flights. As if we are all headed off to a prom on the opposite side of the country together. [My favorite safety video](https://www.youtube.com/watch?v=DtyfiPIHsIg) in the industry starts to play--an accumulation of visuals and beats that usually gives me a giddy feeling that only Beyoncé videos have the power to provoke--however, in this moment, I begin to tear up despite the image of a shimmying nun displayed in front of me. In my mind, overlaying the plane-inspired choreography is a projection of [Rick Blaine reminding me](https://www.youtube.com/watch?v=rEWaqUVac3M&feature=youtu.be&t=1m8s) in my moments of doubt that, I belong on this plane^[Though definitely not to serve as a muse to some man named Victor. Ah, yes, the difference 74 years can make in the purpose of a woman's travels.]: 

> If that plane leaves the ground and you're not [in it], you'll regret it. Maybe not today. Maybe not tomorrow, but soon and for the rest of your life.

I whisper "here's looking at you, kid" to the screen now saturated with dancing flight attendants and fade into a confused dreamscape: Silicon Valley in black and white -- founders still wear hoodies, but they have tossed on hats from the '40s.

A few days later, I am now living in Cambridge, MA. While my senses are overcome by a powerful ensemble of changes, some more discreet or intangible than others, there is one element of the set that is clear, striking, and quantifiable. The thickness and heat in the air that was missing from Palo Alto and San Francisco. After spending a few nights out walking (along rivers, across campuses, over and under bridges, etc.) in skirts and sandals without even the briefest longing for a polar fleece, I am intent on **documenting the difference between Boston and San Francisco temperatures.** Sure, I can't quantify every dimension of change that I experience, but, hey, I can chart temperature differences.

# Coding up weather plots

In order to investigate the two cities and their relevant weather trends, I adapted some [beautiful code](https://rpubs.com/bradleyboehmke/weather_graphic) that was originally written by [Bradley Boehmke](http://bradleyboehmke.github.io/).^[He wrote this code to generate [Tufte](https://www.edwardtufte.com/tufte/)-inspired weather charts using R (specifically making use of the beloved ggplot2 package).] The code is incredible in how simple it is to apply to any of the cities that have data from the University of Dayton’s [Average Daily Temperature archive](http://academic.udayton.edu/kissock/http/Weather/).^[Taking your own city's data for a spin is a great way to practice getting comfortable with R visualization if you're into that sort of thing.] Below are the results I generated for SF and Boston, respectively:

<center>
<img src="/post/go-east-young-woman_files/SF_plot.png" alt="" width="100%" height="100%"/>

<img src="/post/go-east-young-woman_files/Boston_plot.png" alt="" width="100%" height="100%"/>
</center>


While one could easily just plot the recent year's temperature data (2015, as marked by the black time series, in this case), it is quickly evident that making use of historical temperature data helps to both smooth over the picture and put 2015 temperatures in context. The light beige for each day in the year shows the range from historical lows and to historical highs in the time period of 1995-2014. Meanwhile, the grey range presents the 95% confidence interval around daily mean temperatures for that same time period. Lastly, the presence of blue and red dots illustrates the days in 2015 that were record lows or highs over the past two decades. While Boston had a similar number of red and blue dots for 2015, SF is overpowered by red. Almost 12% of SF days were record highs relative to the previous twenty years. Only one day was a record low.

While this style of visualization is primarily intuitive for comparing a city's weather to its own historical context, there are also a few quick points that strike me from simple comparisons across the two graphs. I focus on just three quick concepts that are borne out by the visuals:

1. **Boston's seasons are unmistakable.**^[Speaking of [seasons](https://www.youtube.com/watch?v=fTnU5MG5Edw)...] While the normal range (see darker swatches on the graph) of temperatures for SF varies between 50 (for winter months) and 60 degrees (for late summer and early fall months), the normal range for Boston is notably larger and ranges from the 30's (winter and early spring months) to the 70's (summer months). The difference in the curve of the two graphs makes this difference throughout the months painfully obvious. San Francisco's climate is incredibly stable in comparison with east coast cities--a fact that is well known, but still impressive to see in visual form!
2. **There's a reason SF can have Ultimate Frisbee Beach League in the winter.** Consider the relative wonderfulness of SF in comparison to Boston during the months of January to March. In 2015, SF ranged from 10 to 55 degrees (on a particularly toasty February day) warmer than Boston for those months. In general, most differences on a day-to-day basis are around +20 to +40 degrees for SF.
3. **SF Summer is definitely 'SF Winter' if one defines its temperature relative to that of other climates.** In 2015, the summer months in SF were around 10 degrees colder than were the summer months in Boston. While SF summer is warmer than actual SF winter in terms of absolute temperature comparisons, comparing the temperatures to other areas of the country quickly yields SF summer as the relatively chilliest range of the year.

Of course, it is worth noting that the picture from looking at simple temperature alone is not complete. More interesting than this glance at basic temperature would be an investigation into the "feels like" temperature, which usually takes into account factors such as wind speeds and humidity. Looking into these more complex measurements would very likely heighten the clear distinction in Boston seasons as well as potentially strengthen the case for calling SF summer 'SF winter', given the potential stronger presence of wind chill during the summer months.^[I'd be interested to see which US cities have the largest quantitative difference between "feels like" and actual temperature for each period (say, month) of the year...]

# The coldest winter I ever spent...^[From a [2005 Chronicle article](https://www.sfgate.com/bayarea/article/FOG-HEAVEN-The-sun-will-come-out-tomorrow-Or-2615710.php): "'The coldest winter I ever spent was a summer in San Francisco,' a saying that is almost a San Francisco cliche, turns out to be an invention of unknown origin, the coolest thing Mark Twain never said."]

It is 6:00am EST Saturday morning in Boston, MA. Hot summer morning is sliced into by divine industrial air conditioning. Hypnotized by luggage seemingly floating on the baggage claim conveyor belt and slowly emerging from my black and white dreams, I wonder if Ilsa compared the weather in Lisbon to that in Casablanca when she got off her plane... after contacts render the lines and angles that compose my surroundings crisp again, I doubt it. Not only because Ilsa was probably still reeling from [maddeningly intense](http://www.sheilaomalley.com/archives/casablanca.jpg) eye contact with Rick, but also because Lisbon and Morocco are not nearly as markedly different in temperature as are Boston and San Francisco.

Turns out that the coldest winter I will have ever spent will be winter in Boston. My apologies to summer in San Francisco.

---

# Code

See my adapted R code for SF and Boston [here](https://github.com/apalbright/temp_plots).

Again, the vast majority of credit goes to Bradley Boehmke for the original build!