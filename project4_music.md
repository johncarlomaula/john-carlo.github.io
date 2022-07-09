# Visualizing My Apple Music Consumption

**Project Description:** In this project, I visualize my Apple Music listening history from August 2020 - April 2022. I used SQL to organize and clean the raw data from Apple before visualizing the results in Tableau.

<img src="images/project4_images/apple_music.jpg?_raw=true"/>

I have enjoyed listening to music for as long as I can remember. When I got an iPod Nano for my 12th birthday, I became obsessed with tracking my music listening habits. Every week I would sync my iPod on iTunes, record my top played songs on a piece of paper, and hang it on my fridge like a personal Billboard Chart. Since then, my music data has been lost from losing hard drives or getting new devices. 

When I found out you can request music data from Apple, I decided to analyze my own data and visualize my music listening habits. I officially began my Apple Music subscription on my current Apple ID in August 2020, so I have about a year and a half of data to work with.

For this project, I created two dashboards that can be accessed from my Tableau Public account:

**1. [Listening Activity Dashboard](https://public.tableau.com/views/AppleMusicListeningActivity/AppleMusicListeningActivity?:language=en-US&:display_count=n&:origin=viz_share_link)** - focuses on my music listening habits over time

<img src="images/project4_images/listening_activity.png?_raw=true"/>

**2. [Music Breakdown Dashboard](https://public.tableau.com/views/MusicPlayCounts/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link)** - focuses on my most played artists, albums, songs, and genre

<img src="images/project4_images/count.png?_raw=true"/>

## Methodology

After retrieving my Apple data, the two files of interest are:
1. `Apple Music Play Activity.csv` - data of each instance I played music; contains 38 columns and 118,251 rows. I will refer to this as the *activity* dataset.
2. `Apple Music Library Tracks.json` - metadata of songs in my music library; contains 52 columns and 6,264 rows. I will refer to this as the *metadata* dataset.

To build my listening activity dashboard, I focused on the activity dataset since it includes timestamps of each instance and set the following conditions:
- Instances must have taken place during 2020 or after
- The listening duration must be at least 20% of the song's length
- The song must have ended naturally

The variables of interest include:
1. **Song_Name** - title of the song
2. **Artist_Name** - artist of the song
3. **Media_Duration** - length of the song
4. **Play_Duration** - listening duration of the song
5. **Album** - album containing the song
6. **Genre** - genre of the song
7. **Track_Year** - year the song was released

To build my music breakdown dashboard, I only need the metadata dataset since it contains play count as metadata. Unfortunately, I reset my play counts in the beginning of 2021, so these numbers do not include data from 2020. 

To remedy this, I performed a group by on the activity dataset based on song and artist to count the total number of instances per song. This will then represent play count, and it also follows the aforementioned set of conditions. Next, I joined the two datasets together based on song and artist to obtain metadata such as album, genre, and track year. 

There are some limitations to this method:
- Songs in my library but not on Apple Music are not recorded
- Differences in song titles and artists can lose some data or create duplicates when joining the two tables

For more details on how I cleaned and organized the data, you can check out my SQL scripts on [Github](https://github.com/johncarlomaula/apple-music-activity-project).

## Listening Activity

### Overall Music Breakdown

During the time period of August 2020 - April 2022, I listened to 2,162 hours of music. I played a total of 2,619 songs from 650 albums, 353 artists, 26 genres, and 8 decades for a total play count of 36,375. 

<img src="images/project4_images/breakdown.png?_raw=true"/>

As shown by the donut chart, I tend to listen to the same artists a lot. About 56% of the music I play are from 10 artists, with Taylor Swift being the number one artist at 22%.

As for genre, I primarily listen to pop music at 60%, followed by alternative at 20%. In other words, for every 5 songs I play, about 3 are pop songs and 1 is alternative. 

Finally, the majority of the songs I play have been released fairly recently with 45% being released within the last 2 years and 38% being released during the 2010s.

### Top Most Played Songs

The top 20 most played songs are displayed in the graph below ranging from 143 - 275 play counts. My top most played song is *happiness* by Taylor Swift, followed by *Felt This Way* by Carly Rae Jepsen at 269. Nine of my top 20 most played songs are by Taylor Swift. 

<img src="images/project4_images/top_songs.png?_raw=true"/>

The most recent songs in this list are *easier said* by Kacey Musgraves at 189 and *Hold On* by Adele at 176, released in September 2021 and November 2021, respectively. The oldest song in this list is *Sober* by Kelly Clarkson at 143 and was released in 2007.

### Top Most Played Albums

My top 20 most played albums, calculated by summing the play counts of each individual song in the album, is displayed below, ranging from 354 - 1990 play counts. Unsurprisingly, my top 4 albums are all by Taylor Swift, followed by ***Chromatica*** by Lady Gaga at 991 total plays.

<img src="images/project4_images/top_albums.png?_raw=true"/>

The most recent albums in this list are ***Red (Taylor's Version)*** by Taylor Swift and ***30*** by Adele, accumulating 1,116 and 846 plays, respectively, within 5 months of release. The oldest album in this list is ***Havoc and Bright Lights*** by Alanis Morissette at 354 plays and was released in 2012. I discovered this album fairly recently, which explains its appearance in my top 20.

### Monthly Listening Activity

The graph below shows the total hours of music I listened to each month. The months I listened to music the least are August 2020 and April 2022 as they do not contain data for the full month. The month I listened to music the most was in November 2020 at 172 hours, which averages to about 5.7 hours per day. The full month I listened to music the least was in March 2022 at 55 hours or about 1.8 hour per day.

<img src="images/project4_images/monthly_listening.png?_raw=true"/>

On average, I listen to about 109 hours of music per month, or about 3.5 - 3.6 hours per day. So far, there isn't a specific trend in my monthly listening habits. The amount of time I spend listening to music usually depends on several factors:
- Lack of or abundance of new music from my favorite artists
- Discovering new songs, albums, or artists that I enjoy
- Any new hobbies/activities I can play music to while participating

### Daily & Hourly Listening Habits

The next graphs show my daily and hourly listening activities. Both graphs plot the percentage of time I spent listening to music during a specific day or hour. I slightly listen to more music during the weekend and less during the weekdays. New music usually comes out on Friday, so that's probably why it's the day I listen to music the most.

<img src="images/project4_images/daily_hourly_listening.png?_raw=true"/>

I also tend to listen to music the most at night from 5 PM - 7 AM peaking at 7 PM. I listen to music the least during the day from 8 AM - 4 PM, with the lowest during 12 PM - 2 PM. During this time, I have adopted a night shift schedule and will probably not remain this way in the future.

### Top Most Listened To Artists

The next chart is a donut chart of my top most listened to artist. It is almost distributed the same as my top most played artists, but this focuses on the time spent listening to the artist. My top 10 artists are the same and accounts for about 56.2% of the music I listen to, with 23% being Taylor Swift.

<img src="images/project4_images/artist_listening.png?_raw=true"/>

For every hour I spend listening to music:
- 33.7 minutes are spent listening to 10 artists
- 13.9 minutes are spent listening to Taylor Swift
- 3.5 minutes are spent listening to Carly Rae Jepsen
- 3 minutes are spent listening to Lady Gaga

### Top Most Listened To Songs

My most listened to songs are similar to my top played songs with longer songs having more weight. Lengthy songs like *Hold On* and *I Drink Wine* by Adele are higher up in this list due to both songs being over 6 minutes. However, *happiness* is still my most listened to song as it is my most played song and with a length of 5:15. 

<img src="images/project4_images/songs_listening.png?_raw=true"/>


### Listening Activity Dashboard Example: Taylor Swift

The listening activity dashboard can be filtered by artists by clicking on the donut chart. As an example, clicking on Taylor Swift results in the image below.

<img src="images/project4_images/swift_listening.png?_raw=true"/>

As you can see, 10 of the 20 most listened to songs are by Taylor Swift. Based on the monthly listening activity charts, I listened to Taylor Swift the most on November 2021 at 51 hours. There was fairly long period where I didn't listen much to Taylor Swift from June 2021 - October 2021, ranging to 6 - 13 hours per month. The hourly listening graph did not change much.

### Music Breakdown Dashboard Example: Alternative Genre

The music breakdown dashboard can be filtered by genre and decade. As an example, filtering genre by lternative results in the image below. I listened to 450 alternative songs from 61 artists and 96 albums for a total of 7,417 play counts. About 21% of the alternative songs I played are by Taylor Swift, followed by Alanis Morissette at 16% and Rina Sawayama at 13%.

<img src="images/project4_images/alternative.png?_raw=true"/>

My most played alternative songs are *happiness* at 275, *Missing the Miracle* at 186, *Tokyo Love Hotel* at 177, and *Bad Friend* at 159 plays. My top most played albums are ***evermore*** by Taylor Swift at 1,409, ***Sawayama*** by Rina Sawayama at 934, and ***Such Pretty Forks in the Road*** by Alanis Morissette at 832. All these albums were released in 2020.


## Conclusion

Visualizing my music listening history was a fun experience. While I am very aware and familiar with my own taste in music, this experience allowed me to reflect on some of my listening habits. For example, I could put more effort into discovering new music and new artists instead of playing the same songs/artists repeatedly. However, even though Taylor Swift is my most listened to artist by a wide margin, she did release 5 albums in a span of 2 years, so I think she ended up being overrepresented a bit.

Regardless, this was a fun experience that allowed me to practice some SQL and Tableau. I look forward to doing this analysis in the future and see how my music habits change!
