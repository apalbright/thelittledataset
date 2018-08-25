---
title: On Ego and Sharing Ideas
author: ''
date: '2017-10-12'
slug: on-ego-and-sharing-ideas
categories:
  - models
  - line charts
tags:
  - behavioral economics
  - behavior
  - ideas
  - economics
  - belief-based
  - class participation
  - ego
  - psychology
  - self-image
  - ride share
  - utility
---

# A behavioral Nobel means a behavioral blog post

In honor of Richard Thaler's [recent Nobel prize win](https://www.nobelprize.org/prizes/economics/2017/press-release/), I give you a post on a behavioral economics topic! Welcome to round 2 of *A G2 Talks Models.* Today's topic: ego utility and the decision to speak up in class à la [Koszegi 2006](/post/on-ego-and-sharing-ideas_files/k06.pdf), an approach to belief-based utility adapted from *Psychology and Economics* lecture.

# An admission of ego

I have a confession to make. I want you to think I'm smart. There, I said it. It is important to my self-image that you (yes, you on the other side of this screen!), my academic peers, and even the man (boy?) who tipsily mansplained [the Monty Hall problem](https://en.wikipedia.org/wiki/Monty_Hall_problem) to me perceive me as intelligent. That is, intelligence as signaled by the occasional insightful comment, deep question, or quality idea that I get up the nerve to share.

Classrooms are environments in which lots of signaling of such smarts takes place. Professors ask questions, both rhetorical and not. They let us marinate in pregnant pauses and make a call for ideas. There's a beat in which the tiny neuron-bureaucrat who is tasked with managing and organizing my brain activity files through some nascent concepts and responses. *Is this any good?*, she asks. Her supervisor isn't sure either. *Is this relevant? Yeah, but, is it too obvious?* The supervisor prods her saying, *time is of the essence*. Internal hesitation over whether or not to share an idea in class still plagues me even after multiple decades of participation in the exercise. However, the difference is that now, in 18th grade, I can explicitly model that very idea-sharing decision.

# A twist on classical utility: Enter ego...

To model this decision, I enter into a belief-based utility world. I define my utility function as follows: `$u = r - e + g√p$`, with `$r$` being the classroom response to the idea, `$e$` being the effort cost of sharing the idea, `$p$` being the probability that I think it's a quality idea, and `$g$` being a parameter for "ego utility." In classical utility world, this `$g√p$` term would not exist; I would simply weigh the benefit of sharing the idea `$r$` and the cost of sharing the idea `$e$`. Moreover, in a departure from classical economics assumptions, this form of belief-based utility displays information aversion, thus the square root on the `$p$`.

Now, let's run through the outcomes based on class participation or class non-participation. If I take the jump and share my idea, I always expend some amount of effort `$e>0$`. Meanwhile, the benefit I derive depends on the ex post observable quality of the idea, as measured by the classroom response. If the idea was high quality, I gain `$r=1$`. If instead it was lacking or, shall we say, *basic*, I gain `$r=b$` where `$1>b>0$`. If I keep my thoughts to myself, then `$e=0$` and `$r=0$`.

In effect, if I share my idea, I receive `$u = p(1-e+g√1) + (1-p)(b-e+g√0)$`. The first term on the right hand side is my perceived probability that the idea is of high quality multiplied by the associated payoff, while the second term is my perceived probability that the idea is basic multiplied by that associated payoff. Rearranging terms, `$u = p(1+g) + (1-p)b - e$`. Meanwhile, if I stay silent, my payoff is simply `$u = g√p$`.

Using this simple framework, I will share my idea with the class if and only if `$p(1+g) + (1-p)b - e > g√p$`. Simplified, I share my idea if and only if `$g(p-√p) + p + (1-p)b - e > 0$`.

Given this inequality, we can see that if `$g$` goes to infinity (i.e., my ego utility is huge), and `$p$` is not `$0$` or `$1$`, the inequality will never hold, as `$p-√p$` will always be negative (since `$p$` is a fraction between `$0$` and `$1$`); this means I will never raise my hand to share my ideas because I am so paralyzed by my massive ego utility. Meanwhile, as `$p$` approaches `$0$` or `$1$`, the `$g(p-√p)$` term goes to `$0$`, leaving the decision up to the inequality `$p + (1-p)b > e$`. Thus, I will speak if the expected value of the payoff to my comment exceeds the effort cost. (Recall that this is exactly what I do in the classical utility case in which I have no ego utility.)

