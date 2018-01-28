cmake_minimum_required(VERSION 3.9)

set(CMAKE_MACOSX_RPATH 1)
project(bione)

set(CMAKE_CXX_STANDARD 17)

find_package(openssl REQUIRED)


add_subdirectory(dependency/cpr)


MESSAGE( STATUS "     " ${CPR_INCLUDE_DIRS} )

include_directories(${CPR_INCLUDE_DIRS})

add_executable(bione main.cpp)
target_link_libraries(bione ${CPR_LIBRARIES})
