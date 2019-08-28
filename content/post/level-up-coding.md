---
title: "How to level up your coding skills in research work"
date: 2019-08-27T17:13:39-07:00
draft: true
---

When I started my PhD program ten years ago, I was learning programming nearly from scratch. I had decent Unix skills, but the only coding I'd done was on a TI-83. I quickly learned R and Python and was very excited to use these new tools in my research on human population genetics. 

But once I'd learned the basics, I spent a couple of years at a plateau. I was writing single-use data analysis scripts and it was working for me, but every time I copy/pasted code from one script to another I couldn't help but think that there must be a better way. 

Well, there was a better way, and I've put together a list of the skills that I needed to take my scientific computing to the next level. These are the coding practices and skills that I have found to be the most useful. They've also been useful skills for the junior scientists I have mentored or trained over the years.

## Why are these skills important?

1. **Accuracy**. Just like your lab experiments need carefully regulated conditions and controls, your code needs to be carefully tested and controlled for accuracy.
2. **Reproducibility**. The more closely you follow good programming practices, the easier it will be for you to reproduce an analysis if a reviewer asks you to rerun it with modifications.
3. **Saving your time**. All of the practices and skills I mention below will save you time once you can use them regularly.
4. **Preventing bugs**. These good programming practices will go a long way towards helping you prevent bugs, and saving you time when you have to track bugs down. 

## Practices and skills to level up your coding for science

##### Run batch scripts, rather than working interactively
I love working interactively in R GUI, RStudio, or the Python or IPython interpreter. It's great for figuring out how something is going to work. But it's a terrible way to run an analysis you're actually going to use results from. You can't be sure that you ran all of the code in the proper order. You can't be sure that you actually recorded all of the code that you ran, or the libraries/modules you used. The only way to be sure that you've captured all of the code for you analysis in a reproducible way is to save it in a script that you can without your intervention:

```
# R example of running a batch script
Rscript my_data_analysis.R  # The latest, preferred way
R CMD BATCH my_data_analysis.R  # This is older, but should still work

# Python example of running a batch script
python my_data_analysis.py
```

##### Write reusable functions

##### Add tests
    - Add ad hoc tests
    - Add unit tests
    - Add integration tests

##### Start using version control

##### Use a package manager and control the package version you use

##### Add documentation, and comment like crazy

##### Run your scripts on a cluster or in the cloud, instead of on your laptop/desktop

##### Use logging

##### Use savepoints or checkpointing

##### Write report files that summarize your analysis (but are not the entirety of your analysis)

##### Learn about object-oriented programming and look for opportunities to use it

##### Learn about databases and how to use them for your work

##### Learn UNIX skills
    - grep
    - awk/sed
    - piping, input, output
    - jobs, bg, fg
    - processes
    - different kinds of shells
    - aliases
    - profiles
    -  