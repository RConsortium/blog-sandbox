---
title: Code Coverage Tool for R Working Group Achieves First Release
author: Joseph Rickert
date: '2017-06-28'
categories:
  - Blog
  - News
  - R Consortium Project
  - R Language
slug: code-coverage-tool-for-r-working-group-achieves-first-release
---

by Mark Hornick, Code Coverage Working Group Leader

The "Code Coverage Tool for R" project, proposed by Oracle and approved by the R Consortium Infrastructure Steering Committee, started just over a year ago. Project goals included providing an enhanced tool that determines code coverage upon execution of a test suite, and leveraging such a tool more broadly as part of the R ecosystem.

**What is code coverage?**

As defined in [Wikipedia](https://en.wikipedia.org/wiki/Code_coveragehttps:/en.wikipedia.org/wiki/Code_coverage), "code coverage is a measure used to describe the degree to which the source code of a program is executed when a particular test suite runs. A program with high code coverage, measured as a percentage, has had more of its source code executed during testing which suggests it has a lower chance of containing undetected software bugs compared to a program with low code coverage."

**Why code coverage?**

Code coverage is an essential metric for understanding software quality. For R, developers and users alike should be able to easily see what percent of an R package's code has been tested and the status of those tests. By knowing code is well-tested, users have greater confidence in selecting CRAN packages. Further, automating test suite execution with code coverage analysis helps ensure new package versions don't unknowingly break existing tests and user code.

**Approach and main features in release**

After surveying the available code coverage tools in the R ecosystem, the working group decided to use the **[covr](https://cran.r-project.org/web/packages/covr/index.html)** package, started by Jim Hester in December 2014, as a foundation and continue to build on its success. The working group has enhanced **covr** to support even more R language aspects and needed functionality, including:

  * R6 methods support

  * Address parallel code coverage

  * Enable compiling R with Intel compiler ICC

  * Enhanced documentation / vignettes

  * Provide tool for benchmarking and defining canonical test suite for **covr**

  * Clean up dependent package license conflicts and change **covr** license to GPL-3

**CRAN Process**

Today, code coverage is an optional part of R package development. Some package authors/maintainers provide test suites and leverage code coverage to assess code quality. As noted above, code coverage has significant benefits for the R community to help ensure correct and robust software. One of the goals of the Code Coverage project is to incorporate code coverage testing and reporting into the CRAN process. This will involve working with the R Foundation and the R community on the following points:

  * Encourage package authors and maintainers to develop, maintain, and expand test suites with their packages, and use the enhanced **covr** package to assess coverage

  * Enable automatic execution of provided test suites as part of the CRAN process, just as binaries of software packages are made available, test suites would be executed and code coverage computed per package

  * Display on each packages CRAN web page its code coverage results, e.g., the overall coverage percentage and a detailed report showing coverage per line of source code.

**Next Steps**

The working group will assess additional enhancements for **covr** that will benefit the R community. In addition, we plan to explore with the R Foundation the inclusion of code coverage results in the CRAN process.

**Acknowledgements**

The following individuals are members of the Code Coverage Working Group:

  * Shivank Agrawal

  * Chris Campbell

  * Santosh Chaudhari

  * Karl Forner

  * Jim Hester

  * Mark Hornick

  * Chen Liang

  * Willem Ligtenberg

  * Andy Nicholls

  * Vlad Sharanhovich

  * Tobias Verbeke

  * Qin Wang

  * Hadley Wickham – ISC Sponsor
