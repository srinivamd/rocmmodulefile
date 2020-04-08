## Simple CMakeLists.txt to generate modulefile ##

This uses a simple cmake file to generate modulefile
for installed versions of ROCm and AOMP on the system
where multiple versions of ROCm releases maybe installed.
    
**Usage:**
        (git clone this repo)  
        mkdir build  
        cd build  
        cmake -DROCM_VERSION=X.Y.Z ..   
    
generates rocm-X.Y.Z-modulefile for ROCm and aomp-X.Y.Z-modulefile
for AOMP included with ROCm X.Y.Z in the build directory.
   
The generated modulefiles can be copied over to the module
file collections on the system.

 Example modulefile generation console session log:   
 ===================================================   
   
$ ls   
CMakeLists.txt  README.md  aompmodulefile.in  rocmmodulefile.in   
   
$ mkdir build   
$ cd build   
   
$ cmake -DROCM_VERSION=3.3.0  ..   
   
$ ls   
CMakeCache.txt  CMakeFiles  Makefile  aomp-3.3.0-modulefile  cmake_install.cmake  rocm-3.3.0-modulefile   
   
$ cmake -DROCM_VERSION=3.4.0  ..   
   
$ ls   
CMakeCache.txt  CMakeFiles  Makefile  aomp-3.3.0-modulefile  aomp-3.4.0-modulefile  cmake_install.cmake  rocm-3.3.0-modulefile  rocm-3.4.0-modulefile   
   
   

