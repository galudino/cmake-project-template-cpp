##########################################################################

set(CMAKE_VERSION "3.17")
set(PROJECT_NAME "cmake-project-template-cpp-demo")

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

set(EXECUTABLE_SOURCES 
    "main.cpp"
    ## List any additional source files below
)

set(EXECUTABLE_DEMO "demo")

##########################################################################

cmake_minimum_required(VERSION ${CMAKE_VERSION})
project(${PROJECT_NAME})

message("\tGenerating metabuild for '${PROJECT_NAME}'...")

message("\tAdding executable '${EXECUTABLE_DEMO}'...")
add_executable(${EXECUTABLE_DEMO} ${EXECUTABLE_SOURCES})

message("\tLinking static libraries 
    '${LIBRARY}' 
    to '${EXECUTABLE_DEMO}'...")

target_link_libraries(${EXECUTABLE_DEMO} LINK_PUBLIC ${LIBRARY})

##########################################################################
