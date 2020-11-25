cmake_minimum_required(VERSION 3.16)
set(CMAKE_CXX_STANDARD 17)

project(iolite)

# Get sources
file(GLOB_RECURSE SRC
        "${CMAKE_CURRENT_LIST_DIR}/src/*.h"
        "${CMAKE_CURRENT_LIST_DIR}/src/*.cpp"
        )

add_executable(iolite ${SRC})

target_include_directories(iolite PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src)
target_precompile_headers(iolite PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src/pch.h)

# Add LLVM
find_package(LLVM 10.0.0 REQUIRED CONFIG)
target_include_directories(iolite PRIVATE ${LLVM_INCLUDE_DIRS})
add_definitions(${LLVM_DEFINITIONS})
llvm_map_components_to_libnames(llvm_libs support core)
target_link_libraries(iolite ${llvm_libs})