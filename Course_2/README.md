# Graph Search, Shortest Paths, and Data Structures
## Graph search and connectivity
- Motivations: 
  - check if a network is connected
  - driving direction
  - formulate a plan 
  - compute the "pieces" (or "components") of a graph: clustering, structure of the web graph, etc
  
- Breath-First Search (BFS)
  #### a. Algoirthm O(m+n):
  - mark S as explored
  - let Q = queue data structure (FIFO), initialized with S
  - while Q != empty
    - remove the first node of Q, call it v
    - for each edge (v,m):
     - if w unexplored
      - mark w as explored
      - add w to Q (at the end)
   #### b. Applications:
   - Shortest Path: book-keeping the dist(v) =i (i.e. v in i th layer)
   - Undirected Connectivity (e.g. check if network is disconnected, graph visualization, clustering)
   
- Depth-First Search (DFS)
  #### a. Algorithm O(m+n)
 - similar to BFS code, use a stack instead of a queue
 
  #### b. Applications
 - compute a topological ordering of a directed acyclic graph: DFS O(m+n)
 - compute the strongly connected components of directed graphs: Kosaraju's two-pass algorithm O(m+n):

(Continue here)
## Dijkstra's shortest-path algorithm 
  - can be used to compute le > 1, whereas BFS only compute shortest path when each edge counts 1

## HEAPS

## Balanced binary search trees

## Universal hashing

## Bloom filters
