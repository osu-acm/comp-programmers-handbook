Chapter 11: Basics of graphs
===
 * Lots of problems solve via graphs

Graph terminology
---
 * Consists of nodes and edges
 * Path = from node a to node b
	* Simple = each node only appears once
	* Cycle = First and last node are same
 * Tree = connected graph with `n` nodes and `n-1` edges
 * Directed = edges only go one way
 * Neighbor/adjacent = edge between them
 * Degree = number of neighbors a node has
 * Regular = every node has constant `d` degree
 * Complete = every node is connected to every other node
 * Indegree = Number of edges that start at node, outdegree = number of edges that end at that node
 * Coloring = each node is assigned a color so that no adjacent nodes are of same color
 * Bipartite = Possible for a graph to be colored w 2 colors
 * Simple = No multiple edges between nodes

Graph representation
---
 * Adjacency list = List of lists of connections, i.e. `adj[1]` gets all of the 1st node's connections
	* Weighted graphs can be stored using pairs instead of just ints
 * Adjacency matrix = Really cool matrix version of adjacency list. `adj[a][b]` is the weight of the connection between `a` and `b`.
 * Edge list = Just a 1D list of pairs of nodes that represent edges
