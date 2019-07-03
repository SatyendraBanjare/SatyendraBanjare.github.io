---
layout:     post
comments:   true
title:      GSoC'18 Week 1 Report
date:       2018-05-20 12:52:29
summary:    A small report on my first week work on luagit2  
categories: gsoc18_report
keywords: gsoc blog report
---

The first week was Awesome. I got to know the details of the libgit2 project. I tried and tested many libgit functions and understood their implementation.

As decided in my Proposal, I wrote bindings for the functions of **libgit2** , **Cred** and **Config** module. Though the coding period started on May 
14th, I initialized my project with almost everything I thought was necessary in the period 11th to 13th May. The Project now has *CMakeLists.txt* for 
easily building the shared object **luagit2.so** . The project also contains an empty _readthedocs_ documentation initialized and serving live at http://luagit2.readthedocs.io/ . I will add the complete usage example and documentation as I make progress. 

The project is structured as: 
- The `/src/luaC-api/` contains the lua C api files I am using for building my project.
- The `/src/header_files/` contains the files for all the bindings the I write.  
- The `/src/main_wrapper.c` is the main file responsible for registering the created binding functions while creating luagit2 shared object.

Current method to build the project :
- Go to `/src/` folder and use _cmake_ to build the shared object and run the functions.

Brief insight to functions I wrote bindings for :
- **lua_libgit2.h** : This module contains all the funcitons that can be used to make global settings for the libgit2. I created different functions 
according to those available in the options of `git_libgit2_opts` so that there is ease in using those. 
- **lua_cred.h** : Basically I created a _luagit2_cred_object_ struct and corresponding functions to make a `lua variable` to contain a `git_cred` object. 
The functions help in initializing your luagit_cred_object using libgit methods. A small pseudo-code example would be like :
``` lua
lib = require "luagit2"
lib.luagit_init()
my_cred_obj = lib.luagit2_cred_default_new()
my_other_cred_obj = lib.luagit2_cred_userpass_plaintext_new()
```
and so on.
- **lua_config.h** : I created a _luagit2_config_object_ and _luagit2_buf_object_ struct similar to those in `lua_cred` module. Thus user can initialize
lua variable with luagit2_config and lua_buf objects. The libgit2_cred's original Set and Get functions are also implemented to manipulate the values of a 
already present config file. Most of the set tye functions can be used by passing the lua type config object as in pseudo-code :
``` lua
lib = require "luagit2"
lib.luagit_init()
lua_config_obj = lib.lua_git_config_open_global()
lib.lua_git_config_set_bool(lua_config_obj,"Name_whose_value_is_to_be_set",1) -- 1 here is an integer parameter 
```

Though these are small examples, I will write complete Documentation in coming weeks.  