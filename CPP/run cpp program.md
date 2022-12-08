If you're running Windows then make use of this:

```cpp
g++ -o program program.cpp
```

`g++` is the name of the compiler and `-o` is the option needed for creating a `.o` file. Program (without `.cpp` suffix) is the `exe` file and `program.cpp` is your source file that you want to compile.

```cpp
g++ -o program program.cpp&program.exe
```

Use this shortcut to run the `.exe` file of the program. This might run in Linux but you may have to use `.out` suffix instead of `.exe`. Use this handy batch script to execute your programs on Windows:

```cpp
@echo off&&cls
set /p pathName=Enter The Path where the file is located:%=%
cd %pathName%
REM set /p exec=Enter The Name of the executable you want to make:%=%
set /p file=Enter The Name of the file you want to compile:%=%
g++ -o %file% %file%.cpp
%file%.exe
```

save it as `cppExecutor.bat`

Also you could use the following commands on Unix (Linux and Mac) OS:

```cpp
CC program.cc
```

If you want to use `gcc`:

```cpp
gcc -o program program.cpp
```

With the shortcut:

```cpp
gcc -o program program.cpp&program.exe
```