---
title: Anxious Optimization
author: ''
date: '2016-10-26'
slug: anxious-optimization
categories:
  - models
tags:
  - anxiety
  - economics
  - existential
  - grades
  - maximization
  - model
  - optimization
  - tests
  - time
---

On the morning of my dynamic programming midterm, I tried to calm myself by recalling the golden rules of grad school that have been passed down through the generations[^1]:

> grades don't matter... nothing matters.

However, I quickly realized that by adopting this perspective **I was simply subbing out test anxiety for existential anxiety.** And, come to think of it, the latter didn't seem to be helpful, while the former could actually aid in my short-term goals -- namely, jotting down lots of equations into a collection of small blue booklets.

In considering the roles that angst can play in day-to-day life, **I started to become curious about whether I could model optimal choices of anxiety using dynamic programming techniques.** Allow me to channel my inner Ed Glaeser[^2] using David Laibson-esque framework[^3] and wax poetic on the specifics of something you could call (using very flexible terminology) an "economic model."

# Let's Assume...

Assume that anxiety has some negative cost (say to my overarching mental health), however, its presence in my life also often gets me to achieve goals that I do genuinely want to achieve. Therefore, anxiety factors into my personal utility function in both positive and negative ways. In other words, it is not some force in my life that I want to erase entirely since it can lead to incredibly positive outcomes.

Let's say, for the sake of model simplicity and for the sake of accuracy since I'm in academia now[^4], that my utility function is simply equated to my academic success. Imagine that academic success is some definable and quantifiable concept--we could define this as some weighted average of number of papers published in quality journals, number of good relationships with faculty members, etc. 

Let's also assume that this type of success that is a function of (and increasing in) two items: idea creation and execution of ideas. This seems reasonable to me. The next piece is where the real controversial and strict assumptions come in with respect to anxiety: I assume that idea creation is a function of (and increasing in) existential anxiety, while execution is a function of (and increasing in) time/test anxiety. Assume that the functions with respect to the anxiety types have positive first derivatives and negative second derivatives--this is equivalent to assuming concavity.[^5]

Then, given these assumptions and the framework of dynamic programming, the optimization problem of interest is equivalent to solving a maximization problem over the lifecycle.

<img src="/post/anxious-optimization_files/max_prob.png" alt="" width="90%" height="90%"/>

Explicitly solving this optimization problem requires more assumptions about functional forms and the like. (Ed, I'm open to your ideas!) Sure, it'd be much simpler to somehow make this a one variable maximization problem -- a transformation we are often able to achieve by exploiting some budget constraint and Walras' law -- however, I do not believe that anxiety measures should add to some value beyond human choice. Other potential questions: Do we think our state variables follow an Ito process? I.e., I could see the existential anxiety variable following geometric Brownian motion since drift maybe should rise exponentially with time?

# Back to Reality

An implication of my model build that comes straight out of my assumptions (don't even need first order conditions for this) is that I should not be thinking about how "nothing matters" when there's an upcoming test. A test falls into the category of execution tasks, rather than the realm of idea creation. The existential anxiety that grows out of repeating the mantra "nothing matters" to myself over and over would only be helping come up with ideas... In fact, this whole model idea and post did come from continuing down the path of some existential thought process! So, perhaps the real question should be: is my blogging engrained in weighted average measure for "academic success"? 

If so, I'm feeling pretty optimized.

[^1]: Thank you to the G2's (second-year's) for the soothing (yet still terrifying) words in your recent emails.

[^2]: Ed Glaeser is our Microeconomics professor of "verbal problem" fame.

[^3]: David Laibson is our Macroeconomics professor for the "dynamic programming" quarter of our sequence

[^4]: I kid, I kid. I'm off to a frisbee tournament for this entire weekend, so clearly my utility function must be more complex.

[^5]: Note: In reality, there is most definitely some level of both angsts that stops being productive... noting that this is the case calls for more complex assumptions about the functional forms beyond assuming simple concavity... suggestions are welcome!
