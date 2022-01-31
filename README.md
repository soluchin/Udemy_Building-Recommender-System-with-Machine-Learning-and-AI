# Udemy - Building Recommender System with Machine Learning and Artificial Intelligence
How to create machine learning recommendation systems with deep learning, collaborative filtering, and Python.  
by Sundog Education

**Install library**  
In this course you need to install SurpriseLib from scikit  
``` pip install scikit-surprise ```

## Course Overview
1. [What is Recommender system](https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/blob/main/README.md#what-is-a-recommender-system)
1. Intro to python
2. [Evaluating recommender system](https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/tree/main/evaluating-recommender-system)
3. [Recommender engine framework](recommender-engine-framework)
4. content-based filtering
5. neighborhood-based collaborative filtering
6. model-based methods
7. intro to deep learning
8. recommendations with deep learning
9. scaling up
10. challenges of recommendation system
11. case studies
12. hybrid solution

## What is a Recommender System
* a system that predicts ratings or preferences a user might give to an item. 
* recommending things to people based on their past behavior and the behavior of other people.
* recommending stuff to people based on their pregnancies that we learn over time.
* often there are sorted and presented as **"top-N" recommendations**.
* **also known as** recommender engines, recommendation systems, recommendation platforms.
* **can used to:** recommending items, content, music, movies, games, search results, people etc.

&nbsp;&nbsp;&nbsp;Recommender system can find relationships between users and between items just based on actions. Usually there's no human curation involved, at all. It can use historical patterns to show people stuff they want before they even know they want it.

## How do Recommender System Works?
* comes down to understanding user
* this system start with some sort of data about every user that it can use to figure out user's individual tastes and interests
* then, merge data about one user with the collective behaviour of everyone else like that user
* and recommend stuff that user might like

&nbsp;&nbsp;&nbsp;We can collect data from user to extract their preferences in 2 different way. **Explicit** and **Implicit**. Explicit feedback can take user preferences by asking their review about something, so we can know what users are intrested in and build user profile. But, this methode requires extra work from user so this data tends to be sparse. This problem can lead us to low quality recommendation. Another way to understand user profile is trough implicit behavior, this is looking at the thing user do anyhow and convert them as indications of interest or disinterest. For example, if user click something in the web we could consider that an implicit positive rating. Click data is great and we don't have problem with data sparsity.


![](https://github.com/soluchin/Udemy_Building-Recommender-System-with-Machine-Learning-and-AI/blob/main/Materials/Image-materials/anatomy%20of%20a%20top-N%20recommender.jpg)


&nbsp;&nbsp;&nbsp;At the end of system we could show what system find in front of user in a form of a top-N list. starting with the most relevant to the user. Our success depends on system ability to find the best recommendation for people.
