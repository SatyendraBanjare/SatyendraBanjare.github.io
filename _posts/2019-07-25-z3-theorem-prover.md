---
layout:     post
comments:   true
title:      Z3 theorem prover
date:       2019-07-25 11:21:29
summary:    Exploring Z3 theorem prover.
categories: plt
keywords: Z3 theorem prover tutorial
---

**[Z3](https://github.com/Z3Prover/z3)** is one of the latest SMT solver by Microsoft Research. I came to know about the Z3 theorem prover few months back and was super excited to learn about this tool. It is impressively powerful and capable of solving theories built upon arithmetic, fixed-size bit-vectors, extensional arrays, datatypes, uninterpreted functions, and quantifiers. It has API available in **Java** , **Ocaml** & **Python** . It's python api is easy to use. 

In this post I will be discussing an example tutorial on modelling a famous variation of [Rivercrossing Puzzle](https://en.wikipedia.org/wiki/River_crossing_puzzle) called as [Jealous Husband's Problem](https://en.wikipedia.org/wiki/Missionaries_and_cannibals_problem).

The puzzle goes like this :
<div style="border: thin black;border-style: dashed;padding: 5px;">
	<p>There are 3 couples that wish to cross a river using a boat that needs atleast 1 person to drive it and it can carry atmost 2 person in it. It also has the constraint that no woman can be in the presence of another man unless her husband is also present. </p>
	<p>We need to find the minimum steps required to finish the challenge.</p>
</div>

Let's now model this puzzle in a logic system :
### Assertions : 
-	The time increments in step size.
-	The position of any person is either left or right in a given step.
-	The changed position refers to transition from one side to other. 
-	There are 3 couples. Let the set of people be **S**.

### Logical statements.
<div style="overflow-x:auto;" >
	<ol>
		<li> The Boat should move that is, its position at next time should be different than previous one.
		</li>
		<li>If Position of a man is not equal to his wife (they are both not on same side) , then position of that wife should also be not equal to position of other men. </li>
		<li> The Boat can carry at most 2 person and it should carry at least 1 person.</li>
	</ol>
</div>

### Mathematical representation
Following the logical statements described above, here are the mathematical representation statements respectively.

<p>Statement 1.</p>

\\( (time < timeMax) \wedge (pos(boat,t) \ne pos(boat,t+1))  \\) 

<p>Statement 2.</p>
\\( (time < timeMax) \wedge  \\) (

\\( ( pos(man1,t) \ne pos(wife1,t) ) \rightarrow ( pos(wife1,t) \ne pos(man2,t)) \vee ( pos(wife1,t) \ne pos(man3,t))   \\)

\\( ( pos(man2,t) \ne pos(wife2,t) ) \rightarrow ( pos(wife2,t) \ne pos(man1,t)) \vee ( pos(wife2,t) \ne pos(man3,t))   \\)

\\( ( pos(man3,t) \ne pos(wife3,t) ) \rightarrow ( pos(wife3,t) \ne pos(man1,t)) \vee ( pos(wife3,t) \ne pos(man2,t))   \\)


)
<p>Statement 3.</p>

\\[ \forall (A,B,C) \subset S \mid \\]

\\[ \exists a \in A    \mid  \\]  {

\\[ (  pos(a,t) = pos(boat,t)) \wedge (pos(a,t+1) = pos(boat,t+1) ) \\]
there should be atleast one position change with boat.
\\[ \wedge \\]

\\[(\exists b \in B  \mid (b \ne a ) \wedge  (pos(b,t+1) = pos(boat,t+1)) ) \\]
there maybe another position change of element other than previous one.
\\[ \wedge  \\]
\\[ (\exists c \in C \mid (c \ne a \wedge c \ne b ) \wedge  (pos(c,t+1) = pos(c,t)) ) \\]
element may remain on the same side.
}
## References
<div style="overflow-x:auto;" >
	<ul>
		<li>https://rise4fun.com/Z3/</li>
		<li>http://theory.stanford.edu/~nikolaj/programmingz3.html</li>
		<li>https://yurichev.com/writings/SAT_SMT_by_example.pdf</li>
	</ul>
</div>

