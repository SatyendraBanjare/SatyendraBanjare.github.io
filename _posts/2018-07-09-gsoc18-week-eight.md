---
layout:     post
comments:   true
title:      GSoC'18 Week 8 Report
date:       2018-07-09 12:52:29
summary:    A small report on my eighth week work on luagit2  
categories: gsoc18_report
keywords: gsoc blog report
---

This week I completed writing tests for all the modules except blame and clone.
Therefore now tests and lua bindings along with some helper functions of these modules have been covered. 

- Blob
- Branch
- Buf
- Commit
- Config
- Cred
- Index
- libgit2
- Object
- Oid
- Reference
- Repository
- Signature
- Tree
- Tag

**Note : please refer this branch for development till now, the tests and source of all modules [all tests added](
https://github.com/SatyendraBanjare/luagit2/tree/Reference_Module_Tests) .**


I also refactored the source code for libgit module and now it's usage on lua side feels more lua-way. I have therefore 
rewritten tests to match new styling.

