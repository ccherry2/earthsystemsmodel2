---
author-meta:
- Charlotte Cherry
- Joyce Yang
- Yiwen Zhang
bibliography:
- content/manual-references.json
date-meta: '2020-12-05'
header-includes: '<!--

  Manubot generated metadata rendered from header-includes-template.html.

  Suggest improvements at https://github.com/manubot/manubot/blob/master/manubot/process/header-includes-template.html

  -->

  <meta name="dc.format" content="text/html" />

  <meta name="dc.title" content="Manuscript Title" />

  <meta name="citation_title" content="Manuscript Title" />

  <meta property="og:title" content="Manuscript Title" />

  <meta property="twitter:title" content="Manuscript Title" />

  <meta name="dc.date" content="2020-12-05" />

  <meta name="citation_publication_date" content="2020-12-05" />

  <meta name="dc.language" content="en-US" />

  <meta name="citation_language" content="en-US" />

  <meta name="dc.relation.ispartof" content="Manubot" />

  <meta name="dc.publisher" content="Manubot" />

  <meta name="citation_journal_title" content="Manubot" />

  <meta name="citation_technical_report_institution" content="Manubot" />

  <meta name="citation_author" content="Charlotte Cherry" />

  <meta name="citation_author_institution" content="Department of Civil Engineering, University of Illinois Urbana-Champaign" />

  <meta name="citation_author" content="Joyce Yang" />

  <meta name="citation_author_institution" content="Department of Civil Engineering, University of Illinois Urbana-Champaign" />

  <meta name="citation_author" content="Yiwen Zhang" />

  <meta name="citation_author_institution" content="Department of Civil Engineering, University of Illinois Urbana-Champaign" />

  <link rel="canonical" href="https://ccherry2.github.io/earthsystemsmodel2/" />

  <meta property="og:url" content="https://ccherry2.github.io/earthsystemsmodel2/" />

  <meta property="twitter:url" content="https://ccherry2.github.io/earthsystemsmodel2/" />

  <meta name="citation_fulltext_html_url" content="https://ccherry2.github.io/earthsystemsmodel2/" />

  <meta name="citation_pdf_url" content="https://ccherry2.github.io/earthsystemsmodel2/manuscript.pdf" />

  <link rel="alternate" type="application/pdf" href="https://ccherry2.github.io/earthsystemsmodel2/manuscript.pdf" />

  <link rel="alternate" type="text/html" href="https://ccherry2.github.io/earthsystemsmodel2/v/250654c369197cf6b502bb48a38b7acbcc4f915c/" />

  <meta name="manubot_html_url_versioned" content="https://ccherry2.github.io/earthsystemsmodel2/v/250654c369197cf6b502bb48a38b7acbcc4f915c/" />

  <meta name="manubot_pdf_url_versioned" content="https://ccherry2.github.io/earthsystemsmodel2/v/250654c369197cf6b502bb48a38b7acbcc4f915c/manuscript.pdf" />

  <meta property="og:type" content="article" />

  <meta property="twitter:card" content="summary_large_image" />

  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />

  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />

  <meta name="theme-color" content="#ad1457" />

  <!-- end Manubot generated metadata -->'
keywords:
- Data
- Science
- Earth
- Systems
- Random
- Forest
lang: en-US
manubot-clear-requests-cache: false
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
title: Manuscript Title
...






<small><em>
This manuscript
([permalink](https://ccherry2.github.io/earthsystemsmodel2/v/250654c369197cf6b502bb48a38b7acbcc4f915c/))
was automatically generated
from [ccherry2/earthsystemsmodel2@250654c](https://github.com/ccherry2/earthsystemsmodel2/tree/250654c369197cf6b502bb48a38b7acbcc4f915c)
on December 5, 2020.
</em></small>

## Authors



+ **Charlotte Cherry**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [ccherry2](https://github.com/ccherry2)<br>
  <small>
     Department of Civil Engineering, University of Illinois Urbana-Champaign
  </small>

+ **Joyce Yang**<br><br>
  <small>
     Department of Civil Engineering, University of Illinois Urbana-Champaign
  </small>

+ **Yiwen Zhang**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [Yiwen-Zhang97](https://github.com/Yiwen-Zhang97)<br>
  <small>
     Department of Civil Engineering, University of Illinois Urbana-Champaign
  </small>



## Abstract {.page_break_before}




## II. Introduction

Urban areas take up a relatively small percentage of the Earth’s land cover but have disproportionately large impacts on the climate and on humans. They are major drivers of emissions and climate change, serve as economic and social centers around the world, and house most of the human population. However, the very nature of their small physical footprint makes it challenging to study their impact on humans and the environment accurately and comprehensively.

To grapple with uncertainty and develop climate change mitigation and/or adaptation strategies, it is crucial for policymakers and planners for urban areas to understand different climate projections and scenarios, as well as urban-specific dynamics. Earth Systems Models (ESMs) are complex mathematical models that produce climate projections. They represent physical processes in the atmosphere, ocean, cryosphere, biogeochemical cycling in terrestrial and marine ecosystems, and interactions and feedbacks between these domains. These models are highly computationally demanding – taking long amounts of time and storage capacity to run over timescales of hundreds of years. This can make ESMs impractical for many uses, particularly policy analyses. Interested users may not have the capacity to utilize GCMs on a typical computer or reasonable budget.

Currently, most state-of-the-art ESMs used today for climate change projections do not explicitly parameterize urban areas, largely due to their small area. While this does not significantly impact the quality of regular or large-scale studies, this lack of explicit parameterization limits our ability to adequately capture unique urban characteristics and dynamics. The Community Earth Systems Model (CESM) is one of the few state-of-the-art ESMs that explicitly parameterizes urban areas, with the latest version even distinguishing between three separate urban density classes. Most quantitative attributions have been typically done for non-urban surfaces, but effective development decisions and local actions to manage risks rely on robust urban climate projections. This is the motivation for us to use CESM, which has a representation of urban areas, to build a location dependent emulator, and apply it to other ESMs in order to get their urban temperature responses.

While CESM provides the advantage of explicit urban parameterization, it does still require significant supercomputing resources, which may limit its usefulness. Therefore, there is a desire to use artificial intelligence to reduce this load. A climate emulator could achieve this by statistically replicating the nonlinear behavior of ESMs more quickly and with less computing power. This project will use machine learning methods to develop a model that can emulate urban temperatures (using other atmospheric forcing variables), where the risk of heat waves in the future could have the greatest negative impacts on human health. This model will be loosely based off of the conceptual framework presented by Zhao et al (2020) - "Global multi-model projections of local urban climates" (currently in press). Urban areas in this dataset refers loosely to areas where people live (i.e., not oceans or uninhabitable areas) but they exclusively correspond to cities.


## III. Methods

#### A. Exploratory Data Analysis Findings

#### B. Preprocessing Data for Model

#### C. Model Testing

##### 1. Neural Network

##### 2. Random Forest (Selection of Variables)

##### 3. Random Forest (Minimized Variables)


## IV. Results

### A. Metrics

### B. Model Performance


## V. Discussion and Conclusion

### A. Interpreting Results

### B. What We Learned

### C. Use of Machine Learning for Earth Systems Model Emulation


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
