+++
title = "Part II: Gender Achievement in the Leaving Certificate"
description = "So we do a little statistical analysis...<3 R"
date = "2023-01-30"
author = "Leon Reilly"
categories = [
    "R"
   
]
tags = [
    "Leaving Certificate",
    "School",
]
toc = false
draft = false

+++
[Preface]: I'm doing everything in R

### I.

This is a follow-up to my previous article about the LC. While H1 rates were an important consideration for what subjects we chose, we probably should've paid more attention to the H1 rates by gender. To be fair, however, nobody has (to my knowledge) visualised or even presented these statistics before, so it's not like we didn't do our DD.

Seeing the graph in the previous post got me thinking about if there any of the grades and subjects were independent, i.e., does gender have a relationship with grades? What I want to talk about today is the statistics the State Examinations Commission (SEC) releases that show the grade distribution by gender for each of the subjects examined for the LC. From looking at the graph in my previous article, it seems relatively clear that girls achieve a higher proportion of top grades (H4 or better). I'm going to first try and answer this question for English. Let's take a look at the data.

<iframe title="LC English Grade Distribution by Gender, 2019" aria-label="Grouped Bars" id="datawrapper-chart-aBaIm" src="https://datawrapper.dwcdn.net/aBaIm/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="610" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>

Girls outperform boys—pretty straightforward. To quantify how much better girls perform, we'll analyse the data. We need to consider what type of data we are working with. We only have count data for gender (categorical) and grades (categorical), so we'll use a contingency table. The chi-squared test tells us how much the observed data (the actual data) differs from what we would expect if there were no association between the variable, i.e., gender has no effect on the grade achieved—this is our null hypothesis. 



$$\chi ^{2}= \sum \frac{(O_{i}-E_{i})^{^{2}}}{E_{i}}$$

Unfortunately, the spreadsheet with all the original data is formatted awfully, so we'll have to construct the contingency table ourselves. 

```
library(confintr)
grade = c("H1", "H2", "H3", "H4", "H5", "H6", "H7", "H8")
value = c(1:8)
female = c(733,	2474,	4853,	6233,	5018,	2295,	415,	76)
male = c(448,	1566,	3367,	4851,	4554,	2524,	642,	168)
table = xtabs(cbind(female, male) ~ grade)


```

This gives us a contingency table like this.
   Grade | Male | Female
--------|--------|------
    H1 | 488 | 733
  H2 | 1566 | 2474
  H3 | 3367 | 4853
  H4 | 4861 | 6233
  H5 | 4554 | 5018
  H6 | 2524 | 2295
  H7 | 642 | 415
  H8 | 168 | 76

Now that we have our data in a table, we'll run our chi-squared test on it.

```
> chisq.test(table)

    Pearson's Chi-squared test

data:  table
X-squared = 441.65, df = 7, p-value < 2.2e-16
```

The high chi-squared value and very low p-value confirm what we could see visually from the graph: the results between gender and grades are not independent. We now want to determine the size of the effect of gender. By itself, the chi-squared test does not tell us how large the the association is between gender and grades. To do this, we'll use Cramer's V to determine the effect size. Cramer's V ranges from 0 to 1, where 0 indicates no association and 1 indicates a perfect association, where n is the sample or population size, r is the number of rows, and c is the number of columns in the contingency table. It's a bit like correlation.

$$\phi_{Cramer's V} = \sqrt{\frac{\chi^{2}}{n\cdot min(r-1);(c-1)}}$$

Additionally, to provide some more rigour, we'll calculate the mean and standard deviation of grades by gender by assigning a value to each grade (1 for H1 and 8 for H8).


```

cramersv(table)

female_mean = sum(value*female)/sum(female); female_mean
female_stdev = sqrt(sum(female*(value-female_mean)^2)/sum(female)); female_std
male_mean = sum(value*male)/sum(male); male_mean
male_stdev = sqrt(sum(male*(value-male_mean)^2)/sum(male)); male_std

-----

> cramersv(table)
[1] 0.104794
> female_mean = sum(value*female)/sum(female); female_mean
[1] 3.96185
> female_stdev = sqrt(sum(female*(value-female_mean)^2)/sum(female)); female_std
[1] 1.353199
> male_mean = sum(value*male)/sum(male); male_mean
[1] 4.240453
> male_stdev = sqrt(sum(male*(value-male_mean)^2)/sum(male)); male_std
[1] 1.404254
```


We get a Cramer's V of 0.1048. This is a small effect size but provides strong evidence of a substantive relationship between gender and grades. If we look at the average grades for both genders, we can see that girls perform better than boys (lower mean is better). This also tells us the direction in which Cramer's V points.

It's worth thinking about the mean and standard deviation values too. The data also seems to support the greater male variability hypothesis. This is the tendency for males to show greater variability than females for psychological traits. How does this apply to grades? We'd expect girls' grades to be less variable (more consistent) than boys' grades. We can also expect girls to achieve higher grades, on average. Let's repeat this analysis for some other LC subjects. 



<iframe title="χ2 Statistics for selected LC Subjects, 2019" aria-label="Table" id="datawrapper-chart-AHNkG" src="https://datawrapper.dwcdn.net/AHNkG/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="1052" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>


### III.

I think this table is super interesting. The top three subjects with the strongest association between gender and grade are Home Economics, Art, and Physics. Girls have a higher average grade in almost all subjects—almost a full grade higher (approx. +10 percentage points) in Home Economics—and are more consistent in all subjects, i.e., their standard deviation is lower. 

Boys outperform girls in Mathematics, Chemistry, and Applied Mathematics. Although, it's worth pointing out that Applied Mathematics has the lowest chi-squared statistic. It is also statistically insignificant. The fact that boys do better in these three subjects, however, doesn't neatly map onto the stereotype that girls are better at humanities and boys are better at STEM. In other STEM subjects, girls outperform boys, e.g. Physics, Biology, Technology, and Construction Studies.


### IV.

Unfortunately, I have no other data about other variables that would likely have an effect on grades, i.e., income levels, attending a fee-paying school, etc. I cannot control for these variables because the SEC doesn't collect this data<cite>[^1]</cite>. However, the fact we are testing the entire population rather than just a sample allows us to draw some conclusions with these limitations in mind. 

This was just a fun little project. But it also raises some important questions. Why are boys falling so far behind? Why are girls still weaker at Mathematics? What can we do to address these issues? They're worth thinking quite seriously about.


[^1]: I asked.