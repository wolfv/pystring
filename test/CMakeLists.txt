############################################################################
# Copyright (c) 2016, Johan Mabille and Sylvain Corlay                     #
#                                                                          #
# Distributed under the terms of the BSD 3-Clause License.                 #
#                                                                          #
# The full license is in the file LICENSE, distributed with this software. #
############################################################################

cmake_minimum_required(VERSION 3.1)

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    project(pystring14-test)

    find_package(pystring14 REQUIRED CONFIG)
    set(PYSTRING14_INCLUDE_DIR ${pystring14_INCLUDE_DIRS})
endif ()

message(STATUS "Forcing tests build type to Release")
set(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the type of build." FORCE)

include(CheckCXXCompilerFlag)

string(TOUPPER "${CMAKE_BUILD_TYPE}" U_CMAKE_BUILD_TYPE)

set(PYSTRING14_TESTS
	test.cpp
)

set(TEST_TARGET test_pystring14)
add_executable(${TEST_TARGET} EXCLUDE_FROM_ALL ${PYSTRING14_TESTS} ${PYSTRING14_HEADERS})
target_link_libraries(${TEST_TARGET} pystring14)

add_custom_target(test COMMAND ${TEST_TARGET} DEPENDS ${TEST_TARGET})
