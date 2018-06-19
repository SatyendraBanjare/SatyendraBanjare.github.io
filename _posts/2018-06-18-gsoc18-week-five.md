---
layout:     post
comments:   true
title:      GSoC'18 Week 5 Report
date:       2018-06-18 12:52:29
summary:    A small report on my fifth week work on luagit2  
categories: gsoc18_report
---

Fifth week for me was all about improving luagit2's existing code structure to be more standardized.

This week I solved the issue and luagit2 now installs perfectly (Thanks to luarocks). 

I separated all the definitions and declarations for the binding functions I wrote. I also added error
check functions on all possible binding functions using  `giterr_last()`.

I also addded some object freeing binding functions and also freed the locally used git objects 
involved in writing bindings.

