---
layout:     post
comments:   true
title:      Pointer Analysis
date:       2019-02-02 11:21:29
summary:    Explainatory blog on Steensgaard and Andersen's pointer analysis
categories: plt
keywords: pointer analysis Steensgaard Andersen theoretical computer science
---

Pointer analysis also called **Points-to analysis**  is a static code analysis technique which refers to analyzing the memory locations pointers or heap references point to and how the transformation happens. A related term called **Alias analysis** is used in compiler theory to analyze the ways to access the memory locations. 

Flow-sensitive pointer analysis computes for each program point what memory locations pointer expressions may refer to. Flow-insensitive pointer analysis computes what memory locations pointer expressions may refer to, at any time in program execution. The Flow-sensitive analysis is too expensive. Generally flow-insensitive pointer analysis is used for complete program analyses.

There are two main algorithms studied namely **Steensgaard's Algorithm** and **Andersen's Algorithm**. 

The basic first idea of each is to map a pointer object to the sets of possible memeory	locations that it may point to. This is called **Referencing** `(A = &B)` and it says that the location `A` points to `B` if "Bound" location set points that `B` may be found is a subset of points that `A` points to. This idea is extended to define **Aliasing** that says two pointers are equal if location points set of one is subset of other. **Dereferencing** says the  location points set of RHS is subset of LHS.

following is a simple example : 

```C
int a = &b;
// loc(b) is a subset of pts(a).
int a = b;
// pts(a) = pts(b).
int a = *b;
// it means pts(*b) is a subset of pts(a).
``` 
Lets says intially we have some initial points-to-set elements, We then build a Directed inclusion Graph. Where each of the nodes are memory locations and edges `(A -> B)` refer to pts(a) is subset of pts(b). For an "Error-less" program, it should compute to a finite transitive closure.

For computing the transitive closure, the key difference to make note of is given two pointers pointing to two location point sets , **Steensgaard's** approach merges the two set to create a new set, the **Andersen's** approach says that one location point set may be subset of other and carries out this "subset of" relation to finally reduce to a transitive closure. 

### References :
- https://www.seas.harvard.edu/courses/cs252/2011sp/slides/Lec06-PointerAnalysis.pdf
- https://www.cs.cmu.edu/~aldrich/courses/15-819O-13sp/resources/pointer.pdf
- https://www.youtube.com/watch?v=erIkdIwypbE

