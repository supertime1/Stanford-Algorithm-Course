# Divid and Conquer, Sorting and Searching. and Randomized Algorithms
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
    - O(n log n) steps: array A can be divided into subarray that all can be handled by \*Merge_and_CountSplitInv*\, where two sorted subarrays are merged (O(n)) while counting the total number of split inversions (O(n)). There will be log(n) layers, so total O(n log n).
    
  - O(n^2) Strassen's Subcubic Matrix Multiplication Algorithm
    - Input: two matrices
    - Output: dot product of two matrices
    - Motivation: reduce run time from brute force O(n^3) to O(n^2)
    - O(n^2) steps: 
      1. recursively compute only 7 products; 
      2. do necessary additions + subtractions
