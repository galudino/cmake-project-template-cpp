##########################################################################

set(CMAKE_VERSION "3.17")
set(PROJECT_NAME "cmake-project-template-cpp-library")

set(CMAKE_CXX_STANDARD "20")  ## C++20

if (MSVC)
    ## Microsoft Visual C++
    ## /EHsc
    ##      Enable full compiler support for the Standard C++ exception
    ##      handling model that safely unwinds stack objects
    ## /W4
    ##      Displays level 1 (severe), 
    ##               level 2 (significant),
    ##               level 3 (production quality),
    ##               level 4 (informational) warnings
    ## /permissive-
    ##      Language standard conformance
    set(CMAKE_CXX_FLAGS "/EHsc /W4 /permissive-")
else()
    ## gcc/clang
    ## -Wall               
    ##      Turn on all warnings
    ## -Werror
    ##      Treat all warnings as errors
    ## -pedantic-errors
    ##      Treat code that is non-compliant to the language standard
    ##      as erroneous
    set(CMAKE_CXX_FLAGS "-Wall -Werror -pedantic-errors")
endif()

set(LIBRARY_SOURCES
    "header.hpp"
    "source.cpp"
    ## List any additional source files below
)

##########################################################################

cmake_minimum_required(VERSION ${CMAKE_VERSION})
project(${PROJECT_NAME})

message("\tGenerating metabuild for '${PROJECT_NAME}'...")

message("\tAdding sources 
    '${LIBRARY_SOURCES}'
    for '${LIBRARY}'...")

add_library(${LIBRARY} ${LIBRARY_SOURCES})

message("\tAdding include directories
    '${CMAKE_CURRENT_SOURCE_DIR}'
    to '${LIBRARY}'...")

target_include_directories(${LIBRARY} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

##########################################################################

