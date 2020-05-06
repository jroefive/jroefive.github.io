---
layout: post
collection: learn
---

One of my daily routines during quarantine has been a long walk.  Most days it is around 3 hours long and about 10 miles.  It has been a great way to get some much needed exercise, alone time, time to think, and time for podcasts.  After over thirty days of walking, I’m about to run out of places to walk to.  That has gotten me thinking about if I could have been more efficient or comprehensive with my daily walks to be able to see more of the area and repeat roads less often.  I don’t really need to be efficient at the moment,and I’m sure I’m not the first person to think about how I could see something new everyday when I go on a walk.  

I wouldn’t be surprised if there wasn’t a model out for this already and I definitely don’t have the skills to do all of this yet.  But, I think I can propose an algorithm that could work:

1. Input a desired distance range for walks and choose either loops or one way.  (I was able to do both because I could set up a ride either to or from the endpoint of my walk on some days.)
2. Generate a list of all possible walking routes that fit the inputs in bullet one
3. Drop all generated walks that overlap on the same road, except within a short Euclidean distance from the starting point. (Overlapping close to home is accepted)
4. Drop all possible walks that have endpoints (or farthest point in a loop) less than some specific Euclidean distance away from the starting point. (This should help reduce walks that wander close to the starting point)
5. Choose a walk at random to be the first walk
6. Choose all next walk to have the least amount of overlap with all previous walks
7. Choose a percentage of overlap that will be too high to continue.  
8. Once all walks remaining require overlap higher than the chosen percentage, stop.  Calculate the percentage of roads covered by all  walks in the list.
9 . Simulate steps 5-8 thousands of times and choose the generated list of walks that covers the highest total distance on roads when not counting overlap.

A few variations could be:
* Some days I have more time or energy than others due to shopping trips, weather, etc.  It would be nice to create a system where you are given four or five walk options to do that day instead of an exact formula.  This may cause me not to choose the most optimal set of walking routes to cover the most area, but it would feel more flexible and enjoyable.
* Instead of mapping out everything from the beginning, it might be good to be able to track where I’ve been and generate a list of as many walks as possible to keep seeing as much new stuff every day.  
* Could be interesting to be able to input if elevation changes are preferred or not.  The above model could output the elevation change for all options and report that alongside the percentage of road covered.  Then I could choose a set of routes that fits my preference for elevation gain but covers as much road as possible.
