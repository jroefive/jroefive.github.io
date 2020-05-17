---
layout: post
collection: phish
---

After posting a few of my Phish data visualizations, I got a request to make something focused on the shows being played for the DInner and a Movie streams.  When they finally announced a 1.0 show, I decided it would be fun to learn a bit more about the era of the show while putting together a few visualizations.  

### Song Durations  
This isn’t an original idea.  [Mayacelium on Reddit made one of these for the Magnaball release](https://www.reddit.com/r/PhishData/comments/g1vd8t/dinner_and_a_movie_graphic/).  I thought it would be find to add a layer to show the length of the songs during the 50 shows before the 7/21/97 show and the 50 shows after to help put the show in context of the era.  I think the graphs are pretty self explanatory but here are a few tips:  
* You can click the colored circles at the top to just show that category.  This will help if you can’t see the current show in the swarm.  Click again to bring everything back.  
* Clicking on the previous 50 or next 50 circle can give you a quick reference for how many times the songs had been played during that time period.  The box plot also changes so you can get a bit of a sense if the average length and spread changed much during those time periods.  
* The horizontal direction doesn’t mean much, just that there were a lot of instances where the song was played for that long.  But, whether the dot is on the right or left doesn’t mean anything.  

### Song Placement  
This is similar to [this post](https://jroefive.github.io/2020/05/11/Song-Placement-Analysis.html) I made in the past.  The placing of the dots are where within the show the song has appeared.  For example a song at 2.17 means that the song showed up 17% of the way into the second set.  In the past post, I did this by track number.  So 2.17 would pretty much mean that if there were 6 songs, it was the second song.  In this post, I changed it to the time into the set.  I think this is a bit more accurate because a song showing up as the second song after a short intro song like Buried Alive is in a very different spot in the set than a second song that comes after a killer 25 minute jam.  A couple quick notes:  
* I dropped all the times that a song was played in the third set as a way to compress the graph.  But, if a song was played in another set during a three set show, it will be in there.  
* Like in the last graph, clicking the different circles filters and can give you a bit of a sense about where in the set songs were  showing up in late 96 through mid 98.  

### Overall Show Length and Tracks  
Nothing really next to explain, but some thoughts:  
* Interesting to see how few songs were played during the period compared to the rest of Phish’s career and toggling between previous 50 and next 50 shows that the number of songs in the second set drops off pretty drastically after this show..  You can see [here](https://app.flourish.studio/visualisation/2318099/edit) the same trend. 
* For set duration, you can see that the sets were a bit shorter during this time period by toggling between Rest and either previous 50 or next 50.  
* I dropped Big Cypress to be able to see the data a bit better.  But you can see [Big Cypress included on this graph](https://public.flourish.studio/visualisation/2428059/) for context.  

### Same Transitions
I thought it would be cool to look at other times that the same transitions happened.  

|--|--|--|
|Ghost|Dogs Stole Things|8/2/97|
|Dogs Stole Things|Piper|2/22/03|
|Piper|Dirt|Never|
|Dirt|Ginseng Sullivan|Never|
|Ginseng Sullivan|Bathtub Gin|7/10/97, 8/16/98|
|Bathtub Gin|Character Zero|9/29/00*, 10/10/99*, 6/14/09|
|Character Zero - Closer|Wolfman's Brother - Opener|10/16/96|8/8/97|
|Wolfman's Brother|Magilla|5/4/94|
|Magilla|David Bowie|9/29/90,10/4/91|
|David Bowie|Wading in the Velvet Sea|7/31/99, 10/3/99|
|Wading in the Velvet Sea|Theme from the Bottom|Never|
|Theme from the Bottom|Funky Bitch|1/13/17, 10/23/18, 12/4/19|
|Funky Bitch|Slave to the Traffic Light|6/7/95|
|Slave to the Traffic Light - Closer|Loving Cup - Encore|11/4/94, 5/29/11, 8/29/12^, 10/27/13, 10/21/16, 7/15/17, 6/25/19|  
* - Also closed set with Gin, Zero
^ - Slave > Loving Cup together in the encore

