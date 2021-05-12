cmake_minimum_required(VERSION 3.10) # Min CMake version

project(formatter_ex) # Name project as formatter

set(CMAKE_CXX_STANDARD 17) # Set cpp standart
set(CMAKE_CXX_STANDARD_REQUIRED ON) # Set cpp standart as required
set(CMAKE_CURRENT_SOURCE_DIR)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib) # Include files from given directories
add_library(formatter_ex STATIC formatter_ex.cpp) # Add static library from formatter.cpp

find_library(formatter NAMES libformatter.a PATHS ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/_build)

target_link_libraries(formatter_ex ${formatter}) # Specifies library to use when linking a given target
