# CLion Emscripten project
A skeleton ```Cmake``` project to generate ```WASM``` and ```JS``` file and serving with ```HTML```. ```Ubuntu``` ```WSL2``` is used from ```Microsoft``` ```Windows 10 - x64``` machine for testing..

## How to use
1. Clone this repo.
2. Install ```Emscripten``` by following steps on [emscripten website](https://emscripten.org/docs/getting_started/downloads.html)
3. In CLion CMAKE setting  add ```CMAKE_TOOLCHAIN_FILE=path/to/emscripten/emscripten/version/cmake/Modules/Platform/Emscripten.cmake```
4. Build from ```Clion```
5. It can be run following ways
    1. Run in ```Emscripten``` environment with ```emrun Public/index.htm```. OR
    2. Open file ```Public/index.htm``` in ```Clion``` then click your faworite browser from upper right corner.
6. In developer tools console of browser you will see the result as ```144```.

## Credits
The repo is created from the following references.
1. [Emscripten Installation instructions](https://emscripten.org/docs/getting_started/downloads.html)
2. [Emscripting a C library to Wasm](https://developers.google.com/web/updates/2018/03/emscripting-a-c-library)
3. [Linux: Compile C++ to WebAssembly and JavaScript using Emscripten and CMake](https://gist.github.com/WesThorburn/00c47b267a0e8c8431e06b14997778e4) 
4. [Minimal CMake-driven Emscripten project](https://github.com/adevaykin/minimal-cmake-emscripten-project)
