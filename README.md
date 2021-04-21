# Billboard Top 25 


### Introduction 
For this project, I looked at whether lyrics in a song have an effect on its ranking in the Billboard Top 100. I followed the CRISP-DM methodology and used Natural Language Processing to clean, stem and lemmatize the lyrics data, then used both Random Forest and Naive Bayes to classify. 

I hypothesized that words in a song do have an effect on its ranking and may be specific to the time of its release. 

### Data 
I scraped the data from both Billboard and Genius (found in BillboardTop100_Webscraping notebook). Billboard offered the Top 100 songs for the years 1970-2020, and its corresponding artist. Genius offered the lyrics for each song. Once I finished preprocessing the data, I had over 2,200 songs for the analysis created by 1,000 artists. One thing to note is that the data does not include any collaborations or songs featuring another artist due to scraping technicalities. A few artists had a number of songs in the billboards, such as Madonna, Elton John and Drake, but more than half of the artists in our dataset only had one. 

### Results 
I made predictions with the song lyrics using two classifiers: Random Forest and Naive Bayes (found in BillboardTop100_Model). Our baseline model performed with 67% accuracy. After stemming, lemmatizing and dealing with the class imbalance with SMOTE, our model accuracy improved to 76%, an increase of 9%. However, considering that roughly 25% of our data classify as a Top 25 hit, our model is just as good as guessing that the song will not be a Top 25 hit every single time, which is essentially what was happening in my baseline model. It looked that the model was too scared to classify songs as a Top 25 because there weren't as many Top 25 songs than not. Even when dealing with the imbalance using SMOTE, the accuracy score actually went down. Therefore, I fail to reject the altnerative hypothesis and say that words in a song have no impact on its rank in the Top 100. 

(Accuracy Score for models) 

### Conclusion and Recommendations 
Unfortunately, my models were not able to find what differentiates the Top 25 from the rest of the Top 100 and fail to prove that the words in a song have an impact on its rank. Knowing that, I recommend songwriters do the following: 
* Focus more on the sound composition of the song - tempo and sound may have more of an impact on the success of a song than the lyrics itself. 
* Write about relatable topics - though not specific to the Top 25, we do know that "love" is the most common word found in the Top 100. Listeners may vibe more to topics that are familiar to them and that resonate deeper. 
* Write about anything you want - I could not prove that songs with the word "dance" did better than songs with the word "cry". Therefore, just write about something you are passionate about or write about what you feel like expressing. 

### Future Work 
I was a bit upset that I couldn't come to any conclusions, so I began finding other ways I can classify my data. If given more time with this project, I may try the following. 
* Add additional features - I would love to see if I could add tempo and composition as features to predict if I song is a hit or not. 
* Classify by year - I started to classify whether songs were produced before or after 2000 and had an accuracy score of 80%. 
* Scrape data outside of Top 100 - I think a large reason the results were inconclusive were because the songs were already in the Top 100 and all were successful already. I need to look at songs that are outside and perform poorly. 
* Classify by genre - It would be interesting to see whether some words are found more often in rap or country than other genres 
