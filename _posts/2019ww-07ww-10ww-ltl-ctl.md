---
layout:     post
comments:   true
title:      Understanding  Linear Temporal Logic in COQ
date:       2019-07-10 11:21:29
summary:    A simple blog on proving properties of Linear temporal logics in coq proof assistant.
categories: plt
keywords: ltl coq tutorial 
---

**L**inear **T**emporal **L**ogic is a logic system that defines the behaviour of `Stream of States` using conditional statements that are represented as a mathematical reduction formulae. The future states can be encoded using present states, combining logic operators and rules of existence.

These rules are **N**ext, **G**lobally, **F**uture (Eventually), **R**elease , **U**ntil, **W**eakUntil , **M** (Strong Release).

The basic semantics , semantics and basic properties are discussed on [wikipedia page](https://en.wikipedia.org/wiki/Linear_temporal_logic). 

To begin with lets define the behaviour of the Stream :

<script src="https://gist.github.com/SatyendraBanjare/373360e4eea1e2220dcffc32d0009cf4.js"></script>

We have assumed a list of variable states and defined some common properties and operations on list. 

Next let us define the operators - bool as well as temporal.

<script src="https://gist.github.com/SatyendraBanjare/ff02e7ce6f4f6e50153063060bf871b2.js"></script>

Next we will try to prove the properties of these operators working in conjuction.



In this post I have tried to explore coq formalization of the LTL. 

I created a very basic version of LTL implementation in coq [here](https://github.com/SatyendraBanjare/Formalized-LTL). The more advanced formalization I found and referred are
-	https://github.com/foreverbell/verified/tree/master/ltl
-	https://github.com/coq-contribs/ltl

I highly advice going through them. They will surely give every reader a new inspiration to think about this topic. Finally the superset of LTL called as **CTL** has also been formalized and can be accessed here : https://github.com/coq-contribs/ctltctl .   

