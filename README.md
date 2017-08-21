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

This source data was extracted from the 2015-2016 academic rankings of <a href="http://www.usnews.com/education/best-global-universities/rankings" target="_blank">U.S. News</a>, <a href="https://www.timeshighereducation.com/world-university-rankings" target="_blank">Times Higher Education</a>, <a href="http://www.shanghairanking.com/ARWU2016.html" target="_blank">Academic Rankings of World Universities</a> and <a href="http://new.time.com/money/best-colleges/rankings/best-colleges/" target="_blank">Money Magazine</a> for the top 264 universities in the United States. These institutions were ranked based on 12 indicators that measure their academic research performance and their global and regional reputations. 

### University Endowments

The <a href="http://www.nacubo.org/Documents/EndowmentFiles/2015_NCSE_Endowment_Market_Values.pdf" target="_blank">2015 NCSE Endowment Market Values</a> file was downloaded in a PDF format from the National Association of College and University Business Officers (NACUBO) website. It lists the self-reported market value of endowments for those U.S. and Canadian institutions who responded to a NACUBO survey. We scraped the PDF to convert it into a machine readable format [`endowment/university_endowments_2014-2015.csv`](endowment/university_endowments_2014-2015.csv), then matched the institution to universities on the expert ranking lists. In cases where an endowment was associated with a university system (e.g., University of Minnesota Foundation), we used DBpedia to determine the proportion that should be allocated to a particular university of interest (e.g, University of Minnesota-Twin Cities).


### IPEDS

The [`data/pages-info.csv`](data/pages-info.csv) file represents a list of all 452 Facebook pages affiliated with the websites identified by BuzzFeed News including title, description, fan count, the page ID, and other information extracted from Facebook’s API.

### NCAA

For each Facebook page, we used Facebook’s API to collect all posts published between January 1, 2015 and March 31, 2017. The data included engagement metrics, such as shares, comments, and reactions (likes, loves, hahas, sads etc.). That data is too large to fit in this repository. It can be [found here](https://archive.org/details/partisan-news-facebook-posts-2015-01-01-to-2017-03-31). Note: This data was collected on July 21, 2017. It is possible that some pages deleted posts between when they were published and when the data were collected.

### Twitter Dataset

The entire dataset used to perform the ranking analysis is published as a JSON [`Twitter Accounts/UTE University Twitter Accounts.json`](Twitter Accounts/UTE University Twitter Accounts.json). The JSON file identifies the official primary and affiliated secondary Twitter accounts associated with each institution along with selected attributes for each profile (i.e., screen name, user name, URL, protected, follower count, following count). The Twitter data is used to calculate University Twitter Engagement (UTE) which is the friend and extended follower network of primary and affiliated secondary Twitter accounts referenced on a university's home page. Please note this file is large, and is best opened with a utility such as <a href="http://jsoneditoronline.org/" target="_blank">JSON Editor Online</a>. 

# Results

## ODU Ranking Lists


# Feedback / Questions?

Contact Corren McCoy at [cmccoy@odu.edu](mailto:cmccoy@odu.edu).

Looking for more from the Web Science and Digital Libraries Research Group at Old Dominion University? [Click here to read blog postings and more about research projects and education updates.](http://ws-dl.blogspot.com/)