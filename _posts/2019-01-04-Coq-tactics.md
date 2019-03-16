---
layout:     post
comments:   true
title:      Coq Tactics
date:       2019-01-02 11:21:29
summary:    Some common and useful Coq Tactics
categories: plt
---

These are a set of Coq tactics that I've learned while completing the various courses and solving the software foundation book.

- **intros** : This is the first tactic that is used to introduce the working variables the in the current environement. 

- **simpl** : This simplifies the current expression, breaks down the complex defitions to simplest terms

- **unfold** : This unfolds a definition previously defined for the current state in the the current expression term.

- **rewrite** : Rewrites the expression using a previous definition or a hypotheses.

- **inversion** : Reproduces the hypotheses's forming condition and hence helping to solve the current expression state.

- **assumption** : Solves the program state using a hypothesis or a definition available in that programming environment.

- **reflexivity** : Uses mathematical reflexivity property to show equality

- **auto** : Solves some easy proofs.

- **exact** : Solves a goal the exact proof term that proves the goal is known. 

- **contradiction** : Solves any goal if the context contains False or contradictory hypotheses in current proof environment.

- **left/right** : replaces the goal of disjunction with either one. 

- **split** : produces 2 subgoals of a conjuction term.

- **destruct** : Generates a subgoal for every constructor of an inductive type.

- **induction** : It generates a subgoal for every constructor of an inductive type and provides an induction hypothesis for recursively defined constructors.

Lastly, you can define your own tactic using the **Ltac** .