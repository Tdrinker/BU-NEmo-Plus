# NEmo+

We created the dataset NEmo+ by significantly extending the U.S. gun violence
news-to-emotions dataset, BU-NEmo (https://aclanthology.org/2022.lrec-1.267.pdf), from 320 to 1,297 news headline
and lead image pairings and collecting 38,910 annotations. In curating
the NEmo+ dataset, we developed methods to identify news items that
will trigger similar versus divergent emotional responses. For news
items that trigger similar emotional responses, we compiled them into
the NEmo+-Consensus dataset.

### NEmo+:
* **description**: 
  
  1297 news items (image + headline text) with each news item having 10 emotional reactions (emotion category, intensity, free flow text explanations) for all three conditions T, I, TI.
* **location**: `NEmoP.csv`
    
### NEmo+-Consensus:
* **description**: 
  subsets of the NEmo+ dataset with emotional consensus.    
  
* ### NEmo+-CR:
    * **description**:
      
      We defined the rank difference for a news sample to be the difference in frequency between the most frequent emotional response by the group of annotators and the second most frequent emotional response by the group. 
      For the example frequency annotation vector described above, (0, 0, 1, 0, 0, 2, 0, 7), we sort the entries to yield {disgust: 7, sadness: 2, contentment: 1}. Then the rank difference is the frequency difference between the highest ranked emotion ‘disgust’ and the second highest emotion ‘sadness,’ which is 5.
      We filtered the full dataset to only keep news items that have a rank difference of greater than or equal to 3 in the emotional responses
    * **location**: `NEmoP-Consensus/NEmoP-CR` 
* ### NEmo+-CE:
    * **description**:
      
      The frequency annotation vector can be considered a probability distribution of emotions. If the participants’ emotional responses vary strongly for a news sample, we consider the response uncertain. If there is consensus among the participants, however, we consider the response certain.
      For a fair com- parison, we selected the entropy filtering threshold so that the resulting filtered dataset is similar in size to the rank difference-filtered dataset.
    * **location**: `NEmoP-Consensus/NEmoP-CE`
