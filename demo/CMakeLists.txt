cmake_minimum_required(VERSION "3.18")
project("cmake-project-template-cpp-demo")

set(CXX_STANDARD "20") # C++20
set(CFLAGS "-Wall -Werror -pedantic-errors")

set(CMAKE_CXX_STANDARD ${CXX_STANDARD})
set(CMAKE_CXX_FLAGS ${CFLAGS})

add_executable("demo" "main.cpp")
target_link_libraries("demo" LINK_PUBLIC "cmake-project-template-cpp-library")
