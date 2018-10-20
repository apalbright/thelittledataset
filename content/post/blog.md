---
title: Let Me Upgrade You
author: ''
date: '2018-08-26'
slug: let-me-upgrade-you
categories:
  - code
tags:
  - RStudio
  - R
  - blog
  - blogdown
  - hugo
---

# Goodbye Wordpress, Hello `Blogdown`

Back in December 2014, I wanted to start a blog. Given that the whole process sounded daunting I started with a free Wordpress site. Now that I've become comfortable with R code and the RStudio IDE, I decided to start blogging in my natural habit too... so, I rebuilt my website using the [`blogdown`](https://bookdown.org/yihui/blogdown/) R package! 

Why the switch? Because now I can:

- have direct access to and control over the website source files
    - all files that make up my site are edited locally (in my dropbox) and then pushed to [this Github repo](https://github.com/apalbright/thelittledataset)
- never again serve ads to readers!^[Since I was using the free plan for Wordpress, they would put ads at the bottom of my posts.]
- write my blog content out of the RStudio IDE
    - more efficient since I already write up my R code here for data analysis
    - can work offline^[To edit Wordpress post drafts, you have to be online.]
- can use LaTeX math 
    - e.g. `$q^G_{t+1}>q^*, s^G_{t+1}=1$` (with `$G \in \{B,W\}$`
    - here [[post 1](https://thelittledataset.com/2018/01/29/social-networks-and-the-endurance-of-economic-injury/), [post 2](https://thelittledataset.com/2017/10/12/on-ego-and-sharing-ideas/), [post 3](https://thelittledataset.com/2017/09/07/you-think-there-i-am/)] are some post examples that now are much improved with the LaTeX math functionality
- use footnotes^[See! I am a footnote.] 
    - all my posts use footnotes now, which helps the flow of reading
- can include code chunks 
    - e.g. here's a code chunk from [this post](https://thelittledataset.com/2016/09/30/building-visualizations-using-city-open-data-philly-school-comparisons/):
    
```r
ggplot() + geom_map(data = spr1, aes(map_id = Zip.Code), 
      map = np_dist, fill="gray40", color="gray60") + 
  expand_limits(x = np_dist$long, y = np_dist$lat)+ 
  my_theme()+
  geom_point(data=datadistn, aes(x=X, y=Y, col="District (Neighborhood)"), 
      size=1.5, alpha=1)+
  geom_point(data=datachartn, aes(x=X, y=Y, col="Charter (Neighborhood)"), 
      size=1.5, alpha=1)+
  geom_point(data=datadistc, aes(x=X, y=Y, col="District (Citywide)"), 
      size=1.5, alpha=1)+
  geom_point(data=datachartc, aes(x=X, y=Y, col="Charter (Citywide)"), 
      size=1.5, alpha=1)+
  facet_wrap(~Rpt.Type.Long, ncol=2)+
  ggtitle(expression(atop(bold("Mapping Philly Schools"), 
      atop(italic("Data via OpenDataPhilly; 
      Visual via Alex Albright  (thelittledataset.com)"),""))))+
  scale_colour_manual(values = c("Charter (Citywide)"="#b10026", 
      "District (Citywide)"="#807dba","Charter (Neighborhood)"="red",
      "District (Neighborhood)"="blue"), guide_legend(title="Type of School"))+
  labs(y="", x="")
```

# Making the Blog in RStudio

To build out my blog locally, I followed a few simple steps. I first installed the `blogdown` package and [Hugo](https://gohugo.io/), which is an open source static site generator. 

```r
install.packages("blogdown")
blogdown::install_hugo()
```

Then, I created a new R project in a new directory with `File>New Project`. It was then time to generate a new site and set the theme. [Here](https://themes.gohugo.io/) are all the Hugo themes to choose from. I picked a functional, simple, aesthetically calming hugo theme -- [XMin](https://xmin.yihui.name/)!^[Another plus: this theme was created by [Yihui Xie](https://yihui.name/), who literally wrote the book on `blogdown` with Amber Thomas and Alison Presmanes Hill, so you know it'll work well.]

I then generated a new site: 
```r
blogdown::new_site(theme = "yihui/hugo-xmin")
```

This command creates a whole filing system (for an example site) in the new directory you created. This is fabulous since then you can just edit the pre-built system to deduce how things work. Key things to know: 

- posts are `.md` or `.Rmd` or `.Rmarkdown` files in the `content` folder
- inserting images means calling them from subfolders^[The subfolder depends on where you want to insert the image] in the `static` folder^[Clicking `Tools/Addins/Insert Image` and uploading an image writes the `html` command for inserting the image and puts the image in the correct folder.] 
- edit the `config.toml` file to edit the website footer and menu (universal things) 
- serve the site (`Tools/Addins/Serve Site`) to preview it (you only need to click that once in an R session)

Creating a brand new website locally takes just a few minutes using the above steps. However, migrating my content from Wordpress meant copy-and-pasting posts into `.md` files in the `content` folder and then completely reformatting the posts for markdown (i.e., adding bold, italics, section names, code chunks, latex math, footnotes, images).^[That process took me about 20 hours since many posts were complicated to recreate as `.md` files. [Here](https://thelittledataset.com/2018/01/29/social-networks-and-the-endurance-of-economic-injury/) is the post that took me the longest to move because of all the new LaTeX math additions.]

# Deployment with Netlify

Once I rebuilt my blog locally, I followed the blogdown book's suggestion and used [Netlify](https://www.netlify.com/) to host the website. Netlify is incredible -- it uses continuous deployment from [my Github repo](https://github.com/apalbright/thelittledataset) to host my blog. So, when I push changes to Github, the site updates. It is *that* easy. Also, Netlify is **FREE**!^[It also offers free `https`, which Github Pages does not. More on `https` [here](http://dataninja.me/2017/12/31/moving-from-wordpress-com-github-pages-to-netlify/) and [here](https://medium.com/@squiroid/migrated-my-website-to-https-in-5-min-via-netlify-7db1b2abf5ce).] 

I followed exactly the steps from [section 7 of Alison Presmanes Hill's blogdown post](https://alison.rbind.io/post/up-and-running-with-blogdown/#in-rstudio) for Netlify deployment.^[I specified hugo version is 0.47.1.] Essentially, after building my website locally with RStudio, I moved the whole directory to a new Github repo,^[I followed [these](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/) steps to move all the files to a new repo.] and then created a Netlify account and followed their clear-cut steps for connecting to that Github repo.  

After a few minutes, my site was deployed and available at `https://hopeful-wescoff-036500.netlify.com/`! I quickly changed the title, so then it was `https://thelittledataset.netlify.com/`. 

# Custom Domain

At this point I could have used an [`rbind.io` domain](https://support.rbind.io/about/) for free and been done, but... I still wanted to use `thelittledataset.com`.^[Also, I hear that `rbind.io` sites are sometimes blocked by IT departments... so, I don't want that.] Using the same domain as before is the best case scenario since then old links will still work.^[You must make sure the slugs for the new posts are consistent with the old ones.] 

If you (like me a week ago) don't know a lot about websites, let me explain a few things. There is a registrar of a domain and there is a host. I bought my custom domain through Wordpress back in 2014 and previously used the Wordpress free hosting plan. I pay $18/year to Wordpress for my domain name `thelittledataset.com`. However, *now*, Netlify is my host instead of Wordpress. In general, it is nice for the registrar of a domain and the host to be the same, however Netlify doesn't accept inbound domain transfers. But, there is good news:^[[Here](https://en.support.wordpress.com/move-domain/#change-name-servers-to-point-the-domain-outside-of-wordpress-com) is more on changing name servers on Wordpress.]  

> If you registered your domain with WordPress.com, you don’t have to use WordPress.com as your host. The domain you registered is yours, and you can use it with any host you want.

So, I kept my domain registration with Wordpress and just changed the domain’s nameservers to "point" at Netlify.^[I follow instructions through Netlify's domain dashboard. I use Netlify DNS, which gives me the custom hostnames assigned to your DNS zone that I need to assign to my domain via Wordpress.] So, I still pay $18/year for my domain name to Wordpress, but now I host through Netlify. *Goodbye unwanted advertisements, hello improved functionality and workflow!*

# Boom!

Now, my `blogdown`-built website exists at [`https://thelittledataset.com/`](https://thelittledataset.com/)! Upgrade complete.

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/6nr8hPnZfMU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

---

# Code

Here is [my Github repo](https://github.com/apalbright/thelittledataset), where all the source files for my website live! Damn, I love reproducibility. 

# Resources

If you want to make your own website with `blogdown`, I highly suggest reading both [the `blogdown` book](https://bookdown.org/yihui/blogdown/) and Alison Presmanes Hill's relevant [blog post](https://alison.rbind.io/post/up-and-running-with-blogdown/). 
