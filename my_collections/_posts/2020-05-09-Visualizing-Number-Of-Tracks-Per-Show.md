---
layout: post
collection: phish
---

I’ve decided to do my first real Machine Learning project on predicting how many songs are left in a set at any point.  My first reason is that I think it is a question all fans have had at one point or another.  Do I have time to run to the bathroom before the set closer?  Should we leave now to get in line for the Camden ferry?  I also want to keep the model simple and use some of the more basic ML processes instead of jumping right to a neural network or some other deep learning approach.  

## Equate My Life with Sand
### Set 1
To get started, I’ll do a little analysis on the three domains of features that I think I’ll end up using: How many songs have been played in the set so far? How long (number of minutes) has the set been so far? What song are they currently playing?

The amount of songs played so far in a set will clearly help as one of the inputs in the model.  If the band has been playing a lot of shows with 9 or 10  songs in the first set lately, you could use that to come up with a probability that the current song is the last song in the set.  Since I’ll need to decide on intervals of how far back the model should look before making a prediction, I thought it would be helpful to look at a graph of the changes in song totals per set over Phish’s career.  Since it is very common for these numbers to change pretty drastically from night to night, I decided it was better to show the average over the previous 50 shows instead of trying to plot every point.

### Setbreak
Due to rain, set two is being delayed until I have more time to put together some visuals on the next category: Set Length (in minutes) Patterns over Phish's Career

## Mystified and Mishapen
* The SQL Code I used to create the table that shows every show and how many tracks were in each set.  
![Preview](/photos/tracks_per_set_sql.jpg)
* I just used a simple google sheet average formula to find the 50 show running averages.  Here's a link to the google sheet if you want to take the data and do anything with it.

## And You Step to the Line
<div class="flourish-embed" data-src="story/328860" data-url="https://flo.uri.sh/story/328860/embed"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

The trends are pretty interesting and not surprising.  The short dips in 1992 and 1996 come from festival sets and opening sets for Santana.  The later half of 97 into 98 having fewer total songs, and the dramatic increase in total songs at the start of 3.0 both fit with what we know about setlists from those eras.  Given these relatively big changes in set lengths throughout Phish’s career, it will be important to build in a way to only look at the most recent shows instead of using averages across their whole career.
