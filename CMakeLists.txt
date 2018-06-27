############################################################################
# Copyright (c) 2017, Wolf Vollprecht				                       #
#                                                                          #
# Distributed under the terms of the BSD 3-Clause License.                 #
#                                                                          #
# The full license is in the file LICENSE, distributed with this software. #
############################################################################

cmake_minimum_required(VERSION 3.1)
project(pystring14)

set(PYSTRING14_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

set(PYSTRING14_HEADERS
    ${PYSTRING14_INCLUDE_DIR}/pystring14/pystring.hpp
    ${PYSTRING14_INCLUDE_DIR}/pystring14/pystring_header.hpp
    ${PYSTRING14_INCLUDE_DIR}/pystring14/pystring_utils.hpp
    ${PYSTRING14_INCLUDE_DIR}/pystring14/string_view_lite.hpp
)

# add_library(pystring14 SHARED pystring.hpp)

# add_executable(pystring14_test test.cpp)


OPTION(BUILD_TESTS "xsimd test suite" ON)
if(BUILD_TESTS)
    add_subdirectory(test)
endif()

add_library(pystring14 INTERFACE)
target_include_directories(pystring14 INTERFACE $<BUILD_INTERFACE:${PYSTRING14_INCLUDE_DIR}>
                                                $<INSTALL_INTERFACE:include>)

# Installation
# ============

# include(GNUInstallDirs)
# include(CMakePackageConfigHelpers)

# install(TARGETS pystring14
#         EXPORT ${PROJECT_NAME}-targets)
