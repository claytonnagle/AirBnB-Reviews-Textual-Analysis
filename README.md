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

### Step 3: Examining Results

TF-IDF analysis of the corpus of reviews allowed us to highlight specific features. AirBnB as a service normally does not allow for feature searches, only some filtering for specific features. Performing TF-IDF analysis on the reviews serves as a proxy for a textual search that if applied in a larger scope which would allow an individual to search for specific things they might be interested in during a stay. Searching 'View' through our collection of data would pull up listings which have reviews featuring the 'view'. An interesting listing of note that our research identified was a [stay in a treehouse](https://www.airbnb.com/rooms/589214?source_impression_id=p3_1635055913_M2NBCzhugBcIiSRu&guests=1&adults=1) which we not would have found without our text searching. 

The framework of this research serves as a launching point where our application might take off to a larger scope. Although there's no actual search functionality with our data, it would be easily implementable in a small web application (our project was focused on research and analysis rather than application building). 

