---
title: "Run batch scripts, rather than working interactively"
date: 2019-08-27T23:16:17-07:00
draft: true
tags: ['best-practices', 'r', 'python']
---



I love working interactively in R GUI, RStudio, or the Python or IPython interpreter. It's great for figuring out how something is going to work. But it's a terrible way to run an analysis you're actually going to use results from. You can't be sure that you ran all of the code in the proper order. You can't be sure that you actually recorded all of the code that you ran, or the libraries/modules you used. The only way to be sure that you've captured all of the code for you analysis in a reproducible way is to save it in a script that you can without your intervention:

## What's wrong with working interactively?


## What does running a batch script look like?

```
# R example of running a batch script
Rscript my_data_analysis.R  # The latest, preferred way
R CMD BATCH my_data_analysis.R  # This is older, but should still work

# Python example of running a batch script
python my_data_analysis.py
```

## What about analysis notebooks?

Saving your analysis in an RMarkdown document or a Jupyter notebook can accomplish the same goal, though you need to be careful that you're not misusing options that result in your code not being run in the way that you expect.
