

### Definitions

**Order** : number of vertices _(sommet)_
**Degree** : number of edges going in or out of a vertex

$G = <V,E,(W)>$
$V = \text{Vertices}$
$E = \text{Edges}$
$W = \text{Weights}$

![[graphes1.jpg]]

#### Adjacency Matrix

```python
class GraphMat:
	def __init__(self,order,directed = False):
		self.order = order
		self.directed = directed
		self.adj = [[0 for j in range(order)] for i in range(order)]
```

#### Adjacency Lists

```python
class Graph:
	def __init__(self,order,directed = False,Labels = None):
		self.order = order
		self.directed = directed
		self.adjlists = [[] for i in range(order)]
```

### Traversals

#### Depth First Search

There are 4 types of edges

- the discovery edges (or tree edges)
- the back edges
- the forward edges
- the cross edges

![[arcs_graphes.png]]

#### Breadth First Search