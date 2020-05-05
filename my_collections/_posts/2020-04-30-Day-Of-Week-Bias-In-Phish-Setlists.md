---
layout: post
collection: phish
---

Why isn’t it Friday today? Well it’s never Friday when that song is played, and it’s always Tuesday when Tuesday is played.  But, are there other interesting patterns in Phish song selection for different days of the week?  I decided to make my first mini project in the Phish Stats journey this one because I thought it would be complicated enough to test my skills and straightforward enough to build a little confidence.  I don’t think it will appeal to fans as much as some other projects I’m thinking about, but I’m glad I started with it.

[Just the Jams](#abcd)

## Equate my life with Sand

### Set 1  

I’m using the Phish.in database mainly because it has song duration in it (which I don’t need for this project but will for future projects) and is easier to access than the phish.net one.  I knew there were some quirks in the data because it is scraped from AUD files and not one central setlist database.  But, looking at the distinct track titles, it looks pretty minimal and not worth spending time on cleaning, yet.    

I assumed there were some changes in the distribution of shows across a week throughout Phishs’ career so I looked into that.  The main thing I saw was that Phish stopped playing on Mondays and Thursdays in 3.0.  Not completely, but before 2009, about 10% of shows were on Mondays and after it has only been 4%, and for Thursdays the frequency dropped from 15% to 7%.  This difference was mostly moved to the weekends where there was an increased percentage of shows for Friday - Saturday.  These differences seem significant enough to find a solution for. When I did an initial look at overall day of week bias, I saw that some of the most frequent biased songs were those that were either new for 3.0 or hadn’t been played much in 3.0.  So, likely that change in show frequency contributes a bit of noise to the data.  When I refine the data, I’ll try to create a day of week show frequency for each song based on debut date to try to account for this change in frequency.  

I also made an arbitrary decision to only use songs that have been played more than 100 times[1].  I figure it will be more interesting for others to see songs that are more common and reducing to songs with small sample sizes would create more chaos in the data that may make it feel less interesting.  Plus, this is a band that has over 100 songs that they’ve played 100 times, how cool is that?  

### Setbreak  

One thing I noticed after going through my first mock up of the data was that it stopped at the Mexico 2019 run, thus about 35 of the most recent shows were missing.  Probably not enough to make a huge difference in the data but some of the margins are pretty tiny so it’s worth going through the process again to get updated numbers.  Plus, I think this will push me to try to make the process a little cleaner than last time.  Also, TMWSIY and HYHU came up a few times and I realized that this was because it was counted twice for every show.  Thus, I’ll need to account for that in the next round.  

I’m sure I could figure out how to do the math calculations in sql that I’ll need; but, it feels like there are enough steps that it would get cumbersome there.  So, I decided to get the raw numbers I need from sql and use google sheets to do the calculations.  I’ve done so many of these types of calculations in google sheets before, so it’ll definitely be faster.  

### Set 2  

I wanted to create a way to compare each song’s day of week distribution against the day of week distribution for all shows during the history of that specific song, and not against the day of week distribution of all shows Phish ever played.  First thing I did was figure out that the show_ids weren’t in chronological order.  I need a new id for each show which is chronological order for this project to create show distributions based on debut date, and also for several future projects.  It turned out that the easiest thing was to create a new table with a new column that was just the row number after the shows table was sorted by date.  This gives me the debut date for every song in a table.    

My goal was to create a table that showed the totals of shows played on each day of the week after the debut date for each song.  I was hoping this would erase some of the era bias that I saw in the first round. (Only for the 3.0 songs.)  But, I couldn’t figure out how to do it and decided on a simpler solution.[2]  I decided to compare the 1.0 and 3.0 songs against the day of week show distribution from just that era instead of over Phish’s whole career.  3.0 songs were pretty obvious, but I ended up adding 46 days and Sand to the list because they were played so much more often in 3.0 than any other period.  Any songs where 90% of their plays were in 1.0 got the 1.0 song tag.  

The only other data cleanup I did was removing The Man Who Stepped Into Yesterday from the data set since it was played over 100 times but was counted twice in every setlist (almost), so really it was played less than 100 times.  I could have done the same with Hold Your Head Up but that has over 200 tracks and just doubling every number shouldn’t really have an impact on this type of distribution.    

### Encore 

There are a lot of messy track names with either missing capitalization or segues of several songs making it so they don’t get counted.  While these differences are likely significant due to the tiny margins between some of the ranks, I’m not going to prioritize going through them all and breaking them up.  And, I’m sure, at this point, I’d make some mistakes in updating the database.  It also seems like there shouldn’t be any specific reason why this would happen on one day of the week more than others so maybe it all evens out.  If the data ever gets cleaned up in the future, by me or someone else, I can go back and update all the lists pretty easily.   

Another potentially interesting project could be to look at how song lengths are distributed across different weekdays.  Do we never miss a Sunday show because they play extra Back on the Trains and fewer Mike’s Grooves or is it because it is more likely to have a monster jam or two?  

### Notes 

[1] It would be pretty easy to recreate this data for songs played less than 100 times.  I could do that if there was enough interest.   [2] If it's possible to do this kind of thing in sql, which I’m guessing it is, I’d love some tips on how to do it.  

## Mystified and Mishapen
*   Create a distribution of shows by weekday that shows which percentage of shows have happened on each day of the week.  Slice that data by era and in five year chunks to see if distribution of shows changed much over the years.  (Main difference is that there have been much fewer Monday and Thursday shows in 3.0.)  
*   Create a table of all songs played at least 100 times with a count of how many times it was played on each day of the week.  (Join the tracks table and shows tables and use some case whens and extract dow from date)  
*   Convert the totals to a percentage of times each song was played on each day of the week.  (i.e. 6.7% of all Tweezers were played on Tuesday)  
*   Compare the percentages for all days of a song with the percentages of shows played on that day by finding the [z-score](https://www.tutorialspoint.com/statistics/one_proportion_z_test.htm).  This helps smooth the data out a bit to account for differences in total times played and the large differences in proportion of shows on different days of the week.  
*   This is enough to rank the songs by over- or under-representation on a given weekday.  To see which songs are most and least likely to be played on every day of the week.  
*   Using the show/weekday distribution can give us a prediction of how many times a song should have been played on a given day if the distribution matched the distribution of shows.  From that we can compare the prediction with the total of times a song was played to find how many free versions of songs we’ve gotten and how many were stolen.  (i.e. There should have been 42 Tweezers because the percentage of Tuesday shows is 11.2% and there have been 371 Tweezers.  .112*371 = 42.  There have been 25 Tuesday Tweezers.  Trey, you owe us 17 Tuesday Tweezers!)  
*   Rank all songs by doing sum of squares on their z-scores.  I thought about doing an average of all p-values but I can’t figure out how to get google sheets to spit out a p-value from a z-score.  So, instead of doing about 200 p-values in an online calculator to see if this is the case, I’ll stick with sum of squares of the z-score.  

## And You Step to the Line -  
<a name="abcd"></a>

What do you think? Do you have any guesses?  I could only really guess one song that I thought might show up more on a certain day when I started.  But it was cool to put the answers into context after seeing how it all shook out.  I hope you enjoy doing that same.  

### Top songs by day of the week


<table>
  <tr>
   <td>
   </td>
   <td colspan="2" ><strong>Free!</strong>
   </td>
   <td colspan="2" ><strong>Stolen, stolen, stolen</strong>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td><em>By p-value</em>
   </td>
   <td><em>By Total</em>
   </td>
   <td><em>By p-value</em>
   </td>
   <td><em>By Total</em>
   </td>
  </tr>
  <tr>
   <td>Sunday
   </td>
   <td>Back on the Train (.001)
   </td>
   <td>BoTT + Tweezer Reprise (13)
   </td>
   <td>Sand  (.008)
   </td>
   <td>Mike’s Song (-19)
   </td>
  </tr>
  <tr>
   <td>Monday
   </td>
   <td>Fire (.0006)
   </td>
   <td>Hold Your Head Up and Poor Heart (11)
   </td>
   <td>Light (.016)
   </td>
   <td>Harry Hood (-11)
   </td>
  </tr>
  <tr>
   <td>Tuesday
   </td>
   <td>Weekapaug Groove (.022)
   </td>
   <td>Weekapaug Groove (15)
   </td>
   <td>The Landlady (.005)
   </td>
   <td>Tweezer (-17)
   </td>
  </tr>
  <tr>
   <td>Wednesday
   </td>
   <td>Sample in a Jar (.010)
   </td>
   <td>Sample in a Jar (14)
   </td>
   <td>Dinner and a Movie (.002)
   </td>
   <td>Dinner and a Movie (-11)
   </td>
  </tr>
  <tr>
   <td>Thursday
   </td>
   <td>Uncle Pen (.0008)
   </td>
   <td>Uncle Pen (17)
   </td>
   <td>Light(&lt; .00001)
   </td>
   <td>Slave to the Traffic Light (-14)
   </td>
  </tr>
  <tr>
   <td>Friday
   </td>
   <td>Sand (.0004)
   </td>
   <td>Sand (16)
   </td>
   <td>Tweezer Reprise (.033)
   </td>
   <td>Tweezer Reprise (-15)
   </td>
  </tr>
  <tr>
   <td>Saturday
   </td>
   <td>Lawn Boy(.001)
   </td>
   <td>Harry Hood (25)
   </td>
   <td>I Didn’t Know (.003)
   </td>
   <td>I Didn’t Know (-18)
   </td>
  </tr>
</table>  


A note about what the p-value means - So imagine that the band is so focused on their setlists being random that they get together every Monday morning and pick out all the songs they want to play for the week.  Then they throw them all in a hat for the shows of the week and keep picking out songs during each show to decide what to play next.  Now, let’s say they have always done that.  And there are 1000 other universes where they do the same.  The p-value shows how many of those 1000 universes will have 61 (or more) Lawn Boys.  And, since the universe is a donut, we don’t actually have to assume.  There are at least 1000 other universes where Phish is doing just this. \  


**Most and least biased songs in order**  


<table>
  <tr>
   <td><strong>Most Bias</strong>
   </td>
   <td><strong>Most Consistent</strong>
   </td>
  </tr>
  <tr>
   <td>
<ol>

<li>Sand

<li>Light

<li>Backwards Down the Number Line

<li>46 Days

<li>Tweezer Reprise

<li>Carini

<li>Fee

<li>Back on the Train

<li>Dinner and a Movie

<li>Lawn Boy
</li>
</ol>
   </td>
   <td>
<ol>

<li>Scent of a Mule

<li>Rocky Top

<li>Rift

<li>Geulah Papyrus

<li>NICU

<li>Reba

<li>Big Black Furry Creatures from Mars

<li>The Moma Dance

<li>Sparkle

<li>Runaway Jim  
</li>
</ol>
   </td>
  </tr>
</table>   


Do you have a friend that always calls the same song on Saturday? “Bro, it’s Saturday, we’re totally getting a 2001 today.”  Does it annoy you that just because they played it at like three Saturday shows you went to together doesn’t mean there is a pattern?  Well, you can look it up in the spreadsheet [here](https://docs.google.com/spreadsheets/d/1Zad07yaUdZ7mosk1b7EmPMz_Vbq3ISrAu-jkqLfTw0E/edit#gid=1432443463).    

<span style="text-decoration:underline;">Secret Set</span>  

Bonus question: What’s the most played song that has never been played on each given day of the week?  

Sunday: Bike (25 times played)  

Monday: Halfway to the Moon (43)  

Tuesday: Life on Mars? (23)  

Wednesday: Donna Lee (20)  

Thursday: Golden Age (53)  

Friday: Terrapin (27)  

Saturday: Bittersweet Motel (18)  
