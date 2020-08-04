---
layout: post
collection: phish
---

### Overview
In the last three months of quarantining, I have been teaching myself how to code using Python with a hope of developing skills in data analytics and machine learning/AI.  I'm not really interested in a classing "Data Science" type role but I hope to be able to stay in the education field but have stronger skills with data for whatever I do next.  The more I learn, the more I'm convinced that better data practices and a focused use of ML and AI can help push education policy to be more equity driven.  I've thought a lot about that, and I hope to do some projects in the near future to help test out that theory.  But, for now, the data I have and the projects I've been working on have been solely focused on the band Phish and their song selection patterns over their 35+ years of playing together.  Here are three links that you might find interesting if you know anything about Phish.  If you don't know anything, it will likely not be interesting at all.

### The Story of a Phish Song
[https://the-story-of-a-phish-song.wl.r.appspot.com/dashapp/](https://the-story-of-a-phish-song.wl.r.appspot.com/dashapp/)  

This is my most recent dashboad and it incorporates some of the feedback I got from the first couple that I made.  With those improvements, and the focus, I think this one is the easiest to understand and likely the one you would come back to and use if you got curious about a song or you were looking for inspiration of which song or show or era to listen to.  In the dashboard you can pick any of the 200+ songs that Phish has played 25 or more times and get the following graphs.  

1) Song Duration Scatter Plot - A scatter and box plot that shows every time the song was played and how long it was and overlays a boxplot that shows the median, mean, and standard deviation of every time the song was played.  If you click on any point, it brings up the show info and a link to listen on Phish.in   
  
2) Song Duration Over Time - From the debut of the song, I split the history into 100 shows segments and found that average length over that time as well as the longest and shortest version of that window and the standard deviation to show if the song varied in duration much over that 100 show interval.  Like above, you can click on the longest and shortest points to see what show they came from.  
  
3) Set Placement Scatter Plot - SImilar to the first plot but the points are based on when the song was started in the show.  If the song has a value of 1.0 it was started right at the beginning of set 1, and a value of 2.45 would be a song that was started 45% into the second set.  As with the duration graph, you can click on any point.  
  
4) Set Placement Over Time - Same concept as graph number 2 but with the set placement so you can see how the song's placement has evolved over it's history.  
  
5) Song Frequency Over Time - How many times was the song played in each 100 show interval since the first time it was played.  
  
6) Song Clusters - What song is most likely to be played in the same show, same set, right before, or right after each chosen song.  And, which songs have never been played in those categories?  
  
7) Day of Week Distribution - How does the distribution of the day of the week the song was played compare to the distribution of shows for every day of the week? [I wrote up a whole analysis of this already here, so go there for more info.](https://jroefive.github.io/2020/04/30/Day-Of-Week-Bias-In-Phish-Setlists.html)  
  

### Set Closer Predictor
[https://predicting-phish-set-closers.wl.r.appspot.com/dashapp/](https://predicting-phish-set-closers.wl.r.appspot.com/dashapp/)  

This dashboard allows you to put in any show you want and it will tell you the precent chance that each of the songs would end up being the last song in the set.  Kind of like when you turn on a sportsball game and it says the percent chance your team will win based on the current score.  The dashboard has a link to a longer explanation or you can go directly to it [here.](https://jroefive.github.io/2020/06/22/Predicting-Phish-Set-Closers.html)

### Phish Show Digest Dashboard
[https://phish-show-digest.wl.r.appspot.com/dashapp/](https://phish-show-digest.wl.r.appspot.com/dashapp/)  

This is pretty much the same concept as the first dashboard listed but for a full show and only shows the two scatter plot options.  You pull up a show and a set from that show and it will show you that scatter plot for all songs in that set.  This can be a fun way to pull up a show you went to and then see that you saw the 4th longest Tweezer or that you saw the only show where Backwards Down the Number Line opened the first set.

### Phish Tour Analysis
[https://phish-tour-analysis.wl.r.appspot.com/dashapp/](https://phish-tour-analysis.wl.r.appspot.com/dashapp/)

Pull up a tour (of 13 shows or more) and see how many new songs were played each night of the tour.  Also see the most played song of the tour and the most played songs now played on the tour.  
