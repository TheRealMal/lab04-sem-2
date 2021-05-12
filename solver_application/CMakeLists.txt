# /solver_application
cmake_minimum_required(VERSION 3.10) # Min CMake version

project(solver) # Name project as formatter

set(CMAKE_CXX_STANDARD 17) # Set cpp standart
set(CMAKE_CXX_STANDARD_REQUIRED ON) # Set cpp standart as required
set(CMAKE_CURRENT_SOURCE_DIR)

add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib/solver.cpp)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib
    ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib
    ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib
) # Include files from given directories

add_executable(solver equation.cpp) # Add executable to project

find_library(formatter NAMES libformatter.a PATHS ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/_build)
find_library(formatter_ex NAMES libformatter_ex.a PATHS ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib/_build)

target_link_libraries(solver ${formatter} ${formatter_ex} solver_lib) # Specifies libraries to use when linking a given target
