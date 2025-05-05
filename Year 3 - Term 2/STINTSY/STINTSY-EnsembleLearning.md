

Meta - meaning nothing new, just using established models

- Stacked models
	- Creating multiple models
	- create another models that accepts their predictions and improves them
- Bagging
	- use high variance models
	- lower the variance by getting the average
- Boosting
	- use high bias models
	- lower the bias by stringing them together and learning from past mistakes


## Stacked Models

Here is an example of a stacked model
![[Pasted image 20250409194553.png]]


## Bootstrap Aggregation (Bagging)

- Create many overfitting trees
- Get the average result to reduce the overfitting. 

How do we create many overfitting trees with the same dataset.

Solution: Randomly choose different subsets from the data to introduce variations![[Pasted image 20250409194835.png]]


There does exist a problem with bagging. We can easily make the same base model since we have a limited combination of datasets. 

So we still have our things of $|S| = |S'|$ but we also randomize feature selection too.

And instead of selecting the best feature, we just randomly look at one feature and decide if we want to split
![[Pasted image 20250409195806.png]]

![[Pasted image 20250409195818.png]]

## Boosting 

- Create many underfitting trees
- Make them learn from the previous trees' mistakes to improve accuracy

But how do we create many underfitting trees from the same dataset? Well we do a decision stump. A decision tree with only one query.

![[Pasted image 20250409200935.png]]


![[Pasted image 20250409200944.png]]

### Boosting for Regression

![[Pasted image 20250409201034.png]]
![[Pasted image 20250409201023.png]]

**Gradient Boosting**
- Boosting algorithm where each stump has a different voting power on the overall prediction.

$h(x) = \alpha_{1}h_{1}(x) + \alpha_{2}h_{2}(x)+\dots+\alpha_{n}h_{b}(x)$

The $\alpha$ values are learned through gradient descent. You can think of it as a linear regression but the features are predictions of the stumps.

**Adaboost**
- Boosting algorithm for classification.
- Model which training samples need to have more focus in the succeeding stumps

Algorithm:
1. Assign equal weights to all instances
2. Choose the best stump according to the weights
3. Compute the amount of say of the stump
4. Adjust the weights
5. Repeat step 2 for the next stump

Weights - represents the attention that should be given to each instances. Instances that are mis-classified should be given more attention

Amount of say - represents the "voting power" of each stump, based on how well it distinguishes between the classes.

Lets have an example:

![[Pasted image 20250409201423.png]]

![[Pasted image 20250409201431.png]]
![[Pasted image 20250409201533.png]]

![[Pasted image 20250409201540.png]]
![[Pasted image 20250409201624.png]]
![[Pasted image 20250409201631.png]]


![[Pasted image 20250409202707.png]]

![[Pasted image 20250409202723.png]]

Then we repeat the process but now using the weights when computing the total error

When to stop?
Set a fixed number of iterations

OR 

Stop when the overall accuracy does not improve anymore
![[Pasted image 20250409202859.png]]

