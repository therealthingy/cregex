# C wrapper around C++ 11's [`std::regex`](https://en.cppreference.com/w/cpp/regex)

- DERIVED FROM: https://nullprogram.com/blog/2024/09/04/

- LIMITATIONs:
  - No Unicode support, particularly UTF-8
  - `std::regex` implementations are universally poor and slow
  - libstdc++ `std::regex` is especially slow to compile
  - Isolating in a ~~DLL~~so (if needed) is inconvenient
  - ~~DLL~~so is ~~200K (MSVC) to~~ 700K (GCC) or so
