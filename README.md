# Web Scrapping Github Repositories

In order to grasp a comprehensive scope of current status of all repositories under our lab, I built this brief web scraper to organize my workflow. The motivation for search selection is based on the need of each repo. To gauge the level of needs, I chose to parse out `the number of issues`. Additionally, `last updated dates` are also important to understand whether the repo is actively managed at this time.

<center><img src='./fig/webpage.png' width=80%></center>

For each page that lists repositories, individual url was used to request html output. Then there were two items that were parsed out from the html output which was converted into utf-8 format. 

Aforementioned attributes of interest were parsed using `re` and in-built string methods.

<center><img src='./fig/output-b4-filtering.jpg' width=80%></center>

The following two filters were applied to further narrow down the list.
1. Nubmer of Issues > 0
2. Last Updated Date is no earlier than `2021-09-01`

<center><img src='./fig/output.jpg' width=80%></center>

Recent request from our lab was to generate a list of active PRs in NeuroData organization, thus further scrapping was conducted to extract `title of PR`, `PR's direct URL`, and `the author who made the initial PRs`. The output is exported as an excel spreadsheet, which was subsequently registered as a NeuroData github issue.

## Example output of the extracted and wranggled web-scrapping result

Lead | Repository | PR Name | PR Url
-- | -- | -- | --
adam2392 | scikit-learn | [TEST PR] Adding oblique trees (i.e. Forest-RC) to cythonized tree module | https://github.com//neurodata/scikit-learn/pull/11
adam2392 | scikit-learn | [TEST PR] Oblique forests | https://github.com//neurodata/scikit-learn/pull/10
adam2392 | scikit-learn | Tom/grid to graph 26 | https://github.com//neurodata/scikit-learn/pull/8
LizaNaydanova | ProgLearn | Added streaming capability for ODIN | https://github.com//neurodata/ProgLearn/pull/528
LizaNaydanova | ProgLearn | Added neural network scene segmentation tutorial. | https://github.com//neurodata/ProgLearn/pull/527