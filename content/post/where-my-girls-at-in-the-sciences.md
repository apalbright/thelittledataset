---
title: Where My Girls At? (In The Sciences)
author: ''
date: '2016-05-24'
slug: where-my-girls-at-in-the-sciences
categories:
  - scatter plots
  - line charts
tags:
  - academia
  - bias
  - coding
  - data viz
  - demographics
  - gender
  - ggplot2
  - math
  - NSF
  - national science foundation
  - phd
  - R
  - representation
  - science
  - stereotypes
  - women
---

# Intro

In the current educational landscape, there is a constant stream of calls to improve female representation in the sciences. However, the call to action is often framed within the aforementioned nebulous realm of “the sciences”—an umbrella term that ignores the distinct environments across the scientific disciplines. To better understand the true state of women in “the sciences,” we must investigate representation at the discipline level in the context of both undergraduate and doctoral education. As it turns out, National Science Foundation (NSF) open data provides the ability to do just that!

The NSF’s [Report on Women, Minorities, and Persons with Disabilities in Science and Engineering](http://www.nsf.gov/statistics/wmpd/2013/tables.cfm) includes raw numbers on both undergraduate and doctoral degrees earned by women and men across all science disciplines. With these figures in hand, it’s simple to generate measures of female representation within each field of study—that is, percentages of female degree earners. This NSF report spans the decade 2002–2012 and provides an immense amount of raw material to investigate.^[Unfortunately, we cannot extend this year range back before 2002 since earlier numbers were solely presented for broader discipline categories, or parent science categories—economics and anthropology would be grouped under the broader term “social sciences,” while astronomy and chemistry would be included under the term “physical sciences.”]

# The static picture: 2012

First, we will zero in on the most recent year of data, 2012, and explicitly compare female representation within and across disciplines.^[The NSF differentiates between science and engineering as the latter is often described as an application of the former in academia. While engineering displays an enormous gender imbalance in favor of men, I limit my discussion here to disciplines that fall under the NSF’s science category.]

<center>
<img src="/post/where-my-girls-at-in-the-sciences_files/fig1.png" alt="" width="80%" height="80%"/>
</center>

The NSF groups science disciplines with similar focus (for example, atmospheric and ocean sciences both focus on environmental science) into classified parent categories. In order to observe not only the variation within each parent category but also across the more granular disciplines themselves, the above graph plots percentage female representation by discipline, with each discipline colored with respect to its NSF classified parent category.

The variation within each parent category can be quite pronounced. In the earth, atmospheric, and ocean sciences, female undergraduate representation ranges from 36% (atmospheric sciences) to 47% (ocean sciences) of total graduates. Among PhD graduates, female representation ranges from 39% (atmospheric sciences) to 48% (ocean sciences). Meanwhile, female representation in the physical sciences has an undergraduate range from 19% (physics) to 47% (chemistry) and a PhD range from 20% (physics) to 39% (chemistry). However, social sciences has the largest spread of all with undergraduate female representation ranging from 30% (economics) to 71% (anthropology) and PhD representation ranging from 33% (economics) to 64% (anthropology).

In line with conventional wisdom, computer sciences and physics are overwhelmingly male (undergraduate and PhD female representation lingers around 20% for both). Other disciplines in which female representation notably lags include: economics, mathematics and statistics, astronomy, and atmospheric sciences. Possible explanations behind the low representation in such disciplines have been debated at length.

# Interactions between “innate abilities,” mathematical content, and female representation

Relatively recently, in January 2015, [an article in *Science*](http://science.sciencemag.org/content/347/6219/262) “hypothesize[d] that, across the academic spectrum, women are underrepresented in fields whose practitioners believe that raw, innate talent is the main requirement for success, because women are stereotyped as not possessing such talent.” While this explanation was compelling to many, another group of researchers quickly responded by showing that once measures of mathematical content were added into the proposed models, the measures of innate beliefs (based on surveys of faculty members) shed all their statistical significance. Thus, the latter researchers provided evidence that female representation across disciplines is instead associated with the discipline’s mathematical content [“and that faculty beliefs about innate ability were irrelevant.”](http://science.sciencemag.org/content/sci/349/6246/391.2.full.pdf?sid=fbf0dd62-c973-497d-902c-e1a80bfbe0ea)

However, this conclusion does not imply that stereotypical beliefs are unimportant to female representation in scientific disciplines—in fact, the same researchers argue that beliefs of teachers and parents of younger children can play a large role in silently herding women out of math-heavy fields by [“becom[ing] part of the self-fulfilling belief systems of the children themselves from a very early age.”](http://science.sciencemag.org/content/sci/349/6246/391.2.full.pdf?sid=fbf0dd62-c973-497d-902c-e1a80bfbe0ea) Thus, the conclusion only objects to the alleged discovery of a robust causal relationship between one type of belief, university/college faculty beliefs about innate ability, and female representation.

Despite differences, both assessments demonstrate a correlation between measures of innate capabilities and female representation that is most likely driven by (1) women being less likely than men to study math-intensive disciplines and (2) those in math-intensive fields being more likely to describe their capacities as innate.^[The latter viewpoint does have some scientific backing. The paper [“Nonlinear Psychometric Thresholds for Physics and Mathematics”](http://arxiv.org/pdf/1011.0663.pdf) supports the notion that while greater work ethic can compensate for lesser ability in many subjects, those below some threshold of mathematical capacities are very unlikely to succeed in mathematics and physics coursework.]

The second point should hardly be surprising to anyone who has been exposed to mathematical genius tropes -- think of all those [handsome janitors who write up proofs on chalkboards](https://www.youtube.com/watch?v=N7b0cLn-wHU) whose talents are rarely learned. The second point is also incredibly consistent with the assumptions that underlie "the cult of genius" described by Professor Jordan Ellenberg in [*How Not to Be Wrong: The Power of Mathematical Thinking*](http://www.jordanellenberg.com/how-not-to-be-wrong/) (p.412):

> The genius cult tells students it's not worth doing mathematics unless you're the best at mathematics, because those special few are the only ones whose contributions matter. We don't treat any other subject that way! I've never heard a student say, “I like Hamlet, but I don't really belong in AP English—that kid who sits in the front row knows all the plays, and he started reading Shakespeare when he was nine!”

In short, subjects that are highly mathematical are seen as more driven by innate abilities than are others. In fact, describing someone as a hard worker in mathematical fields is often seen as an implicit insult—an implication I very much understand as someone who has been regularly (usually affectionately) teased as a “try-hard” by many male peers.

# The dynamic picture: 2002–2012

Math-intensive subjects are predominately male in the static picture for the year 2012, but how has the gender balance changed over recent years (in these and all science disciplines)? To answer this question, we turn to a dynamic view of female representation over a recent decade by looking at NSF data for the entirety of 2002–2012.

<center>
<img src="/post/where-my-girls-at-in-the-sciences_files/fig2.png" alt="" width="100%" height="100%"/>
</center>

The above graph plots the percentages of female degree earners in each science discipline for both the undergraduate and doctoral levels for each year from 2002 to 2012. The trends are remarkably varied with overall changes in undergraduate female representation ranging from a decrease of 33.9% (computer sciences) to an increase of 24.4% (atmospheric sciences). Overall changes in doctoral representation ranged from a decline of 8.8% (linguistics) to a rise of 67.6% (astronomy). The following visual more concisely summarizes the overall percentage changes for the decade.

<center>
<img src="/post/where-my-girls-at-in-the-sciences_files/fig3.png" alt="" width="90%" height="90%"/>
</center>

As this graph illustrates, there were many gains in female representation at the doctoral level between 2002 and 2012. All but three disciplines experienced increased female representation—seems promising, yes? However, substantial losses at the undergraduate level should yield some concern. Only six of the eighteen science disciplines experienced undergraduate gains in female representation over the decade.

The illustrated increases in representation at the doctoral level are likely extensions of gains at the undergraduate level from the previous years—gains that are now being eroded given the presented undergraduate trends. The depicted losses at the undergraduate level could very well lead to similar losses at the doctoral level in the coming decade, which would hamper the widely shared goal to tenure more female professors.

The change for computer sciences is especially important since it provides a basis for the vast, well-documented media and academic focus on women in the field.^[[Planet Money](https://www.npr.org/sections/money/2014/10/21/357629765/when-women-stopped-coding) brought the decline in percentage of female computer science majors to the attention of many in 2014.] The discipline experienced a loss in female representation at the undergraduate level that was more than twice the size of that in any other subject, including physics (-15.6%), earth sciences (-12.2%), and economics (-11.9%).

While the previous discussion of innate talent and stereotype threat focused on math-intensive fields, a category computer sciences fall into, I would argue that this recent decade has seen the effect of those forces on a growing realm of code-intensive fields. The use of computer programming and statistical software has become a standard qualification for many topics in physics, statistics, economics, biology, astronomy, and other fields. In fact, completing degrees in these disciplines now virtually requires coding in some way, shape, or form.

For instance, in my experience, one nontrivial hurdle that stands between students and more advanced classes in statistics or economics is the time necessary to understand how to use software such as R and Stata. Even seemingly simple tasks in these two programs requires some basic level of comfort with structuring commands—an understanding that is not taught in these classes, but rather mentioned as a quick and seemingly obvious sidebar. Despite my extensive coursework in economics and mathematics, I am quick to admit that I only became comfortable with Stata via independent learning in a summer research context, and R via pursuing projects for this blog many months after college graduation.

The implications of coding’s expanding role in many strains of scientific research should not be underestimated. **If women are not coding, they are not just missing from computer science—they will increasingly be missing from other disciplines which coding has seeped into.**

# The big picture: present `$\rightarrow$` future

In other words, I would argue academia is currently faced with the issue of improving female representation in code-intensive fields.^[On a positive note, atmospheric sciences, which often involves complex climate modeling techniques, has experienced large gains in female representation at the undergraduate level.] As is true with math-intensive fields, the stereotypical beliefs of teachers and parents of younger children [“become part of the self-fulfilling belief systems of the children themselves from a very early age”](http://science.sciencemag.org/content/sci/349/6246/391.2.full.pdf?sid=fbf0dd62-c973-497d-902c-e1a80bfbe0ea) that discourage women from even attempting to enter code-intensive fields. These beliefs when combined with Ellenberg's described "cult of genius" (a mechanism that surrounded mathematics and now also applies to the atmosphere in computer science) are especially dangerous.

Given the small percentage of women in these fields at the undergraduate level, **there is limited potential growth in female representation along the academic pipeline** -- that is, at the doctoral and professorial levels. While coding has opened up new, incredible directions for research in many of the sciences, **its evolving importance also can yield gender imbalances due to the same dynamics that underlie underrepresentation in math-intensive fields.**

---

# Speaking of coding...

See my ["women_in_sci" Github repo](https://github.com/apalbright/women_in_sci) for all data and R scripts needed to reproduce these visuals.

# Acknowledgements

I thank Ally Seidel for all thorough edits over the past few months. Also, thanks to members of _NYC squad_ for listening to my ideas and debating terminology with me.