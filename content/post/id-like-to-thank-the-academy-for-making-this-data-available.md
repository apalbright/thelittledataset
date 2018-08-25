---
title: I’d Like to Thank the Academy…
author: 'for making this data available'
date: '2015-02-19'
slug: id-like-to-thank-the-academy-for-making-this-data-available
categories:
  - heat maps
tags:
  - data viz
  - oscars
  - awards
  - gender
  - ggplot2
  - heat tables
  - heat maps
  - movies
  - R
  - speeches
  - stata
---

# Intro

The Oscars, like most award shows, are a mixture of the scripted and the unscripted. While the skeleton of the show rests upon the predetermined quips of the host and award presenters, the flesh of the Oscars rests within the surprise wins that are embodied by acceptance speeches given by excited, nervous, and often emotional award winners. Every year there are dozens of Oscar speeches and this year I began to wonder what one could glean from all that information abstractly balled up into little packages of "thank you"s and "wow"s and "I love you, mom"s that are spilled out onto the stage year after year.

Previous inquiries into Oscar speeches have investigated [whom people thank](http://www.slate.com/articles/arts/movies/2014/02/oscar_acceptance_speeches_who_thanks_spouses_agents_directors_and_oprah.single.html) while on stage as well as the [counts associated with certain phrases](https://www.theguardian.com/film/filmblog/2013/feb/19/oscars-2013-academy-acceptance-speech) such as “Wow,” “England,” and even “Oprah.” However, a topic that has not been deeply investigated is how features of acceptance speeches differ across groups of winners. For instance, with respect to word count, it is certain that the most-hyped awards (Director, Best Picture, Best Actor, etc.) have speeches with higher word counts than others since the threat of [being "played off"](https://www.youtube.com/watch?v=0laun_MxqRc) is not as looming for the sparkling celebs as it is for the sincere, but not-Dior-wearing, Documentary Filmmakers. On the other hand, I was less certain about how Best Director speech lengths would compare to Best Picture speech lengths--they are definitely shorter than Best Picture but longer than Visual Effects, however, the specifics have not been previously documented.

Another element of speeches that I thought would be interesting to investigate is the usage of words that are explicitly self-referential, such as “I” or “me,” as opposed to words that reference one’s part of a larger group, such as “we” or “us.” Comparing the percentages of self-related words to the percentages of team-related words could tell us something about the degree to which certain awards are self-oriented or team-oriented.

# Approach

To address both the element of word count as well as the element of the self vs. the team, I used the Academy [Awards Acceptance Speech Database](http://aaspeechesdb.oscars.org/) (yes, that is a thing!) to collect the transcripts of all acceptance speeches given over the past 5 years (that is, speeches given during the Oscars 2010-2014) and looked into four specific statistics by award winner category.

The four statistics^[In order to measure "I.Percent," my Stata code counted the number of instances of “I ”, “I’”, “me ”, “my ”, “My ”, "Me ", and “myself” (self-words) in a speech and calculated that number as a percentage of the total speech word count. In order to measure "We.Percent," my code followed the same process as that described for "I.Percent" with respect to instances of “We ”, “we ”, “our ”, "Our ", “ourselves”, “us ”, "we'", and "We'" (group-words). The measure "Self.Ratio" divided the count of self-words by the count of group-words in order to create a quasi-measure of self-involvement.] are as follows:

1. Average word count ("Word.Count")
2. Average percentage of words related to the self ("I.Percent")
3. Average percentage of words related to the group ("We.Percent")
4. The ratio of self-words to group-words, which can then function as a quasi-measure of self-involvement ("Self.Ratio")

# Results by award categories

See the heat table below (made using the [ggplot2](https://cran.r-project.org/web/packages/ggplot2/ggplot2.pdf) package in R) for the averages of these four statistics across all award categories^[In 2012, Woody Allen was not present to accept the Writing (Original Screenplay) award. Counting that event as 0 words spoken for the category yields the average shown above while excluding that event from the average yields a modified average of 167.8 words for the category.]^[Two teams were awarded the Sounding Editing Oscar in 2012. I calculate the average per team speech, thus, these two speeches were treated as though they were in separate years. I did this in order to avoid overestimating words spoken within this category.]:

<img src="/post/id-like-to-thank-the-academy-for-making-this-data-available_files/oscarplot.png" alt="" width="80%" height="80%"/>

Far from surprising, the speeches with the highest word count are Best Picture, Actress in a Leading Role, and  Actor in a Leading Role. The awards with the highest I.Percent are Actor in a Leading Role, 8.8%, Short Film (Live Action), 8.7%, Writing (Original Screenplay), 8.6%, Cinematography, 8.4%, and Actress in a Leading Role, also 8.4%. However, it is notable that neither Actor in a Leading role nor Actress in a Leading Role are in the group with the highest Self.Ratio, instead, the awards with the highest Self.Ratio are Foreign language Film, 8.8, Short Film (Live Action), 7.9, and Writing (Original Screenplay), 7.3. The fact that Foreign Language Film has the highest Self.Ratio is very surprising since that is the equivalent of the Foreign Best Picture, which should be discussed on stage as an extremely collaborative venture. (It is possible that part of this is due to language barriers since, for non-native speakers, it is more difficult to switch between the subjects "we" and "I" than to just stick with "I.") On the other end of the spectrum, the most team-oriented award categories (using the Self.Ratio metric) are Documentary (Short Subject), 0.5, Sound Mixing, 1.1, Visual Effects, 1.2, Short Film (Animated), 1.2, and Makeup/Makeup and Hairstyling, 1.2.

# Results by gender/actor

Though I was originally primarily interested in the averages of these statistics over the award winner categories, I realized I could also investigate these same statistics over four gender-actor categories: Female Actor, Female Non-Actor, Male Actor, Male Non-Actor. Using this breakdown, I was curious to see whether male and female actors as well as male and female non-actors would have similar statistic averages.

<img src="/post/id-like-to-thank-the-academy-for-making-this-data-available_files/genderactor.png" alt="" width="70%" height="70%"/>

It is immediately evident from the heat table that both genders of actors possess very similar numbers across all four statistics. Meanwhile, the Male Non-Actors speak almost twice as much as the Female Non-Actors, 136.4 words compared to 76.5 words. Therefore, outside of the actors, if you've ever thought that women don't speak as much as men during acceptance speeches the Oscars, this is **not just a consequence of fewer female award winners**--no, this means that even when women do win an award, they, on average, only speak half as much as the men who win. I would hypothesize this is because women rarely speak during the non-acting awards with the longest word counts--the Best Picture and Directing Oscars (In fact, [only one woman has ever won the Directing Oscar](https://fivethirtyeight.com/features/directing-is-even-more-of-a-boys-club-than-you-may-realize/)). The fact that women often don't get to speak in these two large categories probably makes a significant difference in the non-acting word count averages. Furthermore, this gender word count difference could also be due to the fact that, since women often win non-acting awards within a larger team, men on the team speak first and use up some of the team's shared time, leading to a shorter word count for women's speeches.

The heat table also makes evident that Actors possess higher Self.Ratios than Non-Actors and Male Non-Actors have a noticeably higher Self.Ratio than Female Non-Actors, 2.8 compared to 1.6. This implies that women outside the sphere of acting are more likely than their male counterparts to use words that emphasize the greater team effort. Part of this difference could, again, be due to the fact that women are more likely to share awards than men, meaning their acceptance speech lexicon reflects this circumstance.

# More on gender

Due to the obvious differences between non-actor men and women, I decided to delve deeper into the question of gender in acceptance speeches. Instead of looking into words spoken per speech, I now look at aggregate words spoken during the acceptance speeches of the past five years of award ceremonies. Male and female actors have spoken very similar amounts, with 2,718 words spoken by female actors and 2,752 words spoken by male actors. On the other hand, the distinction between non-actors is striking but unsurprising if you've paid attention to who you are always listening to when watching the show--**while 2,065 words have been spoken by female non-actors, 12,416 words have been spoken by male non-actors**. See below for a simple visualization of these differences:

<img src="/post/id-like-to-thank-the-academy-for-making-this-data-available_files/pie.png" alt="" width="80%" height="80%"/>

These numbers mean that **outside of the case of the actors, men have spoken more than six times as many words as women in acceptance speeches over the past five years of Oscar ceremonies**. Even more disturbing is that, over the past five years, the total number of words spoken by female actor winners, 2,718, is greater than the number of words spoken by all other women during the rest of the acceptance speeches, 2,065 words. It is clearly troubling that the two awards that necessitate female winners generate more words spoken by women than do all other awards.

It is a well-known fact that more many [more men win awards than women](https://medium.com/silk-stories/why-oscar-is-a-male-a-data-driven-analysis-of-gender-representation-in-87-years-of-academy-awards-837ddd812d27). Specifically, in the past five years, the winners list includes 141 men and 39 women (excluding Best Picture and Foreign Language Film since these are not awards for individuals). When excluding the two male actors and two female actors that win every year, that becomes 131 men and 29 women. However, as I illustrated in the second heat table, even when women win in non-actor categories, they still talk significantly less than the men who win non-actor categories (approximately half as much).

I mentioned previously that I thought this could be because when women win in non-actor categories, a team often accepts the award, which might lead to women being talked over by men. Well, while men tend to speak first, it is not as egregious as one might think--it turns out that in the past five years there were 16 instances in which at least one man and one woman spoke on the stage in order to accept an award together. In 11 of these 16 instances, a man spoke first to begin accepting the award. As Elinor Burkett exclaimed, after her male co-winner spoke, in her 2009 Documentary (Short Subject) acceptance speech:

> Don't you like that the man never lets the woman talk. Isn't that just the classic thing?

In short, it is worth realizing that women are not just underrepresented in terms of their number of Oscar wins, they are also underrepresented by the number of words they are able to speak on behalf of their own victories.

---

# Code/Data

All scripts and data files necessary to recreate the included visualizations are available in my ["Oscars" Github repo](https://github.com/apalbright/Oscars).

# Future work

- Add more years into this analysis (so that it spans more than 5 years of data)
- Look into coding race variables on top of gender and actor variables
- Does speech length serve as a type of proxy for how much viewers care about each award?^[One could easily imagine a model of the Oscars in which over the years past winners have spoken for as long as possible until they are cut off (due to lack of time and more interest in another award). Then, over time the award winners learn their category’s limit to keep the audience interested. However, would word count be a perfect measure of how much we care about awards in comparison to one another? For instance, if the word count of Best Picture acceptance speeches are three times as long as Best Supporting Actress speeches, does that really mean that viewers care three times as much about Best Picture as they do about Best Supporting Actress?]