---
title: 'Metaplots with Metadata'
author: 'Exploiting Unique Data on Economics Papers'
date: '2021-06-28'
slug: metaplots-metadata
categories:
  - line graph
  - network visualization
  - area plot
  - choropleth
  - tables
tags:
  - economics
  - writing
  - academia
  - working papers
  - methods
  - R
  - visualization
---

# Writing about economics writing: metaplots + metadata

Throughout the last 5 years of my PhD, I've developed a list of questions big and small about economics paper trends and conventions. *Is it just me or do economists love using colons in their titles? Is differences-in-differences bigger than instrumental variables now? Why are economists always talking about how they "exploit" things? What places are economists writing about the most?*

As this [string of questions has gotten a little unwiedly](https://playsnake.org/) over time, I've been on the look out for a nice public dataset to use to address these questions. A new convention in the motivational slides of applied econometricians/methods folks gave me hope on this front. Graphs (metaplots) showing growth in phrases like "administrative data", "census linking", and "staggered differences in differences" using journal article data became a familiar sight. 

Most notably on this front, [Currie, Kleven, and Zwiers (2020)](https://www.aeaweb.org/articles?id=10.1257/pandp.20201058) create dozens of such metaplots to demonstrate changes in applied microeconomics methods over time. They use data from top economics journals and the NBER working papers series to empirically illustrate the credibility revolution (more empirics!), [graphical revolution (more graphs!)](https://twitter.com/AllbriteAllday/status/1392531753835794433), and a few other coming revolutions in the academic economics universe (ML, text mining).

Currie, Kleven, and Zwiers (2020) use data on the full text of "top five" economics journal papers and the full text of NBER working papers. They are not able to share the raw full text data due to access restrictions. However, while the full text is restricted, the **NBER working paper series metadata is public.** [The NBER WP metadata includes titles, dates, author names, abstracts, and more.](https://data.nber.org/nber-wp-logs/working_papers.tab)
 
Equipped with this metadata, I can make my own metaplots to answer some of these questions I've accumulated over the last few years... or, to translate into academic economist speak, *"I exploit unique large-scale text data from a corpus of economics papers to provide descriptive evidence on, well, a bunch of things."*

Since I'll be pulling from a grab bag of questions, [don't expect incredibly smooth transitio--](https://youtu.be/9Tnux7K3MOQ?t=71)

---

# Methods: good times for data and diff-in-diff

Two of the most common words used in the NBER abstracts are, unsurprisingly, "data" and "model". Another way to visualize the "credibility revolution" that CKZ (2020) discuss is to compare the changes in the usage of these terms. "Data" has been showing up "model" every year since 2013. 2020 is a very different picture than 1980, when "model" was more than 15 percentage points higher in abstract representation than "data". 

![data overtakes models](/post/econ-words_files/modelvdata1.png)

One fascinating and intriguing element of CKZ (2020) is the different trends in quasi-experimental techniques.^[See Figure 4 and a few of the appendix tables too.] While they show diff-in-diff (DD) at 23% and IV at 30% in 2020, the picture looks different if I perform a similar exercise with the abstracts data. I plot the % of abstracts the feature words related to diff-in-diff (DD), regression discontinuity (RD), or instrumental variables (IV).^[The relevant plot uses a Wes Anderson-inspired color palette, [which is color vision deficiency friendly](https://twitter.com/moriah_taylor58/status/1395431021051629573?s=20).]

![DD overtakes IV](/post/econ-words_files/quasi-exp-methods1.png)

It wasn't until the mid-1990's that DD or RD made their premiere on the scene of NBER abstracts. IV remained queen until 2016, when DD jumped ahead for the first time. Step aside [IV guys](https://twitter.com/rachdele/status/1392566114618589185). 

Of course, the percentages here are much smaller than in the CKZ (2020) context since I'm using public abstracts data rather than allowing terms to appear anywhere in the full text. This is not surprising; I use DD in my JMP but don't mention DD terminology in my abstract.^[If you use their full text, in fact [it looks like over 50%](https://twitter.com/AllbriteAllday/status/1392534499477450752?s=20) of papers that use quasi-experimental methods use DD methods.]

Regardless of whether we are using full text or just abstracts, both approaches demonstrate a plateau-ing of IV relative to DD.

---

# Deep cuts: some small things about economics papers

## "Exploit"

One surprising word that I see a lot in economics papers is "exploit". Economists seem to love to explain that they exploited something for the sake of their paper. I find this strange since... doesn't "exploit" have negative connotations? Of course, it's worth explaining how the term is generally used in economics papers. The below plot shows that "exploit" has become more popular over time. The plot on word pairings^[Check out [Text Mining with R](https://www.tidytextmining.com/ngrams.html) for materials on text mining.] shows that economists are usually exploiting:

- variation (often, plausibly exogenous variation)/random (assignment)/quasi(-experiments)/natural (experiments)/changes (in policy)
- new/large/unique (data)

![data overtakes models](/post/econ-words_files/econ-exploit2.png)

The increased usage of the word "exploit" is likely tied to the increased focus on finding settings that are ripe for convincing causal identification. Authors are "exploiting" variation (from policy changes, natural experiments, etc.) or the existence of useful data. They (OK, we) are using it in the sense of "to make productive use of" not "to make use of meanly or unfairly for one's own advantage".

In reading a draft of my job market paper, I realize that I now too (after balking at the term dozens of times) naturally write about "exploit[ing] variation".

## Titles

One of the most joked about conventions in academic economics papers is the *"[Catchy title]: [More detailed info]"* title. You can use the first part to get in something catchy or cutesy and the second part to remind everyone you are still a serious researcher.

Another title convention is making your title your research question. A few authors have even been [so bold as to use one-word titles.](https://twitter.com/JustinSandefur/status/1408526421560025091)

It turns out that all those parody titles with :'s or ?'s are, in fact, funny because they hit on something real. 45% of NBER titles use one of those two characters.

|convention                  | fraction of papers|
|:---------------------------|------------------:|
|title w/ question           |               0.13|
|title w/ colon              |               0.34|
|title w/ question or colon  |               0.45|
|title w/ question and colon |               0.03|

While searching for a special character in titles is simple, classifying a title as "cutesy" is not. I leave this exercise to the reader. 

I also leave the reader with this very relatable content from [Racheal Meager](https://twitter.com/economeager/status/1407755640886411266) for all of us who feel magnetically drawn to cutesy title creation,

> Nothing annoys me more than papers with cutesy titles and that's because I am always wrestling with the cutsey-title-writer within

---

# Topics: what do economists write about?

Below I illustrate the most common bigrams (duos of words) in NBER abstracts. The darker the arrow, the more frequent the bigram. The most common are: "monetary policy", "labor market" and "exchange rate". Checks out.

![most common bigrams](/post/econ-words_files/bigrams2.png)

Unsurprisingly, a paper often "suggests"/"develops"/"studies" and "covid" goes with "19". COVID-19 managed to be among one of the top bigrams for all of 1980-present due to the (understandly) high quantity of papers on the topic in the last ~1.5 years. Related papers were ~27% of April 2020 NBER working papers. Now they are about 10% of new NBER working papers.

![covid papers over time](/post/econ-words_files/covid1.png)

---

# Authors: who writes NBER papers?

While the NBER metadata does not have author race or gender in the data, I still think it's worth taking a shot at showing the demographics of NBER authors. The best I can do is to predict race from last name using US Census data and gender from first name using US Social Security Administration data. I use [Jacob Kaplan's {predictrace} R package](https://jacobkap.github.io/predictrace/articles/Predict-race-of-surname.html) to do this. (I am, therefore, limited to the categories specified by the US Census and the US SSA.) 

For each year of NBER papers, I calculate the % of authors that are predicted to belong to each racial and/or gender group. In the top panel, I show the picture over time by race and gender separately. In the bottom panel, I show the changes over time across the intersection of race and gender. These plots paint a picture that aligns with well-known facts about the demographics of the economics profession. 

![area plot showing changing demos](/post/econ-words_files/authors-nber2.png)

White men are the clear [overrepesented majority (ORM)](https://www.selfdefined.app/definitions/overrepresented-majority/). Men are overrepresented relative to women in every racial group. Notice that white women are still a larger share of NBER authors than Asian women, Black men, Black women, Hispanic men, Hispanic women, Native men, and Native women combined. Black women as well as Native men and women are not even visible in the lower panel plot. (See the [Sadie Collective website](https://www.sadiecollective.org/) to learn more about the pathway and pipeline problem for Black women in Economics.)

It's worth breaking down how the descriptive statistics from the plot align with prior research on representation in economics.

According to the name-based predictions, in 2020, ~6% of NBER authors were Black or Hispanic or Native scholars while ~28% of NBER authors were women. These percentages are close to overall faculty percentages from [(Doleac, Hengel, and Pancotti, 2021)](https://pubs.aeaweb.org/doi/pdfplus/10.1257/pandp.20211084) -- "[t]he best data available suggest that 7.3 percent of full-time faculty are URM scholars (Hoover and Washington 2020)" and "[i]n 2019, 21.2 percent of all tenure-track faculty were women, and 24.3 percent of all faculty were women (Levenstein 2020)"^[Relatedly, [Kleemans and Thornton (2021)](https://pubs.aeaweb.org/doi/pdfplus/10.1257/pandp.20211123) explain that "NBER membership as a share of full-time faculty is similar for men and women". Another closely related project is [Chari and Goldsmith-Pinkham (2018)](https://paulgp.github.io/papers/cgp_nbergender.pdf); they document representation of female economists at NBER SI 2001-2018.]

The area plot style here is similar to a recent investigation into race and gender of [Fed directors]((https://www.brookings.edu/research/diversity-within-the-federal-reserve-system/)). In terms of summary stats, eyeballing their graphs, it looks like ~30/110 (27%) directors are non-white while ~40/110 (36%) are women. The corresponding stats for NBER authors are 30% and 28%, respectively.

---

# Where are economists writing about?

As someone who regularly requests data for projects, I've always been very curious whether there is an abundance or scarcity of data in certain parts of the country. My sense is that data requesting is very path dependent -- if another researcher got data from place X, then dozens of other researchers may also request that data since it's known that it's a feasible request. What does # of papers by state or by county look like for specific topics?

Sadly, I can't observe data usage by place explicitly. But, I can at least see US state mentions in abstracts. (This could mean authors use data from the state or authors are simply discussing the state without data... though the latter would be rare in 2021.)

When I calculate state abstract mentions per million state residents, the very unsurprising result is that there's a lot of love for Massachusetts, where the NBER is located. Other top states are New York, Alaska, Rhode Island, Delaware, and North Dakota.

![US state choropleths](/post/econ-words_files/states-nber1.png)

---

# Data/Code

- NBER metadata lives [here](https://data.nber.org/nber-wp-logs/working_papers.tab) and [here](https://www2.nber.org/wp_metadata/txt/)
- [Here](https://rpubs.com/apalbright/metaplots-metadata) is my R notebook for this post
- [Here](https://github.com/apalbright/metaplots-metadata) is my Github repo 