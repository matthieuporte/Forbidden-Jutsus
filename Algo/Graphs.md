

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

```python

# adjlist implementation

def DFS(G):
	visited = [False]*G.order
	for i in range(G.order):
		__DFS(G,i,visited)

def __DFS(G,i,visited):
	visited[i] = True
	for j in G.adjlists[i]:
		if not visited[j]:
			__DFS(G,i,visited)

```

There are 4 types of edges

- the discovery edges (or tree edges)
- the back edges
- the forward edges
- the cross edges


![[arcs_graphes.png]]

Types of edges

| undir | dir |
| --- | --- |  
| tree | tree|
|back|back|
| | forward|
| | cross|

<br>

>[!abstract] Prefix and suffix values
>When going through the graph, the index of the first encounter is the prefix value and the index of the second encounter is the suffix value

tree edge : $p[x] < p[y] <s[y] < s[x]$
back edge : $p[y] < p[x] < s[x]$ ($s[y]$ is unset here)
cross edge : $p[y] < s[y] < p[x] < s[x]$
forward edge : $p[x] < p[y] <s[y] < s[x]$

>[!danger]
>The tree edge and forward edge are the same with thoses specifications. 
>Therefore you want to check a tree edge with `if p[y] != NULL`

#### Breadth First Search

```python
def __BFS(G, x, M):
	q = queue.Queue()
	q.enqueue(x)
	M[x] = True
	while not q.isempty():
		x = q.dequeue()
		for y in G.adjlists[x]:
			if not M[y]:
				q.enqueue(y)
				M[y] = True

def BFS(G):
	M = [False]*G.order
	for i in range(G.order):
		if not M[i]:
			__BFS(G, x, M)
```

>[!info]- Vector of spanning forest exercice
>This function builds the vector of the spanning forest. (have the parent of every vertex)
>```python
>def __BFS_parents(G, x, p):
>	q = queue.Queue()
>	q.enqueue(x)
>	p[x] = -1
>	while not q.isempty():
>		x = q.dequeue()
>		for y in G.adjlists[x]:
>			if p[y] == None:
>				q.enqueue(y)
>				p[y] = x
>
>def BFS_parents(G):
>	p = [None]*G.order
>	for i in range(G.order):
>		if p[i] == None:
>			__BFS_parents(G, x, p)
>```