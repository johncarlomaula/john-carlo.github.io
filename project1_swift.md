# Analyzing The Spotify Features of Taylor Swift's Music

**Project Description:** In this project, I retrieve the Spotify features of Taylor Swift's music and visualize them for analysis.

<img src="images/project1_images/swift.png?raw=true"/>

I have no doubt that Taylor Swift is the artist I listen to the most. For the most part, I can tell which of her songs are upbeat and danceable and which ones are slow and acoustic. But I think it would interesting to see these qualities quantified, see how each of her albums differ from each other, and see the progression in her music.

For this project, I will only be focusing on Taylor's 9 studio albums released throughout 2006 - 2020. This means that I will not be including any EPs or re-recordings (known as "Taylor's Version").I will be including bonus tracks from deluxe versions, but alternative versions of standard songs (e.g. piano version or acoustic version).

### Length
**Song length** *is the track duration in minutes*. 

The distribution of length appears to be right-skewed with an average length of **4 minutes**. Due to her storytelling style of songwriting, her songs tend to have a longer length. As she transitioned to pop music with ***1989***, the overall length of her music began to decrease. Her albums ***folklore*** and ***evermore*** saw a return in her storytelling form, which resulted in longer songs.

<img src="images/project1_images/danceability_plot.png?raw=true"/>

Her top 3 longest songs, *Dear John* (6:43), *Last Kiss* (6:07), and *Enchanted* (5:52) are all from her 3rd album, ***Speak Now***, while her top 3 shortest songs, *It's Nice To Have A Friend* (2:30), *I Forgot That You Existed* (2:50), and *You Need To Calm Down* (2:51) are all from her 7th album, ***Lover***. Although not included in here, her longest song is *All Too Well (10 Minute Version)* from ***Red (Taylor's Version)*** clocking in at 10:13.


### Popularity
**Popularity** *is a measure of a song's popularity with 0 being the least popular and 100 being the most popular. A song's popularity changes depending on when the data was retrieved*.

As of June 2022, her most popular albums are ***Lover*** and ***reputation***. As these are pop albums that have been promoted heavily, it makes sense that they are still popular among the general population despite having 2 newer albums. Her least popular albums are ***Fearless*** and ***Red*** due to the re-recordings of these albums being released.

<img src="images/project1_images/popularity_plot.png?raw=true"/>

As of now, her most popular songs are *Don't Blame Me*, *Lover*, *Cruel Summer*, *Paper Rings*, and *Getaway Car*.

### Danceability
**Danceability** *describes how suitable a track is for dancing with 0 being the least danceable and 1.0 being the most danceable*.

The distribution of danceability is unimodal and symmetric with a mean of 0.59 and standard deviation of 0.12. Her albums tend to become to become more danceable until ***folklore***, where overall danceability began to decrease.

<img src="images/project1_images/danceability_plot.png?raw=true"/>

Interestingly, her most danceable song, *I Think He Knows* (0.90), and least danceable song, *The Archer* (0.29), both appear in the same album, ***Lover***. They are also right next to each in the tracklist.
