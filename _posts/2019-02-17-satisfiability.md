---
layout:     post
comments:   true
title:      SAT
date:       2019-02-17 11:21:29
summary:    Solving a SAT problem
categories: plt
---

SAT or Satisfiability type problem is the problem of determining if there exists a solution to a boolean formula. It checks if a combination of true/False values exist that evaluated the given boolean expression to true.

The representation of a boolean formula is expressed in Conjuctive Normal Form.

The problem's complexity can be broadly classifed as Unrestricted and restricted or SAT-3. The key difference being that the element may be present any number of time in a conjuctive clause in Unrestricted form and exactly once in a restricted form.

### Significance

It was the first problem that was proved to be **NP-complete**. Till date there exists no known algorithm that solves every given SAT problem in a polynominal problem.

The wide areas of SAT solving are artificial intelligence, circuit design and Automatic theorem proving.

Recently [Urmila Mahadev](https://simons.berkeley.edu/people/urmila-mahadev) theoretically formalized the long standing question of Quantum computation, How to know whether anything Quantum has happened ?. In her method she has reduced the complex problem to SAT-3 instance problems.

### Algorithms

The most common algorithm is called **DPLL algorithm** that works as a conflict-driven learning algorithm. The other popular but randomized algorithm is called **PPSZ aLgorithm**.

- **DPLL Algorithm** 
	+ It involves performing a DFS through space of possible assignments for conjuctive sets and stops if statifiability is found or all options have been tested.
	+ Optimizations can be performed by skipping the branches where no satisfying assignments occur and looking for the maximum 'search space' .
	+ Conflict analysis is done and those clauses that are not rooted are removed or are not searched. 

### Formalization

There has been quite a few Coq formalization done that can be looked up. Here I am sharing onw done by Prof. Adam Chlipala as a part of his course Interactive Theorem Proving [link](https://github.com/SatyendraBanjare/itp/blob/master/SAT_SOLVER.v).

Over the years Proof-assistant based SMT-SAT solvers have been researched upon. example : [Z3 Theorem prover](https://github.com/Z3Prover/z3) , [SMT coq](https://smtcoq.github.io/).

