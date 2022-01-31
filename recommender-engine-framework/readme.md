# Chapter 3: Recommender Engine Framework
&nbsp;&nbsp;&nbsp;We need framework to let us easily experiment with new algorithm and evaluate them and compare them each other. SurpriseLib has a python base class called AlgoBase. This class contain functions and variables that can be shared by other that inherit from this class. AlgoBased have some algorithm like SVD, KNNBasic and SVDpp which all of them inherits from AlgoBase class. They can access to the function and data defined in AlgoBase based class. Beside that we can define our own algorithm that inherits from AlgoBase and can be used in the same way. There is the steps:
- All you have to do is create a new class inherits from AlgoBase
- Your algorithm might be predict ratings
- Implement an estimate function

```pyton
#example
#this algorithm will turn 3 for all rating
class MyOwnAlgo(AlgoBase):
  def __init__(self):
    AlgoBase.__init__(self)
  def estimate(self, userID, itemID):
    return 3
```

