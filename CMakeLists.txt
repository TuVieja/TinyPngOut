############################################################################
# Ekaitza Gazte Taldea                                                     #
# C\ Renteria Nยบ3 Bajo                                      			   #
# 20110, Trintxerpe                                                        #
# SPAIN                                                                    #
#                                                                          #
# Copyright (c) 2020 by Erik Fustes                                        #
# All rights reserved.                                                     #
# Erik Fustes provides this product without warranty of any kind and shall #
# not be liable for any damages caused by the use of this product.         #
############################################################################

# Find the dependencies of this project

cmake_minimum_required(VERSION 3.17)
# Set the name of the library
set(LIBRARY_NAME TinyPngOut)

set (CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set (CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

# Define the header and source files of the library
set(HEADER_FILES 
	include/TinyPngOut.hpp
	include/TinyPngOutLib.h
	)

set(SOURCE_FILES 
	src/TinyPngOut.cpp
	src/TinyPngOutLib.cpp
	)

source_group("Sources" FILES ${SOURCE_FILES})

# Define the folder containing the header files for this library
set(TINYPNGOUT_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include PARENT_SCOPE)

# Define the include directory search file for this project
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include )

# Add the library
add_library(${LIBRARY_NAME} SHARED  ${SOURCE_FILES} ${HEADER_FILES})

set_target_properties(${LIBRARY_NAME} PROPERTIES FOLDER "Utilities")

set(TINYPNGOUT_INCLUDED ON PARENT_SCOPE)
