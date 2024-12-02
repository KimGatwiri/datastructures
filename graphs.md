# Graph Theory: Directed vs. Undirected Graphs and Weighted vs. Unweighted Graphs

Graphs are fundamental data structures in computer science, used to model relationships between entities. Here, we discuss the differences between **Directed** and **Undirected Graphs** as well as **Weighted** and **Unweighted Graphs**.

---

## Directed Graphs (Digraphs)
A **directed graph** is a graph where edges have a direction, indicating the relationship flows in one way. Each edge is represented as an ordered pair \( (u, v) \), meaning the edge starts at vertex \( u \) and ends at vertex \( v \).

### Characteristics:
- **Asymmetric Relationships**: Captures relationships like "follows" on social media or "prerequisite" in course requirements.
- **Graph Representation**:
  - **Adjacency List**:
    ```text
    A -> B, C
    B -> D
    C -> D
    ```
  - **Adjacency Matrix**:
    ```
      A  B  C  D
    A  0  1  1  0
    B  0  0  0  1
    C  0  0  0  1
    D  0  0  0  0
    ```

---

## Undirected Graphs
An **undirected graph** is a graph where edges do not have a direction, representing a two-way or symmetric relationship. Each edge is represented as an unordered pair \( \{u, v\} \).

### Characteristics:
- **Symmetric Relationships**: Captures relationships like "friendship" or "collaboration."
- **Graph Representation**:
  - **Adjacency List**:
    ```text
    A: B, C
    B: A, D
    C: A, D
    D: B, C
    ```
  - **Adjacency Matrix**:
    ```
      A  B  C  D
    A  0  1  1  0
    B  1  0  0  1
    C  1  0  0  1
    D  0  1  1  0
    ```

---

## Weighted Graphs
A **weighted graph** assigns a numerical value (weight) to each edge, which might represent distance, cost, time, or capacity.

### Example:
- **Weighted Directed Graph**:
    ```
    A -> B (weight = 4)
    A -> C (weight = 2)
    B -> D (weight = 3)
    C -> D (weight = 1)
    ```
- **Weighted Undirected Graph**:
    ```
    A -- B (weight = 5)
    B -- C (weight = 3)
    C -- D (weight = 2)
    ```

### Use Cases:
- Shortest path algorithms (e.g., Dijkstra's, Bellman-Ford).
- Minimum spanning tree (e.g., Kruskal's, Prim's).

---

## Unweighted Graphs
An **unweighted graph** assumes all edges have the same weight (or no weight). This simplifies algorithms as only connectivity matters.

### Example:
- **Unweighted Directed Graph**:
    ```
    A -> B
    A -> C
    B -> D
    ```
- **Unweighted Undirected Graph**:
    ```
    A -- B
    A -- C
    B -- D
    ```

### Use Cases:
- Breadth-First Search (BFS) to find the shortest path (in terms of hops).
- Depth-First Search (DFS) for connectivity analysis.

---

## Summary Table

| Feature               | Directed Graph   | Undirected Graph | Weighted Graph   | Unweighted Graph |
|-----------------------|------------------|------------------|------------------|------------------|
| **Edge Direction**    | One-way          | Two-way          | Can be either    | Can be either    |
| **Weights on Edges**  | Optional         | Optional         | Required         | Not present      |
| **Applications**      | Social Media, Web Links | Friendship Networks | Routing, Optimization | Connectivity Analysis |

---

Graphs are versatile tools for solving real-world problems. Understanding their types helps in selecting the right algorithms and representations for various applications.
