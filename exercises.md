# My answers
for exercises in the book: [Introduction to Evolutionary Algorithms](file:///E:/Computer%20Science/Research/Genetic%20and%20Evolutionary%20Computation/[Decision%20Engineering%20]%20Xinjie%20Yu,%20Mitsuo%20Gen%20(auth.)%20-%20Introduction%20to%20Evolutionary%20Algorithms%20(2010,%20Springer)%20[10.1007_978-1-84996-129-5]%20-%20libgen.li.pdf)

## Chapter 2
### 2.1
Implement SGA from scratch: [Jobshop SGA implementation](SGA_jobshop.cpp).

Problem statement (classical job-shop scheduling):
- Given $n$ jobs, $m$ machines. Each jobs has exactly $m$ parts that must be completed in order. 
- The $j$-th part of the $i$-th job can only be processed by the machine with id $a_{ij}$ (in $t_{ij}$ unit of time).
- At a time, a machine can only process at most one job (part). Once started, it must finish the task at hand before receiving new one. 

What I did in there?
- Solution representation: Permutation of the multiset $\bigcup_{0 < i < n} \{ i\} \times {m}$, with the meaning: in which order should the jobs' parts be processed? Given the order, one can easily reconstruct the time in which job parts are processed (ie. calculating the objective value).
- Cross-over: Single-point crossover, similar to normal permutation crossing. Take the prefix of one parent, apply the suffix of the other whenever applicable, then fill in the "blank"s.
- Mutation: Simply swap 2 random genes
- $\texttt{pop\_size = 200, p\_c = 0.95, p\_m = 0.05}$. 

### 2.2
"In RWS, is the selection with replacement or without replacement?"

The question is quite confusing to me, because as I understand, RWS is for selecting the "best fit" individuals into mating pool.

The SGA presented in the chapter is, **selection without replacement**

### 2.3
1. Define the crossover rate $p_c$ and the mutation rate $p_m$:
To control and balance the behavior of the algorithm, enable searching capabilities.
2. What will happen if $p_m = p_c = 1$ in an SGA? If $p_m = 1$, all offspring's genes are inverted, thus not able to preserve parents' traits.

### 2.4
