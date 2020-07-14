---
title: Melt I.C.E. with Science 
author: 'Illustrating the Size of International Student Populations in Science & Engineering'
date: '2020-07-14'
slug: melt-ICE-with-science
categories:
  - nightingale plot
  - stacked area plot
  - flowchart
  - bar chart
tags:
  - international
  - academia
  - students
  - immigration
  - R
  - visualization
  - ICE
---

## *Breaking News*

As of 7-14-20 ~3:10pm ET via the [*Harvard Crimson*](https://twitter.com/thecrimson/status/1283116935853506560?s=20):^[According to [this](https://twitter.com/gsiskind/status/1283115441825644545) tweet thread, the government rescinded one minute into the hearing.]

> Breaking: The government has agreed to rescind DHS and ICE rules barring international students attending online universities from staying in the U.S., per a hearing this afternoon in Harvard and MIT's lawsuit against the agencies.

More important info in [this thread](https://twitter.com/ReichlinMelnick/status/1283115985608871944), including this point: *"DHS is likely going to try again with some sort of restrictions on "newly enrolling," international students, but keep those already in the US or already enrolled in schools unaffected. So stay tuned."*

# New ICE regulation

On Monday 7-6-2020, the [U.S. Immigration and Customs Enforcement (ICE) said](https://www.ice.gov/news/releases/sevp-modifies-temporary-exemptions-nonimmigrant-students-taking-online-courses-during) international students will have to **leave the United States** if their schools are not offering in-person classes in the Fall. [Harvard and MIT are suing the Trump administration over this policy.](https://news.harvard.edu/gazette/story/2020/07/higher-ed-leaders-back-harvard-mit-fight-against-ice-rules/) The US District Court will be [considering a preliminary injunction and temporary restraining order](https://www.bostonglobe.com/2020/07/10/metro/big-hearing-set-tuesday-harvard-mit-lawsuit-challenging-ice-rules-international-students/) on enforcing the ICE regulation today (7-14-20) at 3pm ET.^[[The MA AG is suing (as part of a coalition of 18 attorneys) as well.](https://www.mass.gov/news/massachusetts-ags-office-leads-multistate-lawsuit-seeking-nationwide-injunction-against-new)]

This regulation is horrifying in its [**intent**](https://www.nytimes.com/2020/07/07/us/student-visas-coronavirus.html) (and brazen lack of concern for well-being)^[From [MA AG Healey](https://www.npr.org/2020/07/08/889112795/massachusetts-attorney-general-on-new-ice-regulation-regarding-international-stu): "Under normal federal rule-making processes, they actually have to look at the impact of any proposed policy and take comments and consider things. And here, what the Trump administration is doing is essentially forcing colleges and universities to physically reopen their campuses and have students on campus in the midst of a pandemic... this is a sudden, unexplained, drastic shift to the student visa program that not only punishes the 77,000 foreign students who come to Massachusetts for education, but hundreds of thousands of students across this country."] as well as its potential **scale** -- there are about **1 million** international students studying in the US every year.^[The 1 million stat is from [this NYTimes article](https://www.nytimes.com/2020/07/10/us/f1-student-visa-lawsuit.html). Other numbers of interest: these students contribute an estimated $41 billion (stat from [NAFSA](https://www.nafsa.org/policy-and-advocacy/policy-resources/losing-talent-economic-and-foreign-policy-risk-america-cant-ignore)) to $45 billion (stat from [IIE](https://www.iie.org/Research-and-Insights/Open-Doors/Data/Economic-Impact-of-International-Students)) to our economy.] International students are not only a crucial part of our academic student communities -- in some cases, they are actually most of the academic student community! In my discipline of economics, for instance, **60% of doctoral degree earners are temporary residents** (those on student visas) rather than US citizens or permanent residents. To implement this regulation is to cruelly and illegally disrupt the majority of our peers' lives.^[As Martin Aragoneses points out [here](https://twitter.com/m_aragoneses/status/1282424586827595778), "The press has cited estimates of the financial cost of this change to be $41-45 billion dollars (roughly the GDP of Slovenia). This estimate is likely under measuring the negative effects given that it mostly reflects university tuition + expenses." Thus far unquantified is "direct harm, including financial strain, to the international students forced to leave and the future negative ramifications this may have for the U.S. economy." You can help him quantify this by responding to his survey for international students [here](https://t.co/QuwjOWjBF8?amp=1).] 

After the ICE announcement last week, I decided to use NSF data to illustrate the size of the international student population across doctoral science + engineering disciplines.^[Doctoral degrees are the highest level of academic degrees. Usually, this means a PhD (Doctor of Philosophy) but there is also the D.Sc. (Doctor of Science) and other degrees in the doctoral category for science and engineering. As such, I just say "doctoral degree" to include all relevant degrees.] My overarching goal in doing so is to illustrate the enormous impact the ICE regulation would have across doctoral science and engineering communities. While international students make up **5.5%** of the *total* U.S. higher education population^[This 5.5% stat is from [IIE](https://www.iie.org/Why-IIE/Announcements/2019/11/Number-of-International-Students-in-the-United-States-Hits-All-Time-High).], NSF data shows international students make up **38%** of doctoral degrees earned in science and engineering (using the NSF definitions + data, 2006-2016). When it comes to engineering fields, computer science, and economics, international students are consistently the majority of the doctoral student populations.

# International students in science and engineering

I recalled from [a 2015 project](https://thelittledataset.com/2015/12/31/thishttps://thelittledataset.com/2015/12/31/this-post-is-brought-to-you-by-the-national-science-foundation/-post-is-brought-to-you-by-the-national-science-foundation/)
that the NSF posts data on doctoral degree earners by citizenship, race, and ethnicity. The most recent data covers 2006-2016 and is available as table 7-4 [here](https://ncses.nsf.gov/pubs/nsf19304/data). When the NSF says citizenship, they use the categories of "temporary resident" or "US citizen or permanent resident". If the difference between these definitions isn't well known to you, you are probably (like me) in the US citizen category and thus (in a state of blissful ignorance) you don't have to know all the different definitions. Permanent residents are those with green cards, while temporary residents are those on student visas.^[International student visas include: F1 for academic studies, J1 for practical training, and M1 for vocational studies. The F1 is the most common visa type for international student studying in the US.] The ICE regulations thus impact students who fall into the temporary resident category -- I also refer to this group of students as international students. *[Please do email me if there's an issue with the temporary resident/international language -- happy to update and learn more about how to be precise and accurate with these terms.]* 

According to NSF data, 27% of all doctoral degree earners (2006-2016) were temporary residents. When it comes to science and engineering, this percentage increases to 38%. (For economics, in particular, it's 60%.) These are huge figures, especially in comparison to the broadest statistic when it comes to higher education --  5.5% of all students in the US higher education population are international. Clearly, international students make up a much larger percentage of the student population at the doctoral level than at the undergraduate level.^[The reversal of international student percentages at the undergraduate (low % international) and graduate level (high % international) was written about by the NYTimes [back in 2017](https://www.nytimes.com/2017/11/03/education/edlife/american-graduate-student-stem.html).]

## Variation by discipline

Science and engineering in the NSF definition includes disciplines ranging from social sciences like anthropology to engineering fields like aerospace engineering. As such, it's worth looking at doctoral student populations by more specific fields. I use the flowchart below to show how the NSF categorizes disciplines for context. When I discuss fields, I use the most specific field the NSF provides rather than groupings like "social science" or "engineering".

![](/post/ice-phd_files/nsf_cat.png)

First things first, I show the total number of doctoral degrees awarded 2006-2016 by discipline. I then color by the NSF citizenship category.^[I do this with a stacked area plot. In ggplot language, I facet by field and fill by citizenship.]

![](/post/ice-phd_files/phd_count_by_citizenship.png)

While the above shows the count of doctoral degree earners, another figure of interest is the percentage of each discipline's population that is international. I show these percentages over 2006-2016 using the below nightingale plot.^[A nightingale plot is really a stacked bar plot that uses just polar coordinates.]

![](/post/ice-phd_files/phd_per_by_citizenship.png)

While the two above plots show counts and percentages for each of years 2006-2016 separately, the trends over time aren't of great importance to my overarching goal for this post. So, I also simply calculate the percentage of doctoral degree earners that are international across all years 2006-2016. Those stats are represented by a simple bar plot below. I color economics orange for emphasis since that's my academic community. All engineering fields except for aerospace have a majority international doctoral student population. Computer science and economics also have majority international doctoral student populations.

![](/post/ice-phd_files/phd_per_temp.png)

Of course, the fact that less than 10% of doctoral degree earners in psychology are international doesn't mean that ICE's regulation isn't vitally important to the doctoral psychology community. Affronts to the safety and humanity of even small percentage of students are always worth fighting. Nevertheless, I hope pointing out the population compositions by discipline aids our understanding of the **vast scale of the detrimental impacts of this policy for doctoral communities**. I stand in opposition to ICE's announcement with my peers pursuing doctorates, with [HGSU-UAW at the MA State House](https://www.facebook.com/events/727054974760540/?acontext=%7B%22ref%22%3A%2229%22%2C%22ref_notif_type%22%3A%22plan_user_associated%22%2C%22action_history%22%3A%22null%22%7D&notif_id=1594602966382293&notif_t=plan_user_associated&ref=notif), and on the phone for [today's 3pm ET hearing](https://public.mad.uscourts.gov/seating-signup.html).

# `#MeltICE`^[H/t for this phrase: people at the 7-13-20 No #StudentBan Rally & [HGSU-UAW's instagram](https://www.instagram.com/hgsuuaw/?hl=en)]

- Want to support international students + oppose ICE's regulation? **Check out the action items [here](https://linktr.ee/hgsuuaw)**, put together by the [Harvard Grad Union](http://harvardgradunion.org/)!
- Important reading: Martin Aragoneses' thread on costs to international students [here](https://twitter.com/m_aragoneses/status/1282424586827595778)

# Data/Code

- The NSF data on doctoral degrees earned by citizenship is available [here](https://ncses.nsf.gov/pubs/nsf19304/data) as table 7-4.
- [Here](https://rpubs.com/apalbright/melt-ice-with-science) is my R notebook for this post -- it manipulates the NSF data into a form that is workable for making graphs and getting summary stats. 
- [Here](https://github.com/apalbright/melt-ice-with-science) is my Github repo.  