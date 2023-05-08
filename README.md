# PortfolioDeliverable1
Data Analysis Class-Portfolio
This is a poster presentation that investigates the relationship between COVID-19 vaccinations, population density, and new cases. The project seeks to answer whether vaccination rates and population density are associated with new COVID-19 cases and to what extent. The poster uses data from Our World in Data, which is available in CSV format and contains information on COVID-19, including the number of cases, deaths, tests, and vaccinations by country and date. 

The project expects to find that higher vaccination rates and lower population density are associated with lower rates of new COVID-19 cases. The relationship between vaccination rates and new cases may be moderated by population density, such that the negative association between vaccinations and new cases may be stronger in areas with lower population density.

The code loads the necessary libraries and loads the COVID-19 data. The summary of key variables is presented using the kableExtra package. The graph of COVID-19 cases by date is also presented using the ggplot2 package. A scatter plot is presented using the lm() function and kableExtra package to generate a regression summary. 

```{r}
knitr::opts_chunk$set(echo = FALSE,
                      warning = FALSE,
                      tidy = FALSE,
                      message = FALSE,
                      fig.align = 'center',
                      out.width = "100%")
options(knitr.table.format = "html") 

library(tidyverse)
library(kableExtra)
library(patchwork)
library(dplyr)
library(stargazer)
library(lme4)
library(Matrix)
```


```{r load covid, include=FALSE}
   load("covidfinal.RData")

```

# Introduction

The COVID-19 pandemic has had a profound impact on the world in the last few years, leading to numerous deaths and causing significant disruptions to societies and economies. Governments, public health organizations, and individuals have been working tirelessly to curb the spread of the virus and minimize its impact.

One critical tool in this effort has been the development and distribution of COVID-19 vaccines. As more people receive vaccines, it is reasonable to expect that the number of new COVID-19 cases will decrease. However, the effectiveness of vaccines may be influenced by other factors, such as population density.

# Research Question

In this context, the main question of this analysis is:

What is the relationship between COVID-19 vaccinations, population density, and new cases?

Specifically, we will explore whether vaccination rates and population density are associated with new COVID-19 cases, and to what extent.


# Importance and Expectations

Understanding the relationship between vaccinations, population density, and new cases is of critical importance for policymakers, public health organizations, and individuals. This information can help guide decisions around vaccination distribution and other public health interventions, particularly in areas with high population density. It can also inform individual decisions around COVID-19 prevention and help promote a safer and healthier society overall.

This project expects to find that higher vaccination rates and lower population density are associated with lower rates of new COVID-19 cases. We also anticipate that the relationship between vaccination rates and new cases may be moderated by population density, such that the negative association between vaccinations and new cases may be stronger in areas with lower population density.

# Data

The data is the COVID-19 data compiled by Our World in Data, which is a project of the Global Change Data Lab, a non-profit organization based at the University of Oxford.

The data is available in CSV format and includes a wide range of information on COVID-19, including the number of cases, deaths, tests, and vaccinations by country and date. The data is updated regularly, and the latest version was published in 2022. It is important to note that the data is subject to limitations, such as variations in testing and reporting practices across different countries.
