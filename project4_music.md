# Visualizing My Apple Music Consumption

**Project Description:** In this project, I visualized my Apple Music listening history. After retrieving my personal Apple data, I used SQL ot organize and clean the data before visualizing the results in Tableau. 


<img src="images/project4_images/apple_music.jpg?_raw=true"/>

I have enjoyed listening to music for as long as I can remember. When I got an iPod Nano for my 12th birthday, I became obsessed with tracking my music listening habits. Every week I would sync my iPod on iTunes, record my top played songs on a piece of paper, and hang it on my fridge like a personal Billboard Chart. Since then, my music data has been lost from losing hard drives or getting new devices. 

When I found out you can request music data from Apple, I decided to analyze my own data and visualize my music listening habits. I officially began my Apple Music subscription on my current Apple ID on August 2020, so I have about a year and a half of data to work with.

I created two Tableau dashboards:
1. Listening Activity - focuses on my music listening habits over time
2. Music Breakdown - focuses on my most played artists, albums, songs, and genre


## Listening Activity

### Getting the Data
After receiving my Apple data, I focused on two different datasets:
1. Apple Music Library Tracks.json - metadata of the songs I have on Apple Music (song ID, title, play_count, genre, last played, etc.)
2. Apple Music Play Activity.csv - data of each instance I played music media (song, artist, timestamp, listening duration, etc.)

For my listening activity, I focused on the latter dataset. Here are the list of conditions I made for this dataset:
1. There are x columns and n rows
2. The variables of interest are:
3. The yearly timestamps must be 2020 or after
4. The listening duration must be at least 20% of the song's length
5. Song must have ended naturally


### Monthly Listening Habits

I first chart I looked at is my monthly listening activity. The months I listened to music the least are August 2020 and April 2022, because they only contain partial. when looking at full months, I listened the most on Nov. 2020 and Mar. 2021 at 172 and 166 hours, or 5.7 hrs and 5.4 hrs on average per day, respectively. The month I listened to the least is Mar. 2022 at 55 total hours or about 1.8 hrs per day. 

<img src="images/project4_images/monthly_listening.png?_raw=true"/>

On average, I listen to 109 hours of music per month, or about 3.5 - 3.6 hrs per day. The amount of hours I listen to music depends on when a new album from an artist I like comes out, or when I discover new music. It also depends on 

### Daily Listening Habits

The next chart is my daily listening habits. This chart plots the percentage of time I spent listening to music during each hour of the day. I tend to listen to music the most during the hours of 5PM - 7AM, peaking at 7PM and the least during 8AM - 4PM, with the lowest during 12PM - 2PM.

<img src="images/project4_images/hourly_listening.png?_raw=true"/>

This is unorthodox, but since I am currently in a gap year, and with the environment I live in, I  am free to have developed a night shift schedule!

### Top Most Listened To Artists

The next chart is a pie chart of my top artists. My 10 most-listened to artists is about 56.2% of the music I listen to, with 23% being Taylor Swift. 

In other words, for every 1 hour time spent listening to music:
1. 33.7 minutes spent listening to 10 artists
2. 13.9 minutes spent listening to Taylor Swift
3. 3.5 minutes spent listening to Carly Rae Jepsen
4. 3 minutes spent listening to Lady Gaga

<img src="images/project4_images/artist_listening.png?_raw=true"/>

### Top Most Listened to Songs

My top listened to songs are happiness, Daylight, and Hold On. These are relatively long songs (5:15, 4:53, and 6:06), so it's no surprise that these songs occupy the most. Short songs that made it to the list include easier said (3:07), Fun Tonight (2:53)

<img src="images/project4_images/songs_listening.png?_raw=true"/>

### Taylor Swift Example

Finally, filtering by Taylor Swift affects the other charts in the dashboard. 10 of the 20 most played songs are by Taylor Swift. And based on the listening acitivty charts, I listened to Taylor Swift the most on November 2021 (when ***Red (Taylor's Version)*** came out), and the least during Jun. 2021 - Oct. 2021, Jan. 2022, and Mar. 2022. 

The daily listening activity doesn't seem affected much. 

<img src="images/project4_images/swift_listening.png?_raw=true"/>

### Limitations

Excludes songs that are not available in Apple Music. For example, the song *Love Me Right* by Lady Gaga is one of my most played songs, but it is a song I downloaded to my library from a CD. Thus, it was excluded from the dataset. Fortunately, the majority of the songs I listen to are available on Apple Music.


## Music Breakdown

### Getting the Data

Getting the data for should technically be easy, but I since I reset the play counts at the beginning of 2021, the current play counts do not include data from 2020. Fortunately, I can estimate the play counts by counting the instances by song title and artist. 

In order to get information about the album, genre, and track year, I need to join the two tables. Since the first dataset does not have song ID, I joined them by song title and artist.

For more details on this process, you can check out the SQL code on my Github.

### Basic Stats

I listened to a total of 36,375 plays. I listened to 2,619 songs from 650 albums and 353 artists and 8 different decades. I also listened to 26 different genres and songs.

For every 100 songs played:
- 22 songs are by Taylor Swift
- 6 songs are by Carly Rae Jepsen
- 6 songs are by Lady Gaga

I also listen primarily to pop music, consisting 60% of my total play counts, followed by alternative at 20%, and Country at 8%


When it comes to decades, most of the songs I listened to came out in the current decade (2020 - present), followed closely by songs from the previous decade at 38.4%


### Top Songs

My top most played songs are *happiness*, *Felt This Way*, and *Daylight*. 9 of my top 20 most played songs are by Taylor Swift. 

### Top Albums

My top 4 albums are by Taylor Swift: *Lover*, *evermore*, *Red (Taylor's Version)*, and *folklore*. 

### Alternative Genre Example

When filtering by the alternative genre, I listened to 450 songs from 61 artists and 96 albums.

About 21% of the alternative songs I listened to are by Taylor Swift, followed by Alanis Morissette at 16.1% and Rina Sawayama at 12.6% These are two artists I discovered during this time period.

4 of the top 20 songs are alternative *happiness*, *Missing The Miracle*, *Tokyo Love Hotel*, and *Bad Friend* while 6 albums are included: *evermore*, *Sawayama*, *Such Pretty Forks in the Road*, *if i could make it go quiet*, *Havoc and Bright Lights*, and *folklore*. 

### Limitations

Since a join between two tables were made, songs that were not available in Apple Music also did not end up in this resulting dataset, despite being available in the original play count. Another limitation is the join by artist and song name. If the song name or artist were slightly different between the two tables, the resulting data is excluded. 


## Conclusion