While both of these two above conclusions seem predictable, there is a notable intriguing prediction from this model. You might expect that the greater my perceived probability that the idea is high quality, the more likely I am to share the idea. Well, this is not true. In other words, **there is non-monotonicity in `$p$`.** Say I have a moderate level of ego utility `$g$` and my `$p$` grows from a low to a higher level. This positive change in `$p$` could cause me to put my hand down even though now I am more confident in the quality of my idea. Weird! **Ego utility allows there to be a negative correlation between my confidence in my idea's quality and my willingness to share said idea.**

Intuitively, as I become more confident in an idea, not only is there is a higher expected benefit to sharing the idea but there is also a higher possible loss of utility due to the ego utility term. **The way these two opposing effects spar with one another can lead my hand to go up, down, and up again as my confidence in an idea increases.**

Let's illustrate this surprising concept graphically. We can parametrize the model and make visually explicit how the decision to my raise hand changes with `$p$`. Let's set `$g=3$`, `$b=0.5$`, `$e=0.01$`. Given these values, I will speak my idea if and only if `$3(p-√p) + p + (1-p)0.5 - 0.01 > 0$`. I.e., iff `$3.5p - 3√p + 0.49 > 0$`. As such, I can graph the utility function with the full range of possible `$p$` values from `$0$` to `$1$` and accordingly color areas depending on whether or not they correspond to sharing an idea. (I share an idea if the utility function yields a value greater than or equal to `$0$`; otherwise, I do not.)

![](/post/on-ego-and-sharing-ideas_files/share.png)

The above illustrates that I am willing to share an idea when my probability that it is high quality is very low, but that I am no longer willing once the probability is a more moderately low value. This is evidence of the non-monotonicity in `$p$` in this model; I might lower my hand in class to protect my ego.

# Anecdotal evidence, dynamics, and blog posting

I find ego utility fascinating and very believable when reflecting on my own experiences. For one, I have noticed that I often become more silent as conversation topics sway from topics in which I am novice to topics that I am moderately more knowledgable about. I feel acutely aware of the aforementioned tensions in the model; yes, I am more confident in my ideas in this realm, but I now have more to lose if I choose to share them. This is also a hesitation I feel internally when I talk with professors and friends about ideas. If the idea is undeveloped, there is really no harm in sharing it (`$p$` is low at that point); but, if I have been working on it and have a higher `$p$`, now, there is a chance I might realize that my idea was not up to snuff. In this sense, I can sometimes feel myself keeping ideas or projects to myself, as then they can't be externally revealed to be low quality. I can sit on the sidelines and nurture my pet projects without a care in the world, stroking the ego-related term in my utility function.

But, in a more complex model, perhaps one that better represents my reality, idea quality is improved with idea sharing and collaboration. The model at hand is a one-shot game. I have an idea and I decide whether or not to share it. (The end.) But, in my flesh-and-blood/Stata-and-R universe, ideas do not disappear after that first instance of sharing; they develop dynamically. If I imagine refitting the model to mimic my reality, it is clear that silence for ego appeasement is a strategy that does not pay off long term...

I like to think that this is one reason why I write these posts -- to share and accordingly develop ideas. In fact, when I started sharing R code online almost three years ago I was such a novice that I had a very low `$p$` regarding my data visualization capacities. In this way, ego utility was not able to hold me back from openly sharing my scripts. I was a strong advocate for transparency (still am) and at that time didn't mind at all if my code looked like ["a house built by a a child using nothing but a hatchet and a picture of a house."](https://xkcd.com/1513/) However, if I were to imagine starting blogging now, I could see holding off, as I perceive my probability of being a decent coder as much larger than I did three years ago.

In the end, I am very happy that I chose to start sharing my work when I had a very small `$p$`. In fact, if you squint really hard, you can probably see me lounging on the utility function curve, fumbling to use [ggplot2](https://ggplot2.tidyverse.org/), somewhere in that first blue chunk of the graph.

---

# Credit

This post adapts model mechanics from [Koszegi 2006](/post/on-ego-and-sharing-ideas_files/k06.pdf). A *Psychology and Economics* lecture  inspired and informed this piece. 

# Code

Lastly, [here](http://rpubs.com/apalbright/ego-utility-plot) is the R notebook used to create the graphic in this post.