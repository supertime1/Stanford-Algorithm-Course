# Divide and Conquer, Sorting and Searching. and Randomized Algorithms
## 1. Algorithms based on Methodology
  ### Divide and Conquer 
  #### Paradigm
  - DIVIDE into smaller subproblems
  - CONQUER subproblems recursively
  - COMBINE solutions of subproblems into one for the original problem
  - Examples: MergeSort, Integer Multiplication, Strassen's Matrix Multiplication, Counting Inversions, Closest Pair
  
  #### Master Method
  - Motivation: mathematical analysis to evalute Divide and Conquer Algorithm
  - Assumption: all subproblems are equal size
  - Base case: T(n) <= a constant for all sufficiently small n
  - For all larger n:
    T(n) <= aT(n/b) + O(n^d)
    where a = number of recursive calls, b = input size shrinkage factor, d = exponent in running time of "combine step"

       ![Notebook](https://github.com/supertime1/Stanford-Algorithm-Course/blob/master/Images/Master%20Method.png?raw=true)

   where a can be interpretated as "rate of subproblem proliferation (RSP)", and b^d can be interpretated as "rate of work shrinkage (RWS)" per subproblem.
   if RSP < RWS, the master method will be most effective in reduction big O.

  ### Randomized Algorithm: 
  - Introduce a random process into algorithm
  - when a randomized algorithm is used, it is necessary to compute the "chance of success" to detemine the Big-O; this process is often done by using linear expection property to turn a complex expectation of random variables into a sum of simple expectation of random variables
  - Examples: QuickSort, Linear Time Selection, Graph and Contraction Algorithm 
  
## 2. Algorithms based on Applications
  ### Sorting (Divide and Conquer, Randomized)
  - MergeSort: O(n log n) (Divide and Conquer)
    - recursively sort 1st half of the input array
    - recursively sort 2nd half of the input array
    - merge two sorted sublists into one
    
  - QuickSort: O(n log n) on average (Randomized)
    - p = ChoosePivot(array A, length n)
    - partition A around p
    - recursively sort 1st part
    - recursively sort 2nd part
    
  ### Searching (Randomized)
  - O(n) on average: Linear time selection of i th statistics
  - p = ChoosePivot(array A, length n)
  - partition A around p, let j = new index of p
  - if j=i, return p
  - if j>i, return Rselect(1st part of A, j-1, i)
  - if j<i, return Rselect(2nd part of A, n-j, i-j)
  
  ### Graph minimum cut (Randomized)
  - Motivations:
    - identify network bottlenecks/weaknesses
    - community detection in social networks
    - image segmentation
  - Random Contraction Algorithm:
        - while there are more than 2 vertices:
          - pick a remaining edge (u,v) uniformly at random
          - merge/contract u and v into a single vertex
          - remove self-loops
          - return cut represented by final 2 vertices
   - Analysis: with random contraction algorithm  Omiga(n^2 m) -> can be improved to O(n^2) 
   - The number of minimum cuts: the largest number of min cuts that a graph with n vertices can have = n(n-1)/2
   
  ### Counting Inversions (Divide and Conquer)
  - O(n log n)
  - Motivation: numerical similarity measure between two ranked lists: e.g. for collabroative filtering
  - Input: array A containing the numbers 1,2,3,...,n in some arbitrary order
  - Output: number of inversions = number of pairs (i,j) of array indices with i<j and A[i] > A[j]
  - Algoritm:
    - recursively sort-and-count 1st half of the input array
    - recursively sort-and-count 2nd half of the input array
    - Merge_and_CountSplitInv: while merging the two sorted subarrays, keep running total of number of split inversions
  
  ### Find closest pair (Divide and Conquer)
  - O(n log n)
  - Motivation: find similarities of two points in a space
  - Input: a set P = {p1,...,pn} of n points in the plan R^2
  - Output: a pair p*, q* belongs to P of distinct points that minimize Euclidean distance d(p,q) over p,q in the set P
  - O(n log n) steps: 
    - Make copies of points sorted by x-coordinate (Px) and by y-coordinate (Py) (O(n log n))
    - Divide P recursively into subgroups that all can be handled by ClosestSplitPair function
    
  ### Strassen's Subcubic Matrix Multiplication Algorithm (Divide and Conquer)
  - O(n^2.81) 
  - Motivation: reduce run time from brute force O(n^3) to O(n^2.81)
  - Input: two matrices
  - Output: dot product of two matrices
  - O(n^2.81) steps: 
    - recursively compute only 7 products; 
    - do necessary additions + subtractions

## 3. Data Structure
  ### Graph
  - Vertex (node) and Edge
  - Graph representation:
    - Adjacency matrix
    - Adjacency lists
 
