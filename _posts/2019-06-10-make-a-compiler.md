---
layout:     post
comments:   true
title:      Make C compiler using LLVM
date:       2019-06-10 11:21:29
summary:    A simple tutorial on making a C compiler using LLVM backend.
categories: plt
keywords: llvm basics llvm c compiler tutorial
---

Anyone starting with compilers and jumping directly to learn developing tools using **LLVM** or maybe just wanting to get to understand it's working must have felt that their documentation is quite tough to hack into directly. I am writing this post to help understand developing a compiler frontend using LLVM backend.

The most important thing to figure before creating a compiler is to figure out the language for which the compiler will be created. 

In this post we will develop a compiler frontend for an imperative language like **C**. We will be creating a multipass compiler front end that will support features like

-	Loop handling
-	Contextual Semantics
-	Input/Output (only in the form of print)
-	Conditional Statements
-	Binary operations
-	Commenting (both inline and paragrah wise)
-	JIT compilation

The project is available here  https://github.com/SatyendraBanjare/C-LLVM-compiler .

Our compiler frontend will output LLVM IR which can be further analyzed and optimzed using LLVM.

**[NOTE]** I expect the readers to be familiar atleast in theory about compilers, lexing and parsing. 

For learning about tools used, I will request to go through these links beforehand

#### References :
<div style="overflow-x:auto;" >
	<ul>
	<li>http://aquamentus.com/tut_lexyacc.html</li>
	<li>http://dinosaur.compilertools.net/flex/flex_11.html</li>
	<li>https://www.univ-orleans.fr/lifo/Members/Mirian.Halfeld/Cours/TLComp/l3-0708-LexA.pdf</li>
	<li>https://www.ibm.com/support/knowledgecenter/en/ssw_aix_72/com.ibm.aix.genprogc/yaac_file_declarations.htm</li>
	<li>https://gist.github.com/serge-sans-paille/aa332fa22692fcdfdc51</li>
</ul>
</div>


### CodeOut

Let's begin with creating the lexical rules. Referring to above mentioned links, this is how final lexer file should look like. Most of this is self explainatory. Some tricks are used to implement **Comments**. How this works is explained in  http://aquamentus.com/tut_lexyacc.html . We make the state go to comment / comment_oneline state and do nothing till the comment section is not over.

<script src="https://gist.github.com/SatyendraBanjare/a06fc3b844e5d4f50e9166b3f25cef86.js"></script>

At this point We have developed the Vocabulary of our language. Let us now develop the reasoning and grammar.


<script src="https://gist.github.com/SatyendraBanjare/e2b3fc6942116b31f696726c7b6e1be9.js"></script>
This is first part where we have described the various token values, type values and associativity rules. We have created a union of later described block expression. Finally we have created a map for variable name and its value. 

<script src="https://gist.github.com/SatyendraBanjare/b9838fbc9f7ad03178531aecdca37110.js"></script>
This is the second part where we describe all the expressions. We have created blocks that will be used while writing algorithms of implementation. 

<script src="https://gist.github.com/SatyendraBanjare/d3c9f49c2d6d63fd7d9120df0aa6119a.js"></script>
Here are some extra important methods that help in checking the code. Variable's type is checked in here too.

Here is the complete file.
https://gist.github.com/SatyendraBanjare/a9f12d927be4c3fc0537a41ea2573b4d

Now that we have developed our grammar, lets us implement it.

1. We will create a wrapper header for the methods implemented.
<script src="https://gist.github.com/SatyendraBanjare/d048a910c08fb5228c478fb18b9b932e.js"></script>

2. Define the functions to be used.
<script src="https://gist.github.com/SatyendraBanjare/d939ff608a20968bd39ed6b87691a840.js"></script>

3. And the final wrapper.
<script src="https://gist.github.com/SatyendraBanjare/745b1472e3bc981721a8528a1666ea06.js"></script>

### Compile & Run
This is how the Makefile is written. Basically is a series of operations of lexical analysis, parsing and final code generation.

To build , simply do `make`.
<script src="https://gist.github.com/SatyendraBanjare/4a386d92a77b0034a28da1387448f885.js"></script>

### Testing
To test that our compiler works, just do
```
./compiler test.c
```





