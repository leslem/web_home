---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "An old post"
subtitle: ""
summary: ""
authors: []
tags: [old-tag]
categories: []
date: 2018-07-27T18:57:04-07:00
lastmod: 2018-07-27T18:57:04-07:00
draft: true
---

Testing some text out here.

When I started my PhD program ten years ago, I was learning programming nearly from scratch. I had decent Unix skills, but the only coding I'd done was on a TI-83. I quickly learned R and Python and was very excited to use these new tools in my research on human population genetics. 

But once I'd learned the basics, I spent a couple of years at a plateau. I was writing single-use data analysis scripts and it was working for me, but I spent a lot of time tracking down bugs. I once presented results to my department that I later found were wrong due to an error in my code. And every time I copy/pasted code from one script to another I couldn't help but think that there must be a better way.

Well, there was a better way, and I've put together a list of the skills that I needed to take my scientific computing to the next level. These are the coding practices and skills that I have found to be the most useful. They've also been useful skills for the junior scientists I have mentored or trained over the years. I'm going to explain in a bit more detail the kinds of skills and practices I'm talking about, and offer some more motivation for why they're important.

## Skills to level up your science research code

This is a brief list of the skills I'm going to talk about in this series of posts. It's an incomplete list, but I think it's a good place to start.

1. Write reusable functions
1. Write, and regularly run, tests of your code
1. Add documentation, and comment like crazy
1. Run batch scripts, rather than working interactively
1. Use version control
1. Use a package manager
1. Run your analysis on a cluster/the cloud, not your laptop
1. Use Unix tools


## Why are these skills important?

For those of us coding for research applications, it can be difficult to judge how much time, effort, and learning to put into programming skills. When your goal is to answer research questions (and publish papers about them), good programming practices can feel like a distraction. But there are several reasons why following good coding practices will benefit you, your colleagues, and your science.

#### 1. **Accuracy**. 

Your lab experiments require carefully regulated conditions and carefully designed controls. Without them, you can't be sure if the results you're seeing are reliable. Your data analysis code is no different. Tests can serve as positive and negative controls. Documentation and version control can serve as a lab notebook for your code. You should be able to demonstrate that your code gets accurate results, and these skills make that task easier.

#### 2. **Reproducibility**. 

There will be many circumstances under which you need to reproduce an analysis. Perhaps a reviewer will ask you to rerun your analysis with modifications. Perhaps you'll need to train a new lab member to do the same kind of analysis for their project. The skills I've listed will make reproducing your analysis much easier for you.

#### 3. **Saving your time**. 

Learning and using these programming skills will end up saving you more time than you can imagine. You'll be able to update and extend your code more easily and more quickly, and with fewer bugs and less time spent manually verifying results.

#### 4. **Preventing bugs**. 

Writing single-use data analysis scripts will make it difficult for you to prevent bugs, or to find them when they happen. The more reusable your code is, the easier it is to test, and tests are great for preventing bugs before you even get to your results.

#### 5. **Shareability**. 

These leveled-up coding practices will also make it easier for you to share your code with others, and for you to use others' shared code. You'll want to make sure that any code you share with your colleagues is tested, can be used on a system other than yours, and is straightforward for them to understand and potentially modify.

## How to learn these skills

I'll be writing some posts about each of the listed skills in more detail over the coming weeks. I'll try to include some basic Python and R examples, where appropriate. This will be just enough to give you an idea of how to get started looking for resources on each skill.

A great resource to start with is [Software Carpentry's lessons](https://software-carpentry.org/lessons/). Otherwise, the best way to learn them is to look into each skill and start using it, even in a small way, in your work.

