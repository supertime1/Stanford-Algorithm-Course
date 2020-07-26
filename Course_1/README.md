# Divide and Conquer, Sorting and Searching. and Randomized Algorithms
## Summary
### What problems are solved?
  Sorting, Searching i th statistics
### What methodology?
  Divide and Conquer: divide to subrountine problems and combine those smaller problems to solve the bigger one
  Master Method: method to calculate the Big-O for Divide and Conquer + Recursieve problems
  Randomized Algorithm: use linear expection property to turn a complex expectation of random variables into a sum of simple expectation of random variables


***Summarize the notes with algorithm description and Big-O analysis

## Week 1
### Introduction  
  - Recursive Algorithm
  - Karatsuba Multiplication
  - Merge Sort: 
    - use recursive tree to analysis NOP
    - the upper bound turns out to be: 6n x log2(n+1)
  - Guiding Principles
    - Worst case analysis, as opposed to average-case analysis and benchmarks
    - Won't pay much attention to constant factors, lower-order terms
      - way easier
      - constants depend on architecture/complier/programmer anyways
      - lose very little predictive power
    - Asymptotic analysis
      - focus on running time for large input size n 
### Asymptotic analysis
  - High-level idea: suppress constant factors and lower-order terms
  - Big-O, Big-Omega, Big-Theta definition

## Week 2
### Divid & Conquer Algorithms
  - O(n log n) Algorithm for Counting Inversions
    - Input: array A containing the numbers 1,2,3,...,n in some arbitrary order
    - Output: number of inversions = number of pairs (i,j) of array indices with i<j and A[i] > A[j]
    - Motivation: numerical similarity measure between two ranked lists: e.g. for collabroative filtering
    - O(n log n) steps: array A can be divided into subarray that all can be handled by *Merge_and_CountSplitInv*, where two sorted subarrays are merged (O(n)) while counting the total number of split inversions (O(n)). There will be log(n) layers, so total O(n log n).
    
  - O(n^2.81) Strassen's Subcubic Matrix Multiplication Algorithm
    - Input: two matrices
    - Output: dot product of two matrices
    - Motivation: reduce run time from brute force O(n^3) to O(n^2.81)
    - O(n^2.81) steps: 
      - recursively compute only 7 products; 
      - do necessary additions + subtractions
      
  - O(n log n) Algorithm for Closest Pair
    - Input: a set P = {p1,...,pn} of n points in the plan R^2
    - Output: a pair p*, q* belongs to P of distinct points that minimize Euclidean distance d(p,q) over p,q in the set P
    - Motivation: find similarities of two points in a space
    - O(n log n) steps: 
      - Make copies of points sorted by x-coordinate (Px) and by y-coordinate (Py) (O(n log n))
      - Divide P recursively into subgroups that all can be handled by ClosestSplitPair function
      - ClosestSplitPair is O(n) times
  
  ### Master Method
  - Base case: T(n) <= a constant for all sufficiently small n
  - For all larger n:
    T(n) <= aT(n/b) + O(n^d)
    where a = number of recursive calls, b = input size shrinkage factor, d = exponent in running time of "combine step"
    
       ![Notebook](https://github.com/supertime1/Stanford-Algorithm-Course/blob/master/Images/Master%20Method.png?raw=true)
  
   where a can be interpretated as "rate of subproblem proliferation (RSP)", and b^d can be interpretated as "rate of work shrinkage (RWS)" per subproblem.
   if RSP < RWS, the master method will be most effective in reduction big O.
   

## Week 3 
### Quick Sort Algorithm
  - Probability
  
## Week 4
### Linear Time Selection

### Graph and the Contraction Algorithm
- Minimum cut:
  - applications:
    - identify network bottlenecks/weaknesses
    - community detection in social networks
    - image segmentation
 - Graph representation:
  - Adjacency matrix
  - Adjacency lists
 - Random Contraction Algorithm:
  - while there are more than 2 vertices:
    - pick a remaining edge (u,v) uniformly at random
    - merge/contract u and v into a single vertex
    - remove self-loops
    - return cut represented by final 2 vertices
 - Analysis: with random contraction algorithm  Omiga(n^2 m) -> can be improved to O(n^2) 
