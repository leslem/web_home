---
title: "Reflections on ten years using R"
subtitle: ""
summary: ""
authors: []
tags: [R]
categories: []
date: 2019-07-27T18:56:04-07:00
lastmod: 2019-07-27T18:56:04-07:00
draft: true
toc: true
---

## Before I knew about R

Thinking back on it, I've always been interested in analyzing and visualizing data. I remember learning to use Excel for making scatterplots during my high school chemistry class and thinking it was really cool. I was even excited about using Excel when it was still the only data analysis tool I knew about.

During my college classes, I started to use some specialized bioinformatics software for protein and DNA sequence alignment, phylogenetic analysis, and demographic parameter inference. But I was still using Excel for data manipulation and plotting until my biostatistics class. For biostats, I had to use JMP In, a cheaper and now-defunct student version of the visualization-focused statistical software JMP, produced by the same folks who make SAS. Using JMP In was pretty fun and it made much better graphics than anything I'd seen in Excel, so I used it happily for the year or two that my (very expensive) license lasted.


## How I learned about R

My undergrad academic advisor, Dr. G, was also the teacher for my biostatistics course. During one of our advising meetings, we talked about some of the limitations and frustrations of JMP In and why he'd chosen to use it for the course. Basically, it was better than Excel but less expensive than SAS or SPSS. Then Dr. G mentioned wishing he could teach the biostatistics course using R instead, a free statistics programming language that he was really interested to learn. He was sure it wouldn't be a good fit for most of the students (largely pre-med and pre-vet biology majors), but he suggested it might something I would be interested in. I've thought back on this conversation a lot over the years because I wish I'd taken it as an opportunity to learn R on my own then. Instead, I would continue to hear about R here and there for the next year or so before finally starting to learn it during my first year of grad school.


## How I learned R

During my first year of grad school, I did rotations in three different labs in the department before deciding on one to join for my dissertation work. The first lab I rotated in (which I would eventually join for good) had a strong computational biology focus and my advisor basically made it my rotation project to learn R with a couple of small scale genetics data sets. I've gone back and looked at the first few R scripts and plots that I have saved from this rotation and I'm pretty happy with how my first forays into R went.

I'd love to display my very first few bits of R code below, but I unfortunately lost it in a memorable fashion that taught me an important lesson about code reproducibility. My advisor first demonstrated a few R commands by typing directly at the R console in the R.app GUI. I didn't realize at first that there was any other way to interact with R, so I left R.app open for several days as I figured out how to make my first couple of plots. But it never occurred to me to save the commands I was inputting to the console, and after a couple of days running, R.app crashed! When he saw me struggling over this, my advisor finally showed me the R.app editor window and explained about saving the R code to files. I've looked over those first R files, and it's funny to see that I saved them with a .txt extension. I also saved quite a few files with a .r extension instead of .R.

### Some of my earliest R code

The earliest file I can find containing R code written by me is from November 14, 2008, during my first grad school rotation. It was probably from a couple of weeks earlier, but that's the last modified date. I saved the output of the R console rather than just saving the R commands. I saved the file with my R console output on November 14, 2008. I was getting lots of error messages from simple mistakes, and it's really interesting to see this record of me figuring out how R works. I was using R version 2.6.1, compared to today's 3.6.1.

Below I've included a cleaned-up version of the code, for the sake of brevity.

