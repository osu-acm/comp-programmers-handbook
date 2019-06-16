Chapter 12: Graph traversal
===
 * DFS and BFS are super important to basic questions (LC)

Depth-first search
---
 * O(m+n), m = edges, n = nodes
 * Goes as deep as possible first (depth)
 * Uses stack (take a look at code below for BFS)

Breadth-first search
---
 * Opposite of DFS - uses queue 
 * Goes as wide as possible first (breadth)
 * ~~~c++
	visited[x] = true;
	distance[x] = 0;
	q.push(x);
	while (!q.empty()) {
		int s = q.front(); 
		q.pop();
		// process node s
		for (auto u : adj[s]) {
			if (visited[u]) continue;
			visited[u] = true;
			distance[u] = distance[s]+1;
			q.push(u);
		}
	}
   ~~~

Applications
---
 * Check if a node is connected to other nodes - use BFS
 * Find cycles in the graph using DFS
 * Bipartiteness checks
	* Bipartite = can be colored with two colors
 * For K-COLOR, problem is NP-hard.
