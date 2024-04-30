# Hotel Review Analysis of Aurangabad
Analyze TripAdvisor reviews from Aurangabad hotels. Extract sentiments, high-frequency words, and correlations for industry insights.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Data Collection](#data-collection)
- [Data Analysis](#data-analysis)
- [Findings](#findings)

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
---

### Data Analysis

#### Data Scraped from website
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
Full code is in file([Data Collection Data Scraping](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Data%20Collection%20Data%20Scraping.ipynb)

---

#### High frequency mentioned words
~~~r
data_count<- data_new%>%
  count(word, name = "n")%>%
  filter(n> 274, sort(TRUE))
data_count <- data_count %>%
  mutate(word = factor(word, levels = word[order(-n)]))

~~~

![d3e9d944-ebb7-461b-8132-409bd24df9c0](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/assets/162418652/02aec4a0-8173-46c7-b5b6-67bd6303a0e9)


Full code is in file([Most High Frequency word.R](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Most%20High%20Frequency%20word.R)


---
#### Sentiment Analysis of Aurangabad Hotel Reviews.
Discover the heartbeat of customer experiences, sentiments.


![Sentiment Analysys](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/assets/162418652/ed576cad-3e91-40d2-9254-3e38a4bd2e2d)

Full code is in file([Aurangabad Hotel Review Sentiment.R](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Aurangabad%20Hotel%20Review%20Sentiment.R)


---
#### Co-occurring word relationships in aurangabad hotel reviews.
  
  The graph highlights significant associations between words, offering insights into prevalent topics and themes discussed in the reviews.
  

  ![Co-occurring Word Relationships in Aurangabad Hotel Reviews](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/assets/162418652/e70b254c-42af-4b59-9352-373a2444b1f9)

Full code is in file([Co-occurring Word Relationships in Aurangabad Hotel Reviews.R](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Co-occurring%20Word%20Relationships%20in%20Aurangabad%20Hotel%20Reviews.R)


---
#### Positive Sentiment Network.
Mapping the Bright Side of Aurangabad Hotel Reviews. The interconnected web of positivity within TripAdvisor feedback, showcasing the sunny side of customer experiences in Aurangabad's hospitality sector.


![Positive sentiment network](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/assets/162418652/ea0d997f-9691-450c-bf7f-a5df3276cefb)

Full code is in file([Positive Sentiment Netword.R](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Positive%20Sentiment%20Netword.R)


---
#### Negative Sentiment Network.
Navigating the Shadows of Aurangabad Hotel Reviews. The interconnected web of negativity within TripAdvisor feedback, shedding light on areas for improvement in Aurangabad's hospitality sector.


![Negative sentiment](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/assets/162418652/90aadd55-8c3b-4cda-9095-63c96535e827)

Full code is in file([Negative Sentiment Network.R](https://github.com/Saurabh-Ghagare/Aurangabad_Hotel_Review_Analysis/blob/main/Negative%20Sentiment%20Network.R)


---
### Findings
#### Sentiment Analysis Results:
- The sentiment analysis reveals a predominantly positive sentiment among users, with a significant number of positive sentiment words mentioned by users. highlighting aspects like cleanliness, helpful staff, and excellent service.
- Negative sentiments focus on issues such as cleanliness, costliness, and disappointment.
---
#### High-Frequency Terms:
- The most frequently mentioned terms in the reviews include hotel, staff, food, service, stay, clean, restaurant, aurangabad, breakfast, experience, nice, stayed, helpful, comfortable, location indicating their significance in user reviews among each.
--- 
#### Negative Sentiment Words:
Negative sentiments are associated with words like "dirty," "costly," "disappoint," and "shocked," pinpointing areas for improvement.

---

#### Positive Sentiment Words:
Positive sentiments are linked to terms like "excellent," "friendly," and "fantastic," reflecting satisfaction with various aspects of the hotel experience.

---
#### Co-occuring Word Relationships in Aurangabad Hotel Reviews:
- Word Staff correlate with words like cooperative, courteous, polite, helpful, friendly, and other suggest that aurangabad hospitality industrial staff overall positive side inclined.
- Word hotel which is main word in this study have close co-relations with budget, location, booked, star, clean, stay, comfortable suggest Guests concerned who visit aurangabad.

### References
~~~ https://www.researchgate.net/publication/320106421_Application_of_social_media_analytics_A_case_of_analyzing_online_hotel_reviews
~~~
