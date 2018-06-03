---
layout:     post
comments:   true
title:      GSoC'18 Week 3 Report
date:       2018-06-03 12:52:29
summary:    A small report on my third week work on luagit2  
categories: gsoc18_report
---

Third week was exciting as I wrote more tests for the bindings of the functions that I wrote. 
This was one of the time I felt that yes my code works and it has been tested too.

As decided I wrote tests for **OID**, **Signature** , **Tree** ,**Commit**, **Config** and **Cred** module 
functions. The tests are available at `/tests/` . I also configured the testing structure and `.luacov` file
so that it covers only those tests that I have written.
 
I have created different test suite modules referring to lunatest examples. These suites are basically the 
`.lua` test files for the different module's functions. Till now unit tests for functions of each module
have been written in separate test file. These different suites are included in one file i.e `/tests/
luagit2_main_test.lua`  so that now we need to execute only this file to tun the tests.

Testing some of the functions required a repository to be present at the tests folder. I have therefore 
created an [Simple-repository](https://github.com/SatyendraBanjare/Simple-Repository) with example commits 
to test those functions out.

The main_test file initially downloads the repository by doing en external git clone using `os.execute()` 
method provided by lua and then later removes the folder and its contents too.

I also wrote more helper functions for signature module to ease out the testing process.

I also did restructure the project slightly so that all binding function as well as the helper functions are 
available in one folder.

I am here attaching a small screenshot of output of my run tests :  
<img src="{{ site.baseurl }}/images/week-three-test-report.png" alt="Couldn't Load Image" />

The coverage for my written tests can be seen here.

<img src="{{ site.baseurl }}/images/week-three-test-cov.png" alt="Couldn't Load Image" />

It can be clearly seen that I need to improve logics of writing tests. I am working on that. 

To reproduce the test report :

_!! Make sure that lunatest and luacov are installed on the system and you have internet connection so that 
you can clone a repository._

Alternatively one can pre-clone or download the repo at `/tests/` folder and comment out the `os.execute()` 
commands and then run tests. 

```bash
# At root directory
-$ cd tests
-$ lua luagit2_main_test.lua
# Now luacov.stats.out file will be generated
-$ luacov
# This command generates luacov.report.out  (our report file)
```

I will write more tests and bindings for more functions as time comes. I will work upon improving the test 
coverage too.
