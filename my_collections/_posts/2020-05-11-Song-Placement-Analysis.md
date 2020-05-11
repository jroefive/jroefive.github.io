---
layout: post
collection: phish
---

In my ultimate goal to create a model that can predict if a song is the last song in a set or not, I’m looking at the number of songs played so far, the song being played, and the amount of time passed in the set so far.  I already did some work on number of songs played in a set over Phish’s career and today I looked into the way that songs are placed within sets and complete shows.

## Equate My Life with Sand
### Set 2
I had to take several steps to get numbers that I needed.  I started with the table in the last project where it shows every show and how many songs are in each set and was able to create a table that has every track from every show and then shows the following:
How far into the show it was played
The position of the song within its set
Then a true or false for if it is a set opener, a set precloser (song before the closer), a set closer, and then repeats the same three for set 1, set 2, set 3, and encore specifically

This allowed me to create tables that show for each song the percentage of times it opened a set, was the second song in a set, preclosed a set and closed a set.  A table that showed the average placement of a song and the standard deviation of the song placement.  This allowed me to see which songs tend to be at the beginning or end of shows and which songs tend to hover around the same placement in a show and which songs were more likely to show up all over a show.  From this I chose five songs to make some beeswarm diagrams so you could see how song placements are distributed visually.  In that section, I adjusted song placement to be by set instead of overall show.  

In the last step above, I realized that I hadn’t adjusted for shows that had soundcheck tracks.  For the phish.in website, they need to have a position to be shown first, but I didn’t want soundcheck songs to count as part of the show and forgetting that made it so my formulas were off.  Unfortunately, the adjustment I made to my SQL query wouldn’t accomplish what I wanted, so I ended up dropping the 37 shows that had soundcheck tracks included.  

## Mystified and Mishapen
*SQL Code for adding show placement, set position, and true/false for all open/preclose/close spots
[pic](/photos/set_open_close1.jpg)
[pic2](/photos/set_open_close2.jpg)
*SQL Code for finding the percentage of times each song was in each set slot
[pic3](/photos/percent_open_close.jpg)
*SQL Code for finding the average and standard deviation of placement
[pic4](/photos/avg_std_placement.jpg)
*SQL Code for listing all placement for individual songs for the the beeswarm plots
[pic5](/photos/set_placement_for_beeswarm.jpg)

## And You Step to the Line
Just the Jams Link
Most Likely to Open, Second, Preclose, Close Table
Highest/Lowest Avg Placement and Std Dev
<div class="flourish-embed" data-src="story/334562" data-url="https://flo.uri.sh/story/334562/embed"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

### Setlist Notebook:
And here’s a [link to my google spreadsheet](https://docs.google.com/spreadsheets/d/1BpC31Mz0EMFbQslktbcmSgOt_ioh43q2skVeEpxfSJg/edit?usp=sharing) with all the raw data if you want to use it for anything.
