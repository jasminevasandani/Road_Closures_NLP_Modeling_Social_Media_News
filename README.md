# Don't Drown, Turn Around
## Detecting & Mapping Live Road Closures Using NLP and Supervised/Unsupervised Modeling Techniques

- Jasmine Vasandani
- Phillip Dibert
- Eric Kropf

## Overview
When disasters and unexpected events cause road closures, navigation systems are slow to share updates with the public. How might we detect and announce road closures as soon as they happen? Fortunately, social media and news outlets provide live updates on road closures. However, there is no reliable platform that verifies, consolidates, and _maps_ road closures as they happen. Through acquiring credible data about road closures, in this project we implement supervised and unsupervised modeling techniques to map live closures--focusing specifically on Minnesota as our test site. We chose Minnesota because of the state's severe weather conditions and subsequent frequent road closures. 

## Methodology
To achieve our goal of verifying, consolidating, and mapping road closures, we took the following steps. 
- **Step 1: Data Acquisition**: Tweets from official Dept. of Transportation accounts in Minnesota, as well as live road closure announcements made on Minnesota 511--a state-run website. To compare Minnesota 511 announcements, we also scraped North Dakota's Dept. of Transportation road closure announcements. Additionally, we acquired news articles about road closures.
- **Step 2: Exploratory Data Analysis**: Using Natural Language Processing and data analysis, we learned more about what makes a road closure announcement unique compared to all other text.
- **Step 3: Pre-Processing and Modeling**: We implemented a supervised model on the tweets to run on unseen tweets to determine if they are announcing a road closure or not. We also implemented an unsupervised model on news headlines and Dept of Transportation announcements to determine if they were announcing a live road closure. 
- **Step 4: Activation**: Once the announcements, both tweets and news articles, were distinguished as announcing road closures, we detected location from text using spaCy, converted those locations to coordinates, and mapped them on an HTML map.

## Results
We successfully detected tweets and news articles announcing road closures. To detect tweets, we implemented a supervised model, and for the news articles we used unsupervised models. Our baseline accuracy score for our supervised model was 50%, since we built the training set using historic tweets that we scraped. When running the model on unseen tweets, we were pleased with its ability to detect road closure tweets, but the model still needs refining. Specifically, refining our model to detect road closures that are happening now as opposed to planned road closures to happen later -- therefore, making note of time-related words in our model is a next step to consider. Additionally, we were able to increase spaCy's ability to detect text from location by placing emphasis on location-based preposition (such as "at") and spelling out all road-related abbreviations (such as "Hwy"). Below is an image of our map, zoomed in, to show a road closure tweet in Minnesota. 
![image](https://raw.githubusercontent.com/jasminevasandani/Road_Closures_NLP_Modeling_Social_Media_News/master/images/map_example.png)
