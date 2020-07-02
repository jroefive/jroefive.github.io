---
layout: post
title: Data Science in Secondary Education
collection: ed
---

As I’m teaching myself data science, I am thinking a lot about how I may have used data differently if I had known some of the things then
that I’m learning now.  Here are some of the things I would do if I was helping to support a data science initiative at a school district
or CMO.  

### Get teachers involved in the early development of models.  
I have been surprised about how much data cleaning, feature engineering and parameter fine tuning happens in machine learning and I think this is a great place for teachers to offer their expertise and their knowledge of the local context.  Teachers are much better equipped to answer questions like: “Can we drop all this data with a missing value or is it better to fill in the blanks with an average value?” or “Should attendance be included in this model or not?”  or “Do we have too many parameters in this model?”

### Make sure models are focused more on action and less on accuracy.  
In an education setting, no one is looking for a perfect model, they are looking for insights that might help improve the learning environment.  Parameters should be chosen because there are clear ways to impact the data that are manageable and ethical.  And presentation of models to administrators or teachers need to focus a lot more on calls to action and less on the model itself.

### Embed data science into the curriculum.  
And not just math.  While I believe that math curriculum should be much more focused on statistics and modeling, I don’t think this is the only opportunity to discuss and do data science in the classroom.  English and foreign language teachers can learn about Natural Language Processing and how it works.  Social science teachers can discuss how data science is used to predict voting patterns.  And, teachers may be more receptive to discussing models if they know it is something their students are learning.

### Focus on Short Term Models
Many of the models I've seen are for weeks or months into the future.  By the time the prediction window closes, the inputs and noise are so great that it's hard to determine what just happened.  Instead of models predicting a student's attendance rate, I'd predict whether they would come to school tomorrow.  Instead of trying to predict students grades at the end of the term, I'd be working to predict, how they would do on the next assessment.  
