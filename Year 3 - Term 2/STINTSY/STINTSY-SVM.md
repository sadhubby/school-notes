
- Support Vector Machine is a supervised learning algorithm that classify both linear and non linear data based on maximizing margin between support points and non linear mapping
- Vapnik and Cortest and colleagues (1992)



![[Pasted image 20250409155939.png]]
Hyperplane - a line in 4-dimensional and above, we call it a hyperplane

Now we can have many solutions to that, we can just split it in the middle but there is a lot more, as shown below
![[Pasted image 20250409160350.png]]

Now it does beg the question, how do we know which on is better? 
Well we try to maximize the margin 
![[Pasted image 20250409160427.png]]

Meaning in this example, B1 is supposedly a better hyperplane because it has a larger margin. The margin is the dotted lines, the width of the support vector. Ang goal ni SVM is the wider the margin, the better its classification.

But why is it better to be wider? Well for example, unseen data cannot be classified correctly because not within margin.

![[Pasted image 20250409160830.png]]

IN SVM, we will be using Convex Hulls. The vector will be the closest point of each convex hull to each other.
![[Pasted image 20250409160919.png]]


After that, create a plane that bisects closest points. Then we will be able to create na the hyperplane
![[Pasted image 20250409165835.png]]

If we're gonna pick between skinny and wide, skinny margin is more flexible thus more complex. So bale like mas maraming pwedeng support vectors kapag mas skinny. Magiging complex sa evaluation. To mitigate, why not gawa nalang ng wider margin.

SVM is an excellent choice for classification.

If use SVM, it doesn't matter if your dataset is balanced or imbalanced. SVM doesn't matter, as long as ang definition mo is in its margin size. 


## Support Vectors

closest points to the separating hyperplane / supporting hyperplane.
![[Pasted image 20250409170340.png]]

![[Pasted image 20250409170405.png]]

![[Pasted image 20250409170633.png]]

The slope + intercept.
Talking about how we can modify the hyperplane. If we have some kind of dataset and 2D is not enough to visualize it, try to increase its dimensions and have its 3d representations. 

Lets say we have 2 classes that are linearly separable

- Given a set of training data...
	$T = {\{x_{i}, y_{i}\}^n_{i=1}\text{, where }y_{i}\in\{-1, +1\}\text{ and } x_{i}\in R^h}$

- The linear classifier would be hyperplane in $R^h$ characterized by a normal w and an offset b (linear kernel):
	$f(x) = w^Tx + b$

![[Pasted image 20250409191902.png]]
![[Pasted image 20250409192335.png]]

![[Pasted image 20250409192450.png]]

![[Pasted image 20250409192722.png]]

![[Pasted image 20250409192808.png]]

c is a regularization parameter chosen by us the user to tolerate error.

![[Pasted image 20250409192916.png]]
  ![[Pasted image 20250409193442.png]]
![[Pasted image 20250409193545.png]]

![[Pasted image 20250409193601.png]]

![[Pasted image 20250409193607.png]]
![[Pasted image 20250409193618.png]]
![[Pasted image 20250409193636.png]]
![[Pasted image 20250409193650.png]]