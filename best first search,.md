
Best First Search is a search algorithm that explores a graph or a tree by prioritizing nodes based on a heuristic evaluation function that estimates the cost or value of reaching each node. Unlike uniform cost search which selects the node with the lowest total path cost, Best First Search selects the node that appears to be the most promising or closest to the goal state according to the heuristic function.

Here are the key features and steps involved in Best First Search:

1. **Heuristic Function**: Best First Search relies on a heuristic function ℎ(𝑛)h(n) for each node 𝑛n in the search space. This function estimates the cost from the current node to the goal node. The heuristic is typically domain-specific and provides an estimate of how close a node is to the goal.
    
2. **Priority Queue**: Nodes are stored in a priority queue (such as a min-heap) where the priority of each node is determined by the heuristic value ℎ(𝑛)h(n). The node with the lowest ℎ(𝑛)h(n) value (i.e., the node that is estimated to be closest to the goal) is chosen for expansion.
    
3. **Expanding Nodes**: At each step, the algorithm selects and removes the node with the lowest ℎ(𝑛)h(n) value from the priority queue. This node is then expanded, and its neighbors (or children) are added to the priority queue based on their heuristic values.
    
4. **Goal Test**: If the goal node is encountered during the expansion process, the search terminates, and the solution path is reconstructed from the parent pointers stored during the search.
    
5. **Completeness and Optimality**: Best First Search is not guaranteed to find the optimal solution unless the heuristic function is admissible (never overestimates the true cost to reach the goal) and consistent (satisfies the triangle inequality). However, it is often more efficient than uninformed search algorithms like Breadth-First Search or Depth-First Search, especially in large search spaces.
    

**Example**: Consider a pathfinding problem on a map where the goal is to find the shortest path from a start location to a destination. The heuristic function ℎ(𝑛)h(n) could be the straight-line distance (Euclidean distance) between node 𝑛n and the goal node. Best First Search would expand nodes in order of increasing distance from the goal, aiming to reach the destination efficiently.

Overall, Best First Search is a flexible and powerful algorithm used in various applications such as pathfinding, puzzle-solving, and optimization, especially when a good heuristic function is available to guide the search towards the goal state efficiently.

-----------

Best-First Search (BFS) is an informed graph traversal algorithm that explores a graph by selecting the most promising node based on a heuristic function. It combines the advantages of both breadth-first search (BFS) and depth-first search (DFS) algorithms. BFS uses a priority queue to prioritize nodes according to their heuristic values.

The heuristic function provides an estimate of the cost from the current node to the goal node. The algorithm maintains a priority queue of nodes and, at each step, selects the node with the lowest heuristic value as the next node to explore. This makes Best-First Search more efficient in terms of reaching the goal quickly by prioritizing nodes that are likely closer to the goal.

Best-First Search is commonly used in pathfinding problems, such as finding the shortest path in a graph or solving maze puzzles. However, it does not guarantee finding the optimal solution, as it is a greedy algorithm and may get stuck in local optima.

# Complexity Analysis:

  

  

1. Time complexity : O(b^d) to O(V + E) 

- b is the branching factor,
- Time complexity : O(b^d) to O(V + E)   
    
- d is the depth of the optimal solution,
- V is the number of vertices,
- E is the number of edges in the graph.

  

  

2. Space complexity : O(V) 

- V is the number of vertices in the graph.

# Explanation:

1. Best-First Search (BFS) is an informed graph traversal algorithm that selects the most promising node based on a heuristic function.
2. The algorithm maintains a priority queue to prioritize nodes according to their heuristic values. This allows it to focus on the nodes that are likely closer to the goal.
3. BFS starts with an initial node and enqueues it into the priority queue with its heuristic value.
4. At each step, the algorithm dequeues the node with the lowest heuristic value from the priority queue and checks if it is the goal node. If it is, the search is complete and the algorithm terminates.
5. If the dequeued node is not the goal node, it is marked as visited, and its child nodes are generated.
6. The heuristic values of the child nodes are calculated, and they are enqueued into the priority queue based on their heuristic values.
7. The algorithm continues this process of dequeuing, marking as visited, generating child nodes, and enqueuing until the goal node is reached or the priority queue becomes empty.
8. If the priority queue becomes empty and the goal node is not reached, it means that there is no solution.

# Best-First Search Algorithm:

Input: Graph, start node, goal node, heuristic function

