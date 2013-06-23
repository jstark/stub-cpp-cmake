cmake_minimum_required(VERSION 2.8)

project(cbl)

set(CBL_HEADER_DIR "${PROJECT_SOURCE_DIR}/include")
set(CBL_HEADER ${CBL_HEADER_DIR}/cbl/cbl.h)

# the first subproject is the library that implements
# the core functionality
include_directories(${CBL_HEADER_DIR})
add_subdirectory(libcbl)
# the second subproject is a driver program that will
# `interpet' a given input file of commands
add_subdirectory(cbli)
# tests for `libcbl'. Tests are based on gtest/gmock
add_subdirectory(tests)
# you need doxygen for the `documentation' subproject
#add_subdirectory(documentation)

enable_testing()
add_test(NAME all COMMAND all_tests)

