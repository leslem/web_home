---
title: "Write reusable functions"
date: 2019-08-27T23:16:17-07:00
publishdate: 2019-10-26
draft: true
tags: ['best-practices', 'r', 'python']
---

If you aren't already writing reusable functions, this is one of the first steps you can take to improve your analysis code. A function is a named block of code that takes input(s), produces output, and can be used over and over again. You're probably already comfortable with using some of the many "built-in" functions that come standard with R or Python.

#### Examples of R builtin functions

```
> runif(5)
[1] 0.9167304 0.3925537 0.7488157 0.7889727 0.8961944

> mean(c(1.538140, 3.993816, 1.712781, 2.780435, NA), na.rm=TRUE)
[1] 2.506293
```

In these examples, `runif` and `mean` are the functions and the values in the parentheses are the inputs, or function arguments. `runif` takes one argument and `mean` takes two arguments.

#### Examples of Python builtin functions

```
>>> len([2, 63, 0])
3

>>> open('myfile.txt', mode='r')
<_io.TextIOWrapper name='myfile.txt' mode='r' encoding='UTF-8'>
```

`len` and `open` are both functions in Python, with arguments in the parentheses.

Once you start writing your own functions, you'll be able to use them just like builtin functions to run the same bit of code over and over again with different inputs.

## How do I write a function?

Programming languages generally have a standard way to define a function and a standard way to run the function after you've defined it. For defining functions, Python uses `def` and R uses `function`. Below are examples of a function to calculate the GC content[^1] in a DNA sequence, in both R and Python. You can see that the function looks pretty similar in both languages.

#### Define an R function

```
gc_content <- function(dna)
{
    dna <- tolower(dna)
    c_count <- lengths(regmatches(dna, gregexpr("c", dna)))
    g_count <- lengths(regmatches(dna, gregexpr("g", dna)))
    seq_len <- nchar(dna)
    return((c_count + g_count) / seq_len)
}

gc_content('GATTACA')
gc_content('GCGGCGGC')
```

#### Define a Python function

```
def gc_content(dna):
    dna = dna.lower()
    c_count = dna.count('c')
    g_count = dna.count('g')
    return (c_count + g_count) / len(dna)

gc_content('GATTACA')
gc_content('GCGGCGGC')
```

In the examples above, I first define a function, and then run the function with two different input values. This makes it easy to see that if I hadn't written the function I would need to write the same lines of code all over again, but with a different DNA sequence. Packaging it up into a function prevents this duplication.

## What's so great about reusable functions?

#### 1. No more repeated code

One of the main reasons to write reusable functions is to prevent yourself from repeating code. This is such a strong concept in programming that it's often referred to with the acronym "DRY" - don't repeat yourself. If you find an error in code that's repeated multiple times, you'll have to carefully go through and fix it every time and just hope that you didn't miss anything. If instead you're using a function, you just need to make the fix once. Anytime you find yourself repeating similar code, it's time to think about writing a function.

#### 2. Testing is easier

I'll write more about the importance of testing later, but it's much easier to write tests for a reusable function than for standalone code. Once you have a function, it's very straightforward to test that you're getting the expected output given some known input values.

#### 3. Keep your code organized into small, managable pieces

Functions are a great way to keep your code organized and easier to navigate and maintain. The lines of code for the actual function are kept together in an easy-to-find location. A good code editor will let you collapse functions so that they stay out of your way when you're not working on them. You can write a more complex function that itself runs code from smaller, simpler functions.

#### 4. Flexibility for sharing with others

When you need to share your code with your lab mates or collaborators, it will be easier for them to extend it for their own needs if you've organized it into functions. They will be able to run your function as-is with their own input values.

## How about some real examples...

I've used functions extensively in both Python and R analysis code. Here are just a few examples of the kinds of functions I've found useful:

- Make a highly customized plot
- Read in a custom file format
- Write out a custom file format
- Calculate p values from simulated data
- Calculate genetic diversity statistics
- Calculate summary statistics on simulated genetic data
- Identify outliers
- Convert genetic data formats
- Run a genetic simulation program with a specific model

#### Digging up a very old and very real example

Most of the functions I've been writing lately have been for a big Django[^2] project, so they don't make very much sense outside of that context. Instead I went back to the code I used for my dissertation and found this nice example of a function to calcualte the heterozygosity of a genomic site based on the allele frequency.

```
def heterozygosity(p):
        """Calculates heterozygosity from allele frequency.

        Assumes a biallelic site.

        Args:
                p: frequency of either the major or minor allele (doesn't matter which)

        Returns:
                a float value of the heterozygosity
        """
        return 2.0 * p * (1.0 - p)
```

## Go forth and write functions

I hope by now that you're convinced to write some reusable functions wherever possible. You should have enough information to search for tutorials and look through the documentation for R or Python. The best way to learn is to get started.

## Further reading
- [Functions chapter from *R for Data Science*](https://r4ds.had.co.nz/functions.html)
- [Python 3 documentation for function definitons](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)


[^1]: GC content is the percentage of a DNA sequence that is made up of C's and G's (cytosine and guanine), which affects DNA melting temperature, sequencing coverage, etc.
[^2]: A Python web framework.