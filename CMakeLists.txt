cmake_minimum_required(VERSION 2.8)
project(METIS)

set(SHARED TRUE CACHE BOOL "build a shared library")

set(METIS_INSTALL_BIN TRUE)

enable_testing()

# Configure libmetis library.
if(SHARED)
  set(METIS_LIBRARY_TYPE SHARED)
else()
  set(METIS_LIBRARY_TYPE STATIC)
endif(SHARED)

# Add include directories
include_directories("Lib")
include_directories("Programs")

# Recursively look for CMakeLists.txt in subdirs
add_subdirectory("Lib")
add_subdirectory("Programs")
add_subdirectory("Test")
