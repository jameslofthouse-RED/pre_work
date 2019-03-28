## C++ training pre-work

The project is configured to run on both Windows and Linux OS.
We assume that you use Windows. Necessary software:
- CLion (your company should provide you a license key)
- MinGW-w64 (g++, cmake, make)

### Software installation for Windows
1. Please refer to this [video instruction on YouTube](https://www.youtube.com/watch?v=neg4zt5mIwk)
2. [Download and install CLion for Windows](https://www.jetbrains.com/clion/download/#section=windows)
3. [Download and install MinGW](https://mingw-w64.org/doku.php/download/mingw-builds)

### Software installation for Linux
For Linux please install:
- CLion
- g++
- valgrind
- cmake
- make

### Possible problems on Windows
If you can build NumberGenerators target, but you cannot build NumberGenerators-ut target it probably mean that MinGW does not properly support exceptions on your machine. Please reinstall MinGW and select another type of exception implementation in `Exception` field.

If MinGW is problematic on your machine, feel free to use MSVC compiler. In fact, compiler type does not really matter. It should only support C++17.

You only need to be able to compile both NumberGenerators and NumberGenerators-ut targets. We will be using similar build configurations on our training.

### Assignment
1. Optional: Fork this repository to your own GitHub accout (if you have one)
2. Compile binary and unit tests
  steps for manual compilation with CMake:
  - mkdir build
  - cd build
  - cmake ..
  - make
3. Run NumberGenerators target. You should be able to see a [memory leak in Sanitizer window in CLion](https://www.jetbrains.com/help/clion/google-sanitizers.html#LSanChapter)
4. Fix memory leak with delete and remove [[maybe_unused]] attribute.
5. Run NumberGenerators-ut targets
6. Fix mistakes in unit tests. In order to do that you need to implement `sumNumbersFromGenerators()` function to make all UTs pass. You can add more UTs if you wish.
7. Create a Pull Request to inform me about your successful implementation and environment setup. If you do not have and do not want to have a GitHub accout just send me your solution (diff only) via email to lukasz@coders.school

### Useful links
These links may be interesing for you, however we will not need them on our training
- [lib DUMA](http://duma.sourceforge.net) - another memory leak detector for Windows and Linux
- [Linux toolchain on Windows via WSL](https://blog.jetbrains.com/clion/2018/01/clion-and-linux-toolchain-on-windows-are-now-friends/)
- [Valgrind on Windows](https://www.jetbrains.com/help/clion/memory-profiling-with-valgrind.html#valgrind-wsl)