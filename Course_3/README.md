  
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
  - Prim's algorithm: by using heaps O（m log(n)), no heap O(mn), where m is # of edges, and n is # of vertices
    - Initialize X = {s}
    - T = None
    - While X != V
      - Let e = (u,v) be the cheapest edge of G with u in X, v not in X
      - Add e to T
      - Add v to X

#### Kruskal's Minimum Spanning Tree Algorithm
  - Same purpose as Prim's algorithm, but use a Union-Find data structure; and Kruskal's algorithm can be used to solve clustering problems
  - Kruskal's Algorithm: by using Union-Find O(m log(n)), if not O(mn)
    - Sort edges in order of increasing cost
    - T = None
    - For i = 1 to m:
      - if T U {i} has no cycles: add i to T (use BFS or DFS O(n), or Union-Find for cycle checks O(1)))
    - Return T

#### Huffman Codes
  - Best binary prefix-free encoding for a given set of character frequencies
  - Intuition: smallest frequency with longest encoding
  - Huffman codes: bottom-up approach with Heap O(n log(n)), no heap O(n^2)
    - Let a,b have the smallest frequencies
    - Combine a,b into one node ab
    - Repeat step 1 and 2 to compute a tree T'
    - Extend T' to T with leaves
   
### 2. Dynamic Programming
  #### Max-weight independent set (WIS)
  - Given a graph with non-negative weights on vertices, find an independent set (non-adjacent vertices) with maximum total weight
  - Algorithm: O(n)
    - Let A = filled-in array with maximum weight values
    - Let S = None
    - While i >= 1
      - if A[i-1] >= A[i-2] + Wi: i-=1
      - else: add vi to S, i-=2
    - return S
  #### The Knapsack Problem
  - n items each has a value v and size w, and a target capacity W, find a best combination that maximize sum of w <= W
  - Algoritm: O(nW)
    - Let A(i,x) = value of the best solution that use only the first i items, and has total size <= x
    - Initialize A[0,x] = 0 for x = 0:W
    - For i = 1:n
      - For x = 0:W
        - if wi > x: A[i,x] = A[i-1,x]
        - A[i,x] = max[A[i-1,x], A[i-1, x-wi] + vi}
    - Return A[n,W]
    
  
  #### Sequence Alignment
  #### Optimal Binary Search Tress
