cmake_minimum_required(VERSION 3.5)

# Name of your project
project(MyLibrary VERSION 1.0.0)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)

# Add all your source files here
set(SOURCE_FILES
    src/File1.cpp
    src/File2.cpp
)

# Add all your header files here
set(HEADER_FILES
    include/MyLibrary/File1.h
    include/MyLibrary/File2.h
)

# Set the output directory for the compiled library
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)

# Create the static library target
add_library(MyLibrary STATIC ${SOURCE_FILES} ${HEADER_FILES})

# Include directories for header files
target_include_directories(MyLibrary
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)

# Set any additional compiler flags here
target_compile_options(MyLibrary
    PRIVATE
        -Wall
        -Wextra
)
