# Custom LLVM bundles #

This is a repository to hold custom built LLVM bundles.

## Windows ##

* Download the desired version of LLVM.

* Place the file `CMakeSettings.json` that is in this repository within the directory called `llvm` within the downloaded LLVM.

* Open the directory `llvm` with Visual Studio and let it configure with the `CMakeSettings.json`.

* Build and install using the `x64-Clang-{Debug,Release}` configuration.

* The install should be in the `out\install` directory, bundle it using `cmake` as:

```sh
$ cd .\out\install\
# NOTE: Switch out the version (here 11.0.0) and build type (here Release)
#       This takes a long time (especially for the larger Debug build)
$ cmake -E tar -cJ clang+llvm-11.0.0-x86_64-windows.tar.xz x64-Clang-Release
```
