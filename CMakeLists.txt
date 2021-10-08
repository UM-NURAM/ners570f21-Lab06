cmake_minimum_required(VERSION 3.10)
project(SpMV VERSION 0.1.0)


enable_language(CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)


if(NOT DEFINED SpMV_ENABLE_TESTING)
  SET(SpMV_ENABLE_TESTING ON)
endif()

add_subdirectory(src)



if(SpMV_ENABLE_TESTING)
  message(STATUS "Testing enabled for SpMV")
  enable_testing()
  add_subdirectory(test)
endif()
