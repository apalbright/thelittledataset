---
title: Testing for Local Continuity in Racial Animus
author: ''
date: '2018-07-23'
slug: testing-for-local-continuity-in-racial-animus
categories:
  - choropleths
  - regressions
tags:
  - academia
  - academic
  - humanities
  - digital humanities
  - economics
  - google
  - google search
  - history
  - kkk
  - klaverns
  - race
  - racial animus
  - R
  - persecution
---

This past spring I was tasked with writing a final paper for my *Comparative Historical Economic Development* course. In brainstorming, I started a casual fling with one idea that quickly escalated and led to long spring break dates at the library (collecting data, making maps). In a meeting with my professor back at Harvard, I realized that I had been consumed in the honeymoon phase of an idea. Taking off my rose-colored glasses, it became clear I had to end the tryst so I could focus on more promising paths to a paper...

In the end, I wrote about a different idea. Meanwhile, the original one lived in solitude in an inactive Dropbox folder, a digital dead end. While I never developed it into a paper, why not shape it into a blog post? After all, there were interesting datasets and choropleths to share. So, here I am, throwing it a bone! If only for the sake of intellectual closure...

# Persecution Perpetuated `$\rightarrow$` Animus Alive

I was immediately struck by an idea after reading the [QJE](https://academic.oup.com/qje) article ["Persecution Perpetuated: The Medieval Origins of Anti-Semitic Violence in Nazi Germany."](/post/testing-for-local-continuity-in-racial-animus_files/pp_qje.pdf) Co-authors Voigtländer and Voth use an incredible dataset of about 400 towns "where Jewish communities are documented for both the medieval period and interwar Germany." They find local continuity in anti-Semitism over 600 years. Local continuity in this context means attacks on Jews were six times more likely in the 1920's in towns and cities that blamed and then murdered Jews for the Black Death (during 1348-50). Let me repeat myself: local continuity over SIX HUNDRED YEARS.^[More than half a millennium!] The paper provides convincing empirical evidence that group-based persecution (anti-Semitism in this case) can meaningfully persist at the local level. History matters, the data screams.

After reading "Persecution Perpetuated," I was curious if I could merge recently available data sources to test whether racial animus in the US would be display similar local continuity.^[Possible alliterative titles to pay homage to "Persecution Perpetuated" include: "Animus Alive" and "Malice Maintained."] Specifically, what sprang to mind as a possible dependent variable was [Seth Stephens-Davidowitz](http://sethsd.com/)'s [racial animus measure](/post/testing-for-local-continuity-in-racial-animus_files/ranimus.pdf), which is based on based on Google search data. (I've always wanted to play around with Seth's Google data, so I seized on a possible academic opportunity to do so.)

What does it mean to measure racial animus using Google data? Seth proxies for a geographic area's racial animus by calculating the percent of its Google searches (2004-2007) that included the n-word or its plural. The Google data at its finest geographic level is available for US [Designated Market Areas](http://www.nielsen.com/intl-campaigns/us/dma-maps.html). (There are 210 such DMA's in the US.) Specifically, the "racially charged search rate" is calculated as: `$$DMA_j = 100 [n-wordsearches / totalsearches]_j / [n-wordsearches / totalsearches]_{max}$$`

The necessary underlying assumption is that racial animus makes one more likely to make an n-word Google search. (It does not have to be the case that "every individual using the term harbors racial animus, nor that every individual harboring racial animus will use this term on Google.")^[If you want to know more about this measure, read Seth's [NYTimes piece](https://campaignstops.blogs.nytimes.com/2012/06/09/how-racist-are-we-ask-google/) about his academic work as well.]

Why is using Google search data attractive? Seth argues that survey data is unlikely to paint an accurate picture of racial animus because well, people lie.^[Thus the title of his book, [*Everybody Lies*](http://sethsd.com/everybodylies/), which I highly recommend if you're interested in data-driven social science.] Meanwhile, "the conditions under which people [Google] search – online, likely alone, and not participating in an official survey – limit concern of social censoring." In short, Google search data allows us to access a snapshot of attitudes or beliefs that might otherwise be inaccessible with traditional surveys.

While Google search is a new phenomenon in the grand scheme of history, I was curious if historical data related to racial animus could be a powerful predictor of these modern racially charged search patterns. Ie, I sought out a relevant historical independent variable, which led me to Virginia Commonwealth University (VCU)'s project ["Mapping the Second Klu Klux Klan, 1915-1940."](https://labs.library.vcu.edu/klan/) History Professor John Kneebone constructed a list of local KKK chapters (klaverns) using information from a large set of the group’s official publications.^[More on this [here](https://news.vcu.edu/article/Digital_map_shows_spread_of_KKK_across_United_States_like_a_contagion).] The project makes visually explicit the widespread nature of the KKK; "Everywhere there was population, there was the Klan," Kneebone explained. He then worked with digital librarians at VCU Libraries to map out the klaverns and make the raw location data [publicly accessible](https://scholarscompass.vcu.edu/hist_data/1/).

With the VCU data in mind, I wondered: does the local historical KKK prevalence in 1915-1940 predict (through perpetuated racial animus) racially charged Google search rates in 2004-2007? There are some issues to note when using klavern location data:

1. Ideally, I'd use data on the number of members by geographic areas. 
    - Ignoring underlying population figures for a moment: Imagine there are 3 klaverns with 10 members each in `$DMA_A$`. Meanwhile, there is 1 klavern with 100 members in `$DMA_B$`. The Klan is more prevalent in terms of raw members in `$DMA_B$`, but with only the location data in tow, `$DMA_A$` would seem to have a more prevalent Klan presence.
    - Unfortunately, I am not aware of data on historical Klan membership by finer levels (DMA-level) of US geography.
2. The location data are not necessarily complete. Such is the nature of collecting data from a different era. 
    - They are based on historical research and investigative work, but klavern locations are likely missing.
    
So, simply put, the question is: **can I find empirical evidence of local continuity in American racial animus by merging historical and modern metrics?** That is, **will klavern prevalence per capita (1915-1940) meaningfully predict racially charged Google searches (2000-2004)?**

# Maps and regressions

First things first. Let's map both `$klaverns/million$` and racially charged search rates by DMA. The variation in `$klaverns/million$` turned out to be so skewed that using the raw rate made the variation almost impossible to visually decipher. The use of `$log(klaverns/million)$` makes the geographic variation visually interpretable. 

<img src="/post/testing-for-local-continuity-in-racial-animus_files/map_both1.png" alt="" width="100%" height="100%"/>

While I interpreted the two metrics as proxies of racial animus at different times in history, they don't obviously track through time and space visually. The possible story (that one meaningfully predicts the other) isn't very convincing at this stage. But, it's worth seeing the output from a simple regression.^[I use log of `$klaverns/million$` since the distribution of `$klaverns/million$` was skewed, making a nonlinear relationship between modern racially charged search rate and `$klaverns/million$`. To counter [heteroskedasticity](http://www.statsmakemecry.com/smmctheblog/confusing-stats-terms-explained-heteroscedasticity-heteroske.html), I transformed `$klaverns/million$` to its log. I'm open to criticism/discussion on such log transformations.]

<img src="/post/testing-for-local-continuity-in-racial-animus_files/reg1.png" alt="" width="90%" height="90%"/>

While the independent variable is statistically significant (star, star, star), the variation in `$log(klaverns/million)$` explains only 3-4% of the variation in racially charged Google search rates. In terms of magnitude, a 1% increase in klaverns/million is associated with a 0.02645 unit increase in racially charged google search rate. That is economically meaningless considering that the rates range from 25-155. This is also without controlling for any of the analogs of V&V covariates that would need to be included to make a convincing case for the robustness of any supposed relationship.

In the end, the VCU location data aggregated up to totals for DMA areas are not a meaningful predictor of racial animus revealed by Google behavior. This could be for many reasons. It could be because klavern location totals are not accurate depictions of KKK prevalence (data reveals locations rather than member totals, data could be incomplete). Moreover, on a more philosophical level, does this project even test the persistence of racial animus?... or is it asking a question about how language squares with historical locations of institutions? I'll leave that up to my academic counterparts in Political Theory.^[CJ, you're up.]

# Why it wasn't meant to be... a paper

Now, it is worth explaining why this idea was always predestined to stay in blog-land. For one, even an extremely powerful positive result wouldn't "shift priors" (as economists say to one another) -- the result would seem obvious and so, who cares? Voigtländer and Voth's paper was publishable due to the long-term scope (600 years!) and fine geographic level (towns, cities in Germany) of their results. The concept that attitudes could be perpetuated over time wasn't the selling point, it was the fact that attitudes could be perpetuated for **so long** and **in such a locally continuous way**. If the geographies had been more coarse and their data hadn't covered such a long period of time, the paper would not have landed in the QJE. Since I asked if 1915-1940 attitudes would predict 2004-2007 attitudes and I was limited to large designated market areas (due to the nature of the google data), my findings were doomed to be unremarkable even if incredibly powerful (which... they were not).^[A few months after writing this post, I learned about [Jhacova Williams](https://sites.google.com/view/jhacovawilliams/home?authuser=0)'s work on historical lynchings (1882-1930) and contemporary black voting behavior, which reminded me of my original interest in the long-run effects of persecution/violence. [Her paper](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxqaGF3aWxsaWZpbGVzfGd4OjJmMGMyMDY2NjcwMzQyMTI) uses
county-level voter registration data to show "that blacks who reside in southern
counties that experienced a relatively higher number of historical lynchings have lower voter registration rates today." While I was interested in the persistence of animus over time, which could be a simple function of path dependence, Williams focuses on the link between historical violence and modern behaviors of affected groups, which is much more complex in its mechanism. [Here](https://www.youtube.com/watch?v=bgJe2bBO3iE) is a clip of her discussing her research.]

Despite its inevitable end, I did learn a lot from this spring fling. On a qualitative level, I learned about the historical omnipresence of the KKK from an impressive digital humanities project. On a technical level, I learned how how to map DMA areas in R (very tricky). And, on a philosophical level, I learned how to cleanly break up with a project idea.^[Thanks for all the optimal stopping lessons, [David](https://scholar.harvard.edu/laibson/home).]

---

# Data & Code

- Seth's racial animus data is [here](http://sethsd.com/research/).
- VCU data on klaverns is [here](https://scholarscompass.vcu.edu/hist_data/1/).
- My R notebook for this project is [here](http://rpubs.com/apalbright/local-continuity-racial-animus).
- My Github repo for this project is [here](https://github.com/apalbright/local-continuity-racial-animus).
