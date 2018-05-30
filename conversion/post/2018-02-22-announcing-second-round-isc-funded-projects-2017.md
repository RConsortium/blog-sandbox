---
title: Announcing the second round of ISC Funded Projects for 2017
author: John Mertic
date: '2018-02-22'
categories:
  - Announcement
  - Blog
  - News
  - R Consortium Project
slug: announcing-second-round-isc-funded-projects-2017
---

The R Consortium ISC is pleased to announce that the projects listed below were funded under the 2017 edition of the ISC Funded Projects program. This program, which provides financial support for projects that enhance the infrastructure of the R ecosystem or which benefit large segments of the R Community, has awarded $500,000 USD in grants to date. The Spring 2018 call for proposals is now open and will continue to accept proposals until midnight PST on April 1, 2018.  [Learn more about the program and how to apply for funding for your project](https://www.r-consortium.org/projects/call-for-proposals).

# Quantities for R

_Proposed by Iñaki Ucar_

The 'units' package has become the reference for quantity calculus in R, with a wide and welcoming response from the R community. Along the same lines, the 'errors' package integrates and automatises error propagation and printing for R vectors. A significant fraction of R users, both practitioners and researchers, use R to analyse measurements, and would benefit from a joint processing of quantity values with errors.

This project not only aims at orchestrating units and errors in a new data type, but will also extend the existing frameworks (compatibility with base R as well as other frameworks such as the tidyverse) and standardise how to import/export data with units and errors.

# Refactoring and updating the SWIG R module

_Proposed by Richard Beare_

The Simplified Wrapper and Interface Generator (SWIG) is a tool for automatically generating interface code between interpreters, including R, and a C or C++ library. The R module needs to be updated to support modern developments in R and the rest of SWIG. This project aims to make the R module conform to the recommended SWIG standards and thus ensure that there is support for R in the future. We hope that this project will be the first step in allowing SWIG generated R code using reference classes.

# Future Minimal API: Specification with Backend Conformance Test Suite

_Proposed by Henrik Bengtsson _

The objective of the Future Framework implemented in the future package is to simplify how parallel and distributed processing is conducted in R. This project aims to provide a formal Future API specification and provide a test framework for validating the conformance of existing (e.g. future.batchtools and future.callr) and to-come third-party parallel backends to the Future framework.

# An Earth data processing backend for testing and evaluating stars

_Proposed by Edzer Pebesma_

The stars project enables the processing Earth imagery data that is held on servers, without the need to download it to local hard drive. This project will (i) create software to run a back-end, (ii) develop scripts and tutorials that explain how such a data server and processing backend can be set up, and (iii) create an instance of such a backend in the AWS cloud that can be used for testing and evaluation purposes.
