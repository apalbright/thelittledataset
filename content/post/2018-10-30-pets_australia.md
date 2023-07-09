---
title: It's Raining Cats and Dogs Data
author: ''
date: '2018-10-30'
slug: cats-vs-dogs
categories:
  - ridgeline plots
  - density plots
tags:
  - data viz
  - R
  - tf-idf
  - open data
  - notebook
  - cat
  - dog
  - Australia
  - age
  - name
  - Bella
---

# Meow-tivation[^1]

In my day-to-day, I often work with data on ages and names. Age is an important covariate to include in regressions; its continuous evolution can also lend itself to clever regression discontinuity designs.[^2]  Meanwhile, names can be used to infer often omitted demographic variables such as gender and race.[^3] I have seen these two variables collected for scores and scores of people... **but, what about when the sample isn't people anymore?**
 
Back in April, [Data is Plural](https://tinyletter.com/data-is-plural/letters/data-is-plural-2018-04-04-edition) linked to a [spreadsheet](https://data.sunshinecoast.qld.gov.au/Administration/Registered-Animals/7f87-i6kx/data) maintained by the Sunshine Coast Council in Australia.[^4] The spreadsheet lists all animals registered with the Council -- that is, 55,495 dogs and cats.[^5] Among the variables collected on each of these pets is (you guessed it): name and age! As such, please humor me while I take the opportunity to compare dogs and cats along these two dimensions.

# Names

Lots of intriguing analyses have been done with respect to human names. Creative bloggers have investigated [age distribution by name](http://rhiever.github.io/name-age-calculator/index.html), the most [unisex names](https://flowingdata.com/2013/09/25/the-most-unisex-names-in-us-history/), the [trendiest names](https://flowingdata.com/2013/07/29/the-most-trendy-names-in-us-history/) and, lastly, the [most *poisoned* names](https://hilaryparker.com/2013/01/30/hilary-the-most-poisoned-baby-name-in-us-history/). However, blog content comparing cat and dog names is nonexistent to my knowledge. *What a hole in human knowledge, I agree!*

The Sunshine Council data includes 55,495 registered animals.[^6], I wondered if some of these animals could be deceased. The Sunshine Coast Website explains that *“[d]og registrations must be renewed annually as per the Animal Management (Cats & Dogs) Act 2008 Queensland. Cat registrations must be renewed annually as per the Sunshine Coast Local Law No. 2 (Animal Management) 2011.”* As such, all animals in the dataset have been “renewed” within the last year, meaning this is a dataset of “active animals.” (I.e., they were alive at some point this year.)] Of that 9,412 are cats and 46,083 are dogs, meaning there are almost 5 times as many dogs as cats in the data. If I sum up totals for names, I end up with the following top 5 names for cats and dogs.

Top 5 Cat Names | Top 5 Dog Names
------------- | -------------
Bella         | Bella
Charlie       | Charlie 
Molly         | Molly
Max           | Max
Mia           | Buddy

Bella has been shown to be a popular name in [NYC for dogs as well](http://a816-dohbesp.nyc.gov/IndicatorPublic/dognames/). The Bella trend is also pretty clear [for humans](http://rhiever.github.io/name-age-calculator/index.html?Gender=F&Name=bella)... *Twilight's cultural legacy will endure for decades through these very names.*

Since most of the top names are the same for dogs and cats, it would be more interesting to see which are most uniquely cat-y or dog-y names. As such, I generate `tf-idf` measures for all the dog and cat names to measure their relative importance.[^7] In other words, I identify names that are frequently given to cats but infrequently given to dogs and vice verse.

Top 5 Cat-y Names | Top 5 Dog-y Names
------------- | -------------
Puss          | Hudson 
Mittens       | Dozer 
Garfield      | Bronson
Meow          | Chopper
Salem         | Yogi

It's probably not mind-blowing to tell you that a `Puss` or `Mittens` is likely a cat rather than a dog. However, `Hudson` as a dog-specific name is new information to me. 

# Age

In looking through the age data, the five oldest pets are 71, 52, 42, 31, and 28 years-old, respectively. *Are these ages for real?!* It seems hard to believe, but the Council does make people renew them annually. In that case, can someone please go visit 71 year-old `Sprocket` in Mooloolaba? 

Alright, `Sprocket` aside, let's compare age distributions for dogs and cats.

![](/post/pets_australia_files/dog_cat_ages_final.png)

I generate a [ridgeline plot](https://cran.r-project.org/web/packages/ggridges/vignettes/introduction.html) for the two distributions. Essentially, the above is two density plots, one for each animal type. It is immediately clear that the two distributions are incredibly similar, even down to the (colored) quantiles!

## An Aside on Dog-Years

Given that I have a distribution of dog ages at my disposal, it would be an oversight not to address the conventional wisdom on "dog years." It's deeply embedded in the zeitgeist that a dog year is equivalent to seven human years. [A 2008 WSJ article](https://github.com/apalbright/cats_dogs/blob/master/dogyears.pdf) explains the possible origin story as follows:

> Somewhere along the way, it seems likely to several veterinarians, typical lifespans were pegged at about 70 for humans and about 10 for dogs. Thus, the seven-year rule was born. "My guess is it was a marketing ploy," says William Fortney, a veterinarian at Kansas State University, "a way to educate the public on how fast a dog ages compared to a human, predominantly from a health standpoint. It was a way to encourage owners to bring in their pets at least once a year."

After that WSJ article, [a Priceonomics article](https://priceonomics.com/the-mythology-of-dog-years/) was written that explained why data is lacking on pet lifespans:

> Yet because there is no canine equivalent to the National Center for Health Statistics, we rely on a triage of sources for their lifespan data: pet insurance companies, breed-club surveys, and veterinary hospitals. As Carl Bialik of the WSJ notes, these sources often provide inaccurate, skewed results. Dogs who have insurance, for instance, are generally more likely to live longer lives. Surveys, which often require owners to guesstimate their pets’ ages, yield inflated numbers.

With this data on registered dogs in Australia, I can compare ages across dog and humans in a way that data-enthusaists 10 years ago could not. Let's compare median ages.[^8] The [Australian Bureau of Statistics](http://www.abs.gov.au/ausstats/abs@.nsf/featurearticlesbyCatalogue/CCF53AA000E69954CA2582570013F5C6?OpenDocument) says the median age for Australian is 37, as of June 2017. Meanwhile, a simple calculation shows that the median Australian dog age is 6. Assuming we want to match on medians, dog-years could be defined as 6.166667 human years. *Hey, that's pretty close to 7!*


# Back to Human Data

Self-care is exploring/visualizing data that has nothing to do with my PhD research. 🐱 🐶 

Thanks for the therapy-dog-&-cat-data break, Sunshine Council. 

---

# Code

1. [Here](http://rpubs.com/apalbright/cats-vs-dogs) is my R notebook responsible for the data analysis/visualization
2. [Here](https://github.com/apalbright/cats_dogs) is the associated Github repo with everything required to replicate the analysis


[^1]: Forgive me.

[^2]: That is, if treatment is determined by an age cut-off.

[^3]: See pages 14-16 of [Soltas and Broockman (2018)](https://www.gsb.stanford.edu/faculty-research/working-papers/natural-experiment-taste-based-racial-ethnic-discrimination) for a nice description of how researchers infer race and gender from names.

[^4]: Woo open data!

[^5]: Data is Plural has pointed me to [other](https://data.cityoftacoma.org/Neighborhoods/Current-Pet-License-City-of-Tacoma-Fircrest/qnnn-t9wt) [datasets](https://github.com/kaz-a/dog_names) on dogs before, but this is the only one I've seen that includes cats too.

[^6]: Because [pets die](https://www.youtube.com/watch?v=7VzaL4CSfms&feature=youtu.be&t=54).

[^7]: If you want to read more about `tf-idf`, see [here](https://thelittledataset.com/2017/09/14/the-united-nations-of-words/).

[^8]: Let's match on the median rather than life expectancy because I can't see deaths for the dogs (thus hindering a rigorous calculation) and I don't want to get into the intricacies of [life expectancy calculations](https://ourworldindata.org/life-expectancy-how-is-it-calculated-and-how-should-it-be-interpreted).
