# Visualizing My Apple Music Consumption

**Project Description:** In this project, I visualize my Apple Music listening history from August 2020 - April 2022. I used SQL to organize and clean the raw data from Apple before visualizing the results in Tableau.

<img src="images/project4_images/apple_music.jpg?_raw=true"/>

I have enjoyed listening to music for as long as I can remember. When I got an iPod Nano for my 12th birthday, I became obsessed with tracking my music listening habits. Every week I would sync my iPod on iTunes, record my top played songs on a piece of paper, and hang it on my fridge like a personal Billboard Chart. Since then, my music data has been lost from losing hard drives or getting new devices. 

When I found out you can request music data from Apple, I decided to analyze my own data and visualize my music listening habits. I officially began my Apple Music subscription on my current Apple ID in August 2020, so I have about a year and a half of data to work with.

For this project, I created two dashboards that can be accessed from my Tableau Public account:
1. **[Listening Activity](https://public.tableau.com/views/AppleMusicListeningActivity/AppleMusicListeningActivity?:language=en-US&:display_count=n&:origin=viz_share_link)** - focuses on my music listening habits over time
2. **[Music Breakdown](https://public.tableau.com/views/MusicPlayCounts/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link)** - focuses on my most played artists, albums, songs, and genre


## Methodology

After retrieving my Apple data, the two files of interest are:
1. `Apple Music Play Activity.csv` - data of each instance I played music; contains x columns and n rows. I will refer to this as the *activity* dataset.
2. `Apple Music Library Tracks.json` - metadata of songs in my music library; contains x columns and n rows. I will refer to this as the *metadata* dataset.

To build my listening activity dashboard, I focused on the activity dataset since it includes timestamps of each instance and set the following conditions:
- Instances must have taken place during 2020 or after
- The listening duration must be at least 20% of the song's length
- The song must have ended naturally
- The variables of interest are:

To build my music breakdown dashboard, I only need the metadata dataset since it contains play count as metadata. Unfortunately, I reset my play counts in the beginning of 2021, so these numbers do not include data from 2020. 

To remedy this, I performed a group by on the activity dataset based on song and artist to count the total number of instances per song. This will then represent play count, and it also follows the aforementioned set of conditions. Next, I joined the two datasets together based on song and artist to obtain metadata such as album, genre, and track year. 

There are some limitations to this method:
- Songs in my library but not on Apple Music are not recorded
- Differences in song titles and artists can lose some data or create duplicates when joining the two tables

For more details on how I cleaned and organized the data, you can check out my SQL scripts on [Github]().

## Listening Activity

### Overall Music Breakdown

During this time period, I listened to **2,162** hours of music. I played a total of 2,619 songs from 650 albums, 353 artists, 26 genres, and 8 decades for a total play count of 36,375. 

<img src="images/project4_images/breakdown.png?_raw=true"/>

As shown by the donut chart, I tend to listen to the same artists a lot. About 56% of the music I play are from 10 artists, with Taylor Swift being the number one artist at 22%.

As for genre, I primarily listen to pop music at 60%, followed by alternative at 20%. On average, for every 5 songs I play, 3 are pop and 1 is alternative.

Finally, the majority of the songs I play have been released fairly recently with 45% being released within the last 2 years and 38% being released during the 2010s.

### Top Most Played Songs

The top 20 most played song are displayed the in graph below ranging from 143 - 275 play counts. My top most played song is *happiness* by Taylor Swift, followed by *Felt This Way* by Carly Rae Jepsen at 269. Nine of the my top 20 most played songs are by Taylor Swift. 

<img src="images/project4_images/top_songs.png?_raw=true"/>

The most recent songs in this list are *easier said* by Kacey Musgraves at 189 and *Hold On* by Adele at 176, released in Sep. 2021 and Nov. 2021, respectively. The oldest song in this list is *Sober* by Kelly Clarkson at 143 and was released in 2007.

### Top Most Played Albums

My top 20 most played albums, calculated by summing the play counts of each individual song in an album, is displayed below, ranging from 354 - 1990 play counts. Unsurprisingly, the top 4 albums are all by Taylor Swift, followed by ***Chromatica*** by Lady Gaga at 991 total plays.

<img src="images/project4_images/top_albums.png?_raw=true"/>

The most recent albums in this list are ***Red (Taylor's Version)*** and ***30*** by Adele, accumulating 1,116 and 846 plays, respectively, within 5 months of release. The oldest album in this list is ***Havoc and Bright Lights*** by Alanis Morissette at 354 plays being released in 2012. She is an artist that I disovered within the last 2 years.

### Alternative Music

When looking at the dashboard, I can filter by genre by clicking on the donut chart. When I click on the alternative genre, I can see that I listened to 450 alternative songs from 61 artists and 96 albums for a total of 7,417 play counts. About 21% of the alternative songs I played are by Taylor Swift, followed by Alanis Morissette at 16% and Rina Sawayama at 13%.

<img src="images/project4_images/alternative.png?_raw=true"/>

My most played alternative songs are *happiness*, *Missing the Miracle*, and *Tokyo Love Hotel* at 275, 186, and 177 play counts, respectively. My top most played albums are ***evermore*** by Taylor Swift at 1,409, ***Sawayama*** by Rina Sawayama at 934, and ***Such Pretty Forks in the Road*** by Alanis Morisette at 832, which were all released in 2020.

### Monthly Listening Activity

The months I listened to music the least are August 2020 and April 2022 since they don't contain data for the full month. The I listened to music the most on Nov. 2020 at 172 hours and Mar. 2021 at 166 hours. This is about an average of 5.7 hrs and 5.4 hrs per day, respectively. The (full) month I listened to music the least is Mar. 2022 at 55 total hours, or about 1.8 hrs/day. 

<img src="images/project4_images/monthly_listening.png?_raw=true"/>

On average, I listen to about 109 hours of music per month, or about 3.5 - 3.6 hrs per day. The amount of time I spend listening to music usually depend on when a new music from an artist I like comes out (e.g. Taylor Swift and Adele), or when I discover music from artists I've never listened to before (e.g. Alanis Morissette and Rina Sawayama). It can also depend on activities and hobbies I partake in. For example, I became obsessed with doing puzzles during the Spring of 2021 and listened to music while working on them.

### Daily Listening Habits

The next chart is my daily listening habits. This chart plots the percentage of time I spent listening to music during each hour of the day. I tend to listen to music the most during the hours of 5PM - 7AM, peaking at 7PM and the least during 8AM - 4PM, with the lowest during 12PM - 2PM.

<img src="images/project4_images/hourly_listening.png?_raw=true"/>

This is unorthodox, but since I am currently in a gap year, and with the environment I live in, I  am free to have developed a night shift schedule!

### Top Most Listened To Artists

The next chart is a pie chart of my top artists. It is similarly distributed to play counts, but is measured by the time spent listening to artists. My 10 most-listened to artists is about 56.2% of the music I listen to, with 23% being Taylor Swift. 

<img src="images/project4_images/artist_listening.png?_raw=true"/>

In other words, for every 1 hour time spent listening to music:
1. 33.7 minutes spent listening to 10 artists
2. 13.9 minutes spent listening to Taylor Swift
3. 3.5 minutes spent listening to Carly Rae Jepsen
4. 3 minutes spent listening to Lady Gaga


### Taylor Swift Example

Finally, filtering by Taylor Swift affects the other charts in the dashboard. 10 of the 20 most played songs are by Taylor Swift. And based on the listening acitivty charts, I listened to Taylor Swift the most on November 2021 (when ***Red (Taylor's Version)*** came out), and the least during Jun. 2021 - Oct. 2021, Jan. 2022, and Mar. 2022. 

The daily listening activity doesn't seem affected much. 

<img src="images/project4_images/swift_listening.png?_raw=true"/>


## Conclusion
