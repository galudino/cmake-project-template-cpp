cmake_minimum_required(VERSION "3.18")
project("cmake-project-template-cpp-library")

set(CXX_STANDARD "20") # C++20
set(CFLAGS "-Wall -Werror -pedantic-errors")

set(CMAKE_CXX_STANDARD ${CXX_STANDARD})
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} ${CFLAGS})

add_library("cmake-project-template-cpp-library" "header.hpp" "source.cpp")
target_include_directories("cmake-project-template-cpp-library" PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
