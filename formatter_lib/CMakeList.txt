cmake_minimum_required(VERSION 3.4) # Min CMake version

project(formatter) # Name project as formatter

set(CMAKE_CXX_STANDARD 11) # Set cpp standart
set(CMAKE_CXX_STANDARD_REQUIRED ON) # Set cpp standart as required

add_library(formatLib STATIC formatter.cpp) # Add static library from formatter.cpp

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)
