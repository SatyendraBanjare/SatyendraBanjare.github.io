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




