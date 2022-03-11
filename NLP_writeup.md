# Trupm: Historical Presidential Tweets

## Abstract

My client "Political Tomorrow" wants to take a historical look into Donald Trump's twitter history. They want  better insite into how he used twitter and what was said.
"Political Tomorrow" will use my findings as one part of a bigger project, reaserching how politicians have and continue to use social media.
----------
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
