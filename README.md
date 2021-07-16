# HAZ Fractiles

Calculation of fractiles from [HAZ](https://github.com/abrahamson/HAZ).

## Compiling

`haz-fraciles` is written in FORTRAN and may be compiled with Intel's _ifort_
compiler or GNU's _gfortran_ compiler.

### Windows

On Windows, the easiest way to get a build system running is via
[MSYS2](https://msys2.github.io/). After following the installation
instructions, open an _MinGW_ terminal and issue the following commands to
install the required dependencies. Note, that these commands install the 64-bit
versions. If you prefer to use 32-bit versions replace "x86_64" with "i686".
```
pacman -S git mingw-w64-x86_64-gcc-libgfortran mingw-w64-x86_64-cmake 3.4.1-1
```
After installing the required dependencies, `haz-fractiles` can be checked out of Git and
built using the following:
```
git clone https://github.com/abrahamson/Fractiles.git haz-fractiles
cd  HAZ
mkdir build
cd build
cmake .. -G "MSYS Makefiles"
make
```
This build will require DLLs provided by `MSYS2`. A static build that includes
the required DLLs, can be built with:
```
cmake .. -G "MSYS Makefiles" -DSTATIC=ON
make
```

The `haz-fractiles` executable can then be found under
`haz-fractiles/build/haz-fractiles.exe`.
