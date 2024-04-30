# Hotel Review Analysis of Aurangabad
Analyze TripAdvisor reviews from Aurangabad hotels. Extract sentiments, high-frequency words, and correlations for industry insights.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Recommendations](#recommendations)

### Project Overview
---
This project delves into the analysis of hotel reviews sourced from TripAdvisor, focusing on establishments in Aurangabad, Maharashtra, India. Leveraging text data extracted from TripAdvisor reviews, I employed a combination of data cleaning, sentiment analysis, and frequency analysis techniques to extract insights into customer sentiments and preferences regarding hotels in Aurangabad.


### Data Sources

Hotel Review Data: I have used BeautifulSoup python library to scrap data from TripAdvisor site. Then transform into Review.xlsx Excel file to perform text analysis 

### Key Features:

- Web Scraping: Used BeuatifulSoup library to scrap data from the website.(for education purpose)
- Text Data Cleaning: Preprocessing of raw text data to ensure accurate analysis.
- Sentiment Analysis: Determination of sentiment scores to gauge the overall tone of reviews.
- Frequency Analysis: Identification of high-frequency words to understand common themes and topics among reviews.
- Co-occurrence and Correlation Analysis: Exploration of relationships between words and sentiments to uncover patterns.

### Tools
- RStudio
- Python
- MS Excel

### Data Collection
- I used python to scrap data from TripAdvisor and stored data in excel to exercise the analysis.
- collected data from 29 hotels, spanning 5 pages each. 
- The selected hotels range from 3 to 5-star categories.

### Data Cleaning/Preparation
- Data Loading and Inspection.
- Removed blanks and missing values.
- Removed Stop Words and punctuation.
- Tokenized words text data.

### Exploratory Data Analysis
Exploring the data to answer key questions, such as:

- What are the predominant sentiments in the reviews?
- Which words are most frequently mentioned?
- Are there any notable correlations between sentiments and hotel attributes?

### Data Analysis

Data Scraped from website
~~~ python
from random import randint
from time import sleep

customer_reviews = []

for link in new_urls:
    headers = {'User-Agent': "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.97 Safari/537.36"}
    html2 = requests.get(link,  headers=headers, proxies=proxies, verify=False)
    sleep(randint(1, 5))
    bsobj2 = BeautifulSoup(html2.text, 'html.parser')
    for element in bsobj2.find_all(recursive=False):  # Filter out the doctype
        for div in element.find_all('div', class_="fIrGe _T"):
            customer_reviews.append(div)
            print(div)

print(customer_reviews)
~~~ 
full code is in file(Data Collection Data Scraping)
