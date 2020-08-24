  
## Greedy Algorithms, Minimum Spanning Trees, and Dynamic Programming
### 1. Greedy Algorithm
  Iteratively make "myopic" decisions, hope everything works out at the end
#### A Scheduling Application
  Each job has a weight: w and length l, in what order should we sequence the jobs to minimize weigth sum wxC, where C = sum of length l
  solution: schedule w/l by decreasing order
#### Prim's Minimum Spanning Tree Algorithm
  - Connect all vertices in a graph with minimum cost
  - Input: undirected graph, OK if edge costs are negative
  - Output: minimum cost tree T that spans all vertices (i.e. T has no cycles)
  - Prim's algorithm: O（m log(n))
    - Initialize X = {s}
    - T = None
    - While X != V
      - Let e = (u,v) be the cheapest edge of G with u in X, v not in X
      - Add e to T
      - Add v to X
  
  
