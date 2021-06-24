cmake_minimum_required(VERSION "3.18")
project("cmake-project-template-cpp-repository")

## client sources
add_subdirectory("./demo")

## additional sources
add_subdirectory("./src")

## additional sources (git submodules)
add_subdirectory("./libs")
