# About PRFuzz
We design an improved seed schedule strategy, which initially identify effective properties that are truly sensitive to the targets, then distinguish interesting seeds based on temporal state for accurate assessment of a seed's potential, which in turn optimizes the power schedule strategy of the CFG. PRFuzz is developed based on SLIME.

# Environment
Tested on Ubuntu 16.04 64bit, LLVM 12.0.1 and CMake 3.14.0

# Installation
- Before install PRFuzz, user should prepare llvm.
1. Download LLVM 12.0.1 source code from the link.
2. Compile with the following command.
   ```
    $ mkdir build
    $ cd build
    $ cmake \
        -DCLANG_INCLUDE_DOCS="OFF" \
        -DCMAKE_BUILD_TYPE=Release \
        -DLLVM_BINUTILS_INCDIR=/usr/include/ \
        -DLLVM_BUILD_LLVM_DYLIB="ON" \
        -DLLVM_ENABLE_BINDINGS="OFF" \
        -DLLVM_ENABLE_PROJECTS='clang;compiler-rt;libcxx;libcxxabi;libunwind;lld' \
        -DLLVM_ENABLE_WARNINGS="OFF" \
        -DLLVM_INCLUDE_BENCHMARKS="OFF" \
        -DLLVM_INCLUDE_DOCS="OFF" \
        -DLLVM_INCLUDE_EXAMPLES="OFF" \
        -DLLVM_INCLUDE_TESTS="OFF" \
        -DLLVM_LINK_LLVM_DYLIB="ON" \
        -DLLVM_TARGETS_TO_BUILD="host" \
        ../llvm/
    $ make -j4
    $ make install
   ```
- Install PRFuzz
  1. Clone repository:
      ```
      git clone https://github.com/JyC00/PRFuzz
      ```
  2. Compile:
      ```
       cd PRFuzz/PRFuzz && make && cd llvm_mode && make && cd ../llvm_mode_crash && make 
      ```
- Run PRFuzz like SLIME


