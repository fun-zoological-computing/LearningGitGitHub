
## Git history is what type of graph:
* Un-directed cycli. Git history is not time sensative or state sensitive. Git History means the same thing traversing it forwards or backwards. Feedback loops are possible in Git history.
* Un-directed acyclic (convergence and divergence between collabotor forks and branches, but without feedback). In otherwords if there is feedback in githistory you could revisit past states, by following commits back outside a path of convergence, and loop backaround into the same commit/state.
* Directed, Cyclic graph (recurrent connnections between collaborators).
* Directed, Acyclic graph (convergence and divergence between collabotor forks and branches, but without feedback).


## Changing the gitNetwork structure is possible how:
```git init```
```git rebase```
```git reset hard```

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
Which is more Pythonic:

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


Genetic algorithms involve a counter balance of which forces:
*a attraction
*b selection
*c diversity
*d repulsion
*e mutation
