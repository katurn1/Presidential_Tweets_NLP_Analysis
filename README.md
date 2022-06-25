# Presidential Tweets: NLP Analysis
**Using natural language processing to examine Donald Trump's twitter history.**

Kyle Turner

## Background
Donald Trump is the most prolific president when it comes to tweeting. I wanted to take a historical look at how he used Twitter and what was said.

<img width="1129" alt="Screen Shot 2022-06-24 at 1 04 24 PM" src="https://user-images.githubusercontent.com/87869709/175609035-5757130b-b2f9-45ed-9271-c7e44074dbd6.png">

## The Goal
Build a model using topic modeling and sentiment analysis to gain insite into Trump's twitter history.

## Data
[All of Trumps tweet history](https://www.thetrumparchive.com/) 2009-2021

Originally scrapped using "Tweet Scrapper" by the sites creator, I downloaded the csv file.

Features:

- tweet text
- isRetweet
- date/time
- likes
- isDeleted
- isFlagged
- id
- retweets
- device

56,571 rows

## Methodology
I used natural language processing techniques to categorize topics for tweets, looked at topics over time, generated sentiment scores for each tweet, and looked at 
sentiment over time.

### Workflow
**1. Text Preprocessing**

- Removed ‘\n’, numbers & punctuation
- Fixed Unicode encoding errors 
- Converted all characters to lowercase
- Removed URL’s
- Removed non-english characters
- Created date/time column

**2. Vectorize**: sklearn.CountVectorizer

**3. Topic Model**: CorEx

I tried several types of modeling:

- LSA
- NMF w/ TF-IDF
- CorEx w/ TF-IDF
- CorEx w/ CountVectorizer

I got the best results using CorEx w/ CountVectorizer for clear topic catagories.

I named and used the topic categories the get topic probabilities for each tweet. Next the top probabilities were concatenated to one column of the 
dataframe with the topic name for each tweet.

**4. Sentiment Analysis**: vaderSentiment

Sentiment Analysis was run using vaderSentiment and the scores were added to the data frame for each tweet. The dataframe was then split by week and the compound Sentiment 
score was averaged for each week. 

**5. Evaluate & Interpret**

## Topics & Key Insights

### Topics Generated
1. Media
2. Security
3. Political Party
4. Trump Speaks Out
5. Campaign
6. Presidential
7. Trump Being Trump

For the topics 'Trump Speaks Out' and 'Trump Being Trump', they both had similare tweets in them but interestly even thought 'Trump Being Trump' was the last topic 
generated it had the second most tweets of any topic.

<img width="1097" alt="Screen Shot 2022-03-10 at 8 15 26 PM" src="https://user-images.githubusercontent.com/87869709/175753436-ee79b204-1193-4aea-b02c-3d251ae3a55d.png">

### Topics Over Time

<img width="891" alt="topics over time" src="https://user-images.githubusercontent.com/87869709/175753787-a15a6945-55f0-4fee-8b5f-4791de9416e4.png">

### Average Compound Sentiment Score
Here is the average Sentiment score for before and after Trump became president.

<img width="662" alt="Screen Shot 2022-06-24 at 9 47 21 PM" src="https://user-images.githubusercontent.com/87869709/175753700-b8ee0843-e481-432a-a286-79095419080b.png">

### Average Compound Sentiment Over Time

<img width="1343" alt="compound over time" src="https://user-images.githubusercontent.com/87869709/175753821-1865e26c-d102-4963-9efa-e45c9c8dc771.png">

## Key Takeaways
- Overall Trump tweets are not super negative
- He praises quite a bit
- The number topics he tweets about grow in the second half of his presidency
- Earlier tweets vary greatly between +/-
- Unfiltered Trump shows up around July 6, 2011
- He is slightly more positive before his presidency

## Tools
- EDA: Excell
- Data Manipulation: Numpy, Pandas
- Plotting/ Visualizing: matplotlib, seaborn, Tableau 
- Modeling: sklearn, CountVectorizer 
- NLP: NLTK, CorEx, 
- Sentiment Analysis: vaderSentiment

## Communication
Tableau Links to interactive visuals: [LINK 1](https://public.tableau.com/app/profile/katurn1/viz/NLPtopics/NLPtopics) , [LINK 2](https://public.tableau.com/app/profile/katurn1/viz/NLP_AvgSentimentOverTime/Avg_CompoundSentimentScoreOverTime)
