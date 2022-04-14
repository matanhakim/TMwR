---
knit: "bookdown::render_book"
title: "Tidy Modeling with R"
author: ["Max Kuhn and Julia Silge"]
date: "Version 0.0.1.9010 (2022-04-12)"
site: bookdown::bookdown_site
description: "The tidymodels framework is a collection of R packages for modeling and machine learning using tidyverse principles. This book provides a thorough introduction to how to use tidymodels, and an outline of good methodology and statistical practice for phases of the modeling process."
github-repo: tidymodels/TMwR
twitter-handle: topepos
cover-image: images/cover.png
documentclass: book
classoption: 11pt
bibliography: [TMwR.bib]
biblio-style: apalike
link-citations: yes
colorlinks: yes
---

# Hello World {-} 

<a href="https://amzn.to/35Hn96s"><img src="images/cover.png" width="350" height="460" alt="Buy from Amazon" class="cover" /></a>

Welcome to _Tidy Modeling with R_! This book is a guide to using a collection of software in the R programming language for model building called <span class="pkg">tidymodels</span>, and it has two main goals: 

- First and foremost, this book provides a practical introduction to **how to use** these specific R packages to create models. We focus on a dialect of R called [the tidyverse](https://www.tidyverse.org/) that is designed with a consistent, human-centered philosophy, and demonstrate how the tidyverse and the <span class="pkg">tidymodels</span> packages can be used to produce high quality statistical and machine learning models.

- Second, this book will show you how to **develop good methodology and statistical practices**. Whenever possible, our software, documentation, and other materials attempt to prevent common pitfalls. 

In Chapter \@ref(software-modeling), we outline a taxonomy for models and highlight what good software for modeling is like. The ideas and syntax of the tidyverse, which we introduce (or review) in Chapter \@ref(tidyverse), are the basis for the tidymodels approach to these challenges of methodology and practice. Chapter \@ref(base-r) provides a quick tour of conventional base R modeling functions and summarizes the unmet needs in that area. 

After that, this book is separated into parts, starting with the basics of modeling with tidy data principles. Chapters \@ref(ames) through \@ref(performance) introduces an example data set on house prices and demonstrates how to use the fundamental tidymodels packages: <span class="pkg">recipes</span>, <span class="pkg">parsnip</span>, <span class="pkg">workflows</span>, <span class="pkg">yardstick</span>, and others. 

The next part of the book moves forward with more details on the process of creating an effective model. Chapters \@ref(resampling) through \@ref(workflow-sets) focus on creating good estimates of performance as well as tuning model hyperparameters. 

Finally, the last section of this book, Chapters \@ref(dimensionality) through \@ref(inferential), covers other important topics for model building. We discuss more advanced feature engineering approaches like dimensionality reduction and encoding high cardinality predictors, as well as how to answer questions about why a model makes certain predictions and when to trust your model predictions.

We do not assume that readers have extensive experience in model building and statistics. Some statistical knowledge is required, such as random sampling, variance, correlation, basic linear regression, and other topics that are usually found in a basic undergraduate statistics or data analysis course. We do assume that the reader is at least slightly familiar with dplyr, ggplot2, and the `%>%` "pipe" operator in R, and is interested in applying these tools to modeling. For users who don't yet have this background R knowledge, we recommend books such as [*R for Data Science*](https://r4ds.had.co.nz/) by Wickham and Grolemund (2016). Investigating and analyzing data are an important part of any model process,

This book is not intended to be a comprehensive reference on modeling techniques; we suggest other resources to learn more about the statistical methods themselves. For general background on the most common type of model, the linear model, we suggest @fox08.  For predictive models, @apm and @fes are good resources. For machine learning methods, @Goodfellow is an excellent (but formal) source of information. In some cases, we do describe the models we use in some detail, but in a way that is less mathematical, and hopefully more intuitive. 


## Acknowledgments {-}



We are so thankful for the contributions, help, and perspectives of people who have supported us in this project. There are several we would like to thank in particular.

We would like to thank our RStudio colleagues on the <span class="pkg">tidymodels</span> team (Davis Vaughan, Hannah Frick, and Emil Hvitfeldt) as well as the rest of our coworkers on the RStudio open-source team. Thank you to Desirée De Leon for the site design of the online work. We would also like to thank our technical reviewers, Chelsea Parlett-Pelleriti and Dan Simpson, for their detailed, insightful feedback that substantively improved this book, as well as our editor Nicole Tache for her perspective and guidance during the process of writing and publishing.


This book was written in the open, and multiple people contributed via pull requests or issues. Special thanks goes to the thirty-six people who contributed via GitHub pull requests (in alphabetical order by username): Brad Hill (\@bradisbrad), Bryce Roney (\@bryceroney), Cedric Batailler (\@cedricbatailler), Ildikó Czeller (\@czeildi), David Kane (\@davidkane9), \@DavZim, \@DCharIAA, Emil Hvitfeldt (\@EmilHvitfeldt), Emilio (\@emilopezcano), Fgazzelloni (\@Fgazzelloni), Hannah Frick (\@hfrick), Hlynur (\@hlynurhallgrims), Howard Baek (\@howardbaek), Jae Yeon Kim (\@jaeyk), Jonathan D. Trattner (\@jdtrat), Jeffrey Girard (\@jmgirard), John W Pickering (\@JohnPickering), Jon Harmon (\@jonthegeek), Joseph B. Rickert (\@joseph-rickert), Maximilian Rohde (\@maxdrohde), Mine Cetinkaya-Rundel (\@mine-cetinkaya-rundel), Mohammed Hamdy (\@mmhamdy), \@nattalides, Y. Yu (\@PursuitOfDataScience), Riaz Hedayati (\@riazhedayati), Scott (\@scottyd22), Simon Schölzel (\@simonschoe), Simon Sayz (\@tagasimon), \@thrkng, Tanner Stauss (\@tmstauss), Tony ElHabr (\@tonyelhabr), Dmitry Zotikov (\@x1o), Xiaochi (\@xiaochi-liu), Zach Bogart (\@zachbogart), Aris Paschalidis (\@arisp99), \@MikeJohnPage.

## Using Code Examples {-}



This book was written with [RStudio](http://www.rstudio.com/ide/) using [bookdown](http://bookdown.org/). The [website](https://tmwr.org) is hosted via [Netlify](http://netlify.com/), and automatically built after every push by [GitHub Actions](https://help.github.com/actions). The complete source is available on [GitHub](https://github.com/tidymodels/TMwR). We generated all plots in this book using [ggplot2](https://ggplot2.tidyverse.org/) and its black and white theme (`theme_bw()`). 

This version of the book was built with R version 4.1.3 (2022-03-10), [pandoc](https://pandoc.org/) version 2.17.1.1, and the following packages: applicable (0.0.1.2, CRAN), av (0.7.0, CRAN), baguette (0.2.0, CRAN), beans (0.1.0, CRAN), bestNormalize (1.8.2, CRAN), bookdown (0.25, CRAN), broom (0.7.12, CRAN), censored (0.0.0.9000, Github), corrplot (0.92, CRAN), corrr (0.4.3, CRAN), Cubist (0.4.0, CRAN), DALEXtra (2.1.1, CRAN), dials (0.1.1, CRAN), dimRed (0.2.5, CRAN), discrim (0.2.0, CRAN), doMC (1.3.8, CRAN), dplyr (1.0.8, CRAN), earth (5.3.1, CRAN), embed (0.1.5, CRAN), fastICA (1.2-3, CRAN), finetune (0.2.0, CRAN), forcats (0.5.1, CRAN), ggforce (0.3.3, CRAN), ggplot2 (3.3.5, CRAN), glmnet (4.1-3, CRAN), gridExtra (2.3, CRAN), infer (1.0.0, CRAN), kableExtra (1.3.4, CRAN), kernlab (0.9-30, CRAN), kknn (1.3.1, CRAN), klaR (1.7-0, CRAN), knitr (1.38, CRAN), learntidymodels (0.0.0.9001, Github), lime (0.5.2, CRAN), lme4 (1.1-29, CRAN), lubridate (1.8.0, CRAN), mda (0.5-2, CRAN), mixOmics (6.18.1, Bioconductor), modeldata (0.1.1, CRAN), multilevelmod (0.1.0, CRAN), nlme (3.1-157, CRAN), nnet (7.3-17, CRAN), parsnip (0.2.1.9001, local), patchwork (1.1.1, CRAN), pillar (1.7.0, CRAN), poissonreg (0.2.0, CRAN), prettyunits (1.1.1, CRAN), probably (0.0.6, CRAN), pscl (1.5.5, CRAN), purrr (0.3.4, CRAN), ranger (0.13.1, CRAN), recipes (0.2.0, CRAN), rlang (1.0.2, CRAN), rmarkdown (2.13, CRAN), rpart (4.1.16, CRAN), rsample (0.1.1, CRAN), rstanarm (2.21.3, CRAN), rules (0.2.0, CRAN), sessioninfo (1.2.2, CRAN), stacks (0.2.2, CRAN), stringr (1.4.0, CRAN), svglite (2.1.0, CRAN), text2vec (0.6, CRAN), textrecipes (0.5.1.9000, Github), themis (0.2.0, CRAN), tibble (3.1.6, CRAN), tidymodels (0.2.0, CRAN), tidyposterior (0.1.0, CRAN), tidyverse (1.3.1, CRAN), tune (0.2.0.9000, Github), uwot (0.1.11, CRAN), workflows (0.2.6, CRAN), workflowsets (0.2.1, CRAN), xgboost (1.5.2.1, CRAN), and yardstick (0.0.9, CRAN).