1. Initialize an empty priority queue.
2. Enqueue the start node into the priority queue with its heuristic value.
3. Initialize an empty set to keep track of visited nodes.
4. While the priority queue is not empty: a. Dequeue the node with the lowest priority from the priority queue. b. If the dequeued node is the goal node, return true (goal reached). c. Mark the dequeued node as visited. d. Generate the child nodes of the dequeued node. e. For each child node: i. If the child node has not been visited: — Calculate its heuristic value. — Enqueue the child node into the priority queue with its heuristic value.
5. If the priority queue becomes empty and the goal node has not been reached, return false (no solution found).

# Example:

![](https://miro.medium.com/v2/resize:fit:371/0*fvIxRp9ZG3KI0AL4)

Consider a mathematical graph with nodes A, B, C, D, E, F, and G, along with their corresponding heuristic values:

[![](https://blogger.googleusercontent.com/img/a/AVvXsEgcmaLpnmCLsOifLoCHlS64XmzLBTy-PWqAZueEKQqcAexlpgc8H7cCq2wxZwwIBq_oWVzVrDznVfuv_bBjuu1scZ4GrMw0G-pgYXZLT5KPeVXlmetpM_egYo1J4wXUGsjmDRAUVBQB36zd_o5uwOfam5gkYNur-MlINfxvBe8smscMVaAmc_dfy26NHA=w477-h454-p-k-no-nu)](https://blogger.googleusercontent.com/img/a/AVvXsEgcmaLpnmCLsOifLoCHlS64XmzLBTy-PWqAZueEKQqcAexlpgc8H7cCq2wxZwwIBq_oWVzVrDznVfuv_bBjuu1scZ4GrMw0G-pgYXZLT5KPeVXlmetpM_egYo1J4wXUGsjmDRAUVBQB36zd_o5uwOfam5gkYNur-MlINfxvBe8smscMVaAmc_dfy26NHA)

The goal is to find the shortest path from node ‘A’ to node ‘G’ using Best-First Search.

# Step-by-Step Explanation:

Step 1: Start with node A (heuristic value: 10).

Graph:

![](https://miro.medium.com/v2/resize:fit:99/1*LmqxE2fgAhTd6iuRm-MbXQ.png)

Step 2: Expand node A and check its neighbors.

Graph:

![](https://miro.medium.com/v2/resize:fit:245/1*nAKGnoii8LTZGN8G_HfLhg.png)

Step 3: Choose the node with the lowest heuristic value, which is B (heuristic value: 5).

Graph:

![](https://miro.medium.com/v2/resize:fit:240/1*XU3zLWrdU05gcAZmjXy5Hw.png)

Step 4: Expand node B and check its neighbors.

Graph:

![](https://miro.medium.com/v2/resize:fit:333/1*T5JwjTuumr5k4rM8leUyvA.png)

Step 5: Choose the node with the lowest heuristic value, which is D (heuristic value: 4).

Graph:

![](https://miro.medium.com/v2/resize:fit:367/1*iAXg0uJqGTqhkA2Y2ctGTg.png)

Step 6: Expand node D and check its neighbors. Since D has no neighbors, move to the next step.

Step 7: Choose the node with the lowest heuristic value from the remaining unvisited nodes, which is C (heuristic value: 8).

Graph:

![](https://miro.medium.com/v2/resize:fit:379/1*Pz4wxV74ZyV2C9AeJqtLaQ.png)

Step 8: Expand node C and check its neighbors.

Step 9: Choose the node with the lowest heuristic value, which is E (heuristic value: 3).

Graph:

![](https://miro.medium.com/v2/resize:fit:360/1*EOpVHbMey_yi46sUNBcoRA.png)

Step 10: Expand node E and check its neighbors.

Step 11: Choose the node with the lowest heuristic value, which is G (heuristic value: 6).

Graph:

![](https://miro.medium.com/v2/resize:fit:379/1*Ut7v3wqjieer9-J0QcaV2A.png)

Step 12: Since the goal node G is reached, the search is complete.

![](https://miro.medium.com/v2/resize:fit:366/1*V66R1pmQeKOCnHr8OSzkXg.png)

Shortest Path: A -> B -> E -> G

Shortest Path: A -> B -> E -> G

# Graph Traversal Order:

This corresponds to the shortest path from ‘A’ to ‘G’: A -> B -> E -> G.













