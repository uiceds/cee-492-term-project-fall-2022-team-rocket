---
title: Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning Model
keywords:
- markdown
- publishing
- manubot
lang: en-US
date-meta: '2022-09-23'
author-meta:
- Ishfaq Aziz
- Jesus Castro
- Chirayu Kothari
- Omar
header-includes: |-
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta name="dc.title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning Model" />
  <meta name="citation_title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning Model" />
  <meta property="og:title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning Model" />
  <meta property="twitter:title" content="Predicting Delamination in Concrete Bridge Decks from Ground Penetrating Radar Signals using Machine Learning Model" />
  <meta name="dc.date" content="2022-09-23" />
  <meta name="citation_publication_date" content="2022-09-23" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Ishfaq Aziz" />
  <meta name="citation_author_institution" content="CEE, UIUC" />
  <meta name="citation_author_orcid" content="XXXX-XXXX-XXXX-XXXX" />
  <meta name="twitter:creator" content="@johndoe" />
  <meta name="citation_author" content="Jesus Castro" />
  <meta name="citation_author_institution" content="CEE, UIUC" />
  <meta name="citation_author_orcid" content="312-508-2526" />
  <meta name="citation_author" content="Chirayu Kothari" />
  <meta name="citation_author_institution" content="CEE, UIUC" />
  <meta name="citation_author_orcid" content="XXXX-XXXX-XXXX-XXXX" />
  <meta name="citation_author" content="Omar" />
  <meta name="citation_author_institution" content="CEE, UIUC" />
  <meta name="citation_author_orcid" content="XXXX-XXXX-XXXX-XXXX" />
  <link rel="canonical" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta property="og:url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta property="twitter:url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta name="citation_fulltext_html_url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/" />
  <meta name="citation_pdf_url" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/23a39b797a4831f59e44eeedce9da389908cb0e2/" />
  <meta name="manubot_html_url_versioned" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/23a39b797a4831f59e44eeedce9da389908cb0e2/" />
  <meta name="manubot_pdf_url_versioned" content="https://uiceds.github.io/cee-492-term-project-fall-2022-team-rocket/v/23a39b797a4831f59e44eeedce9da389908cb0e2/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...






## Authors



+ **Ishfaq Aziz**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [johndoe](https://github.com/johndoe)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [johndoe](https://twitter.com/johndoe)<br>
  <small>
     CEE, UIUC
     · Funded by Grant XXXXXXXX
  </small>

+ **Jesus Castro**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [312-508-2526](https://orcid.org/312-508-2526)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [jcastr54](https://github.com/jcastr54)<br>
  <small>
     CEE, UIUC
  </small>

+ **Chirayu Kothari**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [chirayu4](https://github.com/chirayu4)<br>
  <small>
     CEE, UIUC
  </small>

+ **Omar**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [Omar](https://github.com/Omar)<br>
  <small>
     CEE, UIUC
  </small>



## Description of Data {.page_break_before}

The data set represents raw signals of Non-Destructive Evaluation (NDE) tests conducted by Ground Penetrating Radar (GPR) which were collected from in-service reinforced concrete bridge decks. The dataset was annotated using three classes in accordance with bridge deck repair: Class 1-No Delamination; Class 2-Delamination (delamination above top bar mat), and Class 3-Delamination (delamination below top bar mat).
The data will be obtained from https://commons.und.edu/data/19/ [1] which contains annotated dataset for the structural defects. Data is present in the. xlsx format. Each column in the dataset has an approximate length of 512 where the first column represents the time (ns), and the rest of the columns are all amplitudes of GPR signals. Hence, each raw signal (columns) is directly annotated to one of the three possible classes. In addition, some other information like the scan length and the coordinates of each signal scan is also provided. 

## Plan {.page_break_before}

Ground Penetrating Radar (GPR) is an imaging technique that uses wide-band sinusoidal electromagnetic waves, with frequencies ranging from 0.5 to 2 GHz, to produce high-resolution images of the subsurface materials. GPR is an effective tool for subsurface inspection and quality control on engineering construction projects. The survey method is rapid, nondestructive, and noninvasive. Interpretation of GPR data commonly helps to evaluate and measure different properties of a concrete structure.

The data collected from the GPR are usually presented in two different formats, A-scan and B-scan. Most modern devices have the capability to present the two formats simultaneously. The A-scan is the raw signal of energy received by the antenna shown as a function of time and signal strength (amplitude). The received signal in Figure 1a is an example of an A-scan. The B-scan, also known as radargram, is constructed from the sequence of multiple A-scans related to the position of the antenna, as shown in Figure 1b, where the depth is represented on the y-axis and the survey distance is shown on the x-axis orthogonal to the y-axis. The amplitude of the received signal is often shown as a color-coded intensity plot, often in grey, as shown in Figure 1c. B-scans are usually visually inspected to identify and locate any delamination within the concrete or to locate the reinforcement rebars.

The A-scan data is categorized into three classes based on the delamination conditions. Fast Fourier transform of the A-scans will be performed to obtain the peak frequency and peak width. These values will act as independent variables in the machine learning model to predict the delamination condition. The bridge health at each location where an A-scan is collected is categorized into three classes: Class 1 No delamination, Class 2 Delamination (above the top bar mat), and Class 3 Delamination (below the top bar mat). Around 10,000 labeled A-scans will be used to train the model and 3000 labeled A-scans will be utilized for validation. Later, the trained model will be tested on 3000 A-scans to predict the delamination condition. Finally, B-scans will be generated and deck conditions at different locations of the bridge will be predicted. 


This is the introduction.
Introduction provides information for readers that are not fully familiar with the project topic.


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
