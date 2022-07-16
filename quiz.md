
Git history is what type of graph:
* Un-directed cyclic git history is not time sensative or state sensitive, and feedback loops are possible.
* Un-directed acyclic
* Directed, Cyclic graph (recurrent connnections between collaborators).
* Directed, Acyclic graph (convergence and divergence between collabotor forks and branches, but without feedback).

Python lists

Which is more Pythonic:

* 1:
a = [1,2,3,4,5]
for ind in range(0,len(a)):
   print(a[ind])
* 2:
for i in [1,2,3,4,5]:
   print(i)

Which is more Pythonic:

* 1:
c = []
a = [1,2,3,4,5]
for ind in range(0,len(a)):
   c.append((a[ind],ind))
* 2:
c= []
for i,x in enumerate([1,2,3,4,5]):
    c.append((x,i))
* 3:
c=[(i,x) for i,x in enumerate([1,2,3,4,5])]
