Rotenone Mortality
================
Vincent Tam
February 12, 2019

library(tidyverse) library(janitor) library(broom) library(httk) library(drc) library(ggplot2) mortality = read\_csv("./RotenoneMortalityRate.csv")

Replication 1
-------------

lo1 &lt;- loess(mortality$\`Grp 1 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 1 Mortality Rate`, main = "Replication 1", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.45)) x1 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x1, predict(lo1,x1), col = 'red', lwd = 2) fit1 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 1 Mortality Rate`) summary(fit1) fitted(fit1) fit1 %&gt;% broom::tidy() pred1 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 1 Mortality Rate`, family = binomial(link = "logit")) summary(pred1) predict(pred1, type = "response") pred1 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 1 Mortality Rate`))

Replication 2
-------------

lo2 &lt;- loess(mortality$\`Grp 2 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 2 Mortality Rate`, main = "Replication 2", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.45)) x2 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x2, predict(lo2,x2), col = 'red', lwd = 2) fit2 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 2 Mortality Rate`) summary(fit2) fitted(fit2) fit2 %&gt;% broom::tidy() pred2 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 2 Mortality Rate`, family = binomial(link = "logit")) summary(pred2) predict(pred2, type = "response") pred2 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 2 Mortality Rate`))

Replication 3
-------------

lo3 &lt;- loess(mortality$\`Grp 3 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 3 Mortality Rate`, main = "Replication 3", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.45)) x3 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x3, predict(lo3,x3), col = 'red', lwd = 2) fit3 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 3 Mortality Rate`) summary(fit3) fitted(fit3) fit3 %&gt;% broom::tidy() pred3 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 3 Mortality Rate`, family = binomial(link = "logit")) summary(pred3) predict(pred3, type = "response") pred3 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 3 Mortality Rate`))

Replication 4
-------------

lo4 &lt;- loess(mortality$\`Grp 4 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 4 Mortality Rate`, main = "Replication 4", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.5)) x4 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x4, predict(lo4,x4), col = 'red', lwd = 2) fit4 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 4 Mortality Rate`) summary(fit4) fitted(fit4) fit4 %&gt;% broom::tidy() pred4 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 4 Mortality Rate`, family = binomial(link = "logit")) summary(pred4) predict(pred4, type = "response") pred4 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 4 Mortality Rate`))

Replication 5
-------------

lo5 &lt;- loess(mortality$\`Grp 5 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 5 Mortality Rate`, main = "Replication 5", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.45)) x5 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x5, predict(lo5,x5), col = 'red', lwd = 2) fit5 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 5 Mortality Rate`) summary(fit5) fitted(fit5) fit5 %&gt;% broom::tidy() pred5 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 5 Mortality Rate`, family = binomial(link = "logit")) summary(pred5) predict(pred5, type = "response") pred5 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 5 Mortality Rate`))

Replication 6
-------------

lo6 &lt;- loess(mortality$\`Grp 6 Mortality Rate\`~mortality$`Concentration (micromolar)`) plot(mortality$\`Concentration (micromolar)\`, mortality$`Grp 6 Mortality Rate`, main = "Replication 6", sub = "Rotenone Conc on Mortality Rate", xlab = "Rotenone Concentration (micromolar)", ylab = "Mortality Rate", ylim = c(0, 0.5)) x6 = seq(min(mortality$\`Concentration (micromolar)\`),  max(mortality$`Concentration (micromolar)`), (max(mortality$\`Concentration (micromolar)\`) -  min(mortality$`Concentration (micromolar)`))/1000) lines(x6, predict(lo6,x6), col = 'red', lwd = 2) fit6 = lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 6 Mortality Rate`) summary(fit6) fitted(fit6) fit6 %&gt;% broom::tidy() pred6 = glm(factor(mortality$\`Concentration (micromolar)\`) ~ mortality$`Grp 6 Mortality Rate`, family = binomial(link = "logit")) summary(pred6) predict(pred6, type = "response") pred6 %&gt;% broom::tidy() abline(lm(mortality$\`Concentration (micromolar)\` ~ mortality$`Grp 6 Mortality Rate`))
