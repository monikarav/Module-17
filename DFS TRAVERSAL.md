# Exp No: 18
# DFS Traversal

## AIM:

To write a Python function BFS to perform Breadth-First Search (BFS) traversal from a given source vertex in a graph.

ALGORITHM:

Step 1 : Represent the graph using an adjacency list.

Step 2 : Define a function BFS(start, graph) that:

a) Initializes a queue and a visited list.

b) Marks the starting vertex as visited and enqueues it.

c) While the queue is not empty:

1.Dequeue a vertex, print it.

2.Enqueue all its adjacent unvisited vertices and mark them as visited.

Step 3 : Take user input for the source vertex and call the BFS function.

# PROGRAM:

```
# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True
		while queue:
		    s=queue.pop(0)
		    print(s,end=" ")
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True

# Create a graph given in
# the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)

```

## OUTPUT :

![image](https://github.com/user-attachments/assets/15976927-a72b-4007-bb50-ea4f2be6ad1d)

## RESULT :

Thus the execution of BFS to perform Breadth-First Search (BFS) traversal from a given source vertex in a graph was successfully verified.

