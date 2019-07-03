---
layout:     post
comments:   true
title:      GSoC'18 Week 11 Report
date:       2018-7-31 12:52:29
summary:    A small report on my eleventh week work on luagit2  
categories: gsoc18_report
keywords: gsoc blog report
---
_Time flies by...!!_  :wink: :wink: :sweat_smile:

All the summer is now over, monsoon has arrived :smiley: and my college has started :disappointed: and
I have reached the final week of my GSoC-2018 work period.

The last week, I completed pendging modules' tests, I got most of my pull requests merged and I started working on 
writing tests and documentation.
Two basic example scripts of adding files to index and cloning can be viewed on the project repository.

The lua bindings bindings for a total of 32 modules has been written and of which 28 modules have their tests 
completed. :wink:

These modules are merged to the master as of now, few are remaining to be added.

**libgit2,
cred,
config,
oid,
signature,
clone,
repository,
tree,
commit,
index,
reference,
branch,
blame,
blob,
tag,
object,
buf,
revwalk,
annotated,
checkout,
reset,
describe,
reflog,
revert,
revparse,
diff**

As an example script to add files to current index,

```lua
------------------------------------------------------------------------------
--
-- luagit2's "add" example
-- ( equivalent to git add <file> )
--
-- Copyright (c) 2018 Satyendra Kumar Banjare
-- 
-- shows how to modify the index
--
-- The user should pass a valid git repository's path as 1st argument.
-- and can pass as many file path to add to the current index as he/she wishes.
-- 
-- Note : the passed file paths must be relative to the given repository's path
--

local luagit2 = require("luagit2")

----------------------------------------------------------
-- The necessary funation call for initializing
-- Libgit2's global state & threading
----------------------------------------------------------
luagit2.init()

----------------------------------------------------------
--
-- Get the params from comand line
----------------------------------------------------------
local repo_path = arg[1]
local num_files = (#arg)

----------------------------------------------------------
--
-- Open repo using passed repository's path
----------------------------------------------------------
local repo = luagit2.repository_open(repo_path)

----------------------------------------------------------
--
-- Get the repository's current index
----------------------------------------------------------

local repo_index = luagit2.repository_index(repo)

----------------------------------------------------------
--
-- Add the files to current index
----------------------------------------------------------
for i=2,num_files do
	luagit2.index_add_bypath(repo_index,arg[i])
end

----------------------------------------------------------
-- Finally write the added files onto the disk
----------------------------------------------------------
luagit2.index_write(repo_index)

----------------------------------------------------------
--
-- must free the used repository and index to prevent
-- memory leaks
----------------------------------------------------------

luagit2.index_free(repo_index)
luagit2.repository_free(repo)
----------------------------------------------------------
--
-- Shutdown the libgit2's threading and global state
----------------------------------------------------------
luagit2.shutdown()

```

The final implementation to do cool git things using luagit2 requires comparitively less number of lines. _Yey!_ 

I am trying to add variant examples, targeting maximum example usage of luagit2 for users.

Also for a better understanding, one may wish to go through the tests for the time documentation has been 
completed.

## To Do

These are some of the further todo on luagit2 project according to me.

- Implement the garbage collecter logic so that user may not need to free the used variables.
- Setup Travis CI and other similar CI checks for luagit2.
- Write lua bindings for **submodule** & **remote** module.
- Convert luagit2 for lua5.1. Very basic and minor task. 
<br>