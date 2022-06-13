# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

project ("CMakeProject1")

include(FetchContent)

# Include sub-projects.
add_subdirectory ("CMakeProject1")
