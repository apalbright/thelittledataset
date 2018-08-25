---
title: A Rising Tide Lifts All Podcasts
author: ''
date: '2017-07-26'
slug: a-rising-tide-lifts-all-podcasts
categories:
  - scatter plots
tags:
  - comedy
  - data viz
  - drunk
  - podcast
  - podcast trends
  - politics
  - R
  - releases
  - science
  - sports
  - trends
---

# A Personal History of Podcast Listening

One afternoon of my junior year, I listened to a chunk of a *Radiolab* episode about ["Sleep"](https://www.wnycstudios.org/story/91528-sleep) as I myself heavily sank into unconsciousness. It was like guided meditation... supported, in part, by the Alfred P. Sloan Foundation. Jad and Robert's forays on *Radiolab* quickly became my new bedtime stories. They helped me transition from days with my nose deep in books and, more accurately, my laptop to dreams that veered away from the geographic markers of one tiny college town in a valley of the Berkshires.

The *Radiolab* archives were a soundtrack to my last years of college and to my transition from "student" at a college to "staff member" at a university. A few months into my new place in the world, I found myself discussing Sarah Koenig's *Serial* with my colleagues in neighboring cubicles. I also wasn't a stranger to the virtual water cooler of [/r/serialpodcast](https://www.reddit.com/r/serialpodcast/). I became so entrenched in the podcast's following that I ended up being inspired to start blogging in order to [document reddit opinion](https://thelittledataset.com/2014/12/21/serial-and-changes-of-heart/) trends on the topic.

Faced with regular Caltrain rides from the crickets and ["beam" store](https://shop.suitabletech.com/) of Palo Alto to the ridiculous-elevation-changes of SF, I started listening to *Gilmore Guys*. You know, the show about two guys who talk about the Gilmore Girls.^[I did not think this would take (I mean, there were hundreds of episodes--who would listen to all that?!) but I was very wrong.] The two hosts accompanied me throughout two full years of solo moments. Their banter bounced next to me during mornings biking with a smile caked across my face and palm trees to my left and right as well as days marked by fierce impostor syndrome. *GG* bits floated next to me in the aftermath of medical visits that frightened me and suburban grocery shopping endeavors (which also sometimes frightened me). Their words, light and harmless, sat with me during evenings of drinking beer on that third-of-a-leather-couch I bought on craigslist and silent moments of self-reflection.

That might sound like pretty heavy lifting for a podcast. But, (silly as it might sound) it was my security blanket throughout a few years of shifting priorities and support networks--tectonic plates grumbling under the surface of my loosely structured young adult life.

When it came time to move to Cambridge from Palo Alto, I bought a [Leesa](https://www.leesa.com/) mattress thanks to Scott Aukerman's 4am mattress store advert bit from *Comedy Bang Bang*.^[Sorry, [Casper](https://casper.com/).] Throughout my first doctoral academic year, I regularly listened to *Two Dope Queens* as I showered and made dinner after frisbee practices. Nowadays, like a good little liberal, I listen to the mix of political yammering, gossip, and calls to arms that makes up *Pod Save America*.

Podcasts seem to be an increasingly important dimension of our alone time. A mosaic of podcast suggestions is consistently part of entertainment recommendations across friends... which leads me to my question of interest: **How are podcasts growing? Are there more created nowadays, or does it just feel like that since we discuss them more?**

# Methodological Motivation

In following the growth of the [R-Ladies organization](https://rladies.org/) and the exciting work of associated women, I recently spotted [a blog post](https://livefreeordichotomize.com/2017/02/09/the-prevalence-of-drunk-podcasts/) by R-lady Lucy McGowan. In this post, Lucy looks at the growth of so-called 'Drunk' Podcasts. She finds a large growth in that "genre" (if you will) while making [great usage of a beer emoji](https://livefreeordichotomize.com/post/2017-02-09-the-prevalence-of-drunk-podcasts_files/figure-html/unnamed-chunk-2-1.png). Moreover, she expresses that:

> While it is certainly true that the number of podcasts in general has absolutely increased over this time period, I would be surprised if the increase is as dramatic as the increase in the number of “drunk” podcasts.

I was super skeptical about this statement. I figured the increase in many podcast realms would be just as dramatic, if not more dramatic than that in the 'drunk' podcasts universe. So, I took this skepticism as an opportunity to build on Lucy's code and emoji usage and look into release trends in other podcasting categories. Think of this all as one big excuse to try using emojis in my `ggplot2` creations while talking about podcasts.^[Thank you to the author of the [`emoGG` package](https://github.com/dill/emoGG), a hero who also created [Beyoncé color palettes for R](https://github.com/dill/beyonce).]

# Plotting Podcasts

I look into podcasting trends in the arenas of 'sports', 'politics', 'comedy' and 'science.' I figured these were general umbrella terms that many pods should fall under. However, you can easily adapt the code to look into different genres/search terms if you're curious about other domains.^[See my [R notebook](http://rpubs.com/apalbright/podcast-release-trends) for reproducible work on this subject.] I, like Lucy, then choose emojis to use in my eventual scatterplot. Expressing a concept as complex as politics with a single emoji was challenging, but a fun exercise in using my millennial skillset.^[The 'fist' emoji was the best I could come up with for 'politics' though I couldn't figure out how to modify the skin tone. I'm open to other suggestions on this front. You can browse through options with unicode [here](https://apps.timwhitlock.info/emoji/tables/unicode#note5).]

In the end, I combine the plots for all four podcasting categories into one aggregated piece of evidence showing that **many podcasts genres have seen dramatic increases in 2017**. The growth in number of releases is staggering in all four arenas. (Thus, the title 'A rising tide lifts all podcasts.') So, this growth doesn't seem to be unique to the 'drunk' podcast. In fact, these more general/conventional categories see much more substantive increases in releases.

<center>
<img src="/post/a-rising-tide-lifts-all-podcasts_files/pods4.png" alt="" width="80%" height="80%"/>
</center>

While the above deals with podcast releases, I would be very curious to see trends in podcast listening visualized. For instance, one could use the [American Time Use Survey](https://www.bls.gov/tus/) to break down people's leisure consumption by type during the day.^[It seems that the ATUS added "listening to podcast" in [2015](https://www.bls.gov/tus/lexiconchanges.pdf).] I'd love to see some animated graphics on entertainment consumption over the hours reminiscent of Nathan Yau's previous amazing work [("A Day in the Life of Americans")](https://flowingdata.com/2015/12/15/a-day-in-the-life-of-americans/) with ATUS data.

# Putting Down the Headphones

Regardless of the exact nature of the growth in podcasts over the past years, there is no doubt the medium has come to inhabit a unique space. Podcasts feel more steeped in solitude than other forms of entertainment like television or movies, which often are consumed in group settings. Podcasts have helped me re-learn how to [be alone](https://i.redd.it/2302x89w2e8y.jpg) (but not without stories, ideas, and my imagination) and enjoy it. And, I am an only-child, so believe me... I used to be quite good at that.

*The Little Dataset* -- despite this focus on podcasts -- is brought to you by `blogdown` and Hugo...  not Squarespace. :)

---

# Code

Check out [this R Notebook](http://rpubs.com/apalbright/podcast-release-trends) for the code needed to reproduce the graphic. You can also see [the relevant github repo](https://github.com/apalbright/podcast-trends).