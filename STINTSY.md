
![[Pasted image 20250203165824.png]]

HIgh or Low type of Bias or Variance

We specifically use the word fit, or "fitting" or "modelling

There are levels of fitting or modelling that required regularization.

What is Bias and Variance in Fitting and Modelling

![[Pasted image 20250203170057.png]]
We fit a linear regression model given the equation we learned. Does it really fit, and we ask can we do better?

![[Pasted image 20250203170152.png]]
So now we edit the equation. we squared it, adding more data.

![[Pasted image 20250203170229.png]]
We change the model by chaging the data and augment to its higher order form (x^2)

![[Pasted image 20250203170449.png]]
So higher order, the supposed better performance

But if we increase complexity of computation, the more data we have. The problem specifically is "overfittin".

![[Pasted image 20250203170615.png]]

Curse of Dimensionality

As dimensionality of features speace increases, the number grows exponentially. Thus number of configurations covered by an observation decreases.

Overfit - pag may tinest, di na niya marerecognize

If you give more orders, masyado siyang magoo-verfit. Magfifit siya on its own instead of entirety.
![[Pasted image 20250203170833.png]]

High Variance 
Model is too complex
Large variety of models with same complexity can fit the data just as nicely

High Bias 
Model is too simple
No matter how much you try to fit, it won't capture the patterns

Underfitting - model did not fit the training data well

Overfitting - model fits the training data well but performs poorly on testing data i.e., did not generalize
May bagong dataset, pero di na solve
![[Pasted image 20250203171819.png]]

![[Pasted image 20250203171931.png]]

Generally we want to find a good balance between the bias and the variance

![[Pasted image 20250203172028.png]]
Just Right is the goldilocks zone
![[Pasted image 20250203172126.png]]

![[Pasted image 20250203172252.png]]
![[Pasted image 20250203172338.png]]

kapag bumubuka na sila, edi nagkakaoverfit. Lumalayo sa actual 
If plateu-ing, its underfit

Regularization
-moethods to reduce overfitting in machine learning models

![[Pasted image 20250203173056.png]]
![[Pasted image 20250203173214.png]]
![[Pasted image 20250203173308.png]]
![[Pasted image 20250203173644.png]]

