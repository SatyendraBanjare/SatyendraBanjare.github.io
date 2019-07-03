---
layout:     post
comments:   true
title:      GSoC'18 Week 6 & 7 Report
date:       2018-07-2 12:52:29
summary:    A small report on my sixth and seventh week work on luagit2  
categories: gsoc18_report
keywords: gsoc blog report
---

These Two weeks, I fixed few issues with working of the library. I also wrote new bindings to the modules and new tests.
Those few issues included errors in building luagit2, Working with luagit2 objects. At first I freed them but then I realized,
doing so causes values to go null and I did undo a couple features related to that. 

I created bindings for **commit create** method and also tested it. I runs perfectly fine. I created few helper Methods for
Commit, Config , Buf Modules. 

I created Bindings for Object,Tag, Buf modules.

#### Tests


I have really improved on my writing test skills :).

The new tests have been written using [Busted](http://olivinelabs.com/busted/) 
as guided by my mentor Etiene. Using Busted does is surely a much better option. My tests does look more elegant now. 

All the tests are available in the `tests/` folder and are categorized as per their module name.
The `Fixtures/` folder contains two repositories for testing :
- `new_test_repo` 
- `testrepo`

I have implemented basic fixig repo functionality taking reference from libgit2's implementation.
Now the repos get moved to `WORKON_REPO` while testing functions and the folder then gets dynamically removed.
This leaves our proect totally unaltered and tests being run fine.

I also implemented a very basi test runner script `test-all.sh` to run tests.

So far, tests for **Blob** , **Branch** , **Buf** , **Config** , **Commit** , **OID**, **Libgit** & **Tree**
modules have been written.

I am working on them and other modules too.
