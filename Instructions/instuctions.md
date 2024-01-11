HDAT9700 Statistical Modelling II
================
Mark Hanly

- [Overview](#overview)
  - [Topic options](#topic-options)
  - [Report structure](#report-structure)
    - [Introduction](#introduction)
    - [Methods](#methods)
    - [Results](#results)
    - [Discussion](#discussion)
    - [References](#references)
    - [Appendix](#appendix)
    - [Student declaration](#student-declaration)
  - [Accessing and submitting your
    report](#accessing-and-submitting-your-report)
  - [Statistical code](#statistical-code)
  - [Marking rubric](#marking-rubric)
  - [ChatGPT and other Generative AI
    tools.](#chatgpt-and-other-generative-ai-tools)
  - [Plagiarism](#plagiarism)
  - [Late submissions and Special
    Considerations](#late-submissions-and-special-considerations)
- [Option 1: Causal inference via
  matching](#option-1-causal-inference-via-matching)
  - [Overview](#overview-1)
  - [Research question](#research-question)
  - [Data](#data)
    - [Hints](#hints)
- [Option 2: Interrupted time series
  analysis](#option-2-interrupted-time-series-analysis)
  - [Overview](#overview-2)
  - [Research question](#research-question-1)
  - [Data](#data-1)
    - [Hints](#hints-1)
- [Option 3: Longitudinal multilevel
  modelling](#option-3-longitudinal-multilevel-modelling)
  - [Overview](#overview-3)
  - [Research question](#research-question-2)
  - [Data](#data-2)
    - [Hints](#hints-2)
- [Marking rubric](#marking-rubric-1)

# Overview

For your final assessment you are required to prepare a short analysis
report applying one of the statistical techniques covered in the course.
The report should be presented in IMRD
(Introduction/Methods/Results/Discussion) format and should be
approximately 1500 words.

## Topic options

You can base your report on one of the following three options:

**Causal analysis via matching** Exploring the causal effect of young
maternal age on perinatal outcomes

**Interrupted time series** Evaluating the effect of media coverage
following publication of new drug safety research on dispensing of oral
contraceptives using time series data

**Longitudinal multilevel modelling** Modelling children’s weight change
between 6 - 24 months

A dataset is supplied for each option. A more detailed description of
each option is provided at the end of this document.

## Report structure

Your report should be presented in IMRaD format (Introduction, Methods,
Results and Discussion) and be approximately 1500 words long. The word
count does not include tables, figures, footnotes, references,
appendices, or the student declaration. You should include up to five
tables/figures in the main body of the report, with supplementary
tables/figures included in the appendix.

Below is in an example of how you might lay out your report:

1.  Student declaration  
2.  Introduction (200-300 words approx.)
3.  Methods (550-650 words approx.)
4.  Results (350-450 words approx.)
5.  Discussion (200-300 words approx.)
6.  References (As appropriate)
7.  Appendix (As appropriate)

### Introduction

*200-300 words approx.*

The introduction section should provide some brief background
information on the research area and motivate why the research question
is of scientific interest. Because you have been presented with a
research topic you do not need to make this section very detailed, you
should simply demonstrate that you have understood the relevance of the
research question, and make the connections between the research
question, the available data and the analytic approach.

### Methods

*550-650 words approx.*

In the methods section you should describe in detail the analyses that
were undertaken, and why. It is important that you demonstrate that you
understand the rationale for applying a particular statistical technique
and/or any alternative model specifications/model diagnostics. You
should demonstrate your understanding of the statistical methods with
appropriate references to the literature.

### Results

*350-450 words approx.*

In the results section you should begin with a descriptive overview of
the dataset you have used, including summaries of any key variables.
Follow this with a summary of your analysis results using appropriate
tables and figures, as well as describing your main results in text.
Appropriate model diagnostics and/or alternative model specifications
should be included but can be presented in the appendix if they are
lengthy.

### Discussion

*200-300 words approx.*

In the discussion you should summarise your main findings, interpret
your results in more detail, discuss implications, and acknowledge
strengths and limitations of the analysis, with an emphasis on the
statistical methods applied.

### References

Your report should include 5-10 appropriate references to the
literature, with a full list of references provided in the references
section. You can use your preferred referencing style. More information
on academic referencing can be found on the UNSW website:
<https://student.unsw.edu.au/referencing>

### Appendix

The appendix should include any supplementary material that does not fit
in the body of the report, for example additional descriptive tables or
model diagnostics plots.

### Student declaration

All assessments should include a copy of the student declaration
regarding plagiarism, student academic misconduct and proper back-up of
your assessment. The text of the declaration is provided below. You
should copy this into your report and tick the boxes to indicate your
agreement with the statements.

> I declare that this assessment item is my own work, except where
> acknowledged, and has not been submitted for academic credit elsewhere
> or previously, or produced independently of this course (e.g. for a
> third party such as your place of employment) and acknowledge that the
> assessor of this item may, for the purpose of assessing this item: (i)
> Reproduce this assessment item and provide a copy to another member of
> the University; and/or (ii) Communicate a copy of this assessment item
> to a plagiarism checking service (which may then retain a copy of the
> assessment item on its database for the purpose of future plagiarism
> checking).  
> - \[ \] I understand and agree I certify that I have read and
> understood the University Rules in respect of Student Academic
> Misconduct.  
> - \[ \] I understand and agree I have a backup copy of the
> assessment.  
> - \[ \] I understand and agree

## Accessing and submitting your report

The data for each assessment option, and any additional hints or
instructions, will be made available in a GitHub repository. You can
clone this repository through a hyperlink provided by your course
convenor. To submit your assessment files, add and commit them to the
repo, and then push to GitHub. You are welcome to explore all three
assessment options before deciding which option to choose.

Please submit your assessment as an R Markdown file (.Rmd), interweaving
the text of your report, statistical code and results. You are welcome
to render the .Rmd file to whatever outcome format you prefer,
e.g. `github_document`, `html_document`, `pdf_document` etc. You can
control this by specifying the appropriate output format in the `yaml`
section at the top of your .Rmd file, as shown below.

``` yaml
---
title: "HDAT9700 Statistical Modelling II"
subtitle: "Assessment 2 ..."
author: "Your Name"
output: 
    github_document:
        toc: true
        toc_depth: 3
---
```

For more information on output formats see
<https://rmarkdown.rstudio.com/lesson-9.html>.

Make sure to push all files to your repo when you submit, i.e. you
should include your .Rmd file, the corresponding rendered file and any
embedded images or plots. If you render your .Rmd file to `pdf_document`
or `github_document` you should be able to open and read the formatted
document in your GitHub repo to make sure everything has pushed
correctly.

## Statistical code

You should carry out all data preparation and statistical analyses using
R. Include all R code you use to prepare and analyse the data as part of
your submission. Following best practice in reproducibility, it should
be straightforward for the marker to reproduce your entire analysis
using only the raw data and the code you submit. Your code should be
clearly commented, to assist in this reproducibility, and to demonstrate
your understanding of the analyses being performed.

## Marking rubric

Your assessment will be marked according to the marking rubric on the
following page. Four criteria are assessed:

- Conceptual understanding (30%)
- Application of statistical method (30%)
- Interpretation (30%)
- Presentation (10%)

More detail on the marking rubric is included at the end of this
document.

## ChatGPT and other Generative AI tools.

Please indicate if you use ChatGPT or other Generative AI tools to help
you write test or code. This can be done by including a comment in your
.Rmd file, such as “ChatGPT used to develop text in this section” or
“ChatGPT used to develop code in this chunk”.

## Plagiarism

While you are welcome to discuss the assessment with your classmates,
the final written report and statistical code must be your own work.
References to other scholarly work should be properly cited. **Direct
plagiarism will not be accepted.** Past incidences of plagiarism have
resulted in students retaking a new assessment. You can read academic
integrity at UNSW and examples of plagiarism here:
<https://www.student.unsw.edu.au/plagiarism>

## Late submissions and Special Considerations

A penalty of 5% per day will apply to late submissions. Special
considerations are handled centrally, not by the course convenor. For
more information on special considerations please see
<https://www.student.unsw.edu.au/special-consideration>

If you think you are going to submit after the deadline, with or without
a special consideration, it is always good to communicate with the
course convenor as early as possible!

------------------------------------------------------------------------

# Option 1: Causal inference via matching

## Overview

Young maternal age is associated with adverse pregnancy outcomes,
including low birthweight and preterm birth. As a result, in some
contexts “teenage pregnancy” has been framed as a public health problem.
However, many academics and health professionals have argued that young
maternal age doesn’t cause adverse outcomes, but rather socio-economic
disadvantage is the primary factor underlying different perinatal
outcomes experienced by younger and older mothers. (cf. Lawlor and Shaw
(2002) “Too much too young? Teenage pregnancy is not a public health
problem”, International Journal of Epidemiology (31) p552-554, and the
subsequent counterpoint articles, for more on this debate).

In this assignment you will use data on maternal and family demographics
and child birth outcomes, to estimate the causal effect of young
maternal age on the risk of preterm birth. Use the MatchIt package in R
to identify a matched “treatment” and control group, who are as similar
as possible in terms of appropriate pre-treatment variables. A DAG
should be used to guide variable selection and highlight limitations of
the available data.

## Research question

> What is the causal effect of young maternal age on the risk of preterm
> birth?

## Data

The data for this assessment are drawn from the National Children’s
Study Archive. The National Children’s Study (NCS) collected birth and
early childhood data on more than 5,000 children and their families in
the USA from 2009-2014. The NCS teaching database contains base
child-level data, as well as several topic-specific modules.

You are provided with a dataset named **ncs_child_mom_matching.csv**.
This file contains information on 3,848 singleton births including
mother and child demographics, birth outcomes and area-level statistics.
The data are drawn from the NCS base Child dataset, and the Mother’s
Pregnancy Health module. Some data preparation has already taken place,
in particular, the aforementioned Child and Mother datasets have been
merged, and variables with high proportions of missing data have been
removed.

The following resources will be useful to help understand the data:

- NCS study description and guide
  `NCS_Archive_Study_Description and User's Manual_July 2017.pdf`
- Codebook for the base Child data
  `NCS_Teaching_Child_V1_1_Codebook_508.pdf`
- Codebook for the Mother’s Pregnancy Health module
  `NCS_Teaching_Child_V1_1_Codebook_508.pdf`

### Hints

- Young maternal age is usually defined as maternal age less than or
  equal to 19 years.
- Preterm birth is usually defined as gestational age less than or equal
  to 37 weeks.
- Use the `MatchIt` package in R to explore different matching
  approaches.
- Assess balance between the treated and matched control groups using
  numeric and graphical summaries.
- Not all variables are necessarily appropriate for matching and not all
  variables you would like to match on will be available. Use DAGs to
  guide variable selection and highlight limitations.
- Remember to apply the matching weights when analysing matched data.

------------------------------------------------------------------------

# Option 2: Interrupted time series analysis

## Overview

Oral contraceptives (“birth control pills”) are taken by women to
prevent pregnancy and to treat other conditions such as endometriosis or
polycystic ovary syndrome. There are two main types of oral
contraceptive pills, the most common being the combined pill, which
contains a combination of the hormones oestrogen and progestogen in
various formulations and doses. The second type is the progestogen-only
pill (also called the “mini pill”) that contains only progestogen.

Although they are effective at reducing the occurrence of unwanted
pregnancy, the combined pill increases the risk of blood clot formation,
such as deep vein thrombosis, pulmonary embolism and stroke. A paper
published in the BMJ on 26 May 2015 was the first to quantify the risk
associated with different oestrogen/progestogen combinations and
received substantial media attention worldwide (Vinogradova et al. Use
of combined oral contraceptives and risk of venous thromboembolism:
nested case-control studies using the QResearch and CPRD databases.
<https://doi.org/10.1136/bmj.h2135>). Note that there is no increased
risk of blood clots in women using the progestogen-only pill.

In this assessment you will use time series data to explore the impact
of the media attention surrounding the publication of this study on the
PBS-subsidised dispensing of combined and progestogen-only oral
contraceptives. In Australia, combined contraceptive pills containing
levonorgestrel/ethinylestradiol, norethisterone/ethinylestradiol and
norethisterone/mestranol are subsidised through the PBS. Other combined
pill formulations are not subsidised, such as those containing
drosperinone, cyproterone and desogestrel and are not captured in the
data. Several progestogen-only mini pills are also subsidised, including
levonorgestrel and norethisterone.

## Research question

> What was the impact of the media attention around the increased risk
> of thrombosis associated with oral contraceptive use on dispensing of
> combined oral contraceptives?

## Data

Data are provided in the file contraceptives.csv. This file includes
monthly counts (per 10,000 women of reproductive age) of PBS-subsidised
dispensings of combined oral contraceptives (“combined”) and
progestogen-only contraceptives (“mini”) between Jan 2013 and Dec 2016.
The peak of the media attention was in the last week of May 2015.

### Hints

- Use appropriate visualisations to explore the raw data.
- Explore seasonal effects, autocorrelation, and delayed impacts with
  statistics and tests.
- Create appropriate variables to model changes after the intervention.
- Use an appropriate model to explore whether there was a change in
  combined oral contraceptive dispensing following the media attention.
- Plot the predicted counterfactual to visualise any change in
  dispensing following the media attention.
- Use the “control” series (dispensing of progestogen-only oral
  contraceptives) and comment on the findings in relation to those from
  the combined pill series.

------------------------------------------------------------------------

# Option 3: Longitudinal multilevel modelling

## Overview

Children’s growth is frequently monitored during their infancy and
understanding growth trajectories is important for identification of
chronic disorders or other health issues, reassuring parents and
providing information on the health of a nation’s children.

In this assignment you will use data including repeated measurements of
children’s weight to model children’s weight change over time. The data
also include information on other infant, environmental and maternal
factors, and you will also explore which of them could further improve
the model for children’s weight gain. You should use the nlme package in
R for carrying out your longitudinal multilevel modelling.

## Research question

> What is the optimal longitudinal multilevel model to describe
> children’s weight change over time?

## Data

The data for this assessment are drawn from the National Children’s
Study Archive. The National Children’s Study (NCS) collected birth and
early childhood data on more than 5,000 children and their families in
the USA from 2009-2014. The NCS teaching database contains base
child-level data, as well as several topic-specific modules.

You are provided with a dataset named **ncs_child_repeated.csv**. This
file contains information on child, mother and household demographics
for 4,531 kids, with 1-4 weight observations for each child (12,654
observations overall). The data are drawn from the NCS base Child
dataset, and the Child health module, including children’s weight
measurements at 6, 12, 18 and 24 months after their birth. Some data
preparation has already taken place, in particular, the above files have
been merged, only singleton births and the oldest siblings have been
included (i.e. only one child per mother), and variables with high
proportions of missing data have been removed.

The following resources will be useful to help understand the data:

- NCS study description and guide
  `NCS_Archive_Study_Description and User's Manual_July 2017.pdf`
- Codebook for the base Child data
  `NCS_Teaching_Child_V1_1_Codebook_508.pdf`
- Codebook for the Child Health module
  `NCS_Teaching_ChildHealth_V1_Codebook_508.pdf`

### Hints

- The outcome weight (`visit_wt`) can be modelled as a function of
  continuous age (`child_age`) or ordinal visit timing (`visit`).
- Conduct appropriate EDA to understand the relationship between weight
  and age.
- Use the `nlme` package for carrying out your multilevel modelling,
  starting with simple models and progressively exploring more complex
  structures.
- There is only one child per mother, and thus you do not need to
  include mother as an additional level in your multilevel modelling.
- Explore alternative functions of time to improve model fit.
- Explore other covariates that help to explain variation in children’s
  weight.
- Some child health variables (e.g. `gastro`, `diarrhoea`,
  `ear_infection`) were not measured on every visit occasion, so if
  these are included you will need to think about how to handle that.

------------------------------------------------------------------------

# Marking rubric

<table class="table table-striped table-hover" style="margin-left: auto; margin-right: auto;border-bottom: 0;">
<caption>
HDAT9700 Statistical Modelling II, Assessment 2 Marking Rubric
</caption>
<thead>
<tr>
<th style="text-align:left;">
Criteria
</th>
<th style="text-align:left;">
Weight
</th>
<th style="text-align:left;">
HD
</th>
<th style="text-align:left;">
DN
</th>
<th style="text-align:left;">
CR
</th>
<th style="text-align:left;">
PS
</th>
<th style="text-align:left;">
FL
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;width: 3cm; font-weight: bold;border-right:1px solid;width: 1cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;">
Conceptual understanding
</td>
<td style="text-align:left;">
30%
</td>
<td style="text-align:left;">
Demonstrates a deep understanding of the relevance of the statistical
technique, its appropriateness to the research question at hand, its
benefits over alternative approaches, and its limitations. Incorporates
content beyond what was covered in the tutorial, such as the pre-reading
and additional references cited in the course notes or other scholarly
work.
</td>
<td style="text-align:left;">
Demonstrates a solid understanding of the statistical technique,
including its relevance and appropriateness for the research question.
Discusses some benefits and limitations but may not delve as deeply into
additional readings.
</td>
<td style="text-align:left;">
Demonstrates a satisfactory understanding of the statistical technique,
though it may be somewhat limited. Addresses the suitability to the
research design and mentions advantages and limitations.
</td>
<td style="text-align:left;">
Demonstrates a limited understanding of the statistical method, with
minimal exploration of its relevance or appropriateness. Offers some
insight into its advantages or limitations, but the depth is lacking.
</td>
<td style="text-align:left;">
Demonstrates a very limited understanding of the statistical technique,
its suitability to the research design, and its advantages or
limitations. May lack critical analysis and depth of understanding.
</td>
</tr>
<tr>
<td style="text-align:left;width: 3cm; font-weight: bold;border-right:1px solid;width: 1cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;">
Application of statistical method
</td>
<td style="text-align:left;">
30%
</td>
<td style="text-align:left;">
Analysis goes beyond the basics covered in the face-to-face tutorial.
The statistical method is correctly applied, variables are selected and
justified, alternative model fits are explored when appropriate,
suitable diagnostic tests are performed, presented, and correctly
interpreted. The rationale for carrying out models/diagnostics is
clearly understood and communicated. All code has a clear purpose and
runs without errors.
</td>
<td style="text-align:left;">
Analysis is largely correct, but it does not go beyond the replication
of what was covered in the tutorial. Limited model specifications and
diagnostics are explored or are presented without demonstrating a
complete understanding of why they are performed. Some code may have an
unclear purpose or produce errors.
</td>
<td style="text-align:left;">
The analysis attempts to apply the statistical method, but there are
significant shortcomings. The correct method may be used, but major
errors invalidate the results. Sections of code do not run or have
unclear purposes. Appropriate diagnostic tests are not performed or are
misinterpreted to some extent.
</td>
<td style="text-align:left;">
The analysis contains some errors and limitations. The choice of the
statistical method is inappropriate, or if the correct method is used,
there are some errors that may invalidate the results. Some sections of
code do not run or have unclear purposes, and diagnostic tests are
inadequately performed and interpreted.
</td>
<td style="text-align:left;">
The analysis is severely flawed, with a lack of understanding and
competence. Inappropriate statistical methods are employed, or the
correct method is so severely misapplied that the results are
unreliable. The majority of the code does not run or has unclear
purposes, and diagnostic tests are either not performed or are grossly
misinterpreted.
</td>
</tr>
<tr>
<td style="text-align:left;width: 3cm; font-weight: bold;border-right:1px solid;width: 1cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;">
Interpretation
</td>
<td style="text-align:left;">
30%
</td>
<td style="text-align:left;">
All relevant statistical output is clearly presented. Output is
interpreted correctly and thoroughly. Implications follow clearly from
the analysis, are nuanced, and demonstrate a deep appreciation for the
strengths and limitations of the analysis.
</td>
<td style="text-align:left;">
Analysis output is presented adequately, with most important features
included. Interpretation is generally accurate but may lack some nuance
or contain minor inaccuracies or misinterpretations. Implications,
strengths, and limitations are discussed at a satisfactory level.
</td>
<td style="text-align:left;">
Correct output but may be missing or presented indiscriminately, without
proper interpretation or highlighting of important statistics.
Interpretation is limted or inaccurate. Implications are absent or do
not logically follow from the analysis. Strengths and limitations are
inaccurate or missing.
</td>
<td style="text-align:left;">
The analysis output is poor, with critical components missing or
incorrectly presented. Interpretation is limted or includes errors, and
there is a complete absence of implications. Strengths and limitations
are not addressed adequately.
</td>
<td style="text-align:left;">
The analysis output is severely lacking, with no discernible
presentation or interpretation of important statistical output. There
are no implications drawn from the analysis, and there is no
understanding of the strengths and limitations of the analysis.
</td>
</tr>
<tr>
<td style="text-align:left;width: 3cm; font-weight: bold;border-right:1px solid;width: 1cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;width: 4cm; font-weight: bold;border-right:1px solid;">
Presentation
</td>
<td style="text-align:left;">
10%
</td>
<td style="text-align:left;">
The report is exceptionally well-written and professionally formatted.
Code is rigorously documented. Tables and figures are presented to a
publication-quality, with clear titles, labeling, and legends.
References are appropriate and presented consistently.
</td>
<td style="text-align:left;">
The report is well presented, with only a small number of typographical
or grammatical errors. Tables and figures are generally interpretable
but may lack some details to reach publication standards, such as
inadequate labeling, legends, or scaling. References are present but may
have minor errors. Code commenting is present but not overly detailed.
</td>
<td style="text-align:left;">
The report is adequately written and presented, with typos and
grammatical errors. Tables and figures are either not presented or are
difficult to interpret due to insufficient headings, labels, legends,
etc. Code documentation is poor. References may be absent or not
presented in a consistent academic format.
</td>
<td style="text-align:left;">
The report quality is basic, with several typographical and grammatical
errors. Tables and figures are not presented adequately, or extensive
output is presented indiscriminately, making interpretation challenging.
Code documentation is lacking. References may be absent or poorly
formatted.
</td>
<td style="text-align:left;">
The report quality is severely lacking, with extensive typographical and
grammatical errors. Tables and figures are missing or presented in a
manner that renders them virtually useless. Code documentation is
virtually non-existent. References are entirely absent or improperly
formatted.
</td>
</tr>
</tbody>
<tfoot>
<tr>
<td style="padding: 0; " colspan="100%">
<span style="font-style: italic;">Note: </span>
</td>
</tr>
<tr>
<td style="padding: 0; " colspan="100%">
<sup></sup> HD=Higher Distinction (85-100%); DN=Distinction (75-84%);
CR=Credit (65-74%); PS=Pass (50-64%); FL=Fail (0-50%)
</td>
</tr>
</tfoot>
</table>