```
> updists <- c(372, 4123, 4869, 6696, 6696, 8877, 10000, 12432, 12813, 12923, 15812, 22195, 32319, 39536, 45515, 45796, 49639, 49639, 60191, 60386, 61398, 80108, 82331, 93432, 96992, 96992, 99483, 99483, 113017, 116420, 116739, 118590, 130589, 132906, 136909, 137431, 139787, 141090, 144052, 144052, 149022, 178492, 188948, 201862, 214210, 225178, 225178, 239578, 246656, 246656, 253112, 256037, 256037, 256281, 328285, 334621, 346868, 356458, 362372, 382964, 390484, 390822, 400372, 407495, 407495, 423019, 424614, 447536, 447536, 461149, 465239, 475320, 483937, 495334, 507504, 538003, 554873, 554873, 568113, 617814, 617814, 661038, 667113, 679319, 687256, 687256, 730803, 732416, 735718, 735718, 756037, 756037, 770129, 792042, 827743, 828278, 863284, 879198, 883252, 977330, 1010270, 1030019, 1030019, 1056608, 1077582, 1179822, 1199123, 1305202, 1359204, 1413200, 1413200, 1438240, 1467874, 1467874, 1570584, 1620552, 1686902, 1790697, 1880952, 1902013, 1902013, 1957573, 2017340, 2031424, 2059710, 2131570, 2262458, 2418625, 2457349, 2470584, 2696310, 2762285, 2956943, 3093364)
> downdists <- c(1291, 1608, 3938, 3938, 9525, 12424, 15283, 15850, 21615, 23575, 23575, 33488, 33488, 33538, 34261, 39717, 40633, 51648, 64674, 72756, 76982, 83946, 86502, 105611, 121690, 121690, 122693, 125576, 153806, 153806, 157295, 167807, 169650, 169864, 218284, 218284, 255532, 256037, 261062, 261564, 264004, 266526, 268402, 269812, 281708, 311399, 312791, 315307, 318215, 330760, 332133, 333422, 333422, 334252, 369925, 369925, 390557, 390557, 401029, 445330, 454505, 461923, 468667, 487149, 490761, 490761, 508434, 519705, 567841, 615403, 627857, 659018, 685509, 685509, 716364, 722824, 726074, 744707, 779387, 788615, 789573, 805902, 810477, 810477, 811630, 814287, 864491, 986412, 1012309, 1031196, 1036900, 1106949, 1138400, 1138618, 1144016, 1144016, 1151364, 1151364, 1168000, 1212389, 1258077, 1258077, 1288622, 1324519, 1342328, 1345815, 1345815, 1357037, 1447885, 1447885, 1453079, 1470745, 1470745, 1506988, 1506988, 1633700, 1703137, 1774600, 1791720, 1822725, 1877306, 1905314, 2081110, 2133184, 2145335, 2322038, 2322038, 2327473, 2327473, 2387185, 2410159, 2410159, 2525037, 2848887, 2858321, 2924966, 2924966)
> a <- density(updists)
> a

Call:
	density.default(x = updists)

Data: updists (134 obs.);	Bandwidth 'bw' = 2.189e+05

       x                 y            
 Min.   :-656411   Min.   :1.733e-10  
 1st Qu.: 445229   1st Qu.:4.880e-08  
 Median :1546868   Median :1.403e-07  
 Mean   :1546868   Mean   :2.267e-07  
 3rd Qu.:2648507   3rd Qu.:3.240e-07  
 Max.   :3750147   Max.   :8.417e-07  
> b <- density(downdists)
> c <- density(downdists, cut=0)
> newdown <- downdists + (max(a$x) + 100000 + abs(min(b$x)))
> plot(rev(a$x), a$y, type="l", xlim=c(0,(max(b$x)+max(a$x)+100000)), ylim=c(0,max(c(max(a$y,b$y)))), xlab="", axes=FALSE, main = "Distances to Nearest Genes", ylab = "Frequency", lwd = 2, cex.main=3, cex.axis=2, cex.lab=2, mgp=c(1,1,0))
> lines(density(newdown), lwd=2)
```

By the end of my rotation I had saved another R script, `NearGeneDist.R`, to create a more refined version of that plot, which I included in my research report presentation at the end of the quarter.

**Insert the final version of the plot here**

Script at /data/grad-school/rotations/akey/Research\ Reports/Figures/Near\ Genes\ Figure/NearGeneDist.R


## How my use of R has changed

It's been interesting to look back at my earliest R code and think about how much my use of R has changed.



- Saving plots using graphics device commands (rather than the save dialog from a Quartz device window)
- Better file names and organization
- Saving reusable scripts for later
- Once-masterful command of base R graphics
- Moved on to ggplot
- Using it for more than just plotting/figures
- Knitr, Sweave, RMarkdown
- data.table
- Wrote reusable scripts for running on large-scale simulated datasets on cluster for dissertation
- Subversion, to Git and now GitHub

## How R has changed
- RStudio
- tidyverse
- Shiny and interactive apps
- More for web than for print!
- New people aren't starting with base graphics and the R.app GUI anymore
- Many more packages

## Looking forward

- Making more of my own packages
- Contributing to collaborative code projects within my group
- Cloud environments
- Jupyter notebooks competition
- R still has an edge for statistical methods, configurable graphics, data manipulation out of the box
- Benefiting from the developer perspective that has come in


## Related resources
[kbroman](https://kbroman.org/hipsteR/)
[kbroman](https://kbroman.org/steps2rr/)
[wordpress](https://practicaldatamanagement.wordpress.com/2014/10/23/baby-steps-for-the-open-curious/)
