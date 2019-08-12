---
title: "Exploring Connecticut's Pretrial Inmate Data"
date: 2019-08-12
slug: ct-pretrial-descriptives
categories:
  - stacked bar plots
  - bar graphs
  - line charts
  - hexagonal binned plots
tags:
  - bail
  - criminal justice
  - race
  - open data
  - R
  - pretrial
  - jail
  - prison
  - Connecticut
---

# Intro

About 65% of people in jail in the US have not yet been convicted of a crime. Instead, they are in jail awaiting court action on a charge -- they are "pretrial" inmates.^[Given that [97% of federal cases and 94% of state cases are resolved with pleas deals](https://theappeal.org/justice-in-america-episode-2-the-94-plea-deals/), perhaps we should more accurately call them "pre-plea" inmates.] The [most recent BJS numbers](https://www.bjs.gov/content/pub/pdf/ji17.pdf) estimate that, on a given day, about 482,000 people were pretrial inmates in mid-2017. Over the course of a whole year, *millions* of people flow in and out of pretrial detention.^[Previously, I estimated that [~2.5-4.5 million unique people](https://thelittledataset.com/2019/01/14/dynamics-of-pretrial-jail-populations/#fnref:He-assumed-about) flow through pretrial detention in a year.] Given ongoing US [bail reform](https://www.themarshallproject.org/records/1439-bail-reform) efforts, it is extremely policy relevant to better understand descriptive statistics about pretrial populations. As such, I'll dig into the following string of questions (with a publicly available dataset):

1. Why are people admitted to jail pretrial? (I.e., what charges are responsible for the most pretrial detention admissions?)
2. What are the demographic characteristics (gender, race, age) of those individuals in jail pretrial? (How does this compare to the general population?)
3. What are the bond amounts that pretrial inmates face? (Are the means different by race?)
4. How long do people stay in jail pretrial? (Again, are the means different by race?)
5. How do bond amounts relate to the length of pretrial detention?

## Connecticut Open Data (again)!^[Note: I also used this data in a January post about the [dynamics of pretrial populations](https://thelittledataset.com/2019/01/14/dynamics-of-pretrial-jail-populations/).]

Our ability to answer the above questions is necessarily limited by data availability. I mean, how often do you find high frequency open data on a pretrial population? Well, that's where [open data provided by the Connecticut Department of Corrections](https://data.ct.gov/Public-Safety/Accused-Pre-Trial-Inmates-in-Correctional-Faciliti/b674-jy6w) comes in. This dataset is, in its own words,

> A listing, updated nightly, of individuals being held in Department of Corrections facilities while awaiting trial. This data is appended on nightly basis reflecting the individual inmates being held in correctional facilities each day beginning July 1, 2016.

The dataset covers all pretrial inmates in DOC facilities from 7/1/16 to present. (I downloaded this on 7/28/19, so I am considering over 3 years of daily data.) The data is deidentified but includes variables such as date, race, gender, age, bond amount, and latest admission date.^[Some technical notes: (1) Since the DOC is a State agency, the data doesn't include those with federal charges or those in the Juvenile Justice system. (2) Defendant characteristics (e.g., race and age) are self-reported by inmates upon intake.] 

During this time period (7/1/16-7/28/19), 34,892 distinct people were recorded as spending time in a DOC facility pretrial. Note that since the data is recorded nightly, this count is an underestimate of the true number who have flowed through such facilities.^[I.e., if you were detained and then released during the same day (before the nightly count), then you would not be recorded.] Some people were detained multiple times -- there were 50,247 unique jail admissions of these 34,892 people. Moreover, (since someone can be in jail pretrial for multiple charges at once) the data covers 54,367 charges.^[Think person-admission-charge.] 

Armed with over three years of pretrial inmate data from Connecticut, I address (with graphs and stats) the aforementioned questions on charges, demographics, bond, and length of stay.

# 1. What are you in for?

While there were 54,367 charges for which people were detained pretrial in this time period, thousands of people were often facing the same charge. As such, there are only 348 unique charges in the data (spread over 34,892 people and 50,247 pretrial jail admissions). Below is a graph of the top 10 most common charges.^[Note: This is not the same picture as you would get for the most common charge *across days in jail*. The measure based on days in jail would be weighting by jail stay duration, which would skew towards more serious offenses (since more serious charges mean higher bail, leading to smaller likelihood of release).]  

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/offense_top_10.png" alt=""/>
    </center>
</figure>

Violation of probation or conditional discharge is far and away the most common reason to end up in jail pretrial. The second most common reason is criminal violation of a protective order, but it pales in a comparison of magnitudes. Failure to appear (in court), which is conceptually more similar to a violation of conditions than a new charge, appears twice on this top 10 list (once for first degree and once for second degree). If we combined both degrees of failure to appear, it would be the second most common charge.

People who work in pretrial services agencies will tell you that violations of probation are a big driver of jail admissions; the above graph puts those conversations that into stark quantitative terms. This graph also makes the case that working to decrease failure to appear by implementing [tools like court text reminders](https://www.povertyactionlab.org/evaluation/costs-failure-appear-arraignment) would address another large driver of pretrial jail admissions.

# 2. Who is in jail pretrial?

Not surprisingly, men are majorly over-represented in this pretrial inmate population compared to women. In terms of race, people who self-identified as black or Hispanic are over-represented compared to those who self-identify as white or Asian. 

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/gender_race.png" alt=""/>
    </center>
</figure>

In order to more clearly demonstrate the difference between racial composition in  the Connecticut pretrial inmate population and the general Connecticut population, I use [estimates from the Census](https://www.census.gov/quickfacts/CT).^[Note that in the Census, Hispanic is not a race; Hispanic/Latinx is an ethnicity. As such, the racial groups in the DOC data don't map perfectly onto the Census figures.] The below makes the over-representation of black and Hispanic defendants more visually explicit.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/race_compare.png" alt=""/>
    </center>
</figure>

To get a snapshot of the age distribution, I focus on the most recent day in the dataset^[Most recent *as of my download*.] -- 7/28/19. As expected, the pretrial inmate population is skewed young, with a median age of 33 compared to a [median age of ~41](https://datausa.io/profile/geo/connecticut/) in the general Connecticut population.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/age_race-7-28-19.png" alt=""/>
    </center>
</figure>

# 3. Bail me out?

Bond amounts set financial conditions for pretrial release. Bond can be changed during an inmate's jail stay, so, for the sake of clarity, I focus here on the original (first) bond amount in the data.^[I exclude bond amounts of less than $100 because the codebook says that "[i]n some instances, for particularly low (less than $100), this bond amount may be considered a place holder value". There are only 104 observations of first bond under $100.] Excluding those individuals who are coded inconsistently by race or gender yields 49,817 first observations of bond for all unique person-admissions.

The mean bond amount is $85,881 and the median is $25,100. This all seems shockingly high to me, but it is worth noting that this distribution is likely higher than the general bond distribution since this data only covers those who are in jail for at least one night. That is, selection into this sample likely leads to an overestimate of the true bond amount distribution.

Given the enormous range, I want to visualize the distribution of bond amounts for pretrial inmates. However, without a transformation, it's super difficult (impossible) to see because there are huge values on the right (in the millions) while most of the mass is on the left. To deal with this, I use a `log10` transformation of the axis with bond amount.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/bond_dist_race.png" alt=""/>
    </center>
</figure>

The coloring of the above distribution doesn't make it clear whether pretrial inmate bond amounts are different by racial group.^[(But it is pretty.)] To address this, I plot the mean bond amount by group with 95% confidence intervals. 

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/bond_race.png" alt=""/>
    </center>
</figure>

It's evident that white pretrial inmates have lower bonds on average than black, Asian, or Hispanic pretrial inmates. Again, note that the pretrial inmate population is not the same as the overall pretrial population -- many pretrial defendants are not detained because they are able to pay bail (or were given ROR).

# 4. How long do people stay in jail pretrial?

Recall, you can get out of pretrial detention if you pay bond or if your case is disposed -- that is, your case is dismissed, you plea out (~95% of the time), you go to trial, etc. Over the 46,722 observations of jail stay (excluding people who never got out and subsetting to those with stable demographics), the duration of a pretrial jail stay^[I count how many times defendants are in the data for a given admission date.] ranges from 1 to 1,038 days, with a mean of 64 days and a median of 28 days. (That is a median of 4 weeks.) 

Let's plot the distribution of length of jail stay. Again, I use a `log10` transformation for the x-axis due to the extreme values present in the data.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/inmatetime.png" alt=""/>
    </center>
</figure>

Using this data source, I cannot observe why people are exiting the dataset. That is, I cannot tell whether they paid bail or their case concluded. But, given the usual time until disposition, the mass around 1 day is likely from paying, while the mass at and after 100 days is likely due to case disposition.

In comparing means of jail stay by race, the means for black, Hispanic, and white inmates are precise (due to larger sample size) and illustrate that, on average, black inmates tend to stay longer than Hispanic inmates who, in turn, stay longer than white inmates.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/stay-race.png" alt=""/>
    </center>
</figure>

Given that whites had lower original bond on admission than black and Hispanic defendants, the above is to be expected. Given the expected relationship between bond amount and jail stay, lower original bond amounts should mean shorter jail stays (on average). The below section illustrates that relationship explicitly.

# 5. How does bond relate to length of time in pretrial detention?

In the case of this dataset, there is a correlation coefficient of ~0.37 between duration of stay in jail and bond amount, which aligns with the simple logic that it takes people longer to pay more expensive bond amounts (and then get out of jail).^[Recall: the data observed here is limited to those present in jail during some night, so it is a subset of the true set of observations on bond and pretrial detention. On another note, this relationship is weaker than one might expect -- I'm open to thoughts on this.] To see the joint distribution of the two variables (bond and stay), I display a hexagonal binned plot below.

<figure>
<center>
    <img src="/post/ct-pretrial-descriptives_files/bondtime.png" alt=""/>
    </center>
</figure>

Looking at the colors of the hexagons, it's readily apparent that the most common scenario (bright yellow) for people in the data is release within 1 day at bond of around $10,000. Northeast of those yellow hexagons, there is also a warmspot (light green) of hexagons (demonstrating a mass of observations) in the area just short of $100,000 and 100 jail days. 

# Conclusion & the future of jail data

These graphs and stats use open data to give some descriptive information on the pretrial inmate population in Connecticut. Some big take-aways are (in order of illustration): 

- probation violations are the largest driver of pretrial jail admissions in Connecticut
- black and Hispanic people (mainly, black and Hispanic men) are over-represented in the Connecticut pretrial inmate population^[This is unsurprising as it mimics the general facts about over-representation in the US criminal justice system.]
- there are shockingly large ranges of bond amounts and pretrial jail stay durations (so much so I have to use `log10` transformations for visuals)
- there is not a perfect correlation between bond amount and jail stay for this population, but there is a correlation (0.37) that aligns with basic intuition

Investigating pretrial inmate populations at a more national level (moving beyond Connecticut) requires more high frequency jail data. *(More states, more counties, please.)* When I first drafted this article, I was bummed to end on a call for better jail data since I was unsure when someone (anyone?) would be able to make this a reality. However, on the exact same day I revisited this Connecticut data (7/28/19), NYU's Public Safety Lab announced the launch of their [Jail Data Initiative](https://twitter.com/annalilharvey/status/1155591656500015104). In describing this new project, [they explain](https://publicsafetylab.org/),

> our data science team is crawling daily county jail rosters and criminal case records in over 1,000 counties. Using these data we will be able both to identify counties that are systematically jailing defendants pre-trial and/or post-fine, and to estimate the impacts of these practices on recidivism.

So, with this recent launch in mind, I am happy to report that future investigations into pretrial practices and populations won't be limited to Connecticut.

---

# Data/Code

- The pretrial inmate dataset is available via Connecticut Open data [here](https://data.ct.gov/Public-Safety/Accused-Pre-Trial-Inmates-in-Correctional-Faciliti/b674-jy6w)
- See [here](http://rpubs.com/apalbright/ct-pretrial-descriptives) for my R notebook
- See [here](https://github.com/apalbright/ct-pretrial-descriptives) for my Github repo