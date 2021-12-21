# Chapter 2: Evaluating Recommender System
System recommendation is difficult to measure how good they are. It's hard to say whether a person considers the recommendation to be good or not. Espesially if you're develop your system offline. But, there is some algortihm that you can use to evaluate machine learning model like **train/test split** and **K-fold validation**. You can used it too for evaluate the system recommendation offline.

## Train/test Split & K-fold Validation
&nbsp;&nbsp;&nbsp;You can measure you system ability to predict how people rated thing in the past. You start to split data into train-dataset and test-dataset. Make the train-dataset bigger than test-dataset, usually train-dataset up to 75-90% of all of your full dataset and test-dataset get the rest of it. So you train your model using only the train-dataset. Once it's trained, you can ask the model to make prediction about how a new user rate some item they've never seen before. And we can measure how close it came by compare the model prediction with real test-dataset.  
&nbsp;&nbsp;&nbsp;It's possible to improve that one using k-fold cross validation technique. With the same idea as train/test split, but instead of a single train-set this method create many randomly assigned train-set it so called fold. And each individual fold is used to train your model independently, and then we measure the result accuracy against our test-set. We end it up with a score of how accuracy each fold and we can average it all.  
</br>
**Train/test split flow:**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**K-fold validation flow:**  
<img src="https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/blob/main/Materials/Image-materials/train%20test%20split.jpg" alt="image" height=400>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/blob/main/Materials/Image-materials/k%20fold%20validation.jpg" alt="image" height=400>

## Accuracy Metrics (RMSE, MAE)
**Accuracy isn't really measuring what we want recommender system to do. Could we care mostly about what out system thinks about the best movie for user to see and that's a different problem from this metrics.**  
</br>
&nbsp;&nbsp;&nbsp;So, here we talk about how to actually come up with an accuracy metrics when testing recommendation system. There is a couple different way to do it. The easiest method is **Mean Absolute Error (MAE)**. This way have mathematic equation like <img src="https://render.githubusercontent.com/render/math?math=\frac{\sum^{n}_{i=1}|y_i - x_i|}{n}">. The meaning of the equation is average absolute values of each error in rating predictions. The other equation is **Root Mean Square Error (RMSE)**. <img src="https://render.githubusercontent.com/render/math?math=\sqrt{\frac{\sum^{n}_{i=1}(y_i - x_i)^2}{n}}">. With this way we take the square root of whole averaged squared error. Everything you need is the lowest score, not the highest. It's mean every lowest score you get the better model.

## TOP-N Hit Rate
&nbsp;&nbsp;&nbsp;After you generate top-N recommendation for all of user in your test-dataset, if one recommendation in each user's top-N recommendation they are actually rated you consider that a hit. You actually managed to show the users something that they want. We can consider our system with something called *hit rate*, all you have to do is add up all of the hits and your top-N recommendations for every user in the test set divided by the number of users. That is your hit rate.
</br>
&nbsp;&nbsp;&nbsp;But, we can't use the same train/test split or cross validation approached to measuring the accuracy because we not measuring the accuracy on individual rating. We are measuring accuracy of top-N list for individual users. So we have to have another way to do that. One way is to use leave-one-out cross-validation.
## Leave-one-out Cross-validation
&nbsp;&nbsp;&nbsp;What we do is compute the top-N recommendations for each user in the train-set and intentionally removed one of those item from that user's training-set. We then test our system abillity to recommend one item was left out before. So we measure our abillity to recommend an item in the top-N list for each user that was left out from the training data. That's why we call it leave-one-out.  
</br>
**Leave-one-out cross-validation flow:**  
<img src="https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/blob/main/Materials/Image-materials/leave%20one%20out.png" alt="image" height=400>

## Coverage, Diversity, and Novelity
### Coverage
&nbsp;&nbsp;&nbsp;Coverage is the percent of items in the training data the model is able to recommend on a test set. In this example, the popularity recommender has only 0.05% coverage, since it only ever recommends 10 items. The random recommender has nearly 100% coverage as expected. Surprisingly, the collaborative filter is only able to recommend 8.42% of the items it was trained on.
### Diversity
&nbsp;&nbsp;&nbsp;Diversity in recommendation systems is used to avoid the overﬁtting prob-lem as well as excellent skill, which provides a recommendation based onincreasing the quality of user experiences. Diversity is inclusion of diﬀerent types of item set in recommendation for user which is diﬀerent from their past preferences. Diversityis calculated using (1-S), where s=avg similarity betweet recommendation pairs.
