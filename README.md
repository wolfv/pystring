# Modern C++ 14 pystring

`pystring14` is a fork of pystring by Sony (https://github.com/imageworks/pystring)

### Planned changes:

- It will support modern C++ (for example, the much hyped string view)
- Make it a CMake - project to facilitate reusal and adopt a modern code style
- Travis/Appveyor CI planned

---

### Original README

Pystring is a collection of C++ functions which match the interface and behavior of python's string class methods using std::string. Implemented in C++, it does not require or make use of a python interpreter. It provides convenience and familiarity for common string operations not included in the standard C++ library. It's also useful in environments where both C++ and python are used.

Overlapping functionality (such as index and slice/substr) of std::string is included to match python interfaces.

Originally developed at Sony Pictures Imageworks.
http://opensource.imageworks.com/

Note: Despite the infrequent updates, this repo is not dead/abandoned - just stable!  We use it every day at Imageworks.