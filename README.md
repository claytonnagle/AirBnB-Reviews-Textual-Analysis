# Project-3: AirBnB review texual analysis with machine learning


## Goals

Our primary objective for this project was to gain insight on what AirBnB reviews might be able to tell us about listings and how they might fit individual preferences. By leveraging natural language processing technology, we were able to discern unique characteristics about specific listings which would have been otherwise unidentifiable due to AirBnB's lack of text-based search. 

## Tasks
### Step 1: Data collection and transformation

Our data was gathered from http://insideairbnb.com/get-the-data.html, which has scraped and saved historical data on AirBnB listings (including reviews). 

**Note:** we tried to  utilize the AirBnB API, but they were not taking applications when we did this project. Fortunately we were able to find the secondary source listed above. 

Downloading and working with the data through .csv files meant we had to hold the csv files locally. Some of these were too large for a normal Github account to accept, so we stored them in a google drive folder at the following link:
https://drive.google.com/drive/folders/12YwziK34jzk9dHIHI1Xyz6LF3WGPTV4V?usp=sharing

After stripping the data of unecessary columns for our analysis, we were able to reload the selected data and subset to listings which had at least 50 reviews. The 50 value is arbitrary, but we wanted a sufficiently large sample of reviews for each listing so that the text analysis would be meaningful. 

### Step 2: Natural Language Processing

The primary work was done with the nltk package, using the nltk.stem stemmer, the nltk corpus, and the nltk stopwords. From sklearn.feature_extraction.text, we imported TfidfTransformer and CountVectorizer. 

We performed some sentiment analysis with the TextBlob package, which showed that the reviews which tended to be more opinionated were also the ones which were more positive, but an extremely small R2 and biased data (there were no reviews which made it fully into 'negative' territory, only going as low as 0.64 out of 1.00, with 0.50 being true neutral) led us to not rely on those results for direction. 

