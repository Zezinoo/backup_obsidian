---
tags:
  - Cpp
---
Cmake is an extremely useful tool used build project in a easier fashion. You can do this with a CmakeList.txt files which shoudl live in the root of your work directory. A sample file is 
```cmake
#This file lives in src/..
cmake_minimum_required (VERSION 3.5)

project (HelloWorld)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Werror -std=c++14")
set (source_dir "${PROJECT_SOURCE_DIR}/src/")

file (GLOB source_files "${source_dir}/*.cpp")

add_executable (HelloWorld ${source_files})
```

Here we can see the compilation flags being set and also the source directory. The next line defines what type of files will be compiled, in our case, .cpp files. Then the last line define the target name of the Executable
