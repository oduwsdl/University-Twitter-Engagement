# University-Twitter-Engagement

This repository contains source data related to the technical report, "[University Twitter Engagement: Using Twitter Followers to Rank Universities](https://arxiv.org)," published August 19, 2017. The goal of this study is to determine how the number of Twitter followers relates to academic prestige. We also consider additional web-based attributes that correlate with rankings but do not require expensive data collection. Please read the tech report which provides important context and details before proceeding.

## Table Of Contents

- [Data](#data)
    - [Expert Ranking Lists](#expert-ranking-lists)
    - [University Endowments](#university-endowments)
    - [IPEDS](#ipeds)
    - [NCAA](#ncaa)
	- [Twitter Dataset](#twitter-dataset)
- [Results](#results)
	- [ODU Ranking Lists](#odu-ranking-lists)	
- [Feedback / Questions?](#feedback--questions)

# Data

## Raw data

The raw, input data for our core analyses was obtained from the following sources:

### Expert Ranking Lists

This source data was extracted from the 2015-2016 academic rankings of <a href="http://www.usnews.com/education/best-global-universities/rankings" target="_blank">U.S. News</a>, <a href="https://www.timeshighereducation.com/world-university-rankings" target="_blank">Times Higher Education</a>, <a href="http://www.shanghairanking.com/ARWU2016.html" target="_blank">Academic Rankings of World Universities</a> and <a href="http://new.time.com/money/best-colleges/rankings/best-colleges/" target="_blank">Money Magazine</a> for the top 264 universities in the United States. These institutions were ranked based on 12 indicators that measure their academic research performance and their global and regional reputations. Note: The ranking data was collected during August 2016. It is possible the ranking pages have been updated subsequent to when the data were originally collected. The list contents as they appeared during our data collection is shown in the [`Expert_Ranking_Lists`](Expert_Ranking_Lists) folder.

### University Endowments

The <a href="http://www.nacubo.org/Documents/EndowmentFiles/2015_NCSE_Endowment_Market_Values.pdf" target="_blank">2015 NCSE Endowment Market Values</a> file was downloaded in a PDF format from the National Association of College and University Business Officers (NACUBO) website. It lists the self-reported market value of endowments for those U.S. and Canadian institutions who responded to a NACUBO survey. We scraped the PDF to convert it into a machine readable format [`endowment/university_endowments_2014-2015.csv`](Endowment/University_Endowments_2014-2015.csv), then matched the institution to universities on the expert ranking lists. In cases where an endowment was associated with a university system (e.g., University of Minnesota Foundation), we used <a href="http://wiki.dbpedia.org/" target="_blank">DBpedia</a> to determine the proportion that should be allocated to a particular university of interest (e.g., University of Minnesota-Twin Cities).

### IPEDS

The <a href="https://nces.ed.gov/ipeds/" target="_blank">Integrated Postsecondary Education Data System (IPEDS)</a> is the core education collection program for the <a href="https://nces.ed.gov/">National Center for Education Statistics (NCES)</a>. The [`IPEDS`](IPEDS) folder contains two zipped files downloaded from IPEDS. These files contain directory information for every institution in the 2015 IPEDS universe. This information includes name, address, city, state, zip code and various URL links to the institution's home page, admissions, financial aid offices and  the net price calculator.  It identifies institutions as currently active, institutions that participate in Title IV federal financial aid programs for which IPEDS is mandatory. It also includes variables derived from the 2015 Institutional Characteristics survey, such as control and level of institution, highest level and highest degree offered and Carnegie classifications. For our research, IPEDS was used to standardize institution names across ranking lists and served as the source for undergraduate enrollment numbers.

### NCAA

To select the universities of interest to our study, we begin with the 351 American colleges and universities as Division I by the the National Collegiate Athletic Association (NCAA). For evalution, we consider a subset of 65 universities associated with the Power Five conferences: SEC, ACC, Big Ten, Pac-12, and Big-12. The [`NCAA`](NCAA) folder contains several files which provide information related to athletic expenditures and conference membership.


### Twitter Dataset

The entire dataset used to perform the ranking analysis is published as a JSON [`Twitter_Accounts`](Twitter_Accounts) folder. The JSON file identifies the official primary and affiliated secondary Twitter accounts associated with each institution along with selected attributes for each profile (i.e., screen name, user name, URL, protected, follower count, following count). The Twitter data is used to calculate University Twitter Engagement (UTE) which is the friend and extended follower network of primary and affiliated secondary Twitter accounts referenced on a university's home page. Please note this file contains over 1 million Twitter profiles, and is best opened with a utility such as <a href="http://jsoneditoronline.org/" target="_blank">JSON Editor Online</a>. 

# Results

In rank-to-rank comparisons we observed a significant, positive rank correlation (τ=0.6018) between UTE and an aggregated reputation ranking (ARR) which indicates that UTE could be a viable proxy for ranking atypical institutions normally excluded from traditional lists. In addition, we significantly reduce the cost of data collection needed to rank each institution by using only web-based artifacts and a publicly accessible Twitter application programming interface (API).

## ODU Ranking Lists

The [`ODU_Ranking_Lists`](ODU_Ranking_Lists) folder contains the complete university listings ranked by our specific criteria of [`adjusted reputation rank (ARR)`](ODU_Ranking_Lists/Ranked_by_ARR.csv), [`ependitures, enrollment and endowment (EEE)`](ODU_Ranking_Lists/Ranked_by_EEE.csv), and [`university Twitter engagement (UTE)`](ODU_Ranking_Lists/Ranked_by_UTE.csv). Please refer to the tech report for more information regarding the methodology used to construct each ranking list.

# Feedback / Questions?

Contact Corren McCoy at [cmccoy@odu.edu](mailto:cmccoy@odu.edu).

Looking for more from the Web Science and Digital Libraries Research Group at Old Dominion University? [Click here to read blog postings and more about research projects and education updates.](http://ws-dl.blogspot.com/)