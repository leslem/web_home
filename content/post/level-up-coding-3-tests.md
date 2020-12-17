---
title: "Write, and regularly run, tests of your code"
date: 2019-08-27T23:16:17-07:00
publishdate: 2019-08-28
draft: true
tags: ['best-practices', 'r', 'python']
---


- Expected good inputs should give the right output
- Expected bad inputs should give a sensible error you can handle
- Add ad hoc tests
    - R and Python: script of if statements that only print when things are wrong
    - Python assert() statements
- Add unit tests (very small tests, generally one thing at a time, generally on functions)
    - Python: unittest, nose, pytest
    - R: testthat
- Add integration tests
    - e.g. given known input you get expected output from entire pipeline/script/analysis etc.
