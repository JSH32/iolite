cmake_minimum_required(VERSION 3.16)
project(Iolite-MAIN)

set(VENDOR_DIR ${CMAKE_CURRENT_LIST_DIR}/vendor)
set(SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/src)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Get flex source
file(GLOB_RECURSE FLEX_SRC
        "${VENDOR_DIR}/flex/src/*.h"
        "${VENDOR_DIR}/flex/src/*.c"
        )

add_subdirectory(${SOURCE_DIR}/iolite)