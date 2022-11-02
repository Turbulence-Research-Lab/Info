---
title:  "MPIIFORT 编译选项"
# image : "/assets/images/post/post-1.jpg"
author: "Admin"
date: 2022-11-2 11:12:58 +0600
description : "intel fortran"
tags: [编译选项]
---
这里只展示mpi部分，其它部分与ifort的设置一样
```
Simple script to compile and/or link MPI programs.
Usage: mpiifort [options] <files>
----------------------------------------------------------------------------
The following options are supported:
   -fc=<name> | -f90=<name>
                   specify a FORTRAN compiler name: i.e. -fc=ifort
   -echo           print the scripts during their execution
   -show           show command lines without real calling
   -show_env       show environment variables
   -config=<name>  specify a configuration file: i.e. -config=ifort for mpif90-ifort.conf file
   -v              print version info of mpiifort and its native compiler
   -profile=<name> specify a profile configuration file (an MPI profiling
                   library): i.e. -profile=myprofile for the myprofile.cfg file.
                   As a special case, lib<name>.so or lib<name>.a may be used
                   if the library is found
   -check_mpi      link against the Intel(R) Trace Collector (-profile=vtmc).
   -static_mpi     link the Intel(R) MPI Library statically
   -mt_mpi         link the thread safe version of the Intel(R) MPI Library
   -ilp64          link the ILP64 support of the Intel(R) MPI Library
   -no_ilp64       disable ILP64 support explicitly
   -fast           the same as -static_mpi + pass -fast option to a compiler.
   -t or -trace
                   link against the Intel(R) Trace Collector
   -trace-imbalance
                   link against the Intel(R) Trace Collector imbalance library
                   (-profile=vtim)
   -dynamic_log    link against the Intel(R) Trace Collector dynamically
   -static         use static linkage method
   -nostrip        turn off the debug information stripping during static linking
   -O              enable optimization
   -link_mpi=<name>
                   link against the specified version of the Intel(R) MPI Library
                   i.e -link_mpi=opt|opt_mt|dbg|dbg_mt
   -norpath        disable rpath for compiler wrapper of the Intel(R) MPI Library
All other options will be passed to the compiler without changing.
----------------------------------------------------------------------------
The following environment variables are used:
   I_MPI_ROOT      the Intel(R) MPI Library installation directory path
   I_MPI_F90 or MPICH_F90
                   the path/name of the underlying compiler to be used
   I_MPI_FC_PROFILE or I_MPI_F90_PROFILE or MPIF90_PROFILE
                   the name of profile file (without extension)
   I_MPI_COMPILER_CONFIG_DIR
                   the folder which contains configuration files *.conf
   I_MPI_TRACE_PROFILE
                   specify a default profile for the -trace option
   I_MPI_CHECK_PROFILE
                   specify a default profile for the -check_mpi option
   I_MPI_LINK      specify the version of the Intel(R) MPI Library
   I_MPI_DEBUG_INFO_STRIP
                   turn on/off the debug information stripping during static linking
----------------------------------------------------------------------------
```