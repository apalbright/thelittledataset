---
title: Senate Votes Visualized
author: ''
date: '2017-08-01'
slug: senate-votes-visualized
categories:
  - grid maps
tags:
  - data viz
  - democrat
  - geofacet
  - ggplot2
  - healthcare
  - magick
  - obamacare
  - politics
  - R
  - repeal and replace
  - republican
  - senate
  - skinny repeal
  - votes
---

It has been exactly one week since the Senate voted to start debate on Obamacare. There were three Obamacare repeal proposals that followed in the wake of the original vote. **Each one failed, but in a different way.** News outlets such as the *NYTimes* did a great job reporting how each Senator voted for [all](https://www.nytimes.com/interactive/2017/07/25/us/politics/senate-vote-republican-health-care-bill.html) [the proposals](https://www.nytimes.com/interactive/2017/07/25/us/politics/senate-votes-repeal-obamacare.html). I then used that data to geographically illustrate Senators' votes for each Obamacare-related vote. See below for a timeline of this past week's events and accompanying R-generated visuals.

# Tuesday, July 25th, 2017

The senate votes to begin debate.

![](/post/senate-votes-visualized_files/deb_final.png)

This passes 51-50 with Pence casting the tie-breaking vote. The visual shows the number of `(R)` and `(D)` Senators in each state as well as how those Senators voted. We can easily identify Collins and Murkowski, the two Republicans who voted `NO`, by the <font color="purple">**purple**</font> halves of their states (Maine and Alaska, respectively). While Democrats vote as a bloc in this case and in the impending three proposal votes, it is the Republicans who switch between `NO` and `YES` over the course of the week of Obamacare votes. Look for the switches between <font color="red">**red**</font> and <font color="purple">**purple**</font>.

# Later that day...

The Senate votes on the **Better Care Reconciliation Act**.

![](/post/senate-votes-visualized_files/rr_final.png)

It fails 43-57 at the mercy of Democrats, Collins, Murkowski, and a more conservative bloc of Republicans.

# Wednesday, July 26th, 2017

The Senate votes on the **Obamacare Repeal and Reconciliation Act**.

![](/post/senate-votes-visualized_files/pr_final.png)

It fails 45-55 at the mercy of Democrats, Collins, Murkowski, and a more moderate bloc of Republicans.

# Friday, July 28th, 2017

The Senate votes on the **Health Care Freedom Act**.

![](/post/senate-votes-visualized_files/sk_final.png)

It fails 49-51 thanks to Democrats, Collins, Murkowski, and McCain. To hear the gasp behind the slice of purple in AZ, watch the video below.

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/iNwLDj6D520" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

---

# Code

This was a great exercise in using a few R packages for the first time. Namely, `geofacet` and `magick`. The [former](https://hafen.github.io/geofacet/) is used for creating visuals for different geographical regions, and is how the visualization is structured to look like the U.S. The [latter](http://www.danielphadley.com/ggplot-logo/) allows you to add images onto plots, and is how there's a little zipper face emoji over DC (as DC has no Senators).

In terms of replication, my R notebook for generating included visuals is [here](http://rpubs.com/apalbright/senate-votes-visualized). The github repo is [here](https://github.com/apalbright/senate-votes-viz).
