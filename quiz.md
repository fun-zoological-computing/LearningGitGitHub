
## Git history is what type of graph:
* Un-directed cycli. Git history is not time sensative or state sensitive. Git History means the same thing traversing it forwards or backwards. Feedback loops are possible in Git history.
* Un-directed acyclic (convergence and divergence between collabotor forks and branches, but without feedback). In otherwords if there is feedback in githistory you could revisit past states, by following commits back outside a path of convergence, and loop backaround into the same commit/state.
* Directed, Cyclic graph (recurrent connnections between collaborators).
* Directed, Acyclic graph (convergence and divergence between collabotor forks and branches, but without feedback).


## DRY principle:
In Python which language features **don't** support DRY: "Don't Repeat Yourself":
* `this`: used to define a class in Java (false choice, Java).
* `isinstance`: used to define a class in Java (false choice, Java).
* `pass`: No operation (correct choice)
* `self`: define a class
* `def`: used to define a function. 
* `super`: to create inheritence in some class definitions.

## Python is what kind of language:
* Typed
* Untyped
* Optionally typed

### Person x claims that Classes and functions make code harder to read, due to there being more special keyword. By contrast Linus Tvoldis the original linux kernel creator is famously qouted that if you have more than 4 levels of indentation then you should fix your code
Python has what tools to you to stop writing overly nested code:

* `zip` (making 2d iterators easily)
* `enumerate`, giving you the index, and the indexed value
* list comprensions and lambda functionn (one liners, syntactic expressions which would otherwise span multiple indentation levels.
* `def` (functions), a function definition contains nesting, but the function call hides the nesting again.
* `self` (classes)

## Changing the git commit history's network structure is possible how:

a) ```git init```

b) ```git rebase```

c) ```git reset hard```

## Python lists

Which is more Pythonic:

* 1:
```
a = [1,2,3,4,5]
for ind in range(0,len(a)):
   print(a[ind])
```
* 2:
```
for i in [1,2,3,4,5]:
   print(i)
```
## Which is more Pythonic:

* 1:
```
c = []
a = [1,2,3,4,5]
for ind in range(0,len(a)):
   c.append((a[ind],ind))
```
* 2:
```
c= []
for i,x in enumerate([1,2,3,4,5]):
    c.append((x,i))
```
* 3:
```
c=[(i,x) for i,x in enumerate([1,2,3,4,5])]
```

## Genetic algorithms involve a counter balance of which forces:
*a attraction
*b selection
*c diversity
*d repulsion
*e mutation

## The exploration exploitation tradeoff describes: 
*1a a conflict in time, there is not enough time to find the best answer and utilize the best ansewer.
*1b a conflict in scale, the error sample is sensitive to big jumps in the parameter space, and small jumps in the parameter space, there is a conflict in time that can be spent searching the macroscale and microscale contributions to error
*1c. Satisficing (pre-registered criterion for when a solution is good enough to be utilized).

## With respect to the exploration exploitation tradeoff Eta should:
* Start small, and get bigger with ongoing iterations of the Genetic Algorithm (GA).
* Start large, and get smaller with ongoing iterations of the genetic algorithm.
* Eta should be initialized with a random seed, and be selected for by comparing against a fitness criterion.

## Differences between Python MATLAB and BASH:
### If Python is so good, Why hasnt Python replaced BASH as a system level language shell?
* BASH is faster
* os.system.
* Python2.7 is used by many operating systems.
* zsh replaces BASH.
* bash does not support floats.
### Which language has base 0 indexing
a) Python
b) Julia
c) MATLAB
d) BASH

## Glob



## In contrast to other machine learning algorithms, genetic algorithms are more suited to what?:
* Function optimization.
* Offline and or Online Function optimization (correct).
* Offline classification.
* offline Regression of non-linear functions
* Gradient descent
* Stochastic Gradient Descent.
* 
## Meta learning or learning to learn describes:
* Tuning one machine learning techniques meta parameters, with a different machine learning algorithm.

## Bogus fun answers:
* Gradient descent
* Gradient ascent
* Never gradient
* Momentum

## Genetic algorithms teach what
Sparse intelligent sampling.
Optimization and inverse problems.

## In Genetic Algorithms $Eta$ is:
*momentum which can be used to plough through smaller gradients.
*a the average step size caused by the combined effects mutation and cross over.
