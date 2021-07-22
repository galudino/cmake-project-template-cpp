##########################################################################

set(CMAKE_VERSION "3.17")
set(PROJECT_NAME "cmake-project-template-cpp-repository")

set(SOURCE_DEMO_DIR "./demo")         # executable
set(SOURCE_ADDITIONAL_DIR "./src")    # local project libraries
set(SOURCE_LIBS_DIR "./libs")         # git submodules

set(LIBRARY "cmake-project-template-cpp-library")

##########################################################################

message("Using CMake version ${CMAKE_VERSION}.")

cmake_minimum_required(VERSION ${CMAKE_VERSION})
project(${PROJECT_NAME})

message("Generating metabuild for '${PROJECT_NAME}'...\n")

## Client sources
message("Entering subdirectory '${SOURCE_DEMO_DIR}'...")
add_subdirectory(${SOURCE_DEMO_DIR})
message("Finished with subdirectory '${SOURCE_DEMO_DIR}'.\n")

## Additional sources
message("Entering subdirectory '${SOURCE_ADDITIONAL_DIR}'...")
add_subdirectory(${SOURCE_ADDITIONAL_DIR})
message("Finished with subdirectory '${SOURCE_ADDITIONAL_DIR}'.\n")

## Git submodules
message("Entering subdirectory '${SOURCE_LIBS_DIR}'.")
add_subdirectory(${SOURCE_LIBS_DIR})
message("Finished with subdirectory '${SOURCE_LIBS_DIR}'.\n")

##########################################################################
