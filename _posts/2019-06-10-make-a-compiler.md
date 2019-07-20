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

**[NOTE]** I expect the readers to be familiar atleast in theory about compilers, lexing and parsing. 

For learning about tools used, I will request to go through these links beforehand

#### References :

-	http://aquamentus.com/tut_lexyacc.html
-	http://dinosaur.compilertools.net/flex/flex_11.html
-	https://www.univ-orleans.fr/lifo/Members/Mirian.Halfeld/Cours/TLComp/l3-0708-LexA.pdf
-	https://www.ibm.com/support/knowledgecenter/en/ssw_aix_72/com.ibm.aix.genprogc/yaac_file_declarations.htm
-	https://gist.github.com/serge-sans-paille/aa332fa22692fcdfdc51

The most important thing to figure before creating a compiler is to figure out the language for which the compiler will be created. 

In this post we will develop a compiler frontend for an imperative language like **C**. We will be creating a multipass compiler front end that will support features like

-	Loop handling
-	Contextual Semantics
-	Input/Output (only in the form of print)
-	Conditional Statements
-	Binary operations
-	Commenting (both inline and paragrah wise)
-	JIT compilation

Our compiler frontend will output LLVM IR which can be further analyzed and optimzed using LLVM.

Let's start with creating the syntactic sugar for our language.

<script src="https://gist.github.com/SatyendraBanjare/a9f12d927be4c3fc0537a41ea2573b4d.js"></script>




