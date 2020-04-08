#
# Simple CMakefile to generate ROCm modulefile for a specific version
#
# Author: srinivasan.subramanian@amd.com
#
project(rocmmodulefile NONE)

cmake_minimum_required(VERSION 3.0)

#
# Use ROCM_VERSION defined using -DROCM_VERSION
#
if (DEFINED ROCM_VERSION)
    set ( ROCM_VERSION "-${ROCM_VERSION}" ) # insert hyphen
else ()
    set ( ROCM_VERSION "")
endif ()

#
# Use AOMP_VERSION defined using -DAOMP_VERSION
#
if (DEFINED AOMP_VERSION)
    set ( AOMP_VERSION "-${AOMP_VERSION}" ) # insert hyphen
else ()
    set ( AOMP_VERSION "")
endif ()


#Generate ROCm version-specific modulefile
configure_file(rocmmodulefile.in rocm${ROCM_VERSION}-modulefile @ONLY)

# Generate AOMP version-specific modulefile for installed ROCm version
configure_file(aompmodulefile.in aomp${AOMP_VERSION}${ROCM_VERSION}-modulefile @ONLY)

