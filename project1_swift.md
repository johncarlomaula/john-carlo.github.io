## Analyzing The Spotify Features of Taylor Swift's Music

**Project Description:** In this project, I retrieve the Spotify features of Taylor Swift's music and visualize them for analysis.

<img src="images/project1_images/swift.png?raw=true"/>


### Introduction

I have no doubt that Taylor Swift is the artist I listen to the most. For the most part, I can tell which of her songs are upbeat and danceable and which ones are slow and acoustic. But I think it would interesting to see these qualities quantified, see how each of her albums differ from each other, and see the progression in her music.

For this project, I will only be focusing on Taylor's 9 studio albums released throughout 2006 - 2020. This means that I will not be including any EPs or re-recordings (known as "Taylor's Version").I will be including bonus tracks from deluxe versions, but alternative versions of standard songs (e.g. piano version or acoustic version).


### Code

The code I used to generate these plots is shown below.

```python
# Define function that plots a boxplot of the features by album and a histogram of that feature
def plot_feature(df, feature, title, xlabel):
    
    fig, (ax1, ax2) = plt.subplots(nrows = 1, ncols = 2, figsize = (18, 9))

    # Plot boxplot
    sns.boxplot(x = feature, y = 'album', data = df, palette = swift_palette, showfliers = False, ax = ax1)
    sns.swarmplot(x = feature, y = 'album', data = df, linewidth = 1, ax = ax1)
    ax1.set_title(title + ' by Album')
    ax1.set_xlabel(xlabel)
    ax1.set_ylabel('Album')

    # Plot histogram
    sns.histplot(x = feature, data = df, ax = ax2, kde = True, bins = 10)
    ax2.set_title('Histogram of ' + title)
    ax2.set_xlabel(xlabel)
    
    # Save plot to images folder
    plt.savefig('images/' + feature + '_plot.png')
    

# Plot song length
plot_feature(df, 'length', 'Song Length', 'Length (min)')
```

For more information about how I retrieved the data, you can check out the Data Retrieval notebook. To see the full code used to generate these plots, see the Swift Analysis notebook.


### Length

***Song length*** *is the track duration in minutes*. The distribution of length appears to be right-skewed with an average length of **4 minutes**. Due to her storytelling style of songwriting, her songs tend to have a longer length. As she transitioned to pop music with ***1989***, the overall length of her music began to decrease. Her albums ***folklore*** and ***evermore*** saw a return in her storytelling form, which resulted in longer songs.

<img src="images/project1_images/danceability_plot.png?raw=true"/>

Her top 3 longest songs, *Dear John* (6:43), *Last Kiss* (6:07), and *Enchanted* (5:52) are all from her 3rd album, ***Speak Now***, while her top 3 shortest songs, *It's Nice To Have A Friend* (2:30), *I Forgot That You Existed* (2:50), and *You Need To Calm Down* (2:51) are all from her 7th album, ***Lover***. Although not included in here, her longest song is *All Too Well (10 Minute Version)* from ***Red (Taylor's Version)*** clocking in at 10:13.


### Popularity
Popularity is a measure of a song's popularity with 0 being the least popular and 100 being the most popular. A song's popularity changes depending on when the data was retrieved.

### Danceability




### 2. Assess assumptions on which statistical inference will be based



### 3. Support the selection of appropriate statistical tools and techniques

<img src="images/dummy_thumbnail.jpg?raw=true"/>

### 4. Provide a basis for further data collection through surveys or experiments

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

