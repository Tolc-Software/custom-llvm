# Custom LLVM bundles #

This is a repository to hold custom built LLVM bundles.

## Windows ##

* Download LLVM and checkout the desired version

```sh
$ git clone --config core.autocrlf=false git@github.com:llvm/llvm-project.git
$ cd llvm-project
# For example
$ git checkout llvmorg-12.0.0
```

* Copy the file `CMakeSettings.json` from this repository and place it into `llvm-project/llvm`

* Open the directory `llvm-project/llvm` with Visual Studio and let it configure with the `CMakeSettings.json`.

* Build and install using the `x64-Clang-{Debug,Release}` configuration.

* The install should be in the `out\install` directory, bundle it using `cmake` as:

```sh
$ cd .\out\install\
# NOTE: Switch out the version (here 11.0.0) and build type (here Release)
#       This takes a long time (especially for the larger Debug build)
$ cmake -E tar -cJ clang+llvm-11.0.0-x86_64-windows-Release.tar.gz x64-Clang-Release
```
