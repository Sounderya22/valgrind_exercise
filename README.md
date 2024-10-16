# Valgrind Exercise

## What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?

When the executable is linked statically, valgrind is still able to find the same bugs along with new issues but it isn't pointing to the line numbers as it was when the executable wasn't linked statically. 

## Why or why not

When the executable is linked statically, valgrind is restricted. Dynamic libraries are usually precompiled and optimized. These libraries may contain hidden bugs or issues that Valgrind can detect only when they are integrated into your executable via static linking. 

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# To build with debugging information, do:
  cmake -S ./ -B build/ -D CMAKE_BUILD_TYPE=Debug
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

