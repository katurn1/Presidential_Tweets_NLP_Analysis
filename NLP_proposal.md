# Question/ Need:
I'm interested in looking at the tweet history of Donald Trump. I want to know over certain date ranges how negative or positive the tweets are to get a better understanding 
of Trumps psyche. I will use historical date range information to help explain any spikes in Trupms mood.

# Data Description:
[All of Trumps tweet history](https://www.thetrumparchive.com/)

Originally scrapped using "Tweet Scrapper" by the sites creator, I downloaded the csv file.

Shows:
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

Every tweet is recorded in the database in UTC time. On the site, dates are translated to Eastern Standard Time (EST) - i.e. the time in Washington DC. No geographic data is 
taken into consideration, so if he tweeted something from London at 9AM it's still presented as 3AM. Daylight savings time is taken into account.

# Tools:
Python, matplotlib, numpy, pandas, sklearn, Excell 

**Preprocessing:**

re, string, datetime
 

# MVP Goal:
Dreak the data in to tweets before Trumpo became president and after and run sentiment analysis.
