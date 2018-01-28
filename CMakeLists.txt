cmake_minimum_required(VERSION 3.9)

set(CMAKE_MACOSX_RPATH 1)
project(bione)

set(CMAKE_CXX_STANDARD 17)
set(DEPENDENCY_DIR dependency)
find_package(openssl REQUIRED)
add_subdirectory(dependency/cpr)



include_directories( ${DEPENDENCY_DIR}/Catch2/single_include)



include_directories(${CPR_INCLUDE_DIRS})

add_executable(bione main.cpp)
target_link_libraries(bione ${CPR_LIBRARIES})
