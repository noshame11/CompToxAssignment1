Rotenone Mortality
================
Vincent Tam
February 12, 2019

library(tidyverse) library(janitor) library(broom) library(httk) library(drc) library(ggplot2) mortality = read\_csv("./RotenoneMortalityRate.csv") \#\# Replication 1 lo1 &lt;- loess(mortality$\`Grp 1 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 1 Mortality Rate`, main = "Replication 1", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.45)) xl = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(xl, predict(lo1,xl), col = 'red', lwd = 2) fit1 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 1 Mortality Rate`) summary(fit1) fitted(fit1) fit1 %&gt;% broom::tidy() pred1 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 1 Mortality Rate`, family = binomial(link = "logit")) summary(pred1) predict(pred1, type = "response") pred1 %&gt;% broom::tidy()

abline(lm(data$\`Concentration (micromolar)\` ~ data$`Grp 1 Mortality Rate`)) lines(data, predict(fit, data.frame(data$'Concentration (micromolar)')), col = "red")

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

Including Plots
---------------

You can also embed plots, for example:

![](CompToxAssn1_files/figure-markdown_github/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
