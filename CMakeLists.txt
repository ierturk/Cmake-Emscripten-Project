project (getES)
cmake_minimum_required(VERSION 3.15)
option(JS_ONLY "Compiles to native JS (No WASM)" OFF)

# add_definitions(-std=c++11 -O3)
include_directories(
        Inc
        )

set(SOURCES
        Src/fib.c
        )

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/Public")
add_executable(${PROJECT_NAME}
        ${SOURCES}
        )

if(JS_ONLY)
    message(STATUS "Setting compilation target to native JavaScript")
    set(CMAKE_EXECUTABLE_SUFFIX ".js")
    set_target_properties(${PROJECT_NAME}
            PROPERTIES LINK_FLAGS "-s WASM=0 -s EXTRA_EXPORTED_RUNTIME_METHODS='[\"cwrap\"]'")
else(JS_ONLY)
    message(STATUS "Setting compilation target to WASM")
    set(CMAKE_EXECUTABLE_SUFFIX ".wasm.js")
    set_target_properties(${PROJECT_NAME}
            PROPERTIES LINK_FLAGS "-s WASM=1 -s EXTRA_EXPORTED_RUNTIME_METHODS='[\"cwrap\"]'")
endif(JS_ONLY)