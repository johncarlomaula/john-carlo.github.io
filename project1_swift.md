# Analyzing The Spotify Features of Taylor Swift's Music

**Project Description:** In this project, I retrieve the Spotify features of Taylor Swift's music and visualize them for analysis.

<img src="images/project1_images/swift.png?raw=true"/>

I have no doubt that Taylor Swift is the artist I listen to the most. For the most part, I can tell which of her songs are upbeat and danceable and which ones are slow and acoustic. But I think it would interesting to see these qualities quantified, see how each of her albums differ from each other, and see the progression in her music.

For this project, I will only be focusing on Taylor's 9 studio albums released throughout 2006 - 2020. This means that I will not be including any EPs or re-recordings (known as "Taylor's Version").I will be including bonus tracks from deluxe versions, but alternative versions of standard songs (e.g. piano version or acoustic version).

### Length
*Song length is the track duration in minutes*. 

The distribution of length appears to be right-skewed with an average length of **4 minutes**. Due to her storytelling style of songwriting, her songs tend to have a longer length. As she transitioned to pop music with ***1989***, the overall length of her music began to decrease. Her albums ***folklore*** and ***evermore*** saw a return in her storytelling form, which resulted in longer songs.

<img src="images/project1_images/danceability_plot.png?raw=true"/>

Her top 3 longest songs, *Dear John* (6:43), *Last Kiss* (6:07), and *Enchanted* (5:52) are all from the album, ***Speak Now***, while her top 3 shortest songs, *It's Nice To Have A Friend* (2:30), *I Forgot That You Existed* (2:50), and *You Need To Calm Down* (2:51) are all from her album, ***Lover***. Although not included in here, her longest song is *All Too Well (10 Minute Version)* from ***Red (Taylor's Version)*** clocking in at 10:13.

### Popularity
*Popularity is a measure of a song's popularity with 0 being the least popular and 100 being the most popular. A song's popularity changes depending on when the data was retrieved*.

As of June 2022, her most popular albums are ***Lover*** and ***reputation***. As these are pop albums that have been promoted heavily, it makes sense that they are still popular among the general population despite having 2 newer albums. Her least popular albums are ***Fearless*** and ***Red*** due to the re-recordings of these albums being released.

<img src="images/project1_images/popularity_plot.png?raw=true"/>

As of now, her most popular songs are *Don't Blame Me*, *Lover*, *Cruel Summer*, *Paper Rings*, and *Getaway Car*.

### Danceability
*Danceability describes how suitable a track is for dancing with 0 being the least danceable and 1.0 being the most danceable*.

The distribution of danceability is unimodal and symmetric with a mean of 0.59 and standard deviation of 0.12. Her albums tend to become to become more danceable until ***folklore***, where overall danceability began to decrease.

<img src="images/project1_images/danceability_plot.png?raw=true"/>

Interestingly, her most danceable song, *I Think He Knows* (0.90), and least danceable song, *The Archer* (0.29), both appear in the same album, ***Lover***. They are also right next to each in the tracklist.

### Acousticness
*Acousticness is a confidence measure of how acoustic a song is with 0 being the least acoustic and 1 being the most acoustic*. 

The distribution of acousticness is strongly right-skewed with a median of 0.16 and a mean of 0.31. Her albums are generally not acoustic with the exception of a few songs. However, ***folklore*** and ***evermore*** have an overall high acousticness due to the alternative genre of these albums.

<img src="images/project1_images/acousticness_plot.png?raw=true"/>

Her most acoustic songs are *It's Nice To Have A Friend*, *hoax*, and *evermore*. Many of her songs have an acousticness equal to 0.

### Energy
*Energy represents the intensity of the songs with 0 having the lowest energy and 1.0 having the most energy*.

The distribution of energy is unimodal and slightly symmetric with a mean of 0.59. The overall energy of her albums tend to stay around the range of 0.60 - 0.70. However, there is a decreasing trend in energy starting with ***reputation*** with ***folklore*** having the lowest energy overall.

<img src="images/project1_images/energy_plot.png?raw=true"/>

Her songs with the most energy are *Haunted* (0.95), *I'm Only Me When I'm With You* (0.93), and *Better Than Revenge* (0.92). Her songs with the lowest energy are *New Year's Day* (0.15), and *It's Nice To Have A Friend* (0.17), and *hoax* tied with *Soon You'll Get Better* with a value of 0.18.


### Instrumentalness
*Instrumentalness measures how much of the song is instrumental*. 

