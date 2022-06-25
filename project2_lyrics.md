# Analyzing The Spotify Features of Taylor Swift's Music

**Project Description:** In this project, I analyze the lyrics of Taylor Swift's music.

<img src="images/project2_images/swift_lyrics.jpg?_raw=true"/>

Taylor Swift is known for her songwriting among her fans. Her diaristic style of songwriting often lead to detailed songs that many fans find relatable. Although she is known for writing songs about relationships, there are some common misconceptions about her. Like does she only write about break ups? 

In this project, I take a look into the lyrics of Taylor Swift's music. I only included songs from her 9 studio albums and excluded alternative versions of songs (e.g. piano versions and acoustic versions) to avoid double counting.

### Word Cloud

After removing the stop words, which are a set of words that are common and uninformative (e.g. "the", "and", etc.), I plotted a word cloud of Taylor Swift's music.

<img src="images/project2_images/word_cloud.png?_raw=true"/>

 The words "love", "time" and "baby" are some of the most frequent words in Taylor's music, as seen by the large size of these words in the word cloud. As most of her music is about love and relationships, it's no surprise that these words appear in her lyrics frequently.

 The word "ooh" is also frequent in her lyrics, but this word is commonly used as a musical effect and does not mean anything significant in the English language.

 ### Word Frequency
 For a more informative visual, I plotted the top 15 most frequent words.

 <img src="images/project2_images/word_count.png?_raw=true"/>

 The word "love" appears 233 times, followed by "time" which appears 203 times. Other common words include "yeah", "wanna", "stay", and "night".

### Lexical Diversity

I wanted to determine how many unique words are used in each of Taylor's songs to see if her vocabulary has gotten more diverse over the years. Thus, I plotted the number of unique words in each of her songs over the years.

 <img src="images/project2_images/lexical_diversity.png?_raw=true"/>

 As shown by the plot, Taylor's lyrical diversity has increased since her debut album in 2006. However, there was a decrease in lexical diversity when she transitioned into pop music starting with her 4th album ***Red*** There was been a slight upward trend starting in 2017 with her 6th album, ***reputation***.

 Her most lyrically diverse song is *All Too Well* with 199 unique words, while her least diverse song is *A Perfectly Good Heart* with 66 unique words. Many critics and fans consider *All Too Well* to be Taylor Swift's best song.


### Positive vs. Negative Sentiment Using the Bing Lexicon

The **bing lexicon** categorizes words into positive and negative categories. Using this lexicon, I categorized Taylor's lyrics into positive and negative categories.

 <img src="images/project2_images/pos_neg_sent.png?_raw=true"/>

The words that contribute the most to the positive sentiment of her lyrics are "like", "love", "right", and "good". Words that contribute to the negative sentiment are "bad", "shake", "break", and "fall". There are significantly more occurences of positive words with the top 3 positive words occurring 389, 233, and 115 times while the top negative word occurs only 71 times. 

### Emotion Association with the NRC Lexicon

The **NRC lexicon** categorizes words into different categories of emotion: positive, negative, anger, anticipation, disgust, fear, joy, sadness, surprise, and trust.

 <img src="images/project2_images/sentiment.png?_raw=true"/>

 According to the NRC lexicon, the most common emotions conveyed by Taylor's lyrics are positive, negative, joy, and anticipation while the least common emotion is disgust. 


 ## Conclusion

 Although most of these results were expected as she often writes about live and relationships, it was still interesting to look at it from a quantitative perspective. Her lyrical diversity has grown over time, and much of her music convey a more positive sentiment. 

These lexicons are not always correct in their interpretation, however. For example, the song *Shake It Off* is full of negative words such as "shake", "hate", and "break" despite being an upbeat, positive song.

For a greater look at this analysis, see the project on Github. Code used to produce these plots can be shown, as well as individual album analyses. 
