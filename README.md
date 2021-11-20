---
editor_options: 
  markdown: 
    wrap: 72
---

# Beijing Air Quality Analysis Proposal

-   Authors: Jacqueline Chong, Junrong Zhu, Macy Chan, Vadim Taskaev

Data analysis project for DSCI 522 (Data Science Workflows); a course in
the Master of Data Science program at the University of British
Columbia.

## Introduction

The objective of this project is to answer the following inferential
question: Does PM2.5 measurement in Beijing, China collected between
2013 and 2017 show any sign of improvement?

The capital city of Beijing, China has long struggled with poor air
quality, a result of the country's rapid industrialization and its heavy
reliance on coal for electricity generation the North, as well as its
growing and increasingly urban middle class (Wang, Hao. 2012 Jan; 24(1):
2-13). This analysis question is important for its timely and global
implications: as air pollution from the burning of fossil fuels and its
association with climate change and direct health outcomes poses a
challenge to nations worldwide, we explore whether we may find evidence
of economic growth coinciding with improving air quality. In fact, in
September 2021 the World Health Organization revised its air quality
guidelines to more restrictive levels following the increasingly evident
causal relationships between poor air quality and its harmful health
consequences on impacted mainly urban communities (Whaley,
Nieuwenhuijsen, Burns. 2021 Sep; 142).

We analyse the Beijing Air Quality data set, donated to the UC Irvine
Machine Learning Repository in 2019, which comprises hourly measurement
of six air pollutants (including PM2.5, PM10, SO2, NO2, CO, O3) and six
meteorological variables spanning from 2013 until 2017 across twelve of
its metropolitan data-collecting stations. While the structure of this
data set makes it suitable for multi-variate time-series regression
analysis, we focus our analysis solely on the readings of the PM2.5
metric, a form of fine particulate matter that is considered especially
harmful for its ability to penetrate deep into the lungs and cause
long-lasting damage to the respiratory system (J Thorac Dis. 2016 Jan;
8(1): E69--E74).

## Methods

**Data Wrangling:**

We will combine sub data-sets, which were collected from twelve testing
locations in Beijing, into one data frame, and then split this data
frame into two samples based on time frames below.

-   Sample_A: air quality data from March 2013 - February 2015

-   Sample_B: air quality data from March 2015 - February 2017

New Column 'Class' will be created to classify each observation as
either Sample_A or Sample_B (during exploratory data analysis)

**Hypothesis Testing:**

Given that we have good sample size for both samples and the data points
are independent, we plan to perform hypothesis testing to estimate the
difference in parameters/sample estimates of two samples.

\- Null Hypothesis: The sample estimates of Sample_A and Sample_B are
equal.

\- Alternative Hypothesis: The sample estimates of Sample_A and Sample_B
are NOT equal .

We will perform exploratory data analysis steps to identify and
demonstrate the unique patterns and distributions of PM2.5 data points
for each sample as well as visualization to compare/contrast two
samples. Then we will decide the suitable tests and estimators to answer
our question from the exploratory steps.

**Results Interpretation:**

We will demonstrate the results in both tables and visualization, for
example:

Previewing the data set by outputting top rows of the imported data
frame.

Creating figures, such as histogram, violin plot and so forth, to
visualize and compare the distribution as well as any possible outliers
of two samples.

Highlighting test statistic values and significance threshold with
shaded bar plot

Summarizing each figure with brief conclusion and providing insightful
explanation for the observed characteristics in organized paragraphs.

## Usage

To replicate the analysis, clone this GitHub repository, install the
[dependencies](#dependencies) listed below, and run the following
commands at the command line/terminal from the root directory of this
project:

    python src/download_data.py --url=https://archive.ics.uci.edu/ml/machine-learning-databases/00501/PRSA2017_Data_20130301-20170228.zip --out_folder=data/raw
    Rscript -e "rmarkdown::render('src/Beijing_air_quality.Rmd')"

## Dependencies {#dependencies}

-   Python 3.7.3 and Python packages:

    -   docopt==0.6.2
    -   requests==2.22.0
    -   pandas==0.24.2
    -   urllib.request==3.9

-   R version 3.6.1 and R packages:

    -   knitr==1.26
    -   tidyverse==1.2.1
    -   ggthemes==4.2.0
    -   here==1.0.1

## License

This dataset is licensed under a[Creative Commons Attribution 4.0
International](https://creativecommons.org/licenses/by/4.0/legalcode) (CC
BY 4.0) license.

This allows for the sharing and adaptation of the datasets for any
purpose, provided that the appropriate credit is given.

# References

Whaley P, Nieuwenhuijsen M, Burns J. 2021. "Update of the WHO global air
quality guidelines: systematic reviews". In *Environ Int.* 142(Special
issue)
[here](https://www.sciencedirect.com/journal/environment-international/special-issue/10MTC4W8FXJ)

Yu-Fei Xing, Yue-Hua Xu, Min-Hua Shi, and Yi-Xin Lian. 2016. "The impact
of PM2.5 on the human respiratory system". In *Journal of Thoracic
Disease.* 8(1):
E69--E74.[here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4740125/)

Wang, Shuxiao, and Hao, Jiming. 2012. "Air quality management in China:
Issues, challenges, and options." In *Journal of Environmental
Sciences*. 24(1).
[here](https://www.sciencedirect.com/science/article/abs/pii/S1001074211607249)
