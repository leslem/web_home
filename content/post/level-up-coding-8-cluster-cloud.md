---
title: "Run your analysis on a cluster/the cloud, not your laptop"
date: 2019-08-27T23:16:17-07:00
publishdate: 2019-12-07
draft: true
tags: ['best-practices', 'r', 'python']
---


Why:
Get used to saving output files rather than looking at interactive output
More compute power
More memory
Don't worry about crashing your laptop from opening up too many tabs
It feels pretty cool to know you've got hundreds of jobs churning away while you're scrolling Twitter

How:
Batch files!
(Not really sure about on the cloud)


Useful techniques
- Always run a small test version first, making sure it runs start to finish and produces expected output files in right format. Only then do you run the whole thing.
- Break things up into small pieces
- Handle dependencies (jobs waiting on other jobs)
- Array jobs