Almost all of Taylor's songs have an instrumentalness of 0. The songs with the highest instrumentalness are *long story short* and *gold rush*, which are from her most recent album, ***evermore***.

<img src="images/project1_images/instrumentalness_plot.png?raw=true"/>

### Liveness
*Liveness detects the presence of an audience in the recordings and is measured from 0 to 1*.

The distribution of liveness is strongly right-skewed with a median of 0.11. Her albums generally have low liveness with a few outliers. There appears to be a decreasing trend in the variability of liveness which could potentially be attributed to how the recording process now versus back then.

<img src="images/project1_images/liveness_plot.png?raw=true"/>

The songs with the highest liveness are *This Is Why We Can't Have Nice Things* (0.38), *Tell Me Why* (0.37), and *Better Than Revenge* (0.36). The songs with the lowest liveness are *The Story of Us*, *King of My Heart*, and *I Knew You Were Trouble*, all with a value of 0.04.


### Loudness
*Loudness measures the overall loudness of a song in decibels (dB) averaged across the entire track. Values are between -60 and 0 dB*.

The distribution of loudness is left-skewed with a mean of -7.15 dB and a median of -6.75 dB. There appears to be an overall decreasing trend in loudness with her albums.

<img src="images/project1_images/loudness_plot.png?raw=true"/>

The songs with the highest loudness are *Picture To Burn* (-2.10), *Haunted (-2.63)*, and *A Place In This World* (-2.88). The songs with the lowest loudness are *hoax* (-15.01), *epiphany* (-13.68), and *peace* (-12.88), which are all from the album, ***folklore***.

### Speechiness
*Speechiness detects the presence of spoken words in a song from 0 to 1.0*.

Similar to instrumentalness, the distribution of speechiness is extremely left-skewed. The album ***reputation*** tends to have an overall higher speechiness compared to the other albums.

<img src="images/project1_images/speechiness_plot.png?raw=true"/>

The songs with the highest speechiness are *I Forgot That You Existed* (0.52), *closure* (0.24), and *False God* (0.24). Many of her songs have a speechiness of 0.2, which is the minimum.

### Tempo
*Tempo is the estimated tempo of the song measured in beats per minute (bpm)*.

The distribution of tempo is unimodal and fairly symmetric with an average of 123.4 bpm and a standard deviation of 31.4 bpm. All her albums tend to to be distributed around the overall mean. However, the overall tempo for ***Red*** and ***Lover*** is slightly lower while the overall tempo for ***Speak Now*** is slightly higher.

<img src="images/project1_images/tempo_plot.png?raw=true"/>

Her songs with the highest tempo are *Soon You'll Get Better* (207.5), *Long Live* (204.1), and *Untouchable* (200.0). The songs with the lowest tempo are *Lover* (68.5), *It's Nice To Have A Friend* (70.0), and *Mary's Song (Oh My My My)* (74.9). Just like danceability, the songs with the highest and lowest tempo appear in the same album, ***Lover***. It's interesting that the song *Soon You'll Get Better* has the highest tempo considering that it is quite a depressing, emotional, acoustic song.

### Time Signature
*Time Signature is the estimated overall time signature of a song*.

Almost all of Taylor Swift's songs have a time signature of 4. The songs *evermore*, *closure*, and *tolerate it* have a time signature of 5. These 3 songs are from the album ***evermore***. The songs *Last Kiss*, *Dear John*, *Sad Beautiful Tragic* have a time signature below 4 with values of 1, 3, and 3, respectively.

<img src="images/project1_images/time_signature_plot.png?raw=true"/>

### Valence
*Valence is a measurement from 0 to 1.0 that represents the musical postiveness conveyed by a track. The more positive the song, the higher the valence*.

The distribution of valence is slightly right-skewed with a mean of 0.42. Her first 4 albums tend to have a similar overall valence while her later albums have a slightly lower valence with ***reputation*** having the lowest.

<img src="images/project1_images/valence_plot.png?raw=true"/>

The most positive songs in her discography are *Shake It Off* (0.94), *Stay Stay Stay* (0.93), *closure* (0.92). The songs with the lowest valence are *Delicate* (0.05), *Dress* (0.09), and *Dear John* (0.10). I find it unexpecting that Dress has a low valence considering that it is a love song.

## Conclusion

I listen to a lot of Taylor Swift so I am quite familiar with her music. Thus, many of these results were expected. However, there were some unexpected moments such as *Soon You'll Get Better* having the highest tempo or *Dress* having a low valence. It was interesting to see these features quantified and to see which songs have the highest or lowest values. 

