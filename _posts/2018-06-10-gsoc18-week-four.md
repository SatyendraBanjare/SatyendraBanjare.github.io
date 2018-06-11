---
layout:     post
comments:   true
title:      GSoC'18 Week 4 Report
date:       2018-06-10 12:52:29
summary:    A small report on my fourth week work on luagit2  
categories: gsoc18_report
---

Google Summer of Code 2018's Fourth coding week comes to end and first
evaluations start off this weekend.

This report of mine consists of my this week work on
 [luagit2](https://github.com/satyendrabanjare/luagit2) as well as
the major checkpoints accomplished in this one month long code out.

### Week four :
- This week I wrote bindings for **Repository** , **Reference** ,
 **Branch** , **Blob** , **Blame** , **Index** modules' functions.
- Got my previous [Pull request](https://github.com/SatyendraBanjare/luagit2/pull/1) on adding more tests reviewed. I am now working on changes suggested.

## Major Checkpoints reached :

### Covered modules
- Blame
- Blob
- Branch
- Clone
- Commit
- Config
- Cred
- Index
- libgit2
- Oid
- Reference
- Repository
- Signature
- Tree

Though Every function originally presently in the libgit2 in these module does not have a binding created  but I tried to cover most of the functions from the respectively modules. I am working on increasing number of functions and making helper methods for easy usage of the library.

### Test written
I have wrote initial tests for the following modules :
- Cred
- Config
- Commit
- Tree
- Signature
- Oid

It can be found in this pull request [Pull request](https://github.com/SatyendraBanjare/luagit2/pull/1).
I have not included these tests in my master branch yet. I am working changes suggested.

- An empty read the docs Documentation generated live at : http://luagit2.readthedocs.io/ .
