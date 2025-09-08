# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to demonstrate the adjacency list representation of the given graph.

## ALGORITHM:

Step 1: Start the program.

Step 2: Define a class AdjNode to create a node for each adjacent vertex:

Store the vertex number.
Store the link to the next adjacent node.
Step 3: Define a class Graph to create the graph using adjacency lists:

Initialize the number of vertices.
Create a list (array) of size V, where each element is initially None.
Step 4: Define a method add_edge(src, dest) to:

Add dest to the adjacency list of src.
Add src to the adjacency list of dest (for undirected graphs).
Step 5: Define a method print_graph() to:

Traverse the adjacency list of each vertex.
Print the vertex and its adjacent nodes.
Step 6: In the main program:

Create a Graph object with V vertices.
Call add_edge() for all desired edges.
Call print_graph() to display the adjacency list.
Step 7: End the program.
## PYTHON PROGRAM

```
name: vishnu priya E
reg.no:212223060305


class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self,vertices):
		self.V = vertices
		self.graph = [None]*self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	# Function to print the graph
	def print_graph(self):
	  
		for i in range(self.V):
			print("Adjacency list of vertex {}\n {}".format(i,i), end="")
			temp = self.graph[i]
			while temp:
				print(" -> {}".format(temp.vertex), end="")
				temp = temp.next
			print(" \n")


# Driver program to the above graph class
if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()
```

## OUTPUT
<img width="624" height="485" alt="image" src="https://github.com/user-attachments/assets/0628e38a-6e43-4d7a-8844-6278a6dd0aef" />

## RESULT
Thus the python program to demonstrate the adjacency list representation of the given graph was implemented and executed successfully.
