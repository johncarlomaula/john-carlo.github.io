# Analyzing The Spotify Features of Taylor Swift's Music

**Project Description:** In this project, I analyze the lyrics of Taylor Swift's music.

<img src="images/project2_images/swift_lyrics.jpg?_raw=true"/>

Taylor Swift is known for her songwriting among her fans and the music industry. Her diaristic style of songwriting often lead to detailed songs that many fans find relatable. I thought it would be interesting to quantify these features and use some basic NLP principles to analyze the words that she uses in her lyrics. 

I only included the lyrics of her 9 studio albums. I also excluded alternative versions (e.g. acoustic or piano versions) and remixes to avoid double counting lyrics.

In this blog, I only show the analysis of Taylor Swift's overall lyrics. To see these results broken down by album, as well as the code used to produce these plots, check out the *Word Count Analysis* and *Sentiment Analysis* sections of the project in Github [here](https://github.com/johncarlomaula/taylorswift-lyrics-project).

### Word Frequency

A word cloud is a common visualization used to represent words. The larger the word is in the word cloud, the more frequent that word occurs in the document. After removing the *stop words*, a set of words that are common and uninformative (e.g. "the", "and", etc.), I plotted the word cloud of Taylor Swift's lyrics.

<img src="images/project2_images/word_cloud.png?_raw=true"/>

The words "love", "time", and "baby" are some of the most frequent words in Taylor Swift's music as seen by the large size of these words in the word cloud. As most of her music is about love and relationships, it's no surprise that these words appear in her lyrics frequently.

The word "ooh" is also frequent in her lyrics, but this word is commonly used as a musical effect and is used to express a range of emotions. For ***Fearless***, ***Red***, ***reputation***, ***Lover***, and ***evermore***, the most common words are either "la", "ooh", or "di", which are musical effects rather than actual words.

I also plotted the top 15 most frequent words, which is shown in the graph below.

<img src="images/project2_images/word_count.png?_raw=true"/>

The word "love" appears 233 times in her lyrics and is followed by "time", which appears 203 times. Althougn "love" appears more frequently, "time" is the most common word in 4 of her albums. Other common words include "yeah", "wanna", "stay", and "night".


### Lexical Diversity

Next, I wanted to see how many unique words are used in each of Taylor Swift's songs to see if her vocabulary has gotten more diverse over the years.

<img src="images/project2_images/lexical_diversity.png?_raw=true"/>

As shown by the plot, her lyrical diversity has increased since she made her debut album in 2006. However, there was a decrease in lexical diversity when she transitioned to pop music starting with her 4th album, ***Red***. There has been a slight upward trend starting in 2017 with her 6th album, ***reputation***.

Her most lyrically diverse song is *All Too Well* with 199 unique words, while her least diverse song is *A Perfectly Good Heart* with 66 unique words. Many critics and fans consider *All Too Well* to be Taylor Swift's best song. 

Although not included here, *All Too Well (10 Minute Version)* contains a lot more lyrics and unique words than the original!

### Positive vs. Negative Sentiment Using the Bing Lexicon

The **bing lexicon** categorizes words into positive and negative categories. Using this lexicon, I categorized Taylor's lyrics into these two categories.

<img src="images/project2_images/pos_neg_sent.png?_raw=true"/>

The words that contribute the most to the positive sentiment of her lyrics are "like", "love", "right", and "good". Words that contribute to the negative sentiment are "bad", "shake", "break", and "fall". There are significantly more occurences of positive words in her lyrics with the top 3 positive words occurring 389, 233, and 115 times while the top negative word occurs only 71 times. 

### Emotion Association with the NRC Lexicon

The **NRC lexicon** categorizes words into different categories of emotion: positive, negative, anger, anticipation, disgust, fear, joy, sadness, surprise, and trust.

<img src="images/project2_images/sentiment.png?_raw=true"/>

According to the NRC lexicon, the most common emotions conveyed by Taylor's lyrics are positive, negative, joy, and anticipation while the least common emotion is disgust. This result generally stays consistent throughout her albums with some minor differences in the order.

## Conclusion

Although these results were expected as Taylor Swift primarily writes about love and relationships, it was still interesting to look at it from a quantitative perspective. It also showed that she writes about these topics from a more positive viewpoint as shown by the large number of positive-associated words used in her lyrics, despite the misconception that she only writes songs about getting back at her exes. I look forward to seeing how her lyrics evolve with her future albums.
