Visibility graphs are a fundamental concept in robot path planning, particularly in the context of geometric environments. They are used to represent the connectivity between key points (or vertices) in a given space based on the visibility or line-of-sight between these points. The concept is based on the idea that a robot can move directly between two points if there are no obstacles blocking the straight-line path between them.

### Understanding Visibility Graphs:

1. **Definition**:
   A visibility graph is a graph representation of a space where nodes (vertices) represent critical points, such as corners of obstacles or start/goal positions, and edges represent direct paths (visibility) between these points that do not intersect with obstacles.

2. **Construction**:
   - **Vertices**: Identify key points in the environment, such as obstacle vertices and the start/goal positions.
   - **Edges**: Connect vertices with straight-line paths (edges) if there are no obstacles obstructing the direct path between them.

3. **Properties**:
   - **Visibility**: Two vertices are connected by an edge if there is a clear line of sight (no obstacles) between them.
   - **Connectivity**: The resulting graph captures all possible direct paths that a robot can take without colliding with obstacles.

### Visibility Graph Method for Robot Path Planning:

Visibility graphs are a fundamental concept in robot path planning, particularly in the context of geometric environments. They are used to represent the connectivity between key points (or vertices) in a given space based on the visibility or line-of-sight between these points. The concept is based on the idea that a robot can move directly between two points if there are no obstacles blocking the straight-line path between them.

### Understanding Visibility Graphs:

1. **Definition**:
   A visibility graph is a graph representation of a space where nodes (vertices) represent critical points, such as corners of obstacles or start/goal positions, and edges represent direct paths (visibility) between these points that do not intersect with obstacles.

2. **Construction**:
   - **Vertices**: Identify key points in the environment, such as obstacle vertices and the start/goal positions.
   - **Edges**: Connect vertices with straight-line paths (edges) if there are no obstacles obstructing the direct path between them.

3. **Properties**:
   - **Visibility**: Two vertices are connected by an edge if there is a clear line of sight (no obstacles) between them.
   - **Connectivity**: The resulting graph captures all possible direct paths that a robot can take without colliding with obstacles.

### Visibility Graph Method for Robot Path Planning:

The visibility graph method is a classical approach to robot path planning that leverages the concept of visibility graphs to compute an optimal path for a robot in a 2D environment. Here's a detailed note on this method:

