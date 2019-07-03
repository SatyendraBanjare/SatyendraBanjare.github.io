---
layout:     post
comments:   true
title:      GSoC'18 Week 2 Report
date:       2018-05-27 12:52:29
summary:    A small report on my second week work on luagit2  
categories: gsoc18_report
keywords: gsoc blog report
---

The second week passed and I learnt to write tests for my project. I understood more about libgit2's code structure.

This week I wrote bindings for **Commit** , **Signature** , **Tree** and **OID** modules. Their Implementation is similar 
to the bindings I wrote for previous modules which include creating a `lua_struct_object` and then making binding functions
accordingly.

I also restructured project the project so that all the used _lua_struct_objects_  are now available at `/src/header_files/lua_objects.h`.
Also the CMakeLists.txt is now available at root directory. Therefore now, We can easily generate all build files and the shared object in a seprate build 
folder using : 

```bash
(At root directory)
-$ mkdir build && cd build
-$ cmake ..
-$ make 
-$ make install
```

I wrote tests for the functions of _Luagit2_libgit_ module lua using **[lunatest](https://luarocks.org/modules/luarocks/lunatest/0.9.5-1)** .
I also included test coverage using **[luacov](https://luarocks.org/modules/mpeterv/luacov/0.13.0-1)**.

Since it was my first experience writing tests, I have simply written tests and not properly configured luacov to lookup for code 
coverage. Also I need to improve the written test cases and logic of implementation. 

I am attaching a small screenshot of `luacov summary` for the tests I wrote. 
<img src="{{ site.baseurl }}/images/luagit2_libgit_coverage_report.png" alt="Couldn't Load Image" />

- The coverage for my written tests i.e `luagit2_libgit_test.lua` can be seen here.

To reproduce the test report :

_!! Make sure that lunatest and luacov are installed on the system. (refer links above)_

```bash
# At root directory
-$ cd tests
-$ lua luagit2_libgit_test.lua
# Now luacov.stats.out file will be generated
-$ luacov
# This command generates luacov.report.out  (our report file)
```

I will write more tests and bindings for more functions as time comes. I will work upon improving the test coverage too.
