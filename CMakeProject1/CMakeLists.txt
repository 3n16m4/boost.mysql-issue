﻿# CMakeList.txt : CMake project for CMakeProject1, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

FetchContent_Declare(
  mysql
  GIT_REPOSITORY https://github.com/anarthal/mysql.git
  GIT_TAG        develop
)

# CMake 3.14+
FetchContent_MakeAvailable(mysql)

# Add source to this project's executable.
add_executable (CMakeProject1 "CMakeProject1.cpp" "CMakeProject1.h")

target_compile_features(CMakeProject1 PRIVATE cxx_std_20)
target_link_libraries (CMakeProject1 PRIVATE Boost::mysql)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET CMakeProject1 PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