1. **Steps**:
   - **Input**: Given a 2D map of the environment with obstacles and defined start/goal positions.
   - **Vertex Identification**: Identify critical points (vertices) in the environment, such as corners of obstacles and start/goal positions.
   - **Visibility Check**: For each pair of vertices, check if there is a direct path (line-of-sight) between them that does not intersect any obstacles.
   - **Graph Construction**: Construct a visibility graph where vertices are the identified points, and edges are added between vertices that have a clear line-of-sight.
   - **Pathfinding**: Use graph search algorithms (e.g., Dijkstra's algorithm) on the visibility graph to find the shortest path between the start and goal vertices.

2. **Advantages**:
   - **Completeness**: The method guarantees finding a solution if one exists, given that the environment is represented accurately.
   - **Optimality**: Can find optimal paths (shortest paths) in terms of Euclidean distance under certain conditions.
   - **Simplicity**: Relatively straightforward to implement and understand, especially for simple environments.

3. **Considerations**:
   - **Environment Representation**: The effectiveness of the visibility graph method depends on how accurately the environment is represented and whether critical points are correctly identified.
   - **Complexity**: While suitable for many scenarios, visibility graphs may become computationally expensive for very dense or complex environments due to the number of vertices and edges.

4. **Limitations**:
   - **Euclidean Assumption**: Paths are optimized based on Euclidean distance and may not account for other factors like terrain difficulty or dynamic obstacles.
   - **Static Environments**: This method is more suitable for static environments as dynamic changes may require frequent graph updates.


In summary, the visibility graph method provides a robust and conceptually elegant approach to robot path planning in geometric environments. It leverages the direct visibility between critical points to construct a graph representation that facilitates efficient pathfinding. While effective for many scenarios, it's essential to consider the computational complexity and suitability of this method for specific robot navigation tasks and environmental conditions.

----------
1. **The visibility graph:** A different type of road map that can be used for finding shortest paths is the _visibility graph_: this is a graph whose vertices are the vertices of the obstacles, and its edges (u,v) are all the pair of vertices that can "see" each other, that is, segment uv does not intersect the interior of any obstacle. Below are some screenshots (the first screenshot is from http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/16311/www/s06/lecture/lec8.html).
    
    ![](https://tildesites.bowdoin.edu/~ltoma/teaching/cs3250-CompGeom/fall21/Assignments/A6-visGraph/pics-visgraph/visgraph.png) ![](https://tildesites.bowdoin.edu/~ltoma/teaching/cs3250-CompGeom/fall21/Assignments/A6-visGraph/pics-visgraph/samanjVG.png) ![](https://tildesites.bowdoin.edu/~ltoma/teaching/cs3250-CompGeom/fall21/Assignments/A6-visGraph/pics-visgraph/sonVG.png)
    
    Shortest paths in 2D have the very nice and convenient property that they are straight lines, and they have to go through the vertices of the obstacles. This basically means that any shortest path will be contained in the VG. Once the visibility graph (VG) is computed, the shortest paths from start to end can be computed for e.g. using Dijkstra's algorithm.
    
    Perspective: The problem with the VG approach is that the VG may have quadratic complexity in the worst case, and any approach that computes the whole VG is doomed to quadratic complexity. It would be nice to compute the shortest path from s to t on the fly, without using at least quadratic time and space to compute and store the VG.This was an open problem for a while; the quadratic barier was first broken by Joe Mitchell, and subsequently Hershberger and Suri (1993) described an optimal (n lg n) algorithm called the _continuous Dijkstra_ algorithm.


-------------

n [computational geometry](https://en.wikipedia.org/wiki/Computational_geometry "Computational geometry") and [robot](https://en.wikipedia.org/wiki/Robot "Robot") [motion planning](https://en.wikipedia.org/wiki/Motion_planning "Motion planning"),[1](1)(https://en.wikipedia.org/wiki/Visibility_graph#cite_note-1) a **visibility graph** is a [graph](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics) "Graph (discrete mathematics)") of intervisible locations, typically for a set of points and obstacles in the [Euclidean plane](https://en.wikipedia.org/wiki/Euclidean_plane "Euclidean plane"). Each [node](https://en.wikipedia.org/wiki/Vertex_(graph_theory) "Vertex (graph theory)") in the graph represents a point location, and each [edge](https://en.wikipedia.org/wiki/Graph_theory "Graph theory") represents a [visible connection](https://en.wikipedia.org/wiki/Visible_connection "Visible connection") between them. That is, if the line segment connecting two locations does not pass through any obstacle, an edge is drawn between them in the graph. When the set of locations lies in a line, this can be understood as an ordered series. Visibility graphs have therefore been extended to the realm of [time series](https://en.wikipedia.org/wiki/Time_series "Time series") analysis.

## Applications[[edit](https://en.wikipedia.org/w/index.php?title=Visibility_graph&action=edit&section=1 "Edit section: Applications")]

Visibility graphs may be used to find [Euclidean shortest paths](https://en.wikipedia.org/wiki/Euclidean_shortest_path "Euclidean shortest path") among a set of [polygonal](https://en.wikipedia.org/wiki/Polygon "Polygon") obstacles in the plane: the shortest path between two obstacles follows straight line segments except at the [vertices](https://en.wikipedia.org/wiki/Vertex_(geometry) "Vertex (geometry)") of the obstacles, where it may turn, so the Euclidean shortest path is the shortest path in a visibility graph that has as its nodes the start and destination points and the [vertices](https://en.wikipedia.org/wiki/Vertex_(geometry) "Vertex (geometry)") of the obstacles.[2](2)(https://en.wikipedia.org/wiki/Visibility_graph#cite_note-robot-2) Therefore, the Euclidean shortest path problem may be decomposed into two simpler subproblems: constructing the visibility graph, and applying a shortest path algorithm such as [Dijkstra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm "Dijkstra's algorithm") to the graph. For planning the motion of a robot that has non-negligible size compared to the obstacles, a similar approach may be used after expanding the obstacles to compensate for the size of the robot.[2](2)(https://en.wikipedia.org/wiki/Visibility_graph#cite_note-robot-2) [](https://en.wikipedia.org/wiki/Visibility_graph#CITEREFLozano-PérezWesley1979) attribute the visibility graph method for Euclidean shortest paths to research in 1969 by [Nils Nilsson](https://en.wikipedia.org/wiki/Nils_Nilsson_(researcher) "Nils Nilsson (researcher)") on motion planning for [Shakey the robot](https://en.wikipedia.org/wiki/Shakey_the_robot "Shakey the robot"), and also cite a 1973 description of this method by Russian mathematicians M. B. Ignat'yev, F. M. Kulakov, and A. M. Pokrovskiy.

Visibility graphs may also be used to calculate the placement of [radio antennas](https://en.wikipedia.org/wiki/Antenna_(radio) "Antenna (radio)"), or as a tool used within [architecture](https://en.wikipedia.org/wiki/Architecture "Architecture") and [urban planning](https://en.wikipedia.org/wiki/Urban_planning "Urban planning") through [visibility graph analysis](https://en.wikipedia.org/wiki/Visibility_graph_analysis "Visibility graph analysis").

The visibility graph of a set of locations that lie in a line can be interpreted as a graph-theoretical representation of a time series.[3](3)(https://en.wikipedia.org/wiki/Visibility_graph#cite_note-3) This particular case builds a bridge between [time series](https://en.wikipedia.org/wiki/Time_series "Time series"), [dynamical systems](https://en.wikipedia.org/wiki/Dynamical_systems "Dynamical systems") and [graph theory](https://en.wikipedia.org/wiki/Graph_theory "Graph theory").

