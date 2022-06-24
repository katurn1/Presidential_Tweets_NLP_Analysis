# Trump: Historical Presidential Tweets

## Abstract

My client "Political Tomorrow" wants to take a historical look into Donald Trump's twitter history. They want  better insight into how he used twitter and what was said.
"Political Tomorrow" will use my findings as one part of a bigger project, researching how politicians have and continue to use social media.
----------
## Data Science Solution
Build a model using topic modeling and sentiment analysis to gain insite into Trump's twitter history.

## Data

[All of Trumps tweet history](https://www.thetrumparchive.com/)

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

Every tweet is recorded in the database in UTC time. On the site, dates are translated to Eastern Standard Time (EST) - i.e. the time in Washington DC. 
No geographic data is taken into consideration, so if he tweeted something from London at 9AM it's still presented as 3AM. Daylight savings time is taken into account.

## Algorithms

**Text Preprocessing**

- Removed ‘\n’, numbers & punctuation
- Fixed Unicode encoding errors 
- Converted all characters to lowercase
- Removed URL’s
- Removed non-english characters
- Created date/time column

**Models**

I tried several types of modeling:

- LSA
- NMF w/ TF-IDF
- CorEx w/ TF-IDF
- CorEx w/ CountVectorizer

I got the best results using CorEx w/ CountVectorizer for clear topic catagories.

I named and used the topic categories the get topic probabilities for each tweet. Next the top probabilities were concatenated to one column of the dataframe with the topic name for each tweet.

Sentiment Analysis was run using vaderSentiment and the scores were added to the data frame for each tweet. The dataframe was then split by week and the compound Sentiment 
score was averaged for each week. I also got the average Sentiment score for before and after Trump became president.

## Tools
- EDA: Excell
- Data Manipulation: Numpy, Pandas
- Plotting/ Visualizing: matplotlib, seaborn, Tableau 
- Modeling: sklearn, CountVectorizer 
- NLP: NLTK, CorEx, 
- Sentiment Analysis: vaderSentiment

## Communication
In addition to this written document, I have created and presented slides and visuals.

Tableau Links to interactive visuals: [LINK 1](https://public.tableau.com/app/profile/katurn1/viz/NLPtopics/NLPtopics) , [LINK 2](https://public.tableau.com/app/profile/katurn1/viz/NLP_AvgSentimentOverTime/Avg_CompoundSentimentScoreOverTime)
