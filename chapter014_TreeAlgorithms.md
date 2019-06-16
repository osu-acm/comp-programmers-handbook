Chapter 14: Tree algorithms
===
 * Tree is a connected, acyclic graph of `n-1` edges.
 * Leaves = nodes with degree 1.
 * Rooted tree = all other nodes are below root node

Tree traversal
---
 * Use DP to calculate a number of things
 * Ex: Calculate number of nodes in subtree
 * ~~~c++
	void dfs(int s, int e) {
		count[s] = 1;
		for (auto u : adj[s]) {
			if (u == e) continue;
			dfs(u, s);
			count[s] += count[u];
		}
	}
   ~~~

Diameter
---
 * Diameter is the maximum length of a path between two nodes
 * Every diameter has to go through a high point
 * Algorithm 1: Calculate `toLeaf(x)` and `maxLength(x)` (max length to leaf and maxLength = `toLeaf(x->r) + toLeaf(x->l)`
 * Algorithm 2: Choose random node, find farthest node `b` from it. Then, find farthest node `c` from `b`.

All longest paths
---
 * Calculate the maximum length of a path that begins at a node for all nodes
 * Solve using maxLength1(x) = max length of path from x and maxLength2(x) = max length in another direction than maxLength1
 * If path `maxLength1(parent)` goes through x, `maxLength(x) = maxLength2(parent)+1`
 * Else, `maxLength(x) = maxLength1(p)+1`

Binary trees
---
 * BT is rooted tree with left and right subtrees.
 * Preorder = Process root, traverse left, traverse right
 * Inorder = Traverse left, process root, traverse right
 * Postorder = Traverse left, traverse right, process root

