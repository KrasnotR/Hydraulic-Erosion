cmake_minimum_required(VERSION 3.12.4)
project(Hydraulic-Erosion)

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(include/random)

find_package(TIFF)

add_executable(Hydraulic-Erosion src/main.cpp src/Erosion.hpp src/Erosion.cpp simplex/SimplexNoise.hpp simplex/SimplexNoise.cpp)
target_link_libraries(Hydraulic-Erosion effolkronium_random TIFF::TIFF)
