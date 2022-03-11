My client want's to take a historical look at Donald Trup's twitter history. Trump is the first president to be that prolific on social media and the client wants better insite into how he used 
twitter and what was said.

I cleaned the data by removing numbers, URL, captial letters, null values, non-english words, and punctuation.

I tried several types of modeling:

- LSA
- NMF w/ TF-IDF
- CorEx w/ TF-IDF
- CorEx w/ CountVectorizer

I got the best results using CorEx w/ CountVectorizer for clear topic catagories. 
![Screen Shot 2022-03-07 at 5 32 10 PM](https://user-images.githubusercontent.com/87869709/157129329-d837dd89-765d-44ac-b323-f9dc3d063f34.png)

I then looked at the top tweets in each topic followed by looking at the total correlation scores.

vaderSentiment was used to create sentiment analysis for each tweet. The sentiment scores were added to the dataframe as their own columns.

I then looked at certain words that came up topic category 3 that were interesting like 'didn' , 'said' , 'just' and the tweets they show up in with the sentiment analysis
to get a better understanding of their use in the tweets and why they show up sow high.

Next I plan to get a better understanding of the sentiment analysis of Trump's tweets over time. I will start with breaking down the tweets by month and graph them using 
the compound sentiment analysis score, by adding them together, and look for any spikes and cross reference them with information about what was happening around that timeframe that could cause the spikes. 
I would then be able to easily breaking down the tweets by week.
