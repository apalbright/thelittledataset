---
title: The Multidimensional Success of Pixar Films Visualized
author: ''
date: '2015-06-30'
slug: the-multidimensional-success-of-pixar-films-visualized
categories:
  - bubble charts
tags:
  - aging
  - ggplot2
  - data viz
  - imdb
  - inside out
  - pixar
  - movies
  - nostalgia
  - R
  - rotten tomatoes
  - success
  - film
---

# Get the popcorn

Last Wednesday, as I watched the letter "I" flattened by a familiar squeaky little lamp, I found myself, for the first time in half a decade, about to enter a new Pixar universe. I hadn’t seen a Pixar film in theaters since Toy Story 3 -- a movie revolving around a boy’s departure to college that was released the same summer my high school graduate cohort and I were also due to leave behind plush bunnies and Hess trucks in pursuit of profound academic knowledge…and a few beers. Now, five years later, I was watching Inside Out, another movie that felt meaningfully-timed due to its release around my one-year anniversary of college graduation. As time has passed since those four years of accelerated, electric activity, we are all left wondering which memories will inevitably roll down into the dusty abyss of lost moments and which will solidify their spots as core memories, turning within our own mental [Kodak Carousels](https://www.youtube.com/watch?v=suRDUFpsHus&feature=youtu.be&t=1m20s).

This [train of thought](http://www.pixarpost.com/2015/01/Train-of-Thought-Concept-Art.html) led me to ponder not only key moments in my own lifetime but also those in the Pixar feature film universe’s almost 20-year existence. Considering all 15 movies Pixar has created and released, are some doomed for the abyss of our collective memory while others are permanent pillars of the Pixar canon? In other words, **how do the individual units within this manifold collection of films stack up against one another?** Moreover, **how can we visualize Pixar's trajectory over the past two decades?**

# Pixar and metrics of success

In attempting to illustrate Pixar's evolution over time, I am inclined to use "success" as a metric of interest. Pixar is considered wildly successful—but how do we define success given its multidimensional nature? Well, for one, success is often substantiated through winning awards. Even Pixar’s first movie, Toy Story, which was released in November 1995, proceeded to receive a Special Achievement Academy Award for being the first feature-length computer-animated film, and this was years before the introduction of the Best Animated Film Academy Award in 2001. In fact, since the latter's inception, Pixar has won the award for Best Animated Film 7 out of 14 years, despite only releasing films in 11. Other meaningful metrics of success include quality ratings, such as those maintained by [Rotten Tomatoes](https://www.rottentomatoes.com/m/toy_story/) and [IMDb](https://www.imdb.com/title/tt0114709/), and... of course, money. Thus, in tracing out Pixar's success, we consider three dimensions of success: award victories (Best Animated Film Academy Award wins), quality ratings (we treat Rotten Tomatoes % Fresh as a measure of critical acclaim and IMDb ratings as a measure of public acclaim), and commercial success (Opening Weekend Gross).[^1]

# A path lined with multidimensional success

In order to map out Pixar’s trajectory, we plot all 15 movies released by Pixar using differing colors and sizes of data points in order to represent all three aforementioned dimensions of success. In this graph, the main focus of interest is the % Fresh Rotten Tomatoes rating, which specifies what percentage of critic reviews' were positive.[^2] This metric accurately separates out those regularly cited as subpar Pixar movies: Cars, Cars 2, Brave, and Monsters University. We use locally weighted scatterplot smoothing ("loess") to fit a curve to the dataset, thus charting the movement of % Fresh over time. The loess curve shows us that Pixar took a dip in critical acclaim between 2010 and 2015--what with the release of Cars 2, Brave, and Monsters University--however, **Inside Out's release has tugged the loess curve back up to pre-2011 levels!**

<figure>
<center>
<img src="/post/the-multidimensional-success-of-pixar-films-visualized_files/pix11.png" alt="" width="85%" height="85%"/>
</center>
</figure>

In this sense, *Inside Out* marks a return to the Pixar of emotive toys and robots—not to mention the [most sob-inducing 4 minutes](https://www.youtube.com/watch?v=F2bk_9T482g) in all of animated film history. The above plot also illustrates Pixar's success at the Oscars, with films depicted by blue points as Best Animated Film Academy Award winners. Lastly, in terms of opening weekend gross, we can see that despite being on the lower end of quality ratings, the disappointing movie grouping of *Cars*, *Cars 2*, *Brave*, and *Monsters University* did not make less money during opening weekend than other films. In fact, in comparing these four films to the other 5 films released since 2005, the average opening weekend gross is actually larger -- $79.46 million rather than $75.78 million.

Pivoting from a measure of critical acclaim to a measure of public acclaim in the quality realm, we now plot the same dimensions of success as defined before but we substitute IMDb scores for the Rotten Tomatoes % Fresh metric. This set of scores also suggests mediocrity in *Cars*, *Cars 2*, *Brave*, and *Monsters University* -- however, it also puts *A Bug’s Life* in the same subpar quality category. Again, we use a loess regression line to exhibit the movement in quality ratings of Pixar movies over time. As was the case before, this line also provides evidence of a return to the old Pixar.

<figure>
<center>
<img src="/post/the-multidimensional-success-of-pixar-films-visualized_files/pix21.png" alt="" width="85%" height="85%"/>
</center>
</figure>

However, there is one element to note about the nature of IMDb scores--that is, [they are often higher when a film is just out](https://www.quora.com/Are-the-IMDB-ratings-accurate). This is because the first people to see and rate films are the hardcore fans, which therefore contributes to a "hype effect," superficially inflating the aggregate rating. This could potentially be an issue in currently measuring the public acclaim of *Inside Out*, as its rating will likely fall to *WALL-E* / *Up* levels as months pass.

Despite this particular caveat, the graph still serves as evidence of an improvement in Pixar film quality following its recent senior slump (~ ages 15-18) -- an improvement that is fitting since, in a few months, we will be able to welcome Pixar to the world of 20-somethings, the beginning of a new decade in which we are content to forget about the mishaps of adolescence.

# Roll the credits

In short, Pixar has faltered in its adolescence, sometimes producing movies that fail to depict the nuanced emotions that color the memories organized within our seemingly endless stockpiles of human experiences. However, just like the wonderfully colored marbles of memories in the Pixar universe, these fifteen films exist within the collective memory as works of art that are, no doubt, greater than the sum of their tangible metrics of success. If Joy herself were to project my memory of *Toy Story* in the headquarters of my brain, I would not see a small black data point—I would see “Andy” written on the bottom of Woody’s boot and feel something that is beyond a simple, neat linear combination of joy and melancholy—something beyond my or Pixar’s capacity for visualization… Something you can’t even see with 3-D glasses.

---

# Visualization update

Thanks to [discussion of the above graphs](https://www.reddit.com/r/dataisbeautiful/comments/3bndes/20_years_of_pixar_films_visualized_oc/) in the [/r/dataisbeautiful](https://www.reddit.com/r/dataisbeautiful/) universe, I have been made acutely aware of improvements that should be made to my visualizations. In particular, there are two issues from my previous work that are worth quickly addressing:

1. In my original visualizations, area is scaled non-linearly with the opening weekend gross data. This was a rookie mistake on my part, especially considering that one of the first things the [Wikipedia "Bubble chart" article](https://en.wikipedia.org/wiki/Bubble_chart) explains is that, "if one chooses to scale the disks' radii to the third data values directly, then the apparent size differences among the disks will be non-linear and misleading." As [/u/FlailingMildly](https://www.reddit.com/user/FlailingMildly) explained, "It looks to me like the diameter of the points scales with opening weekend gross (110 looks roughly twice as wide as 50). However, our brain doesn't look at diameter, it looks at area. So the 110 looks more than four times as large as the 50." 

2. The blue lines from the original graphs are loess curves, or locally weighted scatterplot smoothings. I reasoned that this choice of smoothing was acceptable as an exploratory feature since the original paper that developed loess explains that: ["The first (major use of this local-fitting methodology) is simply to provide an exploratory graphical tool."](http://www.stat.washington.edu/courses/stat527/s13/readings/Cleveland_Delvin_JASA_1988.pdf) However, I knew it could be argued that this curve is over-fitted and better for the purposes of prediction than for conceptual modeling. In the end, individuals on the subreddit came to the conclusion that, in this particular case, the loess curves are not useful since the graph is easy to read without any type of smoothing method. In short, the overarching consensus was that this type of curve is best used for smoothing noisy data--a category to which my Pixar csv file definitely does not belong!

In order to address these genuine issues, I made two quick changes to the previous graphs:

1. I scaled opening weekend box office gross to the area of the circles rather than to their radii

2. I excluded the blue loess curves

See the new graphs below.

<figure>
<center>
<img src="/post/the-multidimensional-success-of-pixar-films-visualized_files/pix1-11.png" alt="" width="85%" height="85%"/>

<img src="/post/the-multidimensional-success-of-pixar-films-visualized_files/pix1-21.png" alt="" width="85%" height="85%"/>
</center>
</figure>

Lastly, I also present a similarly constructed graph with a y-axis corresponding to [Metacritic](http://www.metacritic.com/) scores (to add another quality metric into the mix):

<figure>
<center>
<img src="/post/the-multidimensional-success-of-pixar-films-visualized_files/pix1-31.png" alt="" width="85%" height="85%"/>
</center>
</figure>

---

# Code

Data and R scripts needed to recreate all the included visualizations are available via my ["Pixar" GitHub repo](https://github.com/apalbright/Pixar)!

[^1]: We use opening weekend gross since there is not yet a final box office number for Inside Out.

[^2]: We [truncate the y-axis](https://qz.com/418083/its-ok-not-to-start-your-y-axis-at-zero/) in order to better emphasize the evolution of quality over time.
