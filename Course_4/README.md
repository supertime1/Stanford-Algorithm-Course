## Shortest Paths Revisited, NP-Complete Problems and What To Do About Them
### Single-Source Shortest Paths REVISITED
#### The Bellman-Ford algorithm
- Compare to Dijkstra's algorithm, can compute negative edge length
- The BF algorithm either compute the length of a shortest s-v path, or, output a negative cycle
- Subproblem: L(i,v) = minimum length of a s-v path with <= i edges
  - for every v in V, i = 1:n,
    - L(i,v) = min{ L(i-1,V) or min{L(i-1,w} + c(w,v)}
- Algorithm: O(mn)
  - Let A = L(i,v)
  - A[0,s] = 0; A[0,v] = +infini for all v!=s
  - For i = 1:n-1
    For each v in V:
    - A(i,v) = min{ A(i-1,V) or min{A(i-1,w} + c(w,v)}
  - return A[n-1, v]
- Run BF for one extra iteration to report whether there is negative cycle
- Optimization: create a predecessor point B[i,v] to cache the 2nd-to-last vertex on a shortest s->v path with <= i edges
    
 ### All-Pairs Shortest Paths
 - Floyd-Warshall algorithm: O(n^3) for APSP
 
 ### NP complete problems
 
 
