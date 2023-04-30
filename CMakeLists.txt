#
# see: https://stackoverflow.com/questions/17511496/how-to-create-a-shared-library-with-cmake
#
SET (THE_PROJECT myprogram)

cmake_minimum_required(VERSION 3.26)

PROJECT(${THE_PROJECT} VERSION 1.0.0 DESCRIPTION "describe the project")

# C++ version
SET(CMAKE_CXX_STANDARD 17)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)
SET(CMAKE_CXX_EXTENSIONS OFF)

SET (CMAKE_EXPORT_COMPILE_COMMANDS ON)
SET (CMAKE_VERBOSE_MAKEFILE ON)

# Set the variable source_files to the list of names of your C++ source code
# Note the lack of commas or other deliminators
SET(source_files
   src/main.cpp
   src/other.cpp
)

SET(CMAKE_BUILD_TYPE RELEASE) # Debug, Release, RelWithDebInfo, MinSizeRel

# If you need to use a library, this is a common way to do it
# find_package(PkgConfig REQUIRED)
# pkg_check_modules(SOME_PACKAGE REQUIRED libsomelibrary)
# include_directories(${SOME_PACKAGE_INCLUDE_DIRS})
# link_directories(${SOME_PACKAGE_LIBRARY_DIRS})
# add_definitions(${SOME_PACKAGE_CFLAGS_OTHER})

# Build a program called '${THE_PROJECT}' from the source files we specified above
ADD_EXECUTABLE(${THE_PROJECT} ${source_files})

# Also needed to add a library
# target_link_libraries(${THE_PROJECT} ${SOME_PACKAGE_LIBRARIES})

