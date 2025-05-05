
- <mark style="background: #BBFABBA6;">Supervised</mark> machine learning algorithm for both classification and regression
- **Key Idea:** Make a prediction by <mark style="background: #BBFABBA6;">asking a series of yes / no questions</mark>, based on historical data.

![[Pasted image 20250409015140.png]]

![[Pasted image 20250409015300.png]]
![[Pasted image 20250409015332.png]]
![[Pasted image 20250409015344.png]]

## Allowable Questions

Only yes/no questions are allowed. 
Each question must allow follow the format of: Is (feature) equal to / greater than / less than (value)?

- For categorical variables - equality with each possible value can be asked
- For continuous variables, comparison with every value present in the data can be asked (just choose $>, \geq, <, \leq$)

Let's use this table as an example
![[Pasted image 20250409113618.png]]

- **Categorical Variables**
	- Is the weather sunny?
	- Is the weather rainy?
	- Is the weather snowy? 
- **Continuous Variables**
	- Is the temperature > 35
	- Is the temperature > 32
	- Is the temperature > 24
	- Is the temperature > 20

Do note that the number of possible questions / splits is affected by training data

## Better Tree

![[Pasted image 20250409115845.png]]

## Key Idea

- To make a better tree, we need to ask good questions.
But what makes a question good? How do we quantify this mathematically?

So we know that each question "splits" the data into two. So now what makes a good split? We make good splits with measures of impurity

## Measure of Impurity 

- Given a set of objects, impurity measures how homogenous or heterogenous the objects are.

![[Pasted image 20250409120712.png]]

### Common Measures of Impurity

1. **Shannon's Entropy**

$L(S) = - |S| \Sigma^{y}_{i} p_{i}\log_{2}(p_{i})$

where $p_{i} = \frac{\text{number of class i}}{|S|}$,  
$|S| = \text{total number of observations}$

***Example***
Have this heterogenous example
![[Pasted image 20250409121324.png]]

$L(S) = -7 \times ( \left( \frac{6}{7}  \right) \log_{2}\left( \frac{6}{7} \right)  + \left( \frac{1}{7} \right)\log_{2}( \frac{1}{7}))$
$L(S) = 4.141709$ 

Let's have another example
![[Pasted image 20250409122427.png]]

$L(S) = -6 \times \left( \left( \left( \frac{3}{6} \right) \log_{2}{\left( \frac{3}{6} \right)}\right)+\left( \left( \frac{3}{6} \right)\log_{2}{\left( \frac{3}{6} \right)} \right) \right)$
$L(S) = 6$ 

However, do take note if there only exists one class
![[Pasted image 20250409123047.png]]

2. **Gini Index**

$L(S) = |S| \times (1 - \Sigma^{y}_{i} p_{i}^2)$

where $p_{i} = \frac{\text{number of class i}}{|S|}$,
$|S| = \text{total number of observations}$

***Example***
Let's use the same example as earlier
![[Pasted image 20250409121324.png]]

$L(S) = 7 \times \left( 1- (\left( \frac{6}{7} \right)^2 + \left( \frac{1}{7} \right)^2) \right)$
$L(S) = 1.714$

![[Pasted image 20250409122427.png]]

$L(S) = 6 \times\left( 1-\left( \left( \frac{3}{6} \right)^2 +\left( \frac{3}{6} \right)^2\right)\right)$
$L(S) = 3$

![[Pasted image 20250409125955.png]]
Once again, an entirely homogenous set will have their Index = 0

### Shannon vs Gini
![[Pasted image 20250409130047.png]]


Ok but how about for regression tasks? We also have impurity for that

3. **Variance (*for regression only*)**

$L(S) = |S| \times \frac{\Sigma(x - \mu)^2}{n-1}$
where $|S| = \text{total number of observations}$
Lets have an example

![[Pasted image 20250409130236.png]]

Calculate the mean first: $\mu = 2$
Now we do the impurity
$L(S) = 6 \times (\frac{(3-2)^2 +(2-2)^2+(2-2)^2+(2-2)^2+(2-2)^2+(1-2)^2}{5})$
$L(S) = 2.4$

Lets have another example
![[Pasted image 20250409130538.png]]
Calculate the mean first = $\mu=4.83$
$L(S) = 6 \times \frac{(8-4.83)^2+(8-4.83)^2+(8-4.83)^2+(2-4.83)^2+(2-4.83)^2+(1-4.83)^2}{5}$
$L(S) = 73$

## Information Gain

Amount of impurity that was lost when splitting the dataset through a question
![[Pasted image 20250409131049.png]]

## Training a Decision Tree

So idea is, we will recursively create subtrees so that we can get to the point where all the data have the same class

```
function DTL (data)
	if all data have the same class:
		return class
	else:
		best = Choose Attribute and Threshold(data)
		tree.left = DTL(data matching best)
		tree.right = DTL(data not matching best)
```

So explaining it, our if statement says that we do not need to ask the node any more questions, they are of the same class.

The else statement first assigns <mark style="background: #FFF3A3A6;">best</mark>, which chooses the best question based on the highest Information Gain. Then we recursively call the same function going left and right to make subtrees. One branches out with data matching the assigned <mark style="background: #FFF3A3A6;">best</mark> then data not matching <mark style="background: #FFF3A3A6;">best</mark>

## Decision Trees are High Variance Models

The way DTs are designed is that they keep asking questions until all classes have been completely separated from one another. Unless overlapping classes, <mark style="background: #BBFABBA6;">DT will always achieve 100% accuracy on the training set </mark>

Meaning to say, <mark style="background: #BBFABBA6;">Decision Trees are prone to overfitting</mark>
## Regularization Techniques

- **Stopping Criterion** (stop asking questions once a certain criteria is reached)
	- **Minimum Batch Size** (if number of data points to split < min)
	- **Tree Depth or height** (if height > max)
	- **Number of nodes** (if number of nodes > max)
	- **Impurity reduction** percentage (if impurity < min, return mode / avg)

When we do stop asking questions and dataset is still not homogenous, what do we do to make a prediction?
- For classification: pick majority
- For regression: get the average

![[Pasted image 20250409133126.png]]
![[Pasted image 20250409133137.png]]